### 异常处理

1、调用方法的时候返回布尔值来代替返回null，这样可以 NullPointerException。由于空指针是java异常里最恶心的异常。

2、 catch块里别不写代码。空catch块是异常处理里的错误事件，因为它只是捕获了异常，却没有任何处理或者提示。通常你起码要打印出异常信息，当然你最好根据需求对异常信息进行处理。

3、能抛受控异常（checked Exception）就尽量不抛受非控异常(unchecked Exception[Error或者RuntimeException的异常])。通过去掉重复的异常处理代码，可以提高代码的可读性。

4、 绝对不要让你的数据库相关异常显示到客户端。由于绝大多数数据库和SQLException异常都是受控异常，在Java中，你应该在DAO层把异常信息处理，然后返回处理过的能让用户看懂并根据异常提示信息改正操作的异常信息。

5、 在Java中，一定要在数据库连接，数据库查询，流处理后，在finally块中调用close()方法
