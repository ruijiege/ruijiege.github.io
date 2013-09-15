#  Join Operations in MYSQL

###Difference Between Equal Join and Natural Join in Mysql###
In mysql, *FROM* clause do a cross product between the tables in *FROM* clause. *WHERE* clause add a condition to the query. Tuples only satisfy these conditions can be selected from the cross product table. So, *FROM* \+ *WHERE* clause is equal-join. In mysql:

~~~mysql
SELECT *
FROM table1 T1,table2 T2
WHERE T1.id=T2.id;
~~~

A natural join is a type of equi-join where the join predicate arises implicitly by comparing all columns in both tables that have the same column-names in the joined tables. The resulting joined table contains only one column for each pair of equally named columns. In mysql:

    SELECT *
    FROM table1 T1 natural join table2 T2;

###Inner Join and Outer Join###

{% highlight java %}
//commints
public static void main(String[] args){
  int[] a={1,2,3,4,5,6};
  return;
}
{% endhighlight %}
