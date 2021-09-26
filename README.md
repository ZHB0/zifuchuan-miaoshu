# zifuchuan-miaoshu
项目描述
//  长度受限制的字符串函数介绍

//  strncpy
//  strncat
//  strncmp



// strncpy
//  strncpy(a,b,数值)   
//数值是指定源要到目的地的字节数，移过去不带'\0'
// 如果指定源的字节数大于源本身的元素数量，当拷贝过去目的地的时候，多余的字节数用'\0'


//int main()
//{
//	char a1[10] = "abcdef";
//	//char a2[] = "bit";
//	char a2[] = "hello bit";
//	strncpy(a1, a2, 9);
//	printf("%s\n", a1);
//	return 0;
//}

// 自创 strncpy

//#include<assert.h>
//
//char* my_strncpy(char *b1, const char *b2, int k)
//{
//	assert(b1&&b2);
//	char *ret = b1;
//	int i = 0;
//	while (*b1 != '\0')
//	{
//		for (i = 0; i < k; i++)
//		{
//			*b1++ = *(b2 + i);
//		}
//		break;
//	}
//	return ret;
//}
//
//int main()
//{
//	char a1[10] = "abcdef";
//	char a2[] = "hello bit";
//	int ret = my_strncpy(a1, a2, 9);
//	printf("%s\n", ret);
//	return 0;
//}






// strncat  追加指定字节数
// strncat(a,b,数值)
// 源指定字节数追加到目的地，'\0'在指定字节数后也一同追加到目标地中
// 如果指定源的字节数大于源本身的元素数量，当拷贝过去目的地的时候，
//只会将源中的元素内容全部追加到目的地，当元素全部追加完以后，最后加个'\0'就结束追加
// 且strncat可以将空格传入目的地

//int main()
//{
//	char a1[30] = "hello\0xxxxxxx";
//	char a2[] = "bit world";
//	//strncat(a1, a2, 3);
//	strncat(a1, a2, 4);
//	printf("%s\n", a1);  // hellowor
//	return 0;
//}





// 自创 strncat

#include<assert.h>

char* my_strncat(char *b1, const char *b2, int k)
{
	assert(b1&&b2);
	char *ret = b1;
	int i = 0;
	while (*b1 != '\0')
	{
		*b1++;
	}
	for (i = 0; i <= k; i++)
	{
		*b1++ = *b2++;
	}
	*b1 = '\0';
	return ret;
}

int main()
{
	char a1[30] = "hello\0xxxxxxx";
	char a2[] = "bit hello";
	int ret = my_strncat(a1, a2, 3);
	printf("%s\n", ret);
	return 0;
}
