```
bandit12@bandit:~$ ls
data.txt

bandit12@bandit:~$ mktemp -d
/tmp/tmp.hGj2Yzw1xd

bandit12@bandit:~$ cp data.txt /tmp/tmp.hGj2Yzw1xd
bandit12@bandit:~$ cd /tmp/tmp.hGj2Yzw1xd
bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ xxd -r data.txt > file1.bin
bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ ls
data.txt  file1.bin

bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ file file1.bin
file1.bin: gzip compressed data, was "data2.bin", last modified: Sun Oct 25 13:37:05 2026, max compression, from Unix, original size modulo 2^32 580
bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ mv file1.bin file1.gz
bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ ls
data.txt  file1.gz

bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ gunzip file1.gz
bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ ls
data.txt  file1

bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ file file1
file1: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ mv file1 file1.bz2
bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ bzip2 -d file1.bz2
bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ ls
data.txt  file1

bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ file file1
file1: gzip compressed data, was "data4.bin", last modified: Sun Oct 25 13:37:05 2026, max compression, from Unix, original size modulo 2^32 20480
bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ mv file1 file1.gz
bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ gunzip file1.gz
bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ file file1
file1: POSIX tar archive (GNU)
bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ man tar
bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ tar -xf file1
bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ ls
data.txt  data5.bin  file1

bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ tar -xf data5.bin
bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ ls
data.txt  data5.bin  data6.bin  file1
bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ tar -xf data6.bin
bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ ls
data.txt  data5.bin  data6.bin  data8.bin  file1
bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Sun Oct 25 13:37:05 2026, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ mv data8.bin data8.gz
bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ gunzip data8.gz
bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ file data8
data8: ASCII text

bandit12@bandit:/tmp/tmp.hGj2Yzw1xd$ cat data8
The password is qQYQiHOBPR8zR61qxYqX45quvihF2uzk```
