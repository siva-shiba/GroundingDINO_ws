# GroundingDINO workspace
GroundingDINO用のdockerワークスペース

# set-up
このリポジトリはサブモジュールが含まれているので`GroundingDINO`フォルダの中身がちゃんとcloneされているのを確認すること
```
git clone --recursive git@github.com:siva-shiba/GroundingDINO_ws.git
cd /PATH/TO/GroundingDINO_ws/GroundingDINO
mkdir -p weights && \
    wget -q -O weights/groundingdino_swint_ogc.pth https://github.com/IDEA-Research/GroundingDINO/releases/download/v0.1.0-alpha/groundingdino_swint_ogc.pth
```
もし`--recursive`オプションをつけ忘れた場合は以下のコマンドでサブモジュールがcloneされる
```
cd /PATH/TO/GroundingDINO_ws
git submodule update --init --recursive
```
# start-up
起動方法
```
cd /PATH/TO/GroundingDINO_ws
sh docker/run-docker.sh
```

# demo
GroundingDINOのデモ実行
```
cd /PATH/TO/GroundingDINO_ws
sh docker/run-docker.sh
python demo/inference_on_a_image.py \
-c groundingdino/config/GroundingDINO_SwinT_OGC.py \
-p weights/groundingdino_swint_ogc.pth \
-i [test.png]\
-o [outputs dir] \
-t [prompt]
```
