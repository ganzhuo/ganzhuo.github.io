## 1.冒泡排序

```java
public class BubbleSort {
    public static void main(String[] args) {
        // 需要排序的数组
           int arr[] = { 49,38,65,97,76,13,27,49 };
        System.out.println("排序前");
        System.out.println(Arrays.toString(arr));
        bubbleSort(arr);
        System.out.println("排序后");
        System.out.println(Arrays.toString(arr));
    }

    // 将前面的冒泡排序算法，封装成一个方法
    public static void bubbleSort(int[] arr) {
        int temp = 0;// 临时变量用来做交换
        boolean flag = false;// 标识变量，标识是否进行过交换，用于冒泡排序的优化
        for (int i = 0; i < arr.length - 1; i++) {
            for (int j = 0; j < arr.length - 1 - i; j++) {
                // 如果前面的数比前面的数大，就做交换处理
                if (arr[j] > arr[j + 1]) {
                    flag = true;// 如果交换了就将flag置为true
                    temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
            if (!flag) {// 在一趟排序中，一次交换都没有就退出循环，说明此时的数组已经是有序的了
                break;
            } else {
                flag = false;// 如果有交换的话就重置flag为false，进行下一次循环判断
            }
        }
    }
}
```

## 2.选择排序

```Java
public class A3 {
    public static void main(String[] args) {
        int[] s = {5,7,6,4,3,8};
        sort(s);
        System.out.println(Arrays.toString(s));
    }
    public static void sort(int[] s){
        int N = s.length;
        for (int i = 0; i < N - 1; i++) {
            int index = i;
            for (int j = i+1; j < N; j++) {
                if (s[j] < s[index]){
                    index = j;
                }
            }
            if(index != i){
                int temp = s[i];
                s[i] = s[index];
                s[index] = temp;
            }
        }
    }
}
```

## 3.快速排序

```Java
public class A2 {
    public static void main(String[] args) {
        int s[] = {5,7,9,8,15,3,2,4,6};
        int l = 0;
        int r = 8;
        quick_sort(s,l,r);
        System.out.println("排序后："+ Arrays.toString(s));
    }
    public static void quick_sort(int s[],int l,int r){
        if(l >= r) return;
        int i = l;
        int j = r;
        int x = s[l];
        while(i < j){
            while(i < j && s[j] >= x)
                j--;
            if(i < j){
                s[i] = s[j];
                i++;
            }
            while(i < j && s[i] < x)
                i++;
            if( i < j){
                s[j] = s[i];
                j--;
            }
        }
        s[i] = x;
        quick_sort(s,l,i-1);
        quick_sort(s,i+1,r);
    }
}
```

