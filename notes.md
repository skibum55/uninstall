Carbon Black Removal
Lldb uninstall

https://stackoverflow.com/questions/24431619/find-a-string-memory-using-lldb

sudo lldb -- uninstall -c xyzsk (actually does the uninstall)
sudo lldb -- uninstall -u xyzsk (checks whether code is valid)

Ctrl-c to interrupt
Then bt to backtrace

https://stackoverflow.com/questions/33424637/what-is-the-lldb-equivalent-of-gdbs-args

(lldb) target create "uninstall"
Current executable set to '/Applications/VMware Carbon Black Cloud/uninstall.bundle/Contents/MacOS/uninstall' (x86_64).
(lldb) settings set -- target.run-args  "-c" "xyzsk"
(Lldb) settings show target.run-args

Image list
(lldb) image list
[  0] D3CB985B-1A13-33AA-BF15-C3B12124AF0A 0x0000000100000000 /Applications/VMware Carbon Black Cloud/uninstall.bundle/Contents/MacOS/uninstall

Image dump sections uninstall
(lldb) image dump sections uninstall
Sections for '/Applications/VMware Carbon Black Cloud/uninstall.bundle/Contents/MacOS/uninstall' (x86_64):
  SectID     Type             File Address                             Perm File Off.  File Size  Flags      Section Name
  ---------- ---------------- ---------------------------------------  ---- ---------- ---------- ---------- ----------------------------
  0x00000100 container        [0x0000000000000000-0x0000000100000000)  ---  0x00000000 0x00000000 0x00000000 uninstall.__PAGEZERO
  0x00000200 container        [0x0000000100000000-0x0000000100446000)  r-x  0x00000000 0x00446000 0x00000000 uninstall.__TEXT
  0x00000001 code             [0x0000000100001000-0x00000001003d8585)  r-x  0x00001000 0x003d7585 0x80000400 uninstall.__TEXT.__text
  0x00000002 code             [0x00000001003d8586-0x00000001003d8dd2)  r-x  0x003d8586 0x0000084c 0x80000408 uninstall.__TEXT.__stubs
  0x00000003 code             [0x00000001003d8dd4-0x00000001003d9b90)  r-x  0x003d8dd4 0x00000dbc 0x80000400 uninstall.__TEXT.__stub_helper
  0x00000004 regular          [0x00000001003d9b90-0x00000001003dffd8)  r-x  0x003d9b90 0x00006448 0x00000000 uninstall.__TEXT.__gcc_except_tab
  0x00000005 data-cstr        [0x00000001003dffe0-0x0000000100414aa1)  r-x  0x003dffe0 0x00034ac1 0x00000002 uninstall.__TEXT.__cstring
  0x00000006 regular          [0x0000000100414ac0-0x0000000100443435)  r-x  0x00414ac0 0x0002e975 0x00000000 uninstall.__TEXT.__const
  0x00000007 data-cstr        [0x0000000100443435-0x0000000100443465)  r-x  0x00443435 0x00000030 0x00000002 uninstall.__TEXT.__objc_methname
  0x00000008 compact-unwind   [0x0000000100443468-0x00000001004458b8)  r-x  0x00443468 0x00002450 0x00000000 uninstall.__TEXT.__unwind_info
  0x00000009 eh-frame         [0x00000001004458b8-0x0000000100445a00)  r-x  0x004458b8 0x00000148 0x00000000 uninstall.__TEXT.__eh_frame
  0x00000300 container        [0x0000000100446000-0x0000000100487000)  rw-  0x00446000 0x0003c000 0x00000000 uninstall.__DATA
  0x0000000a data-ptrs        [0x0000000100446000-0x0000000100446008)  rw-  0x00446000 0x00000008 0x00000006 uninstall.__DATA.__nl_symbol_ptr
  0x0000000b data-ptrs        [0x0000000100446008-0x0000000100446258)  rw-  0x00446008 0x00000250 0x00000006 uninstall.__DATA.__got
  0x0000000c data-ptrs        [0x0000000100446258-0x0000000100446d68)  rw-  0x00446258 0x00000b10 0x00000007 uninstall.__DATA.__la_symbol_ptr
  0x0000000d data-ptrs        [0x0000000100446d68-0x0000000100446dd0)  rw-  0x00446d68 0x00000068 0x00000009 uninstall.__DATA.__mod_init_func
  0x0000000e regular          [0x0000000100446dd0-0x0000000100477d58)  rw-  0x00446dd0 0x00030f88 0x00000000 uninstall.__DATA.__const
  0x0000000f objc-cfstrings   [0x0000000100477d58-0x0000000100477df8)  rw-  0x00477d58 0x000000a0 0x00000000 uninstall.__DATA.__cfstring
  0x00000010 regular          [0x0000000100477df8-0x0000000100477e00)  rw-  0x00477df8 0x00000008 0x00000000 uninstall.__DATA.__objc_imageinfo
  0x00000011 data-cstr-ptr    [0x0000000100477e00-0x0000000100477e18)  rw-  0x00477e00 0x00000018 0x10000005 uninstall.__DATA.__objc_selrefs
  0x00000012 data-ptrs        [0x0000000100477e18-0x0000000100477e20)  rw-  0x00477e18 0x00000008 0x10000000 uninstall.__DATA.__objc_classrefs
  0x00000013 data             [0x0000000100477e20-0x0000000100481cf0)  rw-  0x00477e20 0x00009ed0 0x00000000 uninstall.__DATA.__data
  0x00000014 zero-fill        [0x0000000100481cf0-0x0000000100482ab8)  rw-  0x00000000 0x00000000 0x00000001 uninstall.__DATA.__common
  0x00000015 zero-fill        [0x0000000100482ac0-0x0000000100486700)  rw-  0x00000000 0x00000000 0x00000001 uninstall.__DATA.__bss
  0x00000400 container                                                 rw-  0x00482000 0x00000000 0x00000004 uninstall.__RESTRICT
  0x00000016 regular                                                   rw-  0x00482000 0x00000000 0x00000000 uninstall.__RESTRICT.__restrict
  0x00000500 container        [0x0000000100487000-0x00000001004be000)  r--  0x00482000 0x000364b0 0x00000000 uninstall.__LINKEDIT

Set  Breakpoint
(lldb) break set -n memcpy
(lldb) break disable 1
1 breakpoints disabled.
(lldb) break set -n fwrite
(lldb) break set -n sleep
(lldb) r
(lldb) break set -n ___lldb_unnamed_symbol6916$$uninstall
(lldb) break set -n ___lldb_unnamed_symbol81$$uninstall
6915
7048
7049
7047
68
https://stackoverflow.com/questions/36679156/lldb-how-to-set-breakpoint-whch-stops-when-register-somevalue
break modify -c "$r9 == 0x0000000000000009"


Memory  find
(Lldb) mem find -s "code" -- 0x0000000100000000 0x00007fff29de8000
(Lldb) memory find -s "xyzsk" -- 0x0000000000000000 0x00007fff28f82000

Memory Read
memory read -t "char *" -c `(int) $arg1` $arg2

Read Memory
(lldb) x/16 0x000000010000ade5

Watch
w s e -s 2 -- 0x1003e0045

w s e -w read_write -- 0x1003e307a
watchpoint set expression -w read_write -s 1 -- 0x1003e307a
watchpoint set expression -w read -- 0x1003e307a

Backtrace
(lldb)bt

Register read
(lldb) register read

Print registers
(LLDB) po $rax

Register set
(lldb) register write $r15 0x0000000000000000

