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


