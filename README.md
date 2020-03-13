**Sqoop** : Sqoop is a tool designed to transfer data between Hadoop and relational database servers. It is used to import data from relational databases such as MySQL, Oracle to Hadoop HDFS, and export from Hadoop file system to relational databases. Sqoop uses MapReduce to import and export the data, which provides parallel operation as well as fault tolerance.

Here we uses the below tables to test sqoop-import and sqoop-export commands : 

```
mysql> desc orders;
+-------------------+-------------+------+-----+---------+----------------+
| Field             | Type        | Null | Key | Default | Extra          |
+-------------------+-------------+------+-----+---------+----------------+
| order_id          | int(11)     | NO   | PRI | NULL    | auto_increment |
| order_date        | datetime    | NO   |     | NULL    |                |
| order_customer_id | int(11)     | NO   |     | NULL    |                |
| order_status      | varchar(45) | NO   |     | NULL    |                |
+-------------------+-------------+------+-----+---------+----------------+
4 rows in set (0.00 sec)
```

```
mysql> desc order_items;
+--------------------------+------------+------+-----+---------+----------------+
| Field                    | Type       | Null | Key | Default | Extra          |
+--------------------------+------------+------+-----+---------+----------------+
| order_item_id            | int(11)    | NO   | PRI | NULL    | auto_increment |
| order_item_order_id      | int(11)    | NO   |     | NULL    |                |
| order_item_product_id    | int(11)    | NO   |     | NULL    |                |
| order_item_quantity      | tinyint(4) | NO   |     | NULL    |                |
| order_item_subtotal      | float      | NO   |     | NULL    |                |
| order_item_product_price | float      | NO   |     | NULL    |                |
+--------------------------+------------+------+-----+---------+----------------+
6 rows in set (0.00 sec)
```

```
mysql> desc flag;
+------------+----------+------+-----+---------+-------+
| Field      | Type     | Null | Key | Default | Extra |
+------------+----------+------+-----+---------+-------+
| country    | char(50) | NO   | PRI |         |       |
| landmass   | int(11)  | YES  |     | NULL    |       |
| area       | int(11)  | YES  |     | NULL    |       |
| zone       | int(11)  | YES  |     | NULL    |       |
| population | int(11)  | YES  |     | NULL    |       |
| language   | int(11)  | YES  |     | NULL    |       |
| relegion   | int(11)  | YES  |     | NULL    |       |
| bars       | int(11)  | YES  |     | NULL    |       |
| stripes    | int(11)  | YES  |     | NULL    |       |
| colors     | int(11)  | YES  |     | NULL    |       |
| red        | int(11)  | YES  |     | NULL    |       |
| green      | int(11)  | YES  |     | NULL    |       |
| blue       | int(11)  | YES  |     | NULL    |       |
| gold       | int(11)  | YES  |     | NULL    |       |
| white      | int(11)  | YES  |     | NULL    |       |
| black      | int(11)  | YES  |     | NULL    |       |
| orange     | int(11)  | YES  |     | NULL    |       |
| mainhue    | int(11)  | YES  |     | NULL    |       |
| circles    | int(11)  | YES  |     | NULL    |       |
| crosses    | int(11)  | YES  |     | NULL    |       |
| saltires   | int(11)  | YES  |     | NULL    |       |
| quarters   | int(11)  | YES  |     | NULL    |       |
| sunstars   | int(11)  | YES  |     | NULL    |       |
| crescent   | int(11)  | YES  |     | NULL    |       |
| triangle   | int(11)  | YES  |     | NULL    |       |
| icon       | int(11)  | YES  |     | NULL    |       |
| animate    | int(11)  | YES  |     | NULL    |       |
| text       | int(11)  | YES  |     | NULL    |       |
| topleft    | char(20) | YES  |     | NULL    |       |
| botright   | char(20) | YES  |     | NULL    |       |
+------------+----------+------+-----+---------+-------+
30 rows in set (0.03 sec)
```
