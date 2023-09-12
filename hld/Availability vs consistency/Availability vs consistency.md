## Availability vs consistency

### [](https://github.com/donnemartin/system-design-primer/tree/master#cap-theorem)CAP theorem

[![](https://github.com/donnemartin/system-design-primer/raw/master/images/bgLMI2u.png)](https://github.com/donnemartin/system-design-primer/blob/master/images/bgLMI2u.png)  
_[Source: CAP theorem revisited](http://robertgreiner.com/2014/08/cap-theorem-revisited)_

In a distributed computer system, you can only support two of the following guarantees:

- **Consistency** - Every read receives the most recent write or an error
- **Availability** - Every request receives a response, without guarantee that it contains the most recent version of the information
- **Partition Tolerance** - The system continues to operate despite arbitrary partitioning due to network failures

_Networks aren't reliable, so you'll need to support partition tolerance. You'll need to make a software tradeoff between consistency and availability._

#### CP - consistency and partition tolerance

Waiting for a response from the partitioned node might result in a timeout error. CP is a good choice if your business needs require atomic reads and writes.

#### AP - availability and partition tolerance

Responses return the most readily available version of the data available on any node, which might not be the latest. Writes might take some time to propagate when the partition is resolved.

AP is a good choice if the business needs to allow for eventual consistency or when the system needs to continue working despite external errors.


