Combine Two Tables
===

Table: `Person`
```
+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| PersonId    | int     |
| FirstName   | varchar |
| LastName    | varchar |
+-------------+---------+
```
`PersonId` is the primary key column for this table.

Table: `Address`

```
+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| AddressId   | int     |
| PersonId    | int     |
| City        | varchar |
| State       | varchar |
+-------------+---------+
```
AddressId is the primary key column for this table.

Write a SQL query for a report that provides the following information for each person in the Person table, regardless if there is an address for each of those people:

```
FirstName, LastName, City, State
```

## 解题思路

Person 主表 

Address 从表

left outer join 左外链

## SQL
```sql
# Write your MySQL query statement below
select person.FirstName, person.LastName, address.City, address.State from Person person left outer join Address address using(PersonId)
```