非阻塞套接字方法，执行之后立即返回。
然而一些操作并不是马上就能执行完毕的，需要一定的等待时间，这时会产生异常
SocketException.其ErrorCode（NativeErrorCode？）对应于Windows Sockets version 2 API error code：<br>
WSAEWOULDBLOCK<br>
10035<br>
Resource temporarily unavailable.<br>
资源暂时不可用<br>
This error is returned from operations on nonblocking sockets that cannot be completed immediately<br>
非阻塞模式下，套接字执行一些不能立即完成的操作，会返回这个错误码。<br>
for example recv when no data is queued to be read from the socket. <br>
比如当接收缓冲区中没有数据可读时，recv会返回这个错误。<br>
It is a nonfatal error, and the operation should be retried later. <br>
这个不是致命错误，捕获到这个错误后，我们知道当前操作暂时无法执行完毕，所以我们可以稍后继续执行该操作。<br>
It is normal for WSAEWOULDBLOCK to be reported as the result from calling connect on a nonblocking SOCK_STREAM socket, 
since some time must elapse for the connection to be established.<br>
对于非阻塞tcp connect方法来说,这个错误很正常，因为建立连接必然需要一定的时间。
