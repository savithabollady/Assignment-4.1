df1 = data.frame(CustId = c(1:6), Product = c(rep("TV", 3), rep("Radio", 3)))
df2 = data.frame(CustId = c(2, 4, 6), State = c(rep("Texas", 2), rep("NYC", 1)))
df1 #left table
df2 #right table
For the above given data frames and tables perform the following operations:
1. Return only the rows in which the left table have match
2. Return all rows from both tables, join records from the left which have matching keys in the right table.

=====ANSWERS=======

CODE: (R Script)
CustId<-(c(1:6))
Product <-c(rep("TV", 3), rep("Radio", 3))
CustId  
Product          
df1 <- data.frame(CustId, Product)
str(df1)
CustId<-(c(2,4,6))
Product <-c(rep("Texas", 2), rep("NYC", 1))
CustId  
Product          
df2 <- data.frame(CustId, Product)
str(df2)
df<-merge(x=df1,y=df2,by="CustId")
str(df)
df3<-merge(x=df1,y=df2,by="CustId",all=TRUE)

CONSOLE: 
> CustId<-(c(1:6))
> Product <-c(rep("TV", 3), rep("Radio", 3))
> CustId  
[1] 1 2 3 4 5 6
> Product          
[1] "TV"    "TV"    "TV"    "Radio" "Radio" "Radio"
> df1 <- data.frame(CustId, Product)
> str(df1)
'data.frame':	6 obs. of  2 variables:
 $ CustId : int  1 2 3 4 5 6
 $ Product: Factor w/ 2 levels "Radio","TV": 2 2 2 1 1 1
> CustId<-(c(2,4,6))
> Product <-c(rep("Texas", 2), rep("NYC", 1))
> CustId  
[1] 2 4 6
> Product          
[1] "Texas" "Texas" "NYC"  
> df2 <- data.frame(CustId, Product)
> str(df2)
'data.frame':	3 obs. of  2 variables:
 $ CustId : num  2 4 6
 $ Product: Factor w/ 2 levels "NYC","Texas": 2 2 1
> df<-merge(x=df1,y=df2,by="CustId")
> str(df)
'data.frame':	3 obs. of  3 variables:
 $ CustId   : int  2 4 6
 $ Product.x: Factor w/ 2 levels "Radio","TV": 2 1 1
 $ Product.y: Factor w/ 2 levels "NYC","Texas": 2 2 1
> df3<-merge(x=df1,y=df2,by="CustId",all=TRUE)
