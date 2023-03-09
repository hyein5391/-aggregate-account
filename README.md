![합집합 차집합 교집합 전체집합](https://user-images.githubusercontent.com/110071838/223899255-446a0650-72fb-40ce-88b2-026434c3c4d5.jpg)


create table tblAll(
 id char(10) primary key
)

create table tblA(
 id char(10)
)

create table tblB(
 id char(10)
)

insert tblAll values('c1')
insert tblAll values('c2')
insert tblAll values('c3')
insert tblAll values('c4')
insert tblAll values('c5')

insert tblA values('c1')
insert tblA values('c2')
insert tblA values('c3')

insert tblB values('c3')
insert tblB values('c4')


/*교집합*/
select * from tblAll
where id in (select id from tblA) and
          id in (select id from tblB)
        
/*합집합*/ 
select * from tblAll
where id in (select id from tblA) or
          id in (select id from tblB)
         
/*여집합*/ 
select * from tblAll
where not (id in (select id from tblA) or
          id in (select id from tblB))  
        
/*차집합*/ 
select * from tblAll
where id  in (select id from tblA) and
          id not in (select id from tblB)
