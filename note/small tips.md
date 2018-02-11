* Java里用System.out.println()方法直接打印一个对象的引用时，会默认调用Object对象中的toString()方法。

例如：
```
public class Test {
	public static void main(String[] args) {
		Test1 t1 = new Test1(1);
		System.out.println(t1);
	}
}

class Test1 {
	int a;
	Test1(int a) {
		this.a = a;
	}
}
输出结果：Test1@15db9742
```
在直接调用这个输出的话，toString()方法会返回这个对象的String
直接打印对象的话，会输出类名加上这个对象名的哈希码，为了引用堆中的对象。

