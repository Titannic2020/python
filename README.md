# if _name_ == '_main_'的意思是：当.py文件被直接运行时，if _name_ == '_main_'之下的代码块将被运行；当.py文件以模块形式被导入时，if _name_ == '_main_'之下的代码块不被运行。
import requests
def getHTMLTEXT(url):
    try:
        r=requests.get(url)
        r.raise_for_status()
        r.encoding=r.apparent_encoding
        return r.text
    except:
        return "产生异常"

url="http://www.baidu.com"
print(getHTMLTEXT(url))
