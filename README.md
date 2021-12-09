勉強用に記録
# mecab-ipadic-neologd  
リポジトリのあるディレクトリで以下を実行  
Creating mecab-notebook ... done と表示されていれば環境構築が完了 
```
docker-compose up -d --build
```

環境への初回アクセス時にpassword or tokenが必要なため、下記を実行し取得したtokenをアクセス先で入力   
tokenを入力してpasswordを設定することも可能  
```
docker exec -it mecab-notebook jupyter notebook list  
```

環境にて形態素解析の実行  
```
import MeCab

MECAB_SETTING = "/etc/mecabrc"
MECAB_DICTIONARY = "/usr/lib/x86_64-linux-gnu/mecab/dic/mecab-ipadic-neologd"
MECAB_ARGS = " -r " + MECAB_SETTING + " -d " + MECAB_DICTIONARY

m = MeCab.Tagger(MECAB_ARGS)

text = "新型コロナウイルスが猛威を振るった2020年にアベノマスクの配布があった。コロナ禍で打撃を受けた飲食業や観光業の活性化を目的としたGoToトラベルが実施されたこともあった。"
print(m.parse(text))
```
![image](https://user-images.githubusercontent.com/32927796/144154065-1a6160f6-fd0f-4818-85f9-df672c367d38.png)

今回使用した形態素解析ツールはこちら  
mecab-ipadic-NEologd
https://github.com/neologd/mecab-ipadic-neologd/blob/master/README.ja.md


