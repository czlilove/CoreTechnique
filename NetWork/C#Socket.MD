1.Socket的关闭：disconnect,shutdown,close,
shutdown:禁用socket的send或（和）receive。在close前调用它能确保发送或接收中的数据能被完全发送或接收出去。

close：先关闭socket连接，再释放socket的所有托管和非托管资源。调用以后socket就废掉了，不能被重用。
disconnect:关闭socket连接，可以选择socket是否可复用。
不管是close还是disconnect，为了保证数据传输完毕，一般在调用它们之前最好调用shutdown.
一般是：socket.ShutDown(SocketShutDown.Both);socket.Close();
即先shutdown，再close
