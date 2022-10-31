# Researching Commands: `find`

For this lab report, I was tasked with researching a command and finding 3 interesting ways to use it in the command-line. The command I choose to examine for this report is `find`, which used to gather specific files that meet certain criteria in a directory.
<br />

## **Option 1:** `-name`
---

The option `-name` is a way to search for a files with a specific name in a directory. This is a useful addition to the `find` command because there may be times where you know what file you are looking for but forgot where exactly it is in your working directory. For example, if I wanted to search for a file called `chapter-1.txt` in all directories in the current working directory, here's what I could do:
``` 
[cs15lfa22ko@ieng6-202]:technical:184$ find . -name chapter-1.txt
./911report/chapter-1.txt
```

Here I am finding where a file named `preface.txt` is in the current working directory.
``` 
[cs15lfa22ko@ieng6-202]:technical:185$ find . -name preface.txt  
./911report/preface.txt
```

Or if I wanted to find a file called `1471-2105-3-6.txt` in the `biomed` directory:
``` 
[cs15lfa22ko@ieng6-202]:technical:186$ find biomed -name 1471-2105-3-6.txt
biomed/1471-2105-3-6.txt
```

<br />

## **Option 2:** `-type`
---

`-type` is a useful option you can use if you need to search for a file of a certain type, such as a normal file, a directory, or a symbolic link. In order to use this option you will need to specify what type of file you are searching for using one of these descriptors: 

`f`: file <br />
`d`: directory <br />
`l`: symbolic link <br />
`b`: block devices <br />
`p`: named pipe <br />
`s`: socket <br />
`c`: character devices <br />

To find all of the directories in the current working directory:
``` 
[cs15lfa22ko@ieng6-202]:technical:179$ find . -type d
.
./911report
./biomed
./government
./government/About_LSC
./government/Alcohol_Problems
./government/Env_Prot_Agen
./government/Gen_Account_Office
./government/Media
./governmen
```

You can also find all directories in a certain directory. Here I am searching the `government` directory for its internal directories. 
``` 
[cs15lfa22ko@ieng6-202]:technical:176$ find government -type d
government
government/About_LSC
government/Alcohol_Problems
government/Env_Prot_Agen
government/Gen_Account_Office
government/Media
government/Post_Rate_Comm
```

It is also useful to be able to search for a file by specifying its type and its name. There may be content in a folder that are different types but share the same name.
``` 
[cs15lfa22ko@ieng6-202]:technical:175$ find 911report -type f -name chapter-1.txt
911report/chapter-1.txt
```

<br />

## **Option 3:** `-size`
---

The `-size` option will search for files of a given size. It can also be fed a parameter that specifies the unit of measurement you would like to use. Here is the list of paramaters that can be used: 

`b`: 512-byte blocks (default)<br />
`c`: bytes <br />
`w`: two-byte words <br />
`k`: Kilobytes <br />
`M`: Megabytes <br />
`G`: Gigabytes <br />

Here is an instance where I need a list of files that are bigger than 20 kilobytes in the `911report` folder.
``` 
[cs15lfa22ko@ieng6-202]:technical:181$ find 911report -size +20k
911report/chapter-1.txt
911report/chapter-10.txt
911report/chapter-11.txt
911report/chapter-12.txt
911report/chapter-13.1.txt
911report/chapter-13.2.txt
911report/chapter-13.3.txt
911report/chapter-13.4.txt
911report/chapter-13.5.txt
911report/chapter-2.txt
911report/chapter-3.txt
911report/chapter-5.txt
911report/chapter-6.txt
911report/chapter-7.txt
911report/chapter-8.txt
911report/chapter-9.txt
```

It is also helpful to be able to find files that are less than a certain size. Here is an example where I am looking for files in `911report` that are less than 20 kilobytes.
``` 
[cs15lfa22ko@ieng6-202]:technical:181$ find 911report -size -20k
911report
911report/preface.txt
```

You can also search for files that are between a given size. For example, if I want to know what files in `government` are greater than 15 kilobytes but less than 20 kilobytes, this is what I would need to do:
``` 
[cs15lfa22ko@ieng6-202]:technical:183$ find government -size +15k -size -20k
government/About_LSC/reporting_system.txt
government/Gen_Account_Office/og96011.txt
government/Gen_Account_Office/og96038.txt
government/Gen_Account_Office/og96041.txt
```
