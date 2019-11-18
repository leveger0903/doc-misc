# 備份與轉移

https://docs.gitlab.com/12.4/ee/raketasks/backup_restore.html

以下為備份與轉移的步驟

## 備份作業

1. 套件管理庫升級至新版 Gitlab
2. 進入 Gitlab 容器

```
docker exec -it synology_gitlab bash
```

3. 跳至 /home/git/gitlab/bin/

```
cd /home/git/gitlab/bin/
```

4. 進行當前 Gitlab 資料打包

```
# 打包儲存位置: /home/git/data/backups/
# 產生檔名: {timestamp}_{YYYY}_{MM}_{DD}_{VER}.gitlab_backup.tar
bundle exec rake gitlab:backup:create
```

5. 手動備份下列兩隻 config 檔

```
/home/git/gitlab/config/secrets.yml
/home/git/gitlab/config/gitlab.yml
```

## 還原作業

1. 將備份的 gitlab_backup.tar 跟 config 檔複製到 /home/git/data/backups 底下
2. 進入 Gitlab 容器

```
docker exec -it synology_gitlab bash
```

3. 將手動備份的兩隻 config 檔還原至原始位置

```
/home/git/gitlab/config/secrets.yml
/home/git/gitlab/config/gitlab.yml
```

4. 跳至 /home/git/gitlab/bin/

```
cd /home/git/gitlab/bin/
```

5. 進行當前 Gitlab 資料還原

```
# 還原版本輸入方式: {timestamp}_{YYYY}_{MM}_{DD}_{VER}.gitlab_backup.tar
bundle exec rake gitlab:backup:restore BACKUP={timestamp}_{YYYY}_{MM}_{DD}_{VER}
```

## 備註

- 上述方法適用於 docker / synology_gitlab (v11)版本,<br>
v12 版本將會有不同.
- 轉移的新舊機器需為相同版本,<br> 
因此建議 DSM 套件庫的 Gitlab 要常常保持備份動作,<br>
避免因為備份版本與群暉最新版本版號不一致導致無法備份.