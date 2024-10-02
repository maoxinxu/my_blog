# 控制台指令
```bash
# 在migrations文件夹生成一个py文件，记录本次数据库的改动，这是记录没有实际做生效
python manage.py makemigrations polls
# 查看上一部生成的py文件需要那些sql语句来更新数据库，这个是查看指令
python manage.py sqlmigrate polls 0001
# 更新生效，这里面会实际执行指令去创建新的table
python manage.py migrate
# 创建管理账户，之后可以访问 ip:8080/admin/
python manage.py createsuperuser
```

# shell的方式来调试数据库
开启调试环境
```bash
# 使用ipython可以更方便的调试，自带高亮和代码补全
python -m pip install ipython
# 开启一个django的调试shell环境
python manage.py shell
```
导入调试指令
```python
# 导入数据库操作类
from polls.models import Choice, Question
# 查看所有数据
Question.objects.all()

# 插入一条数据
from django.utils import timezone
q = Question(question_text="What's new?", pub_date=timezone.now())
q.save()

# 查看信息
q.id
q.question_text
q.pub_date

# 数据库查询
Question.objects.all()
Question.objects.filter(id=1)
Question.objects.filter(question_text__startswith="What")
Question.objects.get(pk=1)

```
