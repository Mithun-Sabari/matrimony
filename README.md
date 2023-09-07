# matrimony
#A app that finds us bride or groom based on our filters
import sqlite3
connection=sqlite3.connect("Matrimony.db")
connection.execute("""DROP TABLE users;""")
sql_command="""CREATE TABLE users(id INTEGER PRIMARY KEY,name VARCHAR(20),age INTEGER(2),gender CHAR(1),DOB DATE,religion VARCHAR(15),salary INTEGER,occupation VARCHAR(20),email VARCHAR(20));""“
connection.execute(sql_command)
connection.commit()
connection.execute("INSERT INTO users(id,name,age,gender ,DOB,religion ,salary,occupation,email) VALUES(?,?,?,?,?,?,?,?,?)",(1,"JAI",20,'M',"2002-08-09","HINDU",20000,"VENDOR","john@gmail.com"))
connection.execute("INSERT INTO users (id, name, age, gender ,DOB ,religion, salary,occupation,email)VALUES(?,?,?,?,?,?,?,?,?)",(2,"TOM",25,'M',"1997-12-14“ ,"CHRISTIAN“ ,50000, "ENGINEER", "tom@gmail.com"))
connection.execute("INSERT INTO users(id,name,age,gender,DOB,religion, salary,occupation,email)VALUES(?,?,?,?,?,?,?,?,?)",(3,"KELLY",23,'F',"1999-10-22","CHRISTIAN",35000,"NURSE","kelly@gmail.com"))
connection.execute("INSERT INTO users(id,name,age,gender,DOB,religion,salary ,occupation,email)VALUES(?,?,?,?,?,?,?,?,?)",(4,"BABAR",26,'M',"1996-05-13“ ,"MUSLIM",45000,"VENDOR","babar@gmail.com"))
connection.execute("INSERT INTO users(id,name,age,gender,DOB, religion,salary,occupation,email)VALUES(?,?,?,?,?,?,?,?,?)",(5,"PRIYA",24,'F',"1998-05-06","HINDU",80000,"DOCTOR","priya@gmail.com"))
connection.execute("INSERT INTO users(id,name,age,gender,DOB ,religion, salary,occupation,email)VALUES(?,?,?,?,?,?,?,?,?)",(6,"SMITH",29,'M',"1993-11-13","CHRISTIAN",60000,"TEACHER","smith@gmail.com"))
connection.execute("INSERT INTO users(id,name,age,gender,DOB,religion, salary,occupation,email)VALUES(?,?,?,?,?,?,?,?,?)",(7,"ROSE",34,'F',"1988-02-04","CHRISTIAN",0,"NONE","rose@gmail.com"))
connection.execute("INSERT INTO users(id,name,age,gender,DOB, religion, salary,occupation,email)VALUES(?,?,?,?,?,?,?,?,?)",(8,"MITHUN",22,'M',"2000-05-12","HINDU",65000,"ENGINEER","mithun@gmail.com"))
connection.execute("INSERT INTO users(id,name,age,gender,DOB , religion,salary,occupation,email)VALUES(?,?,?,?,?,?,?,?,?)",(9,"NISHA",26,'F',"1996-11-07","HINDU",20000,"CLERK","nisha@gmail.com"))
connection.execute("INSERT INTO users(id,name,age,gender,DOB ,religion,salary,occupation,email)VALUES(?,?,?,?,?,?,?,?,?)",(10,"FAHEEMA",19,'F',"2003-09-08","MUSLIM",70000,"ENGINEER","faheema2gmail.com"))
connection.commit()
cursor=connection.execute("SELECT id,name,age,gender,DOB , religion,salary,occupation,email FROM users")
print("id,name,age,gender,DOB,religion,salary,occupation,email\n")
for row in cursor:    print(row[0],row[1],row[2],row[3],row[4],row[5],row[6],row[7],row[8])
connection.close()

