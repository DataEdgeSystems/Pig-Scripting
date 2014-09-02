Pig-Scripting
=============

A = LOAD '/home/cloudera/student.txt' Using PigStorage AS (student:chararray, a2:int);



--DUMP A;



B = LOAD '/home/cloudera/results.txt' Using PigStorage AS (b1:int, result:chararray);



--DUMP B;



C = JOIN A BY a2, B BY b1;



--DUMP C;



D = FOREACH C generate student, result;



--DUMP D;



E = FILTER D BY result == 'pass';



DUMP E;