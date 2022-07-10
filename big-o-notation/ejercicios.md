# EJERCICIOS Big-O-Notation

1)The following code computes the product of a and b. What is its runtime?
int product(int a, int b) {
    int sum = 0;
    for (int i = 0; i < b; i++) {
        sum += a;
    }
    return sum;
}
## O(b)

2)What is its runtime?
int power(int a, int b){
    if(b < 0) {
        return 0;
    } else if (b == 0) {
        return 1;
    } else {
        return a * power(a, b - 1)
    }
}
## O(b)

3)What is its runtime?
int mod(int a, int b) {
    if (b <= 0) {
        return -1;
    }
    int div = a / b;
    return a - div * b;
}

## O(1)

4)What is its runtime (assume a and b are both positive)?
int div(int a, int b) {
    int count = 0;
    int sum = b;
    while (sum <= a) {
        sum += b;
        count++;
    }
    return count;
}
## O(a/b)

5)What is its runtime?
int sqrt(int n) {
    return sqrt_helper(n, 1, n);
}

int sqrt_helper(int n, int min, int max) {
    if (max < min) return -1;

    int guess = (min + max) / 2;
    if (guess * guess = n) {
        return guess;
    } else if ( guess * guess < n) { // too low
        return sqrt_helper(n, guess + 1, max);
    } else { // too high
        return sqrt_helper(n, min, guess - 1);
    }
}
## O(log n)

6)What is its runtime?
int sqrt(int n) {
    for (int guess = 1; guess * guess <= n; guess++) {
        if(guess * guess == n) {
            return guess;
        }
    }
    return -1;
}
## O(n^1/2);

7)If a binary search tree is not balanced, how long might it take(worst case) to find and element in it?
## O(n);

8)You are looking for a specific value in a binary tree, but the tree is not a binary search tree. What is its runtime?
## O(n)

9)How long does copying an array take?
int[] copyArray(int[] array) { 
    int[] copy = new int[0]; 
    for (int value : array) { 
        copy = appendToNew(copy, value); 
    } 
    return copy; 
} 

int[] appendToNew(int[] array, int value) { 
    // copy all elements over to new array 
    int[] bigger = new int[array.length + 1]; 
    for (int i = 0; i < array.length; i++) {
        bigger[i] = array[i]; 
    }  
// add new element 
    bigger[bigger.length -1] = value; 
    return bigger;
}
## O(n^2)

10)What is its big O time?
int sumDigits(int n) {
    int sum = 0;
    while (n > 0) {
        sum += n % 10;
        n /= 10;
    }
    return sum;
}
## O(log n)

11)What is its runtime?
int numChars = 26; 

void printSortedStrings(int remaining) { 
    printSortedStrings(remaining, ""); 
} 

void printSortedStrings(int remaining, String prefix) { 
    if (remaining == 0) { 
        if (islnOrder(prefix) { 
            system.out.println(prefix); 
        }
    } else { 
        for (int i = 0; i < numChars; i++) { 
            char c = ithLetter(i);
            printSortedStrings(remaining - 1, prefix + c);
        } 
    } 
}

boolean islnOrder(String s) { 
    for (int i = 1; i < s .length(); i++) { 
        int prev = ithLetter(s.charAt(i -1)); 
        int curr = ithLetter(s.charAt(i)); 
        if (prev > curr) { 
            return false; 
        } 
    } 
    return true; 
} 

char ithLetter(int i) {
     return (char)  (((int) 'a') + i); 
}
## O(kc^k)

12)What is its runtime?
int intersection(int[] a, int[] b) { 
    mergesort(b); 
    int intersect = 0; 

    for (int x : a) { 
        if (binarySearch(b, x) >= 0) { 
            intersect++ ; 
        } 
    } 
    return intersect; 
}
## O(b log b + a log b)