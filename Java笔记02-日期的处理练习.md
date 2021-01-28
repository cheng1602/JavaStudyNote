# 字符串处理练习

## 入口

```java
package dateUtil;

import java.util.Scanner;

public class DateUtilTest {

	public static void main(String[] args) {

		Scanner s = new Scanner(System.in);

		// 1.获取当前日期，并返回格式化成年月日时分秒的字符串
		System.out.println("1.当前的时间是：");
		System.out.println(DateUtil.NowDate());

		// 2.传入两个日期字符串，返回这两个日期间隔多少天
		System.out.println("请输入日期一：（输入格式为：年-月-日）");
		String Input1 = s.next();
	
		System.out.println("请输入日期二：");
		String Input2 = s.next();
		
		if (Input1 == null || Input2 == null) {
			System.out.println("输入错误！");
		} else {
			System.out.println("日期一日期二间隔的天数为：");
			System.out.println(DateUtil.IntervalDays(Input1, Input2) + "天。");
		}

		if (s != null) {
			s.close();
		}

	}

}

```



## 方法类

```java
package dateUtil;

import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

public class DateUtil {

	public static String NowDate() {

		Date now = new Date();
		SimpleDateFormat sdf = new SimpleDateFormat("yyyy-mm-dd hh:mm:ss:SSS");

		return sdf.format(now);

	}

	public static long IntervalDays(String str1, String str2) {

		{
			SimpleDateFormat sdf = new SimpleDateFormat("yyyy-mm-dd");

			Date date1;
			Date date2;
			// 格式转化
			try {
				date1 = sdf.parse(str1);
				date2 = sdf.parse(str2);

			} catch (ParseException e) {

				throw new RuntimeException("日期转化错误");
			}

			// 计算间隔
			return absoluteValue(date2.getTime() - date1.getTime()) / (1000L * 3600L * 24L);

		}

	}

	// 取绝对值
	public static long absoluteValue(long l) {
		return (l < 0) ? -l : l;

	};

}

```

