# 编程题   
#### 1、求在有序数组中查找两个数的和为指定数   
题目：
输入一个已经按升序排序过的数组和一个数字，在数组中查找两个数，使得它们的和正好是输入的那个数字。要求时间复杂度是O(n)。如果有多对数字的和等于输入的数字，输出任意一对即可。例如输入数组1、2、4、7、11、15和数字15。由于4+11=15，因此输出4和11。   
分析：
此题目要求是时间复杂度为O(n)，意味着只能遍历一次数组。另外要充分利用该数组已经排序的特征。可以从2端同时遍历，对a[begin]+a[end]进行3种情况的考虑：1）大于给定和，则把end--。2）小于给定和，则把begin++。3）相等，则打印结果。   

####统计qq一天中每秒在线人数   
【问题】为了统计一天内QQ每秒的在线用户数量，每次一个用户下线时会生成一条记录到文件里：记录里有三个字段（上线时间，下线时间，用户名），时间以秒为单位。现在有一个文件包含了当天生成的N条记录（N很大），请设计一个算法根据N条记录统计出当天每秒在线用户的数量。(0<=上线时间& lt;下线时间<=24*3600)   
【思路】创建一个数组change[ 24*3600 ]用来记录一天中，每秒用户的变化情况，在第i秒上线一人change[ i ]++，在第i秒下线一人change[ i ] - -，change[ i ]若为正，说明这一秒上线人数大于下线人数，反之亦然。再创建一个online[ 24*3600 ]，用来记录每秒在线人数，online[ 0 ] = 0表示第0秒在线人数为0，计算方法为online[ n ] = online[ n-1 ] + change[ n ]  
