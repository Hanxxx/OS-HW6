# hmwk6

yz3170 Yufei Zhao

sh3658 Shijun Hou

hl3069 Han Li

## Structure of hmwk6.fs
```
/-
 |-test1.txt
 |-test
     |-test2.txt
```

## Result of file_loc
The result of file_loc for these 1 directory and 2 files is as follow:
```
root@HNKIW-Q:/ # /data/misc/file_loc /data/misc/hmwk6/test1.txt
/data/misc/hmwk6/test1.txt:
	latitude: 40.808935
	longitude: -73.960992
	accuracy: 34.900002m
	Google Maps:
	   http://maps.google.com/maps?iwloc=A&q=40.808935,-73.960992%20(File:%20%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%601.txt)&z=16

root@HNKIW-Q:/ # /data/misc/file_loc /data/misc/hmwk6/test
/data/misc/hmwk6/test:
	latitude: 40.806892
	longitude: -73.962806
	accuracy: 156.199997m
	Google Maps:
	   http://maps.google.com/maps?iwloc=A&q=40.806892,-73.962806%20(File:%20%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60)&z=16

root@HNKIW-Q:/ # /data/misc/file_loc /data/misc/hmwk6/test/test2.txt
/data/misc/hmwk6/test/test2.txt:
	latitude: 40.805481
	longitude: -73.962022
	accuracy: 247.000000m
	Google Maps:
	   http://maps.google.com/maps?iwloc=A&q=40.805481,-73.962022%20(File:%20%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60/test2.txt)&z=16
```
![screenshot of file_loc result](file_loc_result.png)

## References
1. https://www.cnblogs.com/iiiiher/p/5328966.html
2. http://blog.51cto.com/wushank/1212647
3. http://elixir.free-electrons.com/linux/v3.10/ident/MOPT_EXT4_ONLY
4. https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&ved=0ahUKEwjippnR_ITYAhWCg-AKHWqTCZkQFggpMAA&url=https%3A%2F%2Fwww.spinics.net%2Flists%2Farm-kernel%2Fmsg25458.html&usg=AOvVaw0WaQ4AtTmkjwkrH88p2Tu4
5. https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&ved=0ahUKEwiUxLO37YTYAhWnQ98KHZGwDUUQFggwMAE&url=https%3A%2F%2Fwww.gnu.org%2Fs%2Flibc%2Fmanual%2Fhtml_node%2FTesting-File-Access.html&usg=AOvVaw1PZEW5BWUkd090qA1XCb0r
6. https://unix.stackexchange.com/questions/244367/how-does-linux-differentiate-between-real-and-unexisting-eg-device-files
7. https://unix.stackexchange.com/questions/210523/how-do-i-find-a-directory-or-a-file-in-linux-file-system
8. https://stackoverflow.com/questions/30877110/how-to-determine-directory-or-file-in-linux-in-c/30877241

GRADE

P1 10

=====expected=====

[100%] /data/media/0/gps_location.txt
20.805481, -73.962022, 247.000000, 0
[100%] /data/media/0/gps_location.txt
30.805481, -63.962022, 257.000000, 0
[100%] /data/media/0/gps_location.txt

=====test output=====

[100%] /data/media/0/gps_location.txt
20.805481, -73.962022, 247.000000, 0
[100%] /data/media/0/gps_location.txt
30.805481, -63.962022, 257.000000, 0
[100%] /data/media/0/gps_location.txt

P2 5

[100%] /data/media/0/gps_location.txt

===== mount vanilla on vanilla =====

No GPS information:
/data/misc/hw6_grading_dir/mp_vanilla/ll:
	latitude: 30.805481
	longitude: -63.962022
	accuracy: 257.000000m
	Google Maps:
	   http://maps.google.com/maps?iwloc=A&q=30.805481,-63.962022%20(File:%20%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60g_dir%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60)&z=16


===== mount geotag with vanilla =====
/data/misc/hw6_grading_dir/mp_backwards/ll:
	latitude: 30.805481
	longitude: -63.962022
	accuracy: 257.000000m
	Google Maps:
	   http://maps.google.com/maps?iwloc=A&q=30.805481,-63.962022%20(File:%20%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60g_dir%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60)&z=16

/data/misc/hw6_grading_dir/mp_backwards/ll:
	latitude: 30.805481
	longitude: -63.962022
	accuracy: 257.000000m
	Google Maps:
	   http://maps.google.com/maps?iwloc=A&q=30.805481,-63.962022%20(File:%20%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60g_dir%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60)&z=16


