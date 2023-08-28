# TO-EXTRACT-INFORMATION-OF-DATA-FROM-DATABASE
import sqlite3
book=sqlite3.connect("LIBRARY.db")
title=input("Book title:")
n=int(input("no.of copies:"))
cur=book.cursor()
cur.execute("select * from librarybooks where title=?",(title,))
result=cur.fetchall()
print(result)
cur.execute("select price from librarybooks where title=?",(title,))
results=cur.fetchone()

if result==None:
    print("no book available")
else:
    p=results[0]
    total=p*n
    print("total cost is :",total) 
book.close()
# C:\Users\aditri sharma\Downloads\assignment5sql.zip
# you can check database created in sqlstudio
