# 选择排序算法Java实现：

* code（TestArray.java\)：

```java
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

        //外层循环取数，i表示第i个数
        for(int i=0; i<a.length-1; i++) {

        //因为取出一个数之后需要和下面所有的数都进行
        比较，内层循环表示当前取出的数与后面数比较的
        次数，j=i+1表示a[i]的下一个数a[i+1]，比较完
        之后j++，表示a[i]的下一个数a[i+1]，比较完后
        j++表示下个数a[i+2]，直到比较到第a.length个
        数
            for(int j=i+1; j<a.length; j++){
            if(a[i] > a[j]) {
                int temp = a[i];
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

* 但是这样的选择排序效率并不高，因为在j循环里每一次比较，若符合 `a[i] > a[j]` 条件，就会交换一次。

* 例如，现在有 `4 2 3 1` 四个数，需要从小到大排序，那么按这种算法经过第一个j循环后，就变成 `2 4 3 1` ，第二个j循环 `1 4 3 2`，可以看出第一趟的交换其实没有必要。

* 若有多个数都比这个a\[i\]小，那么就需要交换多次，没有必要交换多次，我们需要改善这种算法使每次j循环里遍历完只交换一次就能找到最小的数，以提高效率。

###  改进后的selectionSort\(\)方法：

```
private static void selectionSort(int[] a) {
        int temp, min;    //两个局部变量定义在循环外面，这样就不用每次都重新分配栈空间
        for(int i=0; i<a.length-1; i++) {
            min = i;  //min，记录当前数组的最小值的下标
            //j=min+1，从最小值开始往右边比较
            for(int j=min+1; j<a.length; j++){
                if(a[min] > a[j]) {
                    min = j;   //当前值a[j]比a[min]小，将j赋给min
                }
            }
            //遍历完如果a[i]与a[min]不相等说明a[i]已经不是最小值了，需要交换
            if(a[i] != a[min]) {
                temp = a[i];
                a[i] = a[min];
                a[min] = temp;
            }
        }
    }
```



