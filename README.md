# kait_i2v (infra. to vechicle)
定置型lidarテスト用Gazeboシミュレータ
* 先進研風の実験室（寸法などは適当）
* lidarは1台/2台
* ロボットはtoioシミュレータ参考 (https://note.com/npaka/n/n3d1270475435)

# 動作条件

* ubuntu 18.04
* ros melodic
* WSL2 (windows11)でも動作確認済

# インストール
git cloneだけで動くと思われるが、念のため一部再buildする

```bash
cd ~/catkin_ws/src
git clone https://github.com/kait-wakita/kait_i2v.git
cd plugins/animatedbox
rm -rf build
mkdir build
cd build
cmake ..
make
```

# 使用方法(Gazebo)

静止物シミュレーション
```bash
roslaunch kaitpv lidar2_d2stay1.launch
```

移動物シミュレーション (source gazebo_path_set.shは一度実行すれば良い)
```bash
roscd kait_i2v/plugins/animatedbox
source gazebo_path_set.sh
roslaunch kait_i2v lidar2_d2walk1_3.launch
```

#  カスタマイズ方法

# Note
* 2023.1.15 最初のバージョン

# Author

* wakit@cco.kanagawa-it.ac.jp

# License

"kaitpv" is under [MIT license](https://en.wikipedia.org/wiki/MIT_License).
