# heapsort

#include <stdio.h>
void accept(int a[], int n)
  {
    for (int i = 0; i < n; i++)
    {
      printf("Enter the Data : ");
      scanf("%d", &a[i]);
    }
      printf("\n");
  }
    void display(int a[], int n)
    {
      for (int i = 0; i < n; i++)
      {
        printf("%d ", a[i]);
      }
        printf("\n");
      }
      void heapify(int a[], int n, int i)
      {
          int largest = i;
          int left = 2 * i + 1;
          int right = 2 * i + 2;
          int t;
          if (left < n && a[left] > a[largest])
          {
              largest = left;
          }
            if (right < n && a[right] > a[largest])
          {
              largest = right;
          }

            if (largest != i)
            {
              t = a[i];
              a[i] = a[largest];
              a[largest] = t;
              heapify(a, n, largest);
            }
        }
        void heapSort(int a[], int n)
        {
            int t;
            // Build max heap
            for (int i = n / 2 - 1; i >= 0; i--)
            heapify(a, n, i);
            // Heap sort
            for (int i = n - 1; i >= 0; i--)
             {
                t = a[0];
                a[0] = a[i];
                a[i] = t;
                heapify(a, i, 0);
              }
            }
            
            int main()
            {
                int a[50];
                int n;
                printf("How many Numbers :");
                scanf("%d",&n);
                accept(a,n);
                printf("Before Sort array is \n");
                display(a, n);
                heapSort(a, n);
                printf("Aftre Sort array is \n");
                 display(a, n);
                 
             }
