
### centos ImportError: No module named _sqlite3

	Traceback (most recent call last):
	  File "test.py", line 1, in <module>
	    import db
	  File "/data/hkstock/stis/run/log/process/db.py", line 2, in <module>
	    import sqlite3
	  File "/usr/local/lib/python2.7/sqlite3/__init__.py", line 24, in <module>
	    from dbapi2 import *
	  File "/usr/local/lib/python2.7/sqlite3/dbapi2.py", line 28, in <module>
	    from _sqlite3 import *
	ImportError: No module named _sqlite3

���ֵ�ԭ����û��_sqlite3����ڲ��⣬����ʹ��find �������֮���֣�
	
	find / -name _sqlite3.so
	/usr/usr/lib/python2.6/lib-dynload/_sqlite3.so
	/usr/local/service/python2.7/lib/python2.7/lib-dynload/_sqlite3.so
	/usr/lib64/python2.6/lib-dynload/_sqlite3.so
	
Ȼ�󽫣�
	
	cp /usr/local/service/python2.7/lib/python2.7/lib-dynload/_sqlite3.so /usr/local/lib/python2.7/sqlite3/
	
��������������������ĸ�Сʱ��ԭ������Ϊ���ҵ�һ�β����������ģ�

	cp /usr/usr/lib/python2.6/lib-dynload/_sqlite3.so /usr/local/lib/python2.7/sqlite3/
	
Ȼ�������ֵ�bug��

1. ����ʹ��sqlalchemy���в�����
2. �ַ���ʾ��ȫ��

��һ�����⣬�������ֱ���滻��sqlalchemy��ʹ��ԭ��sqlite3ִ��
���ǵڶ������⣬�޷���������շ���[stackoverflow](http://stackoverflow.com/questions/11394013/problems-with-python-2-7-3-on-centos-with-sqlite3-module/34432084#34432084)
����������Լ�ʹ�õ����⣬û��ʹ��find ������ֱ�ӽ�2.6 �µ�copy��ȥ��

