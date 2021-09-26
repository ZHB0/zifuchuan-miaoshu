# zifuchuan-miaoshu
项目描述
//  求字符串长度
// strlen的使用

//  strlen()打印出来的是一个无符号整型

//#include<string.h>
//int main()
//{        //     3     -         6      =  -3
//	if ( strlen("abc") - strlen("abcedf") > 0)
//	{
//		printf("haha\n");
//	}
//	else
//	{
//		printf("hehe\n");
//	}
//	return 0;
//}
//本来3-6=-3 ，但是因为strlen是一个无符号整型，所以-3经过 反码->补码 后，变成了一个正数


//纯库函数的strlen
//int main()
//{
//	char arr1[] = { "abcdef" };
//	//char arr2[] = { 'a', 'b', 'c', 'd', 'e', 'f' };
//	int len1 = my_strlen(arr1);
//	//int len2 = strlen(arr2);
//	printf("%d\n", len1);
//	//printf("%d\n", len2); // 随机值，因为arr2中的元素不是一个字符串，所以当计算到f之后，后面没有\0。strlen将会继续向后计算，直到遇见\0才停止
//	return 0;
//}

//自创strlen有以下思路
//1.计数器的方法
//2.递归
//3.指针 - 指针


//1.计数器方法

//#include<string.h>
//#include<assert.h>
//
//int my_strlen(const char *str)
//{
//	int count = 0;
//	assert(str!=NULL);
//	while (*str!='\0')
//	{
//		count++;
//		str++;
//	}
//	return count;
//}
//
//int main()
//{
//	char arr1[] = { "abcdef" };
//	int len1 = my_strlen(arr1);
//	printf("%d\n", len1);
//	return 0;
//}




//2.递归
//不创建临时变量求字符串长度

//#include<assert.h>
//
//int my_strlen(const char *pa)
//{
//	assert(pa);
//	if (*pa == '\0')
//	{
//		return 0;
//	}
//	return 1 + my_strlen(++pa); //  此处可以写为 ++pa 或者pa+1
//}
//
//int main()
//{
//	char a[] = "abcdef";
//	int ret = my_strlen(a);
//	printf("%d\n", ret);
//	return 0;
//}


//3.指针 - 指针  
//   地址减地址所得的是 数组中元素距离差值
//   只可大地址减小地址  这样所得的数值才是正数

//#include<assert.h>
//
//int my_strlen(const char *pa)
//{
//	assert(pa);
//	char *pb = pa;
//	while (*++pa)
//	{
//		;
//	}
//	return pa - pb;
//}
//
//int main()
//{
//	char a[] = "abcdef";
//	int ret = my_strlen(a);
//	printf("%d\n", ret);
//	return 0;
//}


//长度不受限制的字符串函数
//  strcpy
//  strcat
//  strcmp

//strcpy
// 源覆盖到目的地，只是把'\0'也一同覆盖过去。
//如果目的地的元素比源多，那么源也只是到'\0'一同复制过去，目的地超出的元素不会自动填补成'\0'

//int main()
//{
//	char a1[] = { "abcdef" };
//	char a2[] = { "bit" };
//	strcpy(a1, a2); // 将a2的内容完全覆盖在a1中，且a1打印出来的内容和a2相同
//	printf("%s\n", a1);
//	return 0;
//}



//  自创strcpy法

//#include<assert.h>
//#include<string.h>
//
//char *my_strcpy(char *b1, const char *b2)
//{
//	assert(b1 != NULL);
//	assert(b2 != NULL);
//	char *ret = b1; // ret指向数组首元素地址，虽然数组内容被覆盖，但是 *ret 指向的仍是数组首元素地址。所以到时候返回的内容不受影响


//	//拷贝b2指向的字符串到b1指向的空间，包含'\0'
//
//	while (*b1++ = *b2++)//经过最终简化，b1和b2即在往后走，又在检测是否遇见\0。当遇见'\0'时，也会从b2中传去b1。
//		                 //当*b1='\0'时，即'\0'= 0，当遇见0的时候就不循环
//
//
//	//while (*b2 != '\0')  //当指针b2指向\0时，将不再循环。所以\0并没有放进b1中
//	{
//		;
//		//*b1++ = *b2++;
//		//下面b1、b2自加，简化成*b1++ = *b2++;
//		//b1++;
//		//b2++;
//	}
//	//*b1 = *b2; //  将'\0'放入b1中
//
//	//返回目的空间的起始地址
//	return ret;
//}
//
//int main()
//{
//	char a1[] = { "abcedf" };
//	char a2[] = { "bit" };
//	printf("%s\n",my_strcpy(a1, a2));
//	return 0;
//}


//strcat  在字符串后面追加内容
//strcat(a,b)   a的数组内容要足够大，且有足够大的空间容纳b的内容。a是目的地，b是源
//且在追加的时候，会将源b的'\0'一同追加去目的地a
//strcat(a,a) 无法实现自己给自己追加

//使用库strcat
//int main()
//{
//	char a1[30] = { "abcedf\0xxxxxxxxxx" };
//	char a2[] = { "bit" };
//	strcat(a1, a2); //a1内部 abcdefbit\0xxxxxxx
//	printf("%s", a1);// abcdefbit
//	return 0;
//}




//自创strcat
//#include<assert.h>
//#include<string.h>
//
//my_strcat(char *b1, const char *b2)
//{
//	char *ret = b1;
//	assert(b1 != NULL&&b2 != NULL);
//	//1.找到目的字符串的'\0'
//	while (*b1 != '\0')
//	{
//		b1++;
//	}
//	//2.追加
//	while (*b1++ = *b2++)
//	{
//		;
//	}
//	return ret;
//}
//
//int main()
//{
//	char a1[30] = { "abcdef" };
//	char a2[] = { "bit" };
//	//my_strcat(a1, a2);
//	printf("%s\n", my_strcat(a1, a2));
//	return 0;
//}
