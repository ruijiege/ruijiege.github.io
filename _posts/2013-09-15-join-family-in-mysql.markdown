---
layout: post
title:  Join Operations in MYSQL
date: 2013-09-15 17:33:00
categories: jekyll update
---

###Difference Between Equal Join and Natural Join in Mysql###
In mysql, *FROM* clause do a cross product between the tables in *FROM* 
clause. *WHERE* clause add a condition to the query. Tuples only satisfy 
these conditions can be selected from the cross product table. So, *FROM*
\+ *WHERE* clause is equal-join. In mysql:

{% highlight mysql %}
SELECT *
FROM table1 T1,table2 T2
WHERE T1.id=T2.id;
{% endhighlight %}

A natural join is a type of equi-join where the join predicate arises 
implicitly by comparing all columns in both tables that have the same 
column-names in the joined tables. The resulting joined table contains 
only one column for each pair of equally named columns. In mysql:

{% highlight mysql %}
SELECT *
FROM table1 T1 natural join table2 T2;
{% endhighlight %}

###Inner Join, Self Join and Outer Join###
1.  Inner Join

    {% highlight mysql %}
    SELECT *
    FROM table1 T1 inner join  table2 T2
    on T1.id=T2.id;
    {% endhighlight %}


    eqlals


    {% highlight mysql %}
    SELECT *
    FROM table1 T1 join  table2 T2 using(id);
    {% endhighlight %}


    equals


    {% highlight mysql %}
    SELECT *
    FROM table1 T1, table2 T2
    Where T1.id=T2.id;
    {% endhighlight %}

2.  Self Join
    The purpose of self join is find a pair of atrributes satisfy a condition,
    the two attributes are within the same table. There is one thing we should
    care about: use '<' to eliminate the duplicated tuples.

3.  Outer Join
    Mysql don't support full outer join, we can use left outer join, right outer 
    join and union to implements full outer join. For example:

    {% highlight mysql %}
    SELECT *
    FROM T1 full outer join T2 on T1.id=T2.id
    {% endhighlight %}


    equals


    {% highlight mysql%}
    SELECT *
    FROM T1 left outer join T2 on T1.id=T2.id
    Union
    SELECT *
    FROM T1 right outer join T2 on T1.id=T2.id
    {% endhighlight %}
