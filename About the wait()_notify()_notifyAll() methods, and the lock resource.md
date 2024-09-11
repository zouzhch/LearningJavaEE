1. The wait() method will have the monitor object record its waiting status, and set the current thread to the block status, at last release the lock resource.
2. When other threads awaken it, this thread will continue its codes from the waiting point as soon as it gets the lock resource.
3. So the wait() method can only be invoked in a synchronised block, otherwise, an IllegalMonitorStateException will be reported since there is no lock resource to compete to get.
4. wait() method belongs to the Object class, it's a native method, so it can not be rewritten. But every class inherits this method, so all the objects can call this method like this: object.wait(), we call this object a monitor object.
5. It will maintain a set of waiting threads at this monitor object as soon as we invoke the object.wait() method. So different monitor objects will maintain different sets of waiting threads. 
6. The notify() method will awaken a random thread from the set of waiting threads at a specific monitor object, so the monitor object of the wait() method is supposed to be the same as the monitor object of the notify() method.
7. The notifyAll() method means awakening all the threads from the set of waiting threads at a specific monitor object, other parts are just the same as the notify() method.



<h3 id="xpheD">About the lock resource</h3>
When a thread gets the lock resource, it will constantly execute all codes covered by the range of the synchronised block, it will not yield the CPU resource of the current progress until the codes block ends or comes into the command of demanding the thread to yield resources.

--- I used to think the thread, which got the lock resource, would not constantly execute all codes of the synchronised block, it might yield resources from time to time. It just looked like constantly executed all the codes because only this thread held the lock and no one else getting the CPU resource could execute, thus only the thread, which got the lock resource, could execute codes. Obviously, it is inefficient!

