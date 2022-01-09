# Execute-the-merge-algorithm-with-the-following-two-arrays-and-justify-the-output-obtained-in-each-c
package javaapplication53;
import java.util.Arrays;
import java.util.Scanner;
public class MargeSort {
 void Marge(int A[], int Left, int mid, int Right){
 int l=mid-Left+1;
 int r=Right-mid;
 int leftArray[] = new int[l];
 int rightArray[] = new int[r];
 for (int i = 0; i < l; ++i) {
 leftArray[i] = A[Left + i];
 }
 for (int j = 0; j < r; ++j) {
 rightArray[j] = A[mid + 1 + j];
 }
 int i = 0, j = 0;
 int k = Left;
 while (i < l && j < r) {
 if (leftArray[i] <= rightArray[j]) {
 A[k] = leftArray[i];
 i++;
 }
 else{
 A[k] = rightArray[j];
 j++;
 }
 k++;
 }
 while (i < l) {
 A[k] = leftArray[i];
 i++;
 k++;
 }
 while (j < r) {
 A[k] = rightArray[j];
 j++;
 k++;
 }
 System.out.println("---_>Left Array" + Arrays.toString(leftArray));
 System.out.println("---_>Right Array" + Arrays.toString(rightArray));
 }
 
 void Sort(int Arr[], int Le, int Ri){
 if(Le<Ri){
 int mid=(Le+Ri)/2;
 Sort(Arr,Le,mid);
 Sort(Arr,mid+1,Ri);
 Marge(Arr, Le, mid, Ri);
 }
 }
 public static void main(String[] args) {
 int A1,A2;
 int[] Array_1;
 int[] Array_2;
 int[] A;
 Scanner Input=new Scanner(System.in);
 System.out.println(" Two Arry Number ? : ");
 A1=Input.nextInt();
 A2=Input.nextInt();
 Array_1=new int[A1];
 Array_2=new int[A2];
 System.out.println("1st Array Values : ");
 for(int i=0; i<A1; i++){
 int n=Input.nextInt();
 Array_1[i]=n;
 }
 System.out.println("\n2nd Array Values: \n");
 for(int i=0; i<A2; i++){
 int n=Input.nextInt();
 Array_2[i]=n;
 }
 A=new int[A1+A2];
 System.arraycopy(Array_1, 0, A, 0, A1);
 System.arraycopy(Array_2, 0, A, A1, A2);
 System.out.println("\nAfter Concatenate Array:\n " + Arrays.toString(A));
 
 MargeSort Object=new MargeSort();
 Object.Sort(A, 0, A.length-1);
 System.out.println("\nSorted Array:\n " + Arrays.toString(A));
 
 }
}
