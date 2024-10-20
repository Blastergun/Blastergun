# 1.program to setup a simple data in MYSQLOPENSOURCE
!pip install mysqlclient
!pip install mysql-connector-python
import sys
import mysql.connector
import mysql.connector
from mysql.connector import Error
import pandas as vAR_pd
vAR_conn=""
vAR_conn=mysql.connector.connect(host="66.42.60.177",database ="dssaiai_lms_structure",user="dssaiai_struct_u",password="~z=wL1jg~Q4$",port=3306)
vAR_cursor=vAR_conn.cursor()
print('Cursor Opened')

##EXPORT form mySQL Database
vAR_Query = vAR_cursor.execute("SELECT * FROM dsai_ilms_course")
vAR_df=vAR_pd.DataFrame(vAR_cursor.fetchall(),columns=['index','course_id','course_name','course_original_id','is_demo','created_by','created_datetime','updated_by','updated_datetime'])
vAR_df.head()
#vAR_Query = vAR_cursor.execute("CREATE TABLE DSAI_EMPLOYEE (EMPID int, EMPFIRSTNAME varchar(255), EMPLASTNAME varchar(255), ADDRESS varchar(255),CITY varchar(255))")
vAR_Query = vAR_cursor.execute("INSERT INTO DSAI_EMPLOYEE VALUES (101,'John','Micheal','123 XYZ','ALABAMA')")
vAR_Query = vAR_cursor.execute("SELECT * FROM DSAI_EMPLOYEE")
vAR_df2 = vAR_pd.DataFrame(vAR_cursor.fetchall(),columns=['EMPID','EMPFIRSTNAME','EMPLASTNAME','ADDRESS','CITY'])
vAR_df2.head()
vAR_Query = vAR_cursor.execute("TRUNCATE TABLE DSAI_EMPLOYEE")
vAR_df2 =vAR_pd.DataFrame(vAR_cursor.fetchall(),columns=['EMPID','EMPFIRSTNAME','EMPLASTNAME','ADDRESS','CITY'])
vAR_df2.head()
vAR_Query = vAR_cursor.execute("DROP TABLE DSAI_EMPLOYEE")
vAR_df2 =vAR_pd.DataFrame(vAR_cursor.fetchall(),columns=['EMPID','EMPFIRSTNAME','EMPLASTNAME','ADDRESS','CITY'])
vAR_df2.head()
