### SQL13

https://www.nowcoder.com/practice/0355033fc2244cdaa09b2bd6e794c762?tpId=199&tags=&title=&difficulty=0&judgeStatus=0&rp=0

这题如果用OR就会显得比较臃肿

答案的这种方法之前没怎么见过，要学会

```sql
select device_id ,gender, age, university, gpa
from user_profile
where university IN ("北京大学","复旦大学","山东大学");
```

### SQL 18

https://www.nowcoder.com/practice/009d8067d2df47fea429afe2e7b9de45?tpId=199&tags=&title=&difficulty=0&judgeStatus=0&rp=0

注意是group by不是groupby

而且group by可以按多个属性分组

```sql
select gender, university, count(gender), avg(active_days_within_30),
avg(question_cnt)
from user_profile
group by university, gender;
```

### SQL20

注意group by和order by的区别

```SQL
select university, avg(question_cnt)
from user_profile
group by university
order by avg(question_cnt) ASC;
```

### SQL22

https://www.nowcoder.com/practice/88aa923a9a674253b861a8fa56bac8e5?tpId=199&tqId=1975674&ru=/exam/oj&qru=/ta/sql-quick-study/question-ranking&sourceUrl=%2Fexam%2Foj

- distinct也可以在聚集函数中使用
- 实际上计算机会先运行from段，所以在from重命名后就应该在其他所有地方都使用新的名字。

```SQL
select university, count(question_id) / count(distinct a.device_id)
from question_practice_detail as a, user_profile as b
where a.device_id = b.device_id
group by university
order by count(question_id) / count(a.device_id);
```

### SQL23

https://www.nowcoder.com/practice/5400df085a034f88b2e17941ab338ee8?tpId=199&tqId=1975675&ru=/practice/979b1a5a16d44afaba5191b22152f64a&qru=/ta/sql-quick-study/question-ranking

要学会 join...on...的写法


```SQL
SELECT university,difficult_level,count(qp.question_id) /count(distinct qp.device_id) avg_answer_cnt
FROM question_practice_detail qp 
    left join user_profile u on qp.device_id=u.device_id
    left join question_detail qd on qp.question_id=qd.question_id  
group by university,difficult_level
```

### SQL25 

https://www.nowcoder.com/practice/979b1a5a16d44afaba5191b22152f64a?tpId=199&tqId=1975677&ru=/practice/5400df085a034f88b2e17941ab338ee8&qru=/ta/sql-quick-study/question-ranking

UNION会去重，UNION ALL不去重

```SQL
select device_id, gender, age, gpa
from user_profile
where university = '山东大学'
UNION ALL
select device_id, gender, age, gpa
from user_profile
where gender = 'male';
```