===== mount geotag with gps mount option =====
/data/misc/hw6_grading_dir/mp_full_gps/ll:
	latitude: 20.805481
	longitude: -73.962022
	accuracy: 247.000000m
	Google Maps:
	   http://maps.google.com/maps?iwloc=A&q=20.805481,-73.962022%20(File:%20%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60g_dir%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60)&z=16

/data/misc/hw6_grading_dir/mp_full_gps/ll:
	latitude: 30.805481
	longitude: -63.962022
	accuracy: 257.000000m
	Google Maps:
	   http://maps.google.com/maps?iwloc=A&q=30.805481,-63.962022%20(File:%20%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60g_dir%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60)&z=16

[100%] /data/media/0/gps_location.txt

===== mount vanilla ext4 with gps_aware_inode option: should print warning of incompatable feature =====
mount: Invalid argument

===== depending on if they handled mounting correctly, this might leave an actual mount =====
/dev/loop0: [b31a]:23 ()

===== in that case run, <adb shell umount /data/misc/hw6_grading_dir/mp_reject> =====

P3
3.1 5
[100%] /data/media/0/gps_location.txt
turning into daemon
_____ls of their file system_____

/data/misc/hw6_grading_dir/mp_hw6:
lost+found

/data/misc/hw6_grading_dir/mp_hw6/lost+found:
_____gps of files_____
/data/misc/hw6_grading_dir/mp_hw6:
	latitude: 0.000000
	longitude: 0.000000
	accuracy: 0.000000m
	Google Maps:
	   http://maps.google.com/maps?iwloc=A&q=0.000000,0.000000%20(File:%20%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60g_dir%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60)&z=16

/data/misc/hw6_grading_dir/mp_hw6/lost+found:
	latitude: 0.000000
	longitude: 0.000000
	accuracy: 0.000000m
	Google Maps:
	   http://maps.google.com/maps?iwloc=A&q=0.000000,0.000000%20(File:%20%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60g_dir%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60)&z=16
	  
3.2 20
[100%] /data/media/0/gps_location.txt
turning into daemon
start up pts 1-3
[100%] /data/media/0/gps_location.txt
===== begin test: =====

===== update file: =====
/data/misc/hw6_grading_dir/mp_hw6/l:
	latitude: 30.805481
	longitude: -63.962022
	accuracy: 257.000000m
	Google Maps:
	   http://maps.google.com/maps?iwloc=A&q=30.805481,-63.962022%20(File:%20%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60g_dir%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60)&z=16

===== update dir: =====
/data/misc/hw6_grading_dir/mp_hw6/dir:
	latitude: 30.805481
	longitude: -63.962022
	accuracy: 257.000000m
	Google Maps:
	   http://maps.google.com/maps?iwloc=A&q=30.805481,-63.962022%20(File:%20%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60g_dir%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60)&z=16

===== update chmod =====
/data/misc/hw6_grading_dir/mp_hw6/ll:
	latitude: 30.805481
	longitude: -63.962022
	accuracy: 257.000000m
	Google Maps:
	   http://maps.google.com/maps?iwloc=A&q=30.805481,-63.962022%20(File:%20%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60g_dir%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60)&z=16

start up pts 4-5
[100%] /data/media/0/gps_location.txt
[100%] /data/media/0/gps_location.txt
===== update on mv =====
/data/misc/hw6_grading_dir/mp_hw6/dir/moved:
	latitude: 30.805481
	longitude: -63.962022
	accuracy: 257.000000m
	Google Maps:
	   http://maps.google.com/maps?iwloc=A&q=30.805481,-63.962022%20(File:%20%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60g_dir%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60)&z=16

===== update on ln =====
/data/misc/hw6_grading_dir/mp_hw6/dir/hdlnk:
	latitude: 30.805481
	longitude: -63.962022
	accuracy: 257.000000m
	Google Maps:
	   http://maps.google.com/maps?iwloc=A&q=30.805481,-63.962022%20(File:%20%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60g_dir%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60)&z=16

===== update dir part 2: file created inside =====
/data/misc/hw6_grading_dir/mp_hw6/dir:
	latitude: 30.805481
	longitude: -63.962022
	accuracy: 257.000000m
	Google Maps:
	   http://maps.google.com/maps?iwloc=A&q=30.805481,-63.962022%20(File:%20%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60g_dir%2F%3A%3B%3D%3F%40%20%22%3C%3E%23%25%7B%7D%7C%5C%5E%7E%5B%5D%60)&z=16
