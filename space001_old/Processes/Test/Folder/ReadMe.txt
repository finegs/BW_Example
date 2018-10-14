1. StartNetworkServer
  D:\Work> C:\Java\jdk1.8.0_151\db\bin\startNetworkServer -h 0.0.0.0 -p 1527
  D:\Work> C:\Java\jdk1.8.0_151\db\bin\startNetworkServer -h 0.0.0.0 -p 1528
2. Connect
  D:\Work> C:\Java\jdk1.8.0_151\db\bin\ij 
   ij>connect 'jdbc:derby://127.0.0.1:1527/SourceDB;create=true;user=user';
   ij>connect 'jdbc:derby://127.0.0.1:1528/TargetDB;create=true;user=user';
3. Check  Table Existence
   ij>select a.tablename,b.schemaname 
       from sys.systables a, sys.sysschemas b 
       where b.schemaname = 'AA' and 
                    b.schemaid = a.schemaid;
4. Create Table
   ij> create table TB_01 ( aaa varchar(1024) not null, bbb varchar(512), ccc int, primary key (aaa));
5. Drop Table
   ij> drop table TB_01;
6. Show Connection

  ij(CONNECTION1)> show connections;
  CONNECTION0 -   jdbc:derby://127.0.0.1:1527/TargetDB;create=true
  CONNECTION1* -  jdbc:derby://127.0.0.1:1527/SourceDB;create=true
7. Disconnect 
   ij>disconnect connection0;

8. Help
   ij>help;

9>