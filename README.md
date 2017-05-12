# ruedX-themes
 
# Установка темы ruedX: #

## Шаг 1 - останавливаем memcached: ##
=======
 

 
>     telnet localhost 11211
>     flush_all
>     quit

 
## Шаг 2 - клонируем тему в /edx/app/edxapp/themes  ##
=======
 

>     cd /edx/app/edxapp/themes
> 
>     clone https://github.com/VladimirAndropov/ruedx-theme

 
Шаг 3 - прописываем в *lms.env.json* 
=======
 
 >     "COMPREHENSIVE_THEME_DIRS": [
>         "/edx/app/edxapp/themes"
> 
>     "USE_CUSTOM_THEME":  true
>  
>     "THEME_NAME": "ruedX", 
>  
>     "DEFAULT_SITE_THEME": "ruedX", 

 
Шаг 3 - Устраняем ошибки прав доступа


> удаляем всё из папки */tmp/mako_lms/*
> 
>  удаляем все из *staticfiles* по пути */edx/var/edxapp*
>  
>  ставим права для edxapp:edxapp на /edx/app/edxapp/themes/ruedX
 

Шаг 4 - компилим тему
=======
 

 
>     sudo -H -u edxapp bash
>     source /edx/app/edxapp/edxapp_env
>     cd /edx/app/edxapp/edx-platform
>     paver update_assets lms --settings=aws --themes=ruedX

 
Должно получиться как здесь: [edx.fpkmgppu.ru](Демо: "ruedX")
=======
 
