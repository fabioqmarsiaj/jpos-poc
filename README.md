## jpos-poc

So far, we know a QBean descriptor:

* Needs a name, used to publish it with the MBeanServer.
* The name can be taken from a name attribute.
* If there's no name attribute, Q2 uses the top level element name as the QBean's name.
* It needs a class attribute defining the class that implements this QBean.

Note: jPOS uses JMX internally (Java Management Extensions):

`"JMX serves as a proxy to the actual object instances registered in the JVM's MBeanServer. This system was established BEFORE Java supported annotations. It identifies available attributes and operations in an MBean through a simple naming convention. To expose a class as an MBean, create an interface with the base class name followed by the MBean suffix. For example, for a class named MyQBean, you would create an interface called MyQBeanMBean to expose certain methods."`

_**Update regarding the statement above:**_

No need to implement an *MBean interface that extends QBean.
Just create your MyQBean class that extends QBeanSupport.

`"...because QBeanSupport implements QBeanSupportMBean that already expose the same operations to JMX"`