## Домашнее задание к занятию «Инструменты Git» - Верзилин Сергей

### Задание

В клонированном репозитории:
1. Найдите полный хеш и комментарий коммита, хеш которого начинается на **aefea**.  
```
┌──(sergey㉿kali)-[~/terraform]
└─$ git show --pretty=oneline aefea                                                                                             
aefead2207ef7e2aa5dc81a34aedf0cad4c32545 Update CHANGELOG.md
diff --git a/CHANGELOG.md b/CHANGELOG.md
index 86d70e3e0d..588d807b17 100644
--- a/CHANGELOG.md
+++ b/CHANGELOG.md
@@ -27,6 +27,7 @@ BUG FIXES:
 * backend/s3: Prefer AWS shared configuration over EC2 metadata credentials by default ([#25134](https://github.com/hashicorp/terraform/issues/25134))
 * backend/s3: Prefer ECS credentials over EC2 metadata credentials by default ([#25134](https://github.com/hashicorp/terraform/issues/25134))
 * backend/s3: Remove hardcoded AWS Provider messaging ([#25134](https://github.com/hashicorp/terraform/issues/25134))
+* command: Fix bug with global `-v`/`-version`/`--version` flags introduced in 0.13.0beta2 [GH-25277]
 * command/0.13upgrade: Fix `0.13upgrade` usage help text to include options ([#25127](https://github.com/hashicorp/terraform/issues/25127))
 * command/0.13upgrade: Do not add source for builtin provider ([#25215](https://github.com/hashicorp/terraform/issues/25215))
 * command/apply: Fix bug which caused Terraform to silently exit on Windows when using absolute plan path ([#25233](https://github.com/hashicorp/terraform/issues/25233))
```


2. Ответьте на вопросы.
 * Какому тегу соответствует коммит **85024d3**?
 * Сколько родителей у коммита **b8d720**? Напишите их хеши.
 * Перечислите хеши и комментарии всех коммитов, которые были сделаны между тегами **v0.12.23** и **v0.12.24**.
 * Найдите коммит, в котором была создана функция **func providerSource**, её определение в коде выглядит так:  
   **func providerSource(...) (вместо троеточия перечислены аргументы)**.
 * Найдите все коммиты, в которых была изменена функция **globalPluginDirs**.
 * Кто автор функции **synchronizedWriters**?

*В качестве решения ответьте на вопросы и опишите, как были получены эти ответы.*



  * commit **85024d3100126de36331c6982bfaac02cdab9e76** (tag: **v0.12.23**)
  * **2** родителя, **56cd7859e0**  **9ea88f22fc** 
  * git log --pretty=format:"%h %s" v**0.12.23**...v**0.12.24**
    **33ff1c03bb** v**0.12.24**  
    **b14b74c493** [Website] vmc provider links  
    **3f235065b9** Update CHANGELOG.md  
    **6ae64e247b** registry: Fix panic when server is unreachable   
    **5c619ca1ba** website: Remove links to the getting started guide's old location  
    **06275647e2** Update CHANGELOG.m  
    **d5f9411f51** command: Fix bug when using terraform login on Windows  
    **4b6d06cc5d** Update CHANGELOG.md  
    **dd01a35078** Update CHANGELOG.md  
    **225466bc3e** Cleanup after **v0.12.23** release
  * 
  * git log -S globalPluginDirs --oneline  
    **65c4ba7363** Remove terraform binary
    **125eb51dc4** Remove accidentally-committed binary
    **22c121df86** Bump compatibility version to 1.3.0 for terraform core release (#30988)
    **7c7e5d8f0a** Don't show data while input if sensitive
    **35a058fb3d** main: configure credentials from the CLI config file
    **c0b1761096** prevent log output during init
    **8364383c35** Push plugin discovery down into command package
  * 
  * 

