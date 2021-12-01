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

```
import MeCab

MECAB_SETTING = "/etc/mecabrc"
MECAB_DICTIONARY = "/usr/lib/x86_64-linux-gnu/mecab/dic/mecab-ipadic-neologd"
MECAB_ARGS = " -r " + MECAB_SETTING + " -d " + MECAB_DICTIONARY

m = MeCab.Tagger(MECAB_ARGS)

text = "新型コロナウイルスが猛威を振るった2020年以降、PCR検査やワクチン接種が普及した"
print(m.parse(text))
```


今回使用した形態素解析ツールはこちら  
mecab-ipadic-NEologd
https://github.com/neologd/mecab-ipadic-neologd/blob/master/README.ja.md


