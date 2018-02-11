# 选择排序算法Java实现：

code（TestArray.java)：
```
public class TestArray {
	public static void main(String[] args) {
	
		int[] a = new int[args.length];
		for(int i=0; i<args.length; i++) {
			a[i] = Integer.parseInt(args[i]);
	   
		}-----------
		selectionSort(a);
		print(a);
	}
	
	
	private static void selectionSort(int[] a) {	
		int temp;
		//外层循环取数，i表示第i个数
		for(int i=0; i<a.length-1; i++) {
		//因为取出一个数之后需要和下面所有的数都进行比较，内层循环表示当前取出的数与后面数比较的次数，j=i+1表示a[i]的下一个数a[i+1]，比较完之后j++，表示a[i]的下一个数a[i+1]，比较完后j++表示下个数a[i+2]，直到比较到第a.length个数
			for(int j=i+1; j<a.length; j++){
			if(a[i] > a[j]) {
				temp = a[i];
				a[i] = a[j];
				a[j] = temp;
			}
			}
		}
	}
	
	private static void print(int[] a) {
		for(int i=0; i<a.length; i++) {
			System.out.print(a[i] + " ");
		}
	}
}

```