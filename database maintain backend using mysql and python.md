# you have to change table Name and header like "MATERIAL,QTY,MATERIAL_TYPE,DATED" ass per your MY SQL database and table

from tabulate import tabulate
import mysql.connector
con=mysql.connector.connect(host="localhost",user="root",password="115829955@Ak",database="sales_tools")

if con:
    print("MY SQL CONNECTED SUCCESSFULLY")
else:
    print("CONNECTION ERROR")


def insert():
    MATERIAL=input("Enter MATERIAL NAME:")
    QTY=input("Enter QUANTITY")
    MATERIAL_TYPE=input("Enter MATERIAL TYPE:")
    DATED=input("Enter DATE:")
    res=con.cursor()
    sql="insert into sales_data (MATERIAL,QTY,MATERIAL_TYPE,DATED) values (%s,%s,%s,%s)"
    user=(MATERIAL,QTY,MATERIAL_TYPE,DATED)
    res.execute(sql, user)
    con.commit()
    print("Data Insert Success")

def update():
    MATERIAL=input("Enter MATERIAL NAME:")
    QTY=input("Enter QUANTITY")
    MATERIAL_TYPE=input("Enter MATERIAL TYPE:")
    DATED=input("Enter DATE:")
    ID=input("Enter ID:")
    res=con.cursor()
    sql= "update sales_tools set MATERIAL=%s,QTY=%s,MATERIAL_TYPE=%s,DATED=%s where id=%s"
    user=(MATERIAL,QTY,MATERIAL_TYPE,DATED,ID)
    res.execute(sql, user)
    con.commit()
    print("Data update Success")

def view():
    ID=input("Enter ID:")
    res=con.cursor()
    sql="SELECT id,MATERIAL,QTY,MATERIAL_TYPE,DATED from sales_data"
    res.execute(sql,)
    result=res.fetchall()
    print(tabulate(result,headers=["ID","MATERIAL","QTY","MATERIAL_TYPE","DATED"]))

def delete():
    ID = input("Enter ID:")
    res = con.cursor()
    sql = "Delete from sales_tools where Id=%S"
    user = (ID,)
    res.execute(sql, user)
    con.commit()
    print("Data Deleted Success")

def Exit():
    quit()

while True:
    print("1.INSERT DATA")
    print("2.UPDATE DATA")
    print("3.VIEW DATA")
    print("4.DELETE DATA")
    print("5.QUIT DATABASE")
    action=int(input("Enter the Below Number to Access Data Base:"))

    if action==1:
        insert()

    elif action==2:
        update()

    elif action==3:
        view()

    elif action==4:
        delete()

    elif action==5:
        Exit()

    else:
        print("Error")
