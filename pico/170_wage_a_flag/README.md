To get the Flag just run follwing in shell
```sh
./warm -h > flag
cat flag
```

Or you can go more technical and run strings on it and the flag is right in front of you
```diff
$ strings warm | head -25
/lib64/ld-linux-x86-64.so.2
libc.so.6
puts
printf
__cxa_finalize
strcmp
__libc_start_main
GLIBC_2.2.5
_ITM_deregisterTMCloneTable
__gmon_start__
_ITM_registerTMCloneTable
=y	
=W	
=Z	
AWAVI
AUATL
[]A\A]A^A_
+ Hello user! Pass me a -h to learn what I can do!
+ Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_f0668f62}
+ I don't know what '%s' means! I do know what -h means though!
;*3$"
GCC: (Ubuntu 7.5.0-3ubuntu1~18.04) 7.5.0
/usr/lib/gcc/x86_64-linux-gnu/7/include
/usr/include/x86_64-linux-gnu/bits
/usr/include
```

