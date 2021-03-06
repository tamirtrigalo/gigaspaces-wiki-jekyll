---
layout: post102
title:  Properties Metadata
categories: XAP102NET
parent: pono-xml-metadata-overview.html
weight: 200
---

{% summary %}{% endsummary %}


All the properties are written automatically into the Space. If the property is a reference to another object, it has to be Serializable and it will be written into the Space as well. Only the properties which need special Space behavior need to be specified in the gs.xml file. Specify the properties which are id's, indexes or need exclusions, etc.


# Property

{: .table   .table-condensed  .table-bordered}
|Syntax     | property name |
|Argument   |  name of the attribute          |
|Description| contains mapping info for a property of a class |

Example:

{% highlight xml %}
<gigaspaces-mapping>
<class name="Model.Person" persist="false" replicate="false">
    <property name="Age" />
</class>
</gigaspaces-mapping>
{% endhighlight %}


### SpaceProperty

{: .table   .table-condensed  .table-bordered}
|Syntax     | null-value |
|Description| Specifies that an attribute value be treated as `null` when the object is written to the space and no value is assigned to the attribute. (where `-1` functions as a `null` value in case of an int)|

Example:

{% highlight xml %}
<gigaspaces-mapping>
<class name="Model.Person" persist="false" replicate="false">
    <property name="Age" null-value="-1" />
    <property name="Status" null-value="-1" />
</class>
</gigaspaces-mapping>
{% endhighlight %}


### Reference

{: .table   .table-condensed  .table-bordered}
|Syntax     | reference |
|Argument   | class name         |
|Description| contains mapping information for a property of a class that is not primitive, but references another entity object. |

Example:

{%highlight xml%}
<gigaspaces-mapping>
<class name="Person">
    <property name="FirstName" />
    <property name="Address" reference="Model.Address" />
</class>
</gigaspaces-mapping>
{%endhighlight%}






### SpaceStorageType

