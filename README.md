# zifuchuan-miaoshu
项目描述

//  memcpy
//  memcpy(a,b,n)

//  memcpy  C语言要求：只要处理 不重叠的内存拷贝就可以

//  整型数组，通过memcpy，进行拷贝
//int main()
//{
//	int arr1[] = { 1, 2, 3, 4, 5 };
//	int arr2[5] = { 0 };
//	
//	memcpy(arr2, arr1, sizeof(arr1));
//	return 0;
//}


//结构体也可以通过 memcpy
//struct S
//{
//	char name[20];
//	int age;
//};
//
//int main()
//{
//	struct S arr1[] = { { "张三", 20 }, { "李四", 18 }, { "王五" }, 30 };
//	struct S arr2[3];
//	memcpy(arr2, arr1, sizeof(arr1));
//	return 0;
//}



//  自创 memcpy
//#include<assert.h>
//#include<string.h>
//
//struct S
//{
//	char name[20];
//	int age;
//};
//
//void* my_memcpy(void *dest, const void *src, size_t num)
//{
//	void *ret = dest;
//	assert(dest != NULL);
//	assert(dest != NULL);
//
//	while (num--)
//	{
//		*(char*)dest = *(char*)src;
//		++(char*)dest;
//		++(char*)src;
//	}
//	return ret;
//}
//
//int main()
//{
//	struct S arr1[] = { { "张三", 18 }, { "李四", 20 }, { "王五", 30 } };
//	struct S arr2[3] = {0};
//	my_memcpy(arr2, arr1, sizeof(arr1));
//}





// memmove    处理内存重叠的情况

//int main()
//{
//	int arr[] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
//	int i = 0;
//	memmove(arr + 2, arr, 20);
//	for (i = 0; i < 10; i++)
//	{
//		printf("%d ", arr[i]);
//	}
//	return 0;
//}



//  自创 memmove
//#include<stdio.h>
//#include<assert.h>
//
//my_memmove(void* dest, const void* src, size_t count)
//{
//	void *ret = dest;
//	assert(dest);
//	assert(src);
//	if (dest < src)
//	{
//		// 前 -> 后
//		while (count--)
//		{
//			*(char*)dest = *(char*)src;
//			++(char*)dest;
//			++(char*)src;
//		}
//	}
//	else
//	{
//		// 后 -> 前
//		while (count--)
//		{
//			*((char*)dest + count) = *((char*)src + count);
//		}
//	}
//	return ret;
//}
//
//int main()
//{
//	int arr[] = { 1, 2, 3, 4, 5, 6, 8, 9, 10 };
//	my_memmove(arr + 2, arr, 20);
//	int i = 0;
//	for (i = 0; i < 9; i++)
//	{
//		printf("%d ", arr[i]);
//	}
//	return 0;
//}









//  memcmp
//  memcmp(a,b,n)   a是目的地，b是源，n是字节数

//#include<stdio.h>
//
//int main()
//{
//	int arr1[] = { 1, 2, 3, 4, 5 };
//	int arr2[] = { 1, 2, 5, 4, 3 };
//	int ret = memcmp(arr1, arr2, 9);
//	printf("%d\n", ret);
//	return 0;
//}
//如果比9个字节
//01 00 00 00 02 00 00 00 03 00 00 00 04 00 00 00 
//01 00 00 00 02 00 00 00 05 00 00 00 04 00 00 00
// 则是03和05比较，通过比较返回的是一个 <0 的数










//  memset  内存设置
//  memset(a,b,n)  a是目的地，b是需要修改成的内容，n是字节数



//  memset 比较适合用char类型，因为char类型是每一个字节计算的
//int main()
//{
//	char arr[10] = "";
//	memset(arr, '#', 10);
//	return 0;
//}


//  memset 对于int类型的错误使用方法
//int main()
//{
//	int arr[10] = { 0 };
//
//	//  int 是每4个字节一个元素，所以arr数组中有40个字节
//	//  当memset 将1放入arr中，且是10个字节
//	//  01 01 01 01 01 01 01 01 01 01 00 00 ...
//	//  01 01 01 01 = 16843009
//	memset(arr, 1, 10);
//	return 0;
//}
