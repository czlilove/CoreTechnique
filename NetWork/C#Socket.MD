1.Socket的关闭：disconnect,shutdown,close,

一般是：socket.ShutDown(SocketShutDown.Both);socket.Close();
即先shutdown，再close
