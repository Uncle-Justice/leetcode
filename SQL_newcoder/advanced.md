### SQL1 

https://www.nowcoder.com/practice/5d2a42bfaa134479afb9fffd9eee970c?tpId=240&tqId=2221797&ru=/ta/sql-advanced&qru=/ta/sql-advanced/question-ranking

- 就是insert into 后面直接接表名

- values 后面加括号，括号里面放数据

```SQL
insert into exam_record
values 
(NULL,1001,9001,'2021-9-1 22:11:12','2021-9-1 23:01:12',90),
(NULL,1002,9002,'2021-9-4 7:1:2',NULL,NULL);
```

### SQL 2

如果是插入整张表，则不需要写VALUES，并且后面直接接一个**一般规则下的查询SQL语句**

```SQL
insert into exam_record_before_2021
    select null,uid,exam_id,start_time,submit_time,score from exam_record
where
    year(submit_time)<2021;
```

### SQL 3

这里exam_id的值已经在表中出现过一次，因此要想硬插入就应该使用replace

```SQL
replace into examination_info ( exam_id, tag, difficulty, duration, release_time)
values (9003,'SQL', 'hard', 90, '2021-01-01 00:00:00');
```

### SQL 4