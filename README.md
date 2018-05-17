# xadmin for django2.0.4 & python3.5


基于**原版**修改部分 bugs
亲测 python3.5+ & python 2.0.4 正常运行

------

- git clone 本项目，把 xadmin 文件夹和 requirements.txt 放到项目根目录下
- 下载依赖包，在项目根目录下运行 pip install -r requirements
- settings.py 的 INSTALLED_APPS 新增 'xadmin' 以及 'crispy_forms'
- 在项目 urls 里新增 xadmin 的 url \n  
   `import xadmin   
   urlpatterns = [path('xadmin/', xadmin.site.urls),]`
- 在 admin.py 同级目录下新建 adminx.py
	`import xadmin
	from .models import UserInfo
	class UserInfoAdmin(object):
	    list_display = ['id', 'user_phone', 'user_nickname', 'user_gender']
	xadmin.site.register(UserInfo, UserInfoAdmin)`
- 进行数据库迁移
  `python manage.py makemigrations
   python manage.py migrate`
- 新建管理员
  `python manage.py createsuperuser`
- 运行项目
  `python manage.py runserver`
- 浏览器访问
  http://127.0.0.1：8000/xadmin


