RK MPI

karappo:
media-ctl -p -d /dev/media0

karappo:
v4l2-ctl --all --device /dev/video0


v4l2-ctl --device /dev/video9 --set-fmt-video=width=2688,height=1520,pixelformat=NV12 --stream-skip=10 --stream-mmap --stream-to=./nv12_2688.jpg --stream-count=1

v4l2-ctl --device /dev/video0 --set-fmt-video=width=2688,height=1520,pixelformat=BG10 --stream-mmap --stream-to=./BG10_2688.jpg --stream-count=1

rtsp
/oem/bin/rtsp_test  -w 1920 -h 1080 --src_rate=50 -n /dev/video8
"rtsp://192.168.0.74:8554/testStream"

i2ctransfer -y -f 7 w2@0x30 0x31 0x07 r2

export LD_LIBRARY_PATH=

将一张图片显示到HDMI  图片位置/oem/data  图片名字res_1080P.yuv vo.txt /oem/data/res_1080P.yuv
./rk_mpi_vo_test -i vo.txt --image0_width 1920 --image0_height 1080 --disp_width 1920 --disp_height 1080 --ui=1 --video_format=0

播放一个本地视频到HDMI
rk_mpi_vplay_test -i ./config.txt --screen0_chn=1 --screen1_chn=1 --screen0_rows=1 --screen1_rows=1

相机录像
/oem/bin/rk_mpi_vi_test -w 1280 -h 720 -n /dev/video0 -m 1 -o 1 -l 1000

视频 相机到HDMI
/oem/bin/rk_mpi_vi_test -w 2688 -h 1520 -n /dev/video8 -m 4 -l 10000

查看video*节点
grep '' /sys/class/video4linux/video*/name

相机截图单张
/oem/bin/rk_mpi_vi_test -w 2688 -h 1520 -n /dev/video8 -m 0 -o 1 -l 1

[root@RK3588:/]# grep '' /sys/class/video4linux/video*/name
/sys/class/video4linux/video0/name:stream_cif_mipi_id0
/sys/class/video4linux/video1/name:stream_cif_mipi_id1
/sys/class/video4linux/video10/name:rkisp_fbcpath
/sys/class/video4linux/video11/name:rkisp_iqtool
/sys/class/video4linux/video12/name:rkisp_rawrd0_m
/sys/class/video4linux/video13/name:rkisp_rawrd2_s
/sys/class/video4linux/video14/name:rkisp_rawrd1_l
/sys/class/video4linux/video15/name:rkisp-statistics
/sys/class/video4linux/video16/name:rkisp-input-params
/sys/class/video4linux/video2/name:stream_cif_mipi_id2
/sys/class/video4linux/video3/name:stream_cif_mipi_id3
/sys/class/video4linux/video4/name:rkcif_scale_ch0
/sys/class/video4linux/video5/name:rkcif_scale_ch1
/sys/class/video4linux/video6/name:rkcif_scale_ch2
/sys/class/video4linux/video7/name:rkcif_scale_ch3
/sys/class/video4linux/video8/name:rkisp_mainpath
/sys/class/video4linux/video9/name:rkisp_selfpath