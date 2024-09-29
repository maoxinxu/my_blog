# 控制台指令
```bash
# 在migrations文件夹生成一个py文件，记录本次数据库的改动
python manage.py makemigrations polls
# 查看上一部生成的py文件需要那些sql语句来更新数据库
python manage.py sqlmigrate polls 0001
# 更新生效
python manage.py migrate

```

# shell的方式来调试数据库
```bash
# 使用ipython可以更方便的调试，自带高亮和代码补全
python -m pip install ipython
# 开启一个django的调试shell环境
python manage.py shell
```
