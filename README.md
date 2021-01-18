# C++ Internship-Paper-3
## Table of contents:
*Question 1
*Question 2

## Question 1
<p>
 Q1. Union and Intersection of two sorted arrays.

Given two sorted arrays, find their union and intersection.

Input : arr1[] = {1, 3, 4, 5, 7} arr2[] = {2, 3, 5, 6} 
Output :
Union : {1, 2, 3, 4, 5, 6, 7} 
Intersection : {3, 5} 

Input : arr1[] = {2, 5, 6} arr2[] = {4, 6, 8, 10} 
Output : 
Union : {2, 4, 5, 6, 8, 10} 
Intersection : {6}
</p>
  
## code:
```c++
#include<bits/stdc++.h>
using namespace std;

void union ( int arr1[], int arr2[], int m, int n) {
    vector<int> un;
    int i =0, j=0;
    while(i<m && j<n) {
        if(arr1[i]==arr2[j]) {//if both array elemnts are same print any one of them and increment i and j
            un.push_back(arr1[i]);
            i++;
            j++;
        }
        else if(arr1[i]>arr2[j]) { 
            j++;
        }
        else {
            i++;
        }
    }
    vector<int> ::iterator it;
    for(it=un.begin();it!=un.end();it++) {
        cout << *it << " " ;
    }
    cout << endl;
}

void intersection(int arr1[], int arr2[], int m , int n) {
    vector<int> inter;
    int i = 0;
    int j = 0;
    while(i<m && j<n) {
        if(arr1[i]==arr2[j]) {
            inter.push_back(arr1[i]);
            i++;
            j++;
        }
        else if(arr1[i]>arr2[j]) {
            inter.push_back(arr2[j]);
            j++;
        }
        else {
            inter.push_back(arr1[i]);
            i++;
        }
    }
    vector<int> ::iterator it;
    for(it=inter.begin();it!=inter.end();it++) {
        cout << *it << " " ;
    }
    cout << endl;
}
int main() {
    int arr1[] = {1, 3, 4, 5, 7} 
    int arr2[] = {2, 3, 5, 6}
    int len1= sizeof(arr1)/sizeof(arr1[0]);
    int len = sizeof(arr2)/sizeof(arr2[0]);
    union(arr1,arr2,m,n);
    intersection(arr1,arr2,len1,len);
    return 0;
}
```

## Question 2:
<p>
Write a function rotate(arr[], d, n) that rotates arr[] of size n by d elements.
Rotation of the above array by 2 will make array

Input: arr[] = {1,2,3,4,5,6}, n = 6, d = 2
Output: arr[] = {3,4,5,6,1,2}
</p>

## Approach:
   Using built in STL function reverse to do the work
   <b>Time complexity: O(n)  //doesnt work for large array inputs
##Code
```c++
void rotate(vector<int>& nums, int d,int n){
        d = d % n;
        //Reverse the first d numbers
        std::reverse(nums.begin(),nums.begin() + k);
        //Reverse the last n - d numbers
        std::reverse(nums.begin()+d,nums.end());
        //Reverse the entire list
        std::reverse(nums.begin(),nums.end());
}
```
