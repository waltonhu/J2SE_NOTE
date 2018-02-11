# 冒泡排序算法Java实现：

* code(bubbleSortTest.java)

```
public class bubbleSortTest {
	public static void main(String[] args) {
		int[] arr = {2,4,6,8,1,3,5,9,10,7};
		bubbleSort(arr);
		for(int i=0; i<arr.length; i++) {
		System.out.print(arr[i] + " ");
		}
	}
	
	private static void bubbleSort(int[] a) {
		int temp;
		
		/*外循环后面再分析，所以外循环控制趟数
		每一趟都会得出一个最小值，当除了第一个数都是最小值时，
		排序完毕，所以趟数为a.length-1次。
		*/
		
		for(int i=0; i<a.length-1; i++) {
			
			/*先分析内循环，第一趟内循环需要a[j]与a[j+1]
			比较，若有前数大于后数则互换，那么每一趟下来最大的
			数必定落在当前最后面。第一趟需要对比a.length-1
			次，第二趟需要对比a.length-1-1次，...,最后一
			趟比较1次，那么我们可以把i初值设为0,i++,直到i<
			a.length-1。所以每一趟需要比较a.length-i-1
			次。用内循环来控制每一趟比较的次数以及值的交换，外循环
			控制趟数。
			*/
			
			for(int j=0; j<a.length-1-i; j++) {
				if(a[j] > a[j+1]) {
					temp = a[j];
					a[j] = a[j+1];
					a[j+1] = temp;
				}
			}
		}
	}
}


```