# 实时时钟(RTC)

## 概述

RTC是用来计时的单元，在设置时间后具备计时功能。  
**注意** RTC模块仅当 PLL0 使能,并且 CPU 频率大于 30MHz 时使用

## 功能描述

RTC 模块具有以下功能：

- 获取当前日期时刻
- 设置当前日期时刻

## API参考

对应的头文件 `rtc.h`

为用户提供以下接口

- rtc\_init

- rtc\_timer\_set

- rtc\_timer\_get

### rtc\_init

#### 描述

初始化RTC。

#### 函数原型

```c
int rtc_init(void)
```

#### 参数

无。

#### 返回值

| 返回值 | 描述 |
| :----  | :----|
| 0      | 成功 |
| 非0    | 失败 |

### rtc\_timer\_set

#### 描述

设置日期时间。

#### 函数原型

```c
int rtc_timer_set(int year, int month, int day, int hour, int minute, int second)
```

#### 参数

| 参数名称     |   描述     |  输入输出  |
| :--------   | :--------- | :-------- |
| year        | 年         | 输入       |
| month       | 月         | 输入       |
| day         | 日         | 输入       |
| hour        | 时         | 输入       |
| minute      | 分         | 输入       |
| second      | 秒         | 输入       |

#### 返回值

无

### rtc\_timer\_get

#### 描述

获取日期时间。

#### 函数原型

```c
int rtc_timer_get(int *year, int *month, int *day, int *hour, int *minute, int *second)
```

#### 参数

| 参数名称     |   描述     |  输入输出  |
| :--------   | :--------- | :-------- |
| year        | 年         | 输出       |
| month       | 月         | 输出       |
| day         | 日         | 输出       |
| hour        | 时         | 输出       |
| minute      | 分         | 输出       |
| second      | 秒         | 输出       |

#### 返回值

| 返回值 | 描述 |
| :----  | :----|
| 0      | 成功 |
| 非0    | 失败 |

### 举例

```c
rtc_init();
rtc_timer_set(2018, 9, 12, 23, 30, 29);
int year;
int month;
int day;
int hour;
int minute;
int second;
rtc_timer_get(&year, &month, &day, &hour, &minute, &second);
printf("%4d-%d-%d %d:%d:%d\n", year, month, day, hour, minute, second);
```