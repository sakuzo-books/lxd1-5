# 正誤情報

## 初版

* P99: MariaDBを冗長化するコマンド操作に誤りがあります。  
  * 誤: `MASTER_LOG_POS=713486`   
    ```
    　　　：
    MariaDB [(none)]>
    MariaDB [(none)]> CHANGE MASTER TO
    -> MASTER_HOST='192.168.56.51',             ← マスターのIP アドレス
    -> MASTER_PORT=3306,                        ← マスターのポート番号
    -> MASTER_USER='repl',                      ← マスターで作ったレプリケーション用ユーザー
    -> MASTER_PASSWORD='Password123!',          ← マスターで作ったレプリケーション用パスワード
    -> MASTER_LOG_FILE='mysql-bin.000001',      ← マスターでのバイナリーログのファイル名
    -> MASTER_LOG_POS=713486;                   ← マスターでのバイナリーログのポジション
    Query OK, 0 rows affected (0.021 sec)
    MariaDB [(none)]>
    　　　：
    ```

  * 正：`MASTER_LOG_POS=1316`  
    ```
    　　　：
    MariaDB [(none)]>
    MariaDB [(none)]> CHANGE MASTER TO
    -> MASTER_HOST='192.168.56.51',             ← マスターのIP アドレス
    -> MASTER_PORT=3306,                        ← マスターのポート番号
    -> MASTER_USER='repl',                      ← マスターで作ったレプリケーション用ユーザー
    -> MASTER_PASSWORD='Password123!',          ← マスターで作ったレプリケーション用パスワード
    -> MASTER_LOG_FILE='mysql-bin.000001',      ← マスターでのバイナリーログのファイル名
    -> MASTER_LOG_POS=1316;                     ← マスターでのバイナリーログのポジション
    Query OK, 0 rows affected (0.021 sec)
    MariaDB [(none)]>
    　　　：
    ```


* P128: 説明文に誤りがあります。  
  * 誤  
    > 予行演習モードで実行しエラー表示はなく受信データは約90.3KByteで、転送速度は約201.2KByte/秒という表示が確認できたので、**"-nv"** オプションを除いて本番モードで実行します。
  
  * 正  
    > 予行演習モードで実行しエラー表示はなく受信データは約90.3KByteで、転送速度は約201.2KByte/秒という表示が確認できたので、**"-n"** オプションを除いて本番モードで実行します。
