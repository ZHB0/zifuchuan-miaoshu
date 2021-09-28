# zifuchuan-miaoshu
项目描述


//  strstr   查找字符串 寻找的是地址

//  strstr(a,b)   a相当于库，b相当于搜索的内容
//  如果b的内容在a中找到，那么将会输出是被找到的地址
//  通过指针解引用即可打印出输出的内容

// NULL  --  空指针
// NUL  Null - '\0'


//#include<string.h>
//
//int main()
//{
//	char p1[] = "abccddefghij";
//	char p2[] = "abccddef";
//	char *ret = strstr(p1, p2);
//	if (ret == NULL)
//	{
//		printf("子串不存在\n");
//	}
//	else
//	{
//		printf("%s\n", ret);
//	}
//	return 0;
//}




//  自创 strstr

//#include<assert.h>
//#include<string.h>
//
//char* my_strstr(char *b1, char *b2)
//{
//	assert(b1, b2);
//	char *c1 = b1;
//	char *c2 = b2;
//	char *cur = b1;
//	if (*b2 == '\0')
//	{
//		return (char*)b1;
//	}
//	while (*cur)
//	{
//		c1 = cur;
//		c2 = (char*)b2;
//		//while ((*c1 != '\0') && (*c2 != '\0') && (*c1 == *c2))
//		//  经过简化
//		while (*c1 && *c2 && (*c1 == *c2))
//		{
//			c1++; 
//			c2++;
//		}
//		if (*c2 == '\0')
//		{
//			return cur; // 找到字符串
//		}
//		cur++;
//	}
//	return NULL; // 找不到字符串
//}
//
//int main()
//{
//	char a1[] = "abcccddefghij";
//	char a2[] = "ccc";
//	char *ret = my_strstr(a1, a2);
//	printf("%s\n", ret);
//	return 0;
//}









//  strtok  

//#include<string.h>
//
//int main()
//{
//	//192.168.31.121   这串里面的分隔符是 .
//	//192 168 31 121  - strtok
//
//	// zpw@bitedu.tech  这串里面的分隔符是 @ .
//	// zpw bitedu tech
//
//	char arr[] = "192.168.31.121";
//	char *p = ".";
//
//	//char arr[] = "zpw@bitedu.tech";
//	//char *p = "@.";
//
//	char buf[1024] = { 0 };
//	strcpy(buf, arr);
//
//	char *ret = NULL;
//
//	for (ret = strtok(arr, p); ret != NULL; ret = strtok(NULL, p))
//	{
//		printf("%s\n", ret);
//	}
//	return 0;
//}






//  strerror   错误报告函数

//错误码    错误信息
// 0 -      No error
// 1 -      Operation not permitted
// 2 -      No such file or directory
// ... 

//#include<errno.h>
//#include<string.h>
//#include<stdio.h>
//
//int main()
//{
//	// errno 是一个全局的错误码的变量
//	//当 c语言的库函数在执行过程中，发生错误，就会把对应的错误码，赋值到errno中
//	//char *str = strerror(errno);
//	//printf("%s\n", str);
//
//	FILE *pf = fopen("test.txt", "r");
//
//	if (pf == NULL)
//	{
//		printf("%s\n", strerror(errno));
//	}
//	else
//	{
//		printf("open file success\n");
//	}
//	return 0;
//}
