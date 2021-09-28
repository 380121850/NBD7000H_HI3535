# NBD7000H_HI3535

CRAMFS文件系统简介：

CRAMFS文件系统是由Linux Torvalds编写的专门针对闪存设计的只读压缩文件系统。

与RAM disk方式不同，CRAMFS文件系统不需要一次性地将文件系统中的所有内容都解压到内存中，而只是在系统需要访问某个数据时，马上计算出该数据在CRAMFS中的位置，将其实时的解压到内存之中，然后通过对内存的访问来获取文件系统中需要读取的数据

源文件：从http://sourceforge.net/projects/cramfs下载cramfs-1.1.tar.gz

# tar -zxvf cramfs-1.1.tar.gz

# cd cramfs-1.1

# make

经过以上步骤会生成两个可执行文件：

mkcramfs和cramfsck；

把这两个可执行文件拷贝到/bin 目录下，就可以使用相应的命令了；

命令使用：

mkcramfs工具用来创建CRAMFS文件系统

# mkcramfs dirname outfile

cramfsck工具用来进行CRAMFS文件系统的释放和检查

# cramfsck -x dirname filename

-x dirname 表示释放到dirname所指定的目录中.


例如：
cramfsck -x root root.cramfs 解压*.cramfs 文件

mkcramfs root root.cramfs 压缩root根文件为root.cramfs
