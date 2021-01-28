# 字符串处理练习

## 入口

```java
package utilTest;

import java.util.Scanner;

public class UtilTest {

	public static void main(String[] args) {

		// 传入一个字符串
		System.out.println("请输入需要处理的字符串：");
		Scanner s = new Scanner(System.in);
		String Input = s.next();

		// 判断字符串是否为空（包括null和空字符串和空格），返回boolean值
		System.out.println("1.字符串是否为空：");
		System.out.println(UtilString.IsNull(Input));

		// 返回字符串的前面4位
		System.out.println("2.字符串的前4位是：");
		System.out.println(UtilString.FrontFour(Input));

		// 返回字符串的后面4位
		System.out.println("3.字符串的后4位是：");
		System.out.println(UtilString.BackFour(Input));

		// 截取前面4位，后面再拼接0，总共返回12位
		System.out.println("4.字符串的前4位拼接0至12位后是：");
		System.out.println(UtilString.ZeroFour(Input));

		// 返回字符串倒序后的新字符串
		System.out.println("5.字符串倒序后是：");
		System.out.println(UtilString.FlashBack(Input));

		// 返回字符串按分隔符分割后的数组,比如传入aa,bb,cc，返回分割后的数组
		System.out.println("请输入想要分割的字符串（以分隔符隔开）：");
		String Input2 = s.next();
		System.out.println("6.字符串按分隔符分割后的数组是：");

		for (String string : UtilString.Array(Input2)) {

			System.out.print(string + "/");
		}

		if (s != null) {
			s.close();
		}

	}

}


```

```java
package utilTest;

public class UtilString {

	public static boolean IsNull(String str) {

		if (str == null || str.trim().length() == 0) {

			return true;
		} else {
			return false;
		}

	}

	public static String FrontFour(String str) {

		if (IsNull(str) || str.length() < 4) {
			return "字符串位数不足！";
		} else {
			return str.substring(0, 4);
		}

	}

	// 注意提高代码复用率！
	// 每一项都要注意空指针异常的发生！
	public static String BackFour(String str) {

		if (IsNull(str) || str.length() < 4) {
			return "字符串位数不足！";
		} else {
			return str.substring(str.length() - 4);
		}
	}

	public static String ZeroFour(String str) {

		return String.format("%s00000000", FrontFour(str));

	}

	public static StringBuffer FlashBack(String str) {

		IsNull(str);

		StringBuffer fb = new StringBuffer(str);

		return fb.reverse();

	}

	public static String[] Array(String str) {

		IsNull(str);

		String[] arr = str.split(",");

		return arr;

	}

	public static String Eight(String str) {
		if (IsNull(str) || str.length() > 8) {

			return "数字输入异常";

		} else {

			int n = 8 - str.length();

			for (int i = 0; i < n; i++) {

				str = "0" + str;

			}
			return str;
		}

	}

}

```



## 方法类

```java
package utilTest;

public class UtilString {

	public static boolean IsNull(String str) {

		if (str == null || str.trim().length() == 0) {

			return true;
		} else {
			return false;
		}

	}

	public static String FrontFour(String str) {

		if (IsNull(str) || str.length() < 4) {
			return "字符串位数不足！";
		} else {
			return str.substring(0, 4);
		}

	}

	// 注意提高代码复用率！
	// 每一项都要注意空指针异常的发生！
	public static String BackFour(String str) {

		if (IsNull(str) || str.length() < 4) {
			return "字符串位数不足！";
		} else {
			return str.substring(str.length() - 4);
		}
	}

	public static String ZeroFour(String str) {

		return String.format("%s00000000", FrontFour(str));

	}

	public static StringBuffer FlashBack(String str) {

		IsNull(str);

		StringBuffer fb = new StringBuffer(str);

		return fb.reverse();

	}

	public static String[] Array(String str) {

		IsNull(str);

		String[] arr = str.split(",");

		return arr;

	}

	public static String Eight(String str) {
		if (IsNull(str) || str.length() > 8) {

			return "数字输入异常";

		} else {

			int n = 8 - str.length();

			for (int i = 0; i < n; i++) {

				str = "0" + str;

			}
			return str;
		}

	}

}

```

