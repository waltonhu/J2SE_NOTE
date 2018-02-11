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