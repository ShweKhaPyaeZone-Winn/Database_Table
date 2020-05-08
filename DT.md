# Creating Database and Tables

**How to create database!**
Database ကို ဘယ်လို တည်ဆောက်ကြမလဲ

MySQL နဲ့ အလုပ်တစ်ခုပြုလုပ်မည်ဆိုပါက သက်ဆိုင်ရာ database တစ်ခု တည်ဆောက်ရန်လိုအပ်သည်
database တစ်ခုကို အရင်မတည်ဆောက်ပဲ  မည်သည့်အလုပ်မှ လုပ်လို့ ရမည် မဟုတ်ပါ

အရင်ဆုံး Cloud9 installation ကနေ ရေးမဲ့သူဆိုရင် container တစ်ခုဆောက်ပြီး mysql-ctl cli နဲ့ MySQL ထဲ ၀င်ထားပါ
Mac installation ကနေ ရေးမဲ့သူဆိုရင် MySQL Command Line Client ထဲ၀င်ပြီး password နှိပ်လိုက်ပါ
```sh
mysql>show databases;
```
လို့ ရိုက်နှိပ်ပြီး ရှိပြီးသား database တွေကို ထုတ်ကြည့်နိုင်ပါတယ်
+--------------------+
| Database           |
+--------------------+
| classicmodels      |
| information_schema |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
5 rows in set (0.00 sec)

![show](./images/Capture13.png)

အခု စာအုပ်တွေနဲ့ ပက်သက်တဲ့ databaseတစ်ခု တည်ဆောက်ကြည့်ကြရအောင်

```sh
mysql>CREATE database books_db;
Query OK, 1 row affected (0.12 sec)
```
ဆိုပြီး ရိုက်လိုက်ရင် book databaseတစ်ခု တည်ဆောက်ပြီး သွားပါပြီ
![create](./images/Capture14.png)

အခု database ဆောက်ပြီးသွားပြီဆိုတော့ books_db ထဲမှာ သိမ်းမည့် data တွေကို ထည့်ရန် **table**တစ်ခု တည်ဆောက်ပါ့မယ်

database ကို တည်ဆောက်ပြီးပေမဲ့ ထို database နဲ့ သက်ဆိုင်တဲ့ table ဆောက်ဖို့
```sh
mysql>USE books_db;
Database changed
```
ဆိုပြီး ခေါ်သုံးဖို့ လိုအပ်ပါတယ်

table မှာ row နဲ့ column ပါ၀င်ပါတယ်
ထို့ကြောင့် MySQL မှာ table ဆောက်ရင်လဲ row နဲ့ column မြဖစ်မနေ ပါရပါမယ်

အရင်ဆုံး table တစ်ခု တည်ဆောက်ပါမယ်

```sh
mysql> CREATE table books(Name VARCHAR(20),Price INT);
Query OK, 0 rows affected (4.72 sec)
```
အခု table ရဲ့ column တွေကို တည်ဆောက်ပြီးပါပြီ

Name ဆိုတာ ပါ၀င်တဲ့ စာအုပ်ရဲ့ နာမည်ကို ရည်ညွှန်းပြီး
Price က ထိုစာအုပ်ရဲ့ စျေးနှုန်းကို ပြောတာပါ

Name က alphabet တွေနဲ့ ဖွဲ့စည်းထားသောကြောင့် VARCHAR variable ကို အသုံးပြုပြီး 20 ဆိုတာ အများဆုံးရှိရမဲ့ စာလုံးအရေအတွက်ကို ဖော်ပြတာ ဖြစ်ပါတယ်
Price က  နံပါတ်တွေနဲ့ ေရးရသောကြောင့် integer variable ကိူ အသုံးပြုပါတယ်

table ရဲ့ row မှာ data တွေကို ထည့်ပါမယ်

| Name | Price |
| ------ | ------ |
| 10% Happier | 25$ |
| Fake book | 30$ |
| Lincoln In The Bardo | 12$ |

```sh
mysql> INSERT INTO books(Name,Price)
    -> VALUES('10% Happier',25),
    -> ('Fake book',30),
    -> ('Lincoln In The Bardo',12);
Query OK, 3 rows affected (0.26 sec)
Records: 3  Duplicates: 0  Warnings: 0
```

ဆိုပြီး ရေးပြီးရင် အောက်ပါပုံအတိုင်း ထွက်လာပါမည်
![table](./images/Capture15.png)


