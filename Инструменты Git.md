\## Домашнее задание к занятию «Инструменты Git» - Верзилин Сергей

### Задание

В клонированном репозитории:

 1. Найдите полный хеш и комментарий коммита, хеш которого начинается на **aefea**.
 2. Ответьте на вопросы.
  * Какому тегу соответствует коммит **85024d3**?
  * Сколько родителей у коммита **b8d720**? Напишите их хеши.
  * Перечислите хеши и комментарии всех коммитов, которые были сделаны между тегами **v0.12.23** и **v0.12.24**.
  * Найдите коммит, в котором была создана функция func providerSource, её определение в коде выглядит так:  
    **func providerSource(...) (вместо троеточия перечислены аргументы)**.
  * Найдите все коммиты, в которых была изменена функция **globalPluginDirs**.
  * Кто автор функции **synchronizedWriters**?

*В качестве решения ответьте на вопросы и опишите, как были получены эти ответы.*

***

### Ответ

 1. commi **aefead2207ef7e2aa5dc81a34aedf0cad4c32545**, Update CHANGELOG.md 
 2. ответы:  
  * commit **85024d3100126de36331c6982bfaac02cdab9e76** (tag: **v0.12.23**)
  * **2** родителя, **56cd7859e0**  **9ea88f22fc** 
  * **33ff1c03bb** v**0.12.24**  
    **b14b74c493** [Website] vmc provider links  
    **3f235065b9** Update CHANGELOG.md  
    **6ae64e247b** registry: Fix panic when server is unreachable   
    **5c619ca1ba** website: Remove links to the getting started guide's old location  
    **06275647e2** Update CHANGELOG.m  
    **d5f9411f51** command: Fix bug when using terraform login on Windows  
    **4b6d06cc5d** Update CHANGELOG.md  
    **dd01a35078** Update CHANGELOG.md  
    **225466bc3e** Cleanup after v0.12.23 release
  * 
  * 
  * 
  * 

