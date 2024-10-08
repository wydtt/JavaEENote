tomcat负责接受浏览器的请求

public class Main {
    public static void main(String[] args) {
        //要访问hello.html 需要写一个程序实现监听读取请求，触发获得hello.html文件返回给浏览器
        //在9999端口上进行监听
        try {
            ServerSocket serverSocket = new ServerSocket(9999);

            while (!serverSocket.isClosed()){
                //等待其他客户端连接,得到socket,盖socker用于通信
                System.out.println("=============9999===============");
                Socket socket = serverSocket.accept();
                //通过socket 得到输出流
                OutputStream outputStream = socket.getOutputStream();
                //读取hello.html文件返回即可
                //得到字符输入流，循环的读取
                BufferedReader bufferedReader = new BufferedReader(new FileReader("src/hello.html"));
                String buf="";
                while ((buf=bufferedReader.readLine())!=null){
                    outputStream.write(buf.getBytes());
                }
                outputStream.close();
                socket.close();
            }
            serverSocket.close();
        } catch (IOException e) {
            throw new RuntimeException(e);
        }
    }
}