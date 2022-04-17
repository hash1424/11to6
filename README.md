# 11to6
public class Apr11 {
	
	
public static void main(String[] args) {
		
		
		int arr1[] = { 1, 2, 4, 5, 6 };
        int arr2[] = { 2, 3, 5, 7 };
        int m = arr1.length;
        int n = arr2.length;
        printUnion(arr1, arr2, m, n);
        
        
        int[] a = { 1, 2, 4, 5, 6 };
        System.out.println(findDisappearedNumbers(a));
        
        
        if (isSubset(arr1, arr2, m, n))
            System.out.print("arr2[] is "+ "subset of arr1[] ");
        else
            System.out.print("arr2[] is"+ "not a subset of arr1[]");

	}
	
	
	
	public static boolean isSubset(int arr1[],int arr2[],int m, int n)
	{
		int i = 0;
		int j = 0;
		for (i = 0; i < n; i++) {
			for (j = 0; j < m; j++)
				if (arr2[i] == arr1[j])
					break;

			if (j == m)
				return false;
		}


		return true;
	}
	public static int findDisappearedNumbers(int[] nums)
    {
        int n=nums.length;
        int sum=((n+1)*(n+2))/2;
        for(int i=0;i<n;i++)
          sum-=nums[i];
        return sum;
    }
	
	public static int printUnion(int arr1[], int arr2[], int m, int n)
    {
        int i = 0, j = 0;
        while (i < m && j < n) {
            if (arr1[i] < arr2[j])
                System.out.print(arr1[i++] + " ");
            else if (arr2[j] < arr1[i])
                System.out.print(arr2[j++] + " ");
            else {
                System.out.print(arr2[j++] + " ");
                i++;
            }
        }
 
        
        while (i < m)
            System.out.print(arr1[i++] + " ");
        while (j < n)
            System.out.print(arr2[j++] + " ");
 
        return 0;
    }
    
    package com.DSA_Assingment;



public class Apr13 {

	

	public static void main(String[] args) {

		int[][] arr = new int[][] { {3, 4, 1, 8},

            {1, 4, 9, 11},

            {76, 34, 21, 1},

           {2, 1, 4, 5} };

           

           int t=4;

 

           	maxelement(4, arr);

           	

           	System.out.println(searchMatrix(arr,t));

           	

           	

           	int numRay[] = { 0, 4, 3, 2, 7, 8, 2, 3, 1 };

            

            for (int i = 0; i < numRay.length; i++) {

                numRay[numRay[i] % numRay.length]= numRay[numRay[i] % numRay.length]+ numRay.length;

            }

            System.out.println("The repeating elements are : ");

            for (int i = 0; i < numRay.length; i++) {

                if (numRay[i] >= numRay.length * 2) {

                    System.out.println(i + " ");

                }

            }

        



	}

	

	

	public static boolean searchMatrix(int[][] matrix, int target) {

        int row = matrix.length;

        int col = matrix[0].length;

        int l = 0;

        int r = row * col - 1;



        while(l <=r ){

            int mid = l + (r-l)/2;

            int val = matrix[mid/col][mid%col];

            if(val == target) return true;

            if(val > target){

                r = mid-1;

            }else{

                l = mid+1;

            }

        }



        return false;

    }

	

	 

    public static void maxelement(int no_of_rows, int[][] arr) {

        int i = 0;

         

       

        int max = 0;

        int[] result = new int[no_of_rows];

        while (i < no_of_rows) {

            for (int j = 0; j < arr[i].length; j++) {

                if (arr[i][j] > max) {

                    max = arr[i][j];

                }

            }

            result[i] = max;

            max =0;

            i++;

 

        }

        printArray(result);

 

    }

 

    

    private static void printArray(int[] result) {

        for (int i =0; i<result.length;i++) {

            System.out.println(result[i]);

        }

 

    }



}

package com.DSA_Assingment;



public class Apr14 {



	

public static int N = 4;

    

    

    public static void diagonalBoundarySum(int arr[][]){

        int requiredSum = 0;

         

       

        for (int i = 0; i < N; i++) {

     

            

            for (int j = 0; j < N; j++) {

     

                

                if (i == j || (i + j) == N - 1) {

                    requiredSum += arr[i][j];

                }

     

               

                else if (i == 0 || j == 0 || i == N - 1|| j == N - 1) {

                    requiredSum += arr[i][j];

                }

            }

        }

     

        System.out.println(requiredSum);

    }



    

    

	public static void main(String[] args) {

		int arr[][] = { 

				{ 1, 2, 3, 4 },

				{ 1, 2, 3, 4 },

                { 1, 2, 3, 4 },

                { 1, 2, 3, 4 } };



			diagonalBoundarySum(arr);

	}

}

package com.DSA_Assingment;



public class Apr15 {



	

	public static void main(String[] args) {

		int N = 4;

		 

       

        int mat[][] = {

            { 1, 2, 3, 4 },

            { 5, 6, 7, 8 },

            { 9, 10, 11, 12 },

            { 13, 14, 15, 16 }

        };

           rotateMatrix(N, mat);

 

        displayMatrix(N, mat);

	}

	

	public static void rotateMatrix(int N, int mat[][])

	    {

	       

	        for (int x = 0; x < N / 2; x++) {

	           

	            for (int y = x; y < N - x - 1; y++) {

	               

	                int temp = mat[x][y];

	 

	                mat[x][y] = mat[y][N - 1 - x];

	 

	                mat[y][N - 1 - x]

	                    = mat[N - 1 - x][N - 1 - y];

	 

	                mat[N - 1 - x][N - 1 - y] = mat[N - 1 - y][x];

	 

	               mat[N - 1 - y][x] = temp;

	            }

	        }

	    }

	 

	    

	    static void displayMatrix(

	        int N, int mat[][])

	    {

	        for (int i = 0; i < N; i++) {

	            for (int j = 0; j < N; j++)

	                System.out.print(" " + mat[i][j]);

	 

	            System.out.print("\n");

	        }

	        System.out.print("\n");

	    }

}

package com.DSA_Assingment;



public class Apr16 {

	

	public static void main(String[] args) {

		int [] A=  { 3,5,7,1,0,1,2,-2,-1,-3};

		int i = A.length;

		int m=0;

		int sum=0;

		

       // System.out.println(maxElement(A, i));

       sumElement(A, i,sum,m);

       

       negativeNumbers(A,i, m);

       

       int n=1234;

	    

	    print(n);





	}

	

	public static void print(int n)

	{

	   if(n<10){

		   System.out.println(n);

		   return;

	         

	         

	   }   

	   else{

		  

		   System.out.print(n%10);

		   print(n/10);

	      

	         

	   }

	   

	   

}

	private static void negativeNumbers(int[] a,int i,int m) {

		if(i==m) {

			return;

		}

		else {

			if(a[m]<0)

			System.out.println(a[m]+" ");

			m++;

			negativeNumbers(a,i, m);

			

		}

	}





	private static void sumElement(int[] a, int i,int sum,int m) {

		

		if(i==m) {

			System.out.println(sum);

			return;

		}else {

			sum=sum+a[m];

			m++;

			sumElement(a,i,sum,m);

		}

		

		

	}





	public static int maxElement(int []A,int i) {

		

		if(i == 1)

	        return A[0];

	         

	        return Math.max(A[i-1], maxElement(A, i-1));

		

	}





}
