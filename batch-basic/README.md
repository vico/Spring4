#サンプルの実行方法
## HSQLDBの起動
1.HSQLDBを起動する。
1-1. HSQLDB(1.8.0)をダウンロードする。
1−2. %HSQLDB_HOME%¥libフォルダへ移動。以下のコマンドでHSQLDBをサーバーモードで起動する。
・java -cp hsqldb.jar org.hsqldb.Server -database db/test
1−2. 同様に、libフォルダで以下のコマンドでDatabaseManagerを起動する
・java -cp hsqldb.jar org.hsqldb.util.DatabaseManager
・ダイアログが出てくるのでTypeに「HSQL Database Engine Server」を選択すればOK。

## Eclipseからの動作確認
1.batch-basicプロジェクトを選択し、右クリックでRun as > Run Configurations...を選択する。
2.ダイアログが表示されるので、mainタブのプロジェクトに「batch-basic」を、mainクラスに「org.springframework.batch.core.launch.support.CommandLineJobRunner」を設定する。
3.Argumentタブを選択し、Program argumentsに「classpath:/batch-context.xml job1 inputFile=classpath:/product_csv/1.csv」を設定する。
4.Runボタンをクリックすると、バッチが実行される。
5.DatabaseManagerでバッチが起動し、テーブルが変更されたことを確認する（必要があればDatabaseManagerでView>Refresh Treeを行う）。

## Intellij IDEAからの動作確認
1. MavenのパーネルにあるPlugins/exec:javaをダブルクリックすることで、実行できる。
