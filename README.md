 ## 多线程</br>
#### 线程的状态</br>
    
		1.New:新建状态。就是对象刚被new出，还有start()。
		2.Runnable:可运行状态。调用start(),此时线程就是Runnable状态，可能正在运行也可能没有运行（取决于操作系统提供的运行时间）。
		3.Blocked:阻塞状态。
		4.Waiting:等待状态。线程暂时不活动，并且不运行任何代码，这此时线程消耗资源最小，直到线程调度器重新激活。
		5.Time waitiing 超时等待装填。PS:和Wating 状态的区别是它可以在指定的时间自行返回。
		6.Terminated:终止状态。表示当前线程已经执行完毕。
		PS:1.run方法执行完毕正常退出；
            2.没有捕获异常而终止run方法，线程终止。

		sleep()
		    sleep()方法需要指定等待的时间，进入阻塞状态，让其他同优先级或者高优先级的线程得到执行的机会，也可以让低优先级的线程得到执行机会。
		    注：sleep()方法不会释放“锁标志”，也就是说如果有synchronized同步块，其他线程仍然不能访问共享数据。 
		
        sleep() 
		    sleep()方法需要指定等待的时间，进入阻塞状态，让其他同优先级或者高优先级的线程得到执行的机会，也可以让低优先级的线程得到执行机会。
		    注：sleep()方法不会释放“锁标志”，也就是说如果有synchronized同步块，其他线程仍然不能访问共享数据。 
		
        wait() 
		    wait()、notify()及notifyAll()，这三个方法用于协调多个线程对共享数据的存取，必须在synchronized语句块内使用，调用wait()，
		    notify()和notifyAll()的任务在调用这些方法前必须拥有对象的锁。注意，它们都是Object类的方法，而不是Thread类的方法。 
		    注：wait()方法会释放对象的“锁标志”。当调用某一对象的wait()方法后，会使当前线程暂停执行，并将当前线程放入对象等待池中，直到调用了
		    notify()方法后，将从对象等待池中移出任意一个线程并放入锁标志等待池中，只有锁标志等待池中的线程可以获取锁标志，
		    它们随时准备争夺锁的拥有权。当调用了某个对象的notifyAll()方法，会将对象等待池中的所有线程都移动到该对象的锁标志等待池。 
		    除了使用notify()和notifyAll()方法，还可以使用带毫秒参数的wait(long timeout)方法，效果是在延迟timeout毫秒后，被暂停的线程将被恢
		    复到锁标志等待池。 此外，wait()，notify()及notifyAll()只能在synchronized语句中使用，但是如果使用的是ReenTrantLock实现同步时使用ReenTrantLock.newCondition()获取一个Condition类对象，然后Condition的await()，signal()以及signalAll()分别对应上面的三个方法。

		yield() </br>
		yield()方法和sleep()方法类似，也不会释放“锁标志”，区别在于，它没有参数，即yield()方法只是使当前线程重新回到可执行状态，所以执行yield()
		的线程有可能在进入到可执行状态后马上又被执行，另外yield()方法只能使同优先级或者高优先级的线程得到执行机会，这也和sleep()方法不同。

		join() </br>
		    join()必须等被调用线程结束后才能返回。


![ZQUKpT.md.png](https://s2.ax1x.com/2019/06/29/ZQUKpT.md.png)
