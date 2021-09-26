# zifuchuan-miaoshu
项目描述
// strcmp       比较两字符串的大小

// 比较情况有 大于、小于、等于
// 如果字符串1小于字符串2   返回<0的值
// 如果字符串1大于字符串2   返回>0的值
// 如果字符串1等于字符串2   返回0


//int main()
//{
//	//若字符串中首元素相等，则两字符串自动比较下一个元素大小
//	char *p1 = "awcdef";
//	char *p2 = "aberty";
//	int ret = strcmp(p1, p2);//比较的是ASCII码值
//	printf("%d\n", ret);
//	return 0;
//}


//自创strcmp
//#include<assert.h>
//#include<string.h>
//
//int my_strcmp(const char *a1,const char *a2)
//{
//	assert(a1 != NULL&&a2 != NULL);
//	//比较
//	while (*a1 == *a2)
//	{
//		if (*a1 == *a2 == '\0')
//		{
//			return 0; // 相等
//		}
//		a1++;
//		a2++;
//	}
//	return(*a1 - *a2);  //这样写更加简便，不会给人误解返回的值是固定的
//
//	//if (*a1 > *a2)
//	//{
//	//	return 1;  // 大于
//	//}
//	//else
//	//{
//	//	return -1; // 小于
//	//}
//}
//
//int main()
//{
//	char *p1 = "abcdef";
//	char *p2 = "qwerty";
//	int ret = my_strcmp(p1, p2);
//	printf("%d\n", ret);
//	return 0;
//}
