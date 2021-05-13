// # 2-1
// Program that declares an array with length of 10, gets 10 integers and prints odd / even numbers separately.

#include <iostream>
using namespace std;

void PrintOdd(int *arr, int oddNum)
{
	int oddArr[oddNum], counter = 0;
	for(int i = 0; i < 10; i++)
	{
		if(*(arr + i) % 2 == 1)
		{
			oddArr[counter] = *(arr + i);
			counter++;
		}
	}
	cout << "홀수 출력: ";
	for(int i = 0; i < oddNum; i++)
	{
		if (i != oddNum - 1)
			cout << oddArr[i] << ", ";
		else
			cout << oddArr[i] << endl;
	}
}

// 			oddArr[counter] = *(arr + i);
void PrintEven(int *arr, int evenNum)
{
	int evenArr[evenNum], counter = 0;
	for(int i = 0; i < 10; i++)
	{
		if(*(arr + i) % 2 == 0)
		{
			evenArr[counter] = *(arr + i);
			counter++;
		}
	}
	cout << "짝수 출력: ";
	for(int i = 0; i < evenNum; i++)
	{
		if (i != evenNum - 1)
			cout << evenArr[i] << ", ";
		else
			cout << evenArr[i] << endl;
	}
}

int main()
{
	int arr[10], oddNums = 0, evenNums = 0;
	int *arrPtr = arr;
	for (int i = 0; i < 10; i++)
		cin >> *(arrPtr + i);
	for(int i = 0; i < 10; i++)
	{
		if(*(arr + i) % 2 != 0)
			oddNums++;
	}
		for(int i = 0; i < 10; i++)
	{
		if(*(arr + i) % 2 == 0)
			evenNums++;
	}
	PrintOdd(arrPtr, oddNums);
	PrintEven(arrPtr, evenNums);
	return 0;
}
