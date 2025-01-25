# 歌单管理系统

这是一个简单的歌单管理系统，用于管理直播间的歌曲列表。

## 文件说明

### all.json

这是主要的歌单数据文件，包含所有歌曲的详细信息。每首歌曲包含以下字段：

- `title`: 歌曲名称
- `artist`: 演唱者
- `genre`: 音乐流派
- `notes`: 备注信息
- `is_paid`: 是否为付费歌曲
- `order`: 歌曲排序序号（从1开始的整数）

URL: https://raw.githubusercontent.com/Akuma-real/gugu-music-list/refs/heads/main/all.json

### song-stats.json

这是一个自动生成的统计文件，当 all.json 更新时会自动更新。包含以下统计信息：

- `total`: 歌单中的总歌曲数量
- `paid`: 付费歌曲数量
- `free`: 免费歌曲数量
- `genres`: 各个流派的歌曲数量统计

URL: https://raw.githubusercontent.com/Akuma-real/gugu-music-list/refs/heads/main/song-stats.json

### song-genre-all.json

按照 order 字段排序的所有歌曲列表。

URL: https://raw.githubusercontent.com/Akuma-real/gugu-music-list/refs/heads/main/song-genre-all.json

### song-genre-[曲风].json

按照曲风分类并排序的歌曲列表。目前包含：

- 流行: https://raw.githubusercontent.com/Akuma-real/gugu-music-list/refs/heads/main/song-genre-流行.json

## 自动化功能

本项目使用 GitHub Actions 实现了自动化统计功能：

- 当 all.json 文件发生变化时，会自动更新所有统计文件
- 统计数据会自动提交到仓库中
- 无需手动维护统计数据

## 使用说明

1. 要添加或修改歌曲，直接编辑 all.json 文件
2. song-stats.json 会自动更新，无需手动修改
3. 所有的变更都会被自动记录和追踪
4. 添加新歌曲时，请确保设置正确的 order 值以保持歌单顺序