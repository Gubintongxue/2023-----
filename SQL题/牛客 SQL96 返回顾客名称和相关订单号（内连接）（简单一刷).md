# 题目

![image-20230416163251796](image/image-20230416163251796.png)



# 我的题解

## 思路

使用内连接，排序



```sql
select c.cust_name, o.order_num 
from Customers c 
inner join Orders o 
on c.cust_id = o.cust_id Order by cust_name asc;
```



结果正确

![image-20230416163416356](image/image-20230416163416356.png)



# 其他解法



分为显示内连接和 隐式内连接（where)

## 方法一

就是使用 `where` 进行简单的联结

```sql
select cust_name,order_num
from Customers,Orders
where Customers.cust_id=Orders.cust_id
order by cust_name,order_num;


```

## 方法二

使用内联结



```sql
select cust_name,order_num
from Customers
INNER JOIN Orders ON Orders.cust_id=Customers.cust_id
order by cust_name,order_num;

```

