{: .table   .table-condensed  .table-bordered}
|Syntax     | storage-type|
|Argument   | [StorageType](http://www.gigaspaces.com/docs/dotnetdocs{%currentversion%}/html/T_GigaSpaces_Core_Metadata_StorageType.htm)          |
|Default    | object |
|Description| This tag is used to specify how the property is stored in the space. |

Example:

{% highlight xml %}
<gigaspaces-mapping>
<class name="Model.Person" persist="false" replicate="false">
    <property name="Age" null-value="-1" />
    <property name="Address" storage-type="binary" />
</class>
</gigaspaces-mapping>
{% endhighlight %}

{%learn%}./poco-storage-type.html{%endlearn%}

### SpaceIndex

{: .table   .table-condensed  .table-bordered}
|Syntax     |  index type|
|Argument   |  [SpaceIndexType](http://www.gigaspaces.com/docs/dotnetdocs{%currentversion%}/html/T_GigaSpaces_Core_Metadata_SpaceIndexType.htm)  |
|Description| Querying indexed fields speeds up read and take operations. The `index` tag should be used to specify an indexed field.|

Example:

{%highlight xml%}
<gigaspaces-mapping>
    <class name="Model.Person" persist="false" replicate="false" >
        <property name="LastName">
            <index type="basic"/>
        </property>
        <property name="FirstName">
            <index type="basic"/>
        </property>
        <property name="Age">
             <index type="extended"/>
        </property>
    </class>
</gigaspaces-mapping>
{%endhighlight%}


{%learn%}./indexing.html{%endlearn%}

### SpaceIndex Path

{: .table   .table-condensed  .table-bordered}
|Syntax     |  path type|
|Argument   |  [SpaceIndexType](http://www.gigaspaces.com/docs/dotnetdocs{%currentversion%}/html/T_GigaSpaces_Core_Metadata_SpaceIndexType.htm)|
|Description| The `path` attribute represents the path of the indexed property within a nested object. |

Example:

{%highlight xml%}
<gigaspaces-mapping>
    <class name="Model.Person"  >
        <property name="PersonalInfo">
		    <index path="SocialSecurity" type = "extended"/>
		    <index path="Address.zipCode" type = "basic"/>
		</property>
    </class>
</gigaspaces-mapping>
{%endhighlight%}

{%learn%}./indexing-nested-properties.html{%endlearn%}


### Unique Index

{: .table   .table-condensed  .table-bordered}
|Syntax     |  index type unique|
|Argument   |  [SpaceIndexType](http://www.gigaspaces.com/docs/dotnetdocs{%currentversion%}/html/T_GigaSpaces_Core_Metadata_SpaceIndexType.htm)  |
|Description| Unique constraints can be defined for an attribute or attributes of a space class. |
|Note |   The uniqueness is enforced per partition and not over the whole cluster. |

Example:

{%highlight xml%}
<gigaspaces-mapping>
    <class name="Model.Person" persist="false" replicate="false" >
        <property name="LastName">
            <index type="BASIC" unique="true"/>
        </property>
        <property name="FirstName">
            <index type="BASIC"/>
        </property>
        <property name="Age">
             <index type="EXTENDED"/>
        </property>
    </class>
</gigaspaces-mapping>

{%endhighlight%}


{%learn%}./indexing.html{%endlearn%}


### SpaceFifoGroupingIndex

{: .table   .table-condensed  .table-bordered}
|Syntax     | fifo-grouping-index path|
|Description| This tag is used to define a space FIFO grouping Index. |
|Note |This tag can be declared on several properties in a class in order to assist in efficient traversal.{%wbr%}If defined, there must be a property in the class, marked with the `@SpaceFifoGroupingProperty` annotation.{%wbr%}A compound index that contains this FIFO grouping index and the FIFO grouping property will be created.   |

Example:

{%highlight xml%}
<gigaspaces-mapping>
	<class name="com.gigaspaces.examples.FlightReservation />
		<property name="ProcessingState">
			<fifo-grouping-index />
		</property>
		<property name="Customer">
			<fifo-grouping-index  path="id"/>
		</property>
</gigaspaces-mapping>

{%endhighlight%}

{%learn%}./fifo-grouping.html{%endlearn%}



# SpaceId

{: .table   .table-condensed  .table-bordered}
|Syntax     | id name|
|Argument   | auto-generate |
|Default    | false |
|Description| Defines whether this field value is used when generating the Object ID. The field value should be unique -- i.e., no multiple objects with the same value should be written into the space (each object should have a different field value). When writing an object into the space with an existing `id` field value, an `EntryAlreadyInSpaceException` is thrown. The Object ID is created, based on the `id` field value.{%wbr%}Specifies if the object ID is generated automatically by the space when written into the space. If `false`, the field is indexed automatically, and if `true`, the field isn't indexed. If `autoGenerate` is declared as `false`, the field is indexed automatically. If `autoGenerate` is declared as `true`,the field isn't indexed. If `autoGenerate` is `true`, the field must be of the type `String`. |

Example:

{%highlight xml%}
<gigaspaces-mapping>
	<class name="Model.Person">
	    <property name="PersonId" />
        <property name="FirstName" />
        <property name="LastName" />
        <property name="Type" />
		<id name="PersonId" auto-generate="true" />
	</class>
</gigaspaces-mapping>
{%endhighlight%}


{%learn%}./poco-object-id.html{%endlearn%}


# SpaceRouting

{: .table   .table-condensed  .table-bordered}
|Syntax     | routing name|
|Description| The `routing` tag specifies a get method for the field to be used to calculate the target space for the space operation (read , write...). The `routing` field value hash code is used to calculate the target space when the Space is running in **partitioned mode**.{%wbr%}The field value hash code is used to calculate the target space when the space is running in **partitioned mode**. |

Example:

{%highlight xml%}
<gigaspaces-mapping>
	<class name="Model.Person">
		<property name="Id" />
        <property name="FirstName" />
        <property name="LastName" />
        <property name="Type" />
		<id name="Id" auto-generate="true" />
        <routing name="Type" />
	</class>
</gigaspaces-mapping>
{%endhighlight%}

{%learn%}{%currentadmurl%}/data-partitioning.html{%endlearn%}

# Class Reference

{: .table   .table-condensed  .table-bordered}
|Syntax     | class-ref |
|Argument   | class name   |
|Description| Contains the full qualified name of the specified class. |

Example:

{%highlight xml%}
<gigaspaces-mapping>
<class name="Person">
    <property name="FirstName" />
    <property class-ref="Model.Person" />
</class>
</gigaspaces-mapping>
{%endhighlight%}

# SpacePersist

{: .table   .table-condensed  .table-bordered}
|Syntax     | persist name|
|Description| This specifies a getter method for holding the persistency mode of the object overriding the class level persist declaration. This field should be of the boolean data type.{%wbr%}If the persist class level annotation is true, all objects of this class type will be persisted into the underlying data store (Mirror, ExternalDataSource, Storage Adapter).|
|Note       | When using this option, you must have the space class level `persist` decoration specified.|

Example:

{%highlight xml%}
<gigaspaces-mapping>
<class name="Model.Person" persist="false" replicate="false">
    <property name="Age" null-value="-1" />
    <persist name="Persistence" />
</class>
</gigaspaces-mapping>
{%endhighlight%}

# SpaceVersion

{: .table   .table-condensed  .table-bordered}
|Syntax     |  version name|
|Description| This tag is used for object versioning used for optimistic locking. |
|Note       | The attribute must be an `int` data type. |

Example:

{%highlight xml%}
<gigaspaces-mapping>
	<class name="Model.Person">
		<property name="Id" />
		<property name="VersionId" />
        <property name="FirstName" />
        <property name="LastName" />
        <property name="Type" />
		<id name="Id" auto-generate="true" />
        <routing name="Type" />
        <version name="VersionId" />
	</class>
</gigaspaces-mapping>
{%endhighlight%}

{%learn%}./transaction-optimistic-locking.html{%endlearn%}



# SpaceExclude

{: .table   .table-condensed  .table-bordered}
|Syntax     |  exclude name|
|Description| When this tag is specified the property is not written into the space.|
|Note | - When `include-properties` is defined as `implicit`, `exclude` should   be used. This is because `implicit` instructs the system to take all POJO fields into account.{%wbr%}- When `include-properties` is defined as `explicit`, there is no need to use `exclude`.{%wbr%}- `exclude` can still be used, even if `include-properties` is not defined.  |

Example:

{%highlight xml%}
<gigaspaces-mapping>
	<class name="Model.Person">
		<property name="Id" />
        <property name="FirstName" />
        <property name="LastName" />
        <property name="Type" />
		<id name="Id" auto-generate="true" />
        <routing name="Type" />
        <exclude name="StreetAddress" />
	</class>
</gigaspaces-mapping>
{%endhighlight%}


# SpaceLeaseExpiration

{: .table   .table-condensed  .table-bordered}
|Syntax     |  lease-expiration name|
|Description|This tag specifies the property for holding the timestamp of when the instance's lease expires. This property should not be populated by the user code. The space will populate this property automatically based on the lease time given by the user when writing the object. When using an external data source, you can choose to persist this value to the database. Subsequently, when data is reloaded from the external data source (at startup time for example), the space will filter out instances whose lease expiration timestamp has already passed. This field should be a `long` data type.|

Example:

{%highlight xml%}
<gigaspaces-mapping>
	<class name="Model.Person">
		<property name="Id" />
        <property name="FirstName" />
        <property name="LeaseExp" />
        <property name="Type" />
		<id name="Id" auto-generate="true" />
        <routing name="Type" />
        <lease-expiration name="LeaseExp" />
	</class>
</gigaspaces-mapping>
{%endhighlight%}

{%learn%}./leases-automatic-expiration.html{%endlearn%}

# SpaceFifoGroupingProperty

{: .table   .table-condensed  .table-bordered}
|Syntax     | fifo-grouping-property name path|
|Argument   | path          |
|Description| This tag is used to define a space FIFO grouping property. |
|Note | If defined, the `TakeModifiers.FIFO_GROUPING_POLL` or `ReadModifiers.FIFO_GROUPING_POLL` modifiers can be used to return all space entries that match the selection template in FIFO order. Different values of the FG property define groups of space entries that match each value. FIFO ordering exists within each group and not between different groups. |

Example:

{%highlight xml%}
<gigaspaces-mapping>
    <class name="com.gigaspaces.examples.FlightReservation">
        	<fifo-grouping-property name="FlightInfo" path="FlightNumber" />
    </class>
</gigaspaces-mapping>

{%endhighlight%}

{%learn%}./fifo-grouping.html{%endlearn%}


# SpaceDynamicProperties

{: .table   .table-condensed  .table-bordered}
|Syntax     | dynamic-properties name|
|Description| Allows adding properties freely to a class without worrying about the schema.|
|Note|**Only one property per class can be declared as `dynamic-properties`.**|

Example:

{%highlight xml%}
<gigaspaces-mapping>
	<class name="Model.Person">
		<property name="Id" />
        <property name="FirstName" />
        <property name="PersonInfo" />
        <property name="Type" />
		<id name="Id" auto-generate="true" />
        <routing name="Type" />
        <dynamic-properties name="PersonInfo" />
	</class>
</gigaspaces-mapping>
{%endhighlight%}

{%learn%}./poco-dynamic-properties.html{%endlearn%}





