Fist check what is static `file static`
```
static: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=9f1762ab580608bef0d251f5fdfaad3d19ae0963, not stripped
```
So its a ELF executable, so make this executable with `chmod +x static` and run it with `./static`
```
Oh hai! Wait what? A flag? Yes, it's around here somewhere!
```

Okay its somewhere here then look for strings then with `strings static -n 15`
```
/lib64/ld-linux-x86-64.so.2
__libc_start_main
_ITM_deregisterTMCloneTable
_ITM_registerTMCloneTable
Oh hai! Wait what? A flag? Yes, it's around here somewhere!
picoCTF{d15a5m_t34s3r_6f8c8200}
GCC: (Ubuntu 7.5.0-3ubuntu1~18.04) 7.5.0
deregister_tm_clones
__do_global_dtors_aux
__do_global_dtors_aux_fini_array_entry
__frame_dummy_init_array_entry
__init_array_end
__init_array_start
__GNU_EH_FRAME_HDR
_GLOBAL_OFFSET_TABLE_
__libc_csu_fini
_ITM_deregisterTMCloneTable
puts@@GLIBC_2.2.5
__libc_start_main@@GLIBC_2.2.5
__libc_csu_init
_ITM_registerTMCloneTable
__cxa_finalize@@GLIBC_2.2.5
.note.gnu.build-id
```
There you go its in front of us, the bash script was kinda useless.
