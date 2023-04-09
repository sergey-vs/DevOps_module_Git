## Домашнее задание к занятию «Инструменты Git» - Верзилин Сергей

### Задание

В клонированном репозитории:
1. *Найдите полный хеш и комментарий коммита, хеш которого начинается на* **aefea**.  
```
└─$ git show --pretty=oneline aefea                                                                                             
aefead2207ef7e2aa5dc81a34aedf0cad4c32545 Update CHANGELOG.md
```
2. Ответьте на вопросы.
 * *Какому тегу соответствует коммит* **85024d3**?
```
└─$ git show --pretty=oneline 85024d3                                                                                           
85024d3100126de36331c6982bfaac02cdab9e76 (tag: v0.12.23) v0.12.23
```
 * *Сколько родителей у коммита* **b8d720**? *Напишите их хеши*.
```
└─$ git show --pretty=%P b8d720
56cd7859e05c36c06b56d013b55a252d0bb7e158 9ea88f22fc6269854151c571162c5bcf958bee2b
```
 * *Перечислите хеши и комментарии всех коммитов, которые были сделаны между тегами* **v0.12.23** *и* **v0.12.24**.

```
└─$ git log v0.12.23..v0.12.24 --oneline                                                                                        
33ff1c03bb (tag: v0.12.24) v0.12.24
b14b74c493 [Website] vmc provider links
3f235065b9 Update CHANGELOG.md
6ae64e247b registry: Fix panic when server is unreachable
5c619ca1ba website: Remove links to the getting started guide's old location
06275647e2 Update CHANGELOG.md
d5f9411f51 command: Fix bug when using terraform login on Windows
4b6d06cc5d Update CHANGELOG.md
dd01a35078 Update CHANGELOG.md
225466bc3e Cleanup after v0.12.23 release
```
 * *Найдите коммит, в котором была создана функция **func providerSource**, её определение в коде выглядит так*:  
   **func providerSource(...) (вместо троеточия перечислены аргументы)**.
### Ответ: 8c928e83589d90a031f811fae52a81be7153e82f
```
└─$ git log -S "func providerSource" --pretty=oneline                                                              
5af1e6234ab6da412fb8637393c5a17a1b293663 main: Honor explicit provider_installation CLI config when present
8c928e83589d90a031f811fae52a81be7153e82f main: Consult local directories as potential mirrors of providers
```
```git checkout 8c928e83589d90a031f811fae52a81be7153e82f``` 

``` 
└─$ git grep -n 'func providerSource(.*)'                                                                          
provider_source.go:19:func providerSource(services *disco.Disco) getproviders.Source {
```
```
└─$  git blame -L 19,19 provider_source.go                                                                         
8c928e83589 (Martin Atkins 2020-04-02 18:04:39 -0700 19) func providerSource(services *disco.Disco) getproviders.Source {
```
```git checkout 5af1e6234ab6da412fb8637393c5a17a1b293663```
```
└─$ git grep -n 'func providerSource(.*)'                                                                          
provider_source.go:23:func providerSource(configs []*cliconfig.ProviderInstallation, services *disco.Disco) (getproviders.Source, tfdiags.Diagnostics) {
```
```
└─$ git blame -L 23,23 provider_source.go                                                                        
5af1e6234ab (Martin Atkins 2020-04-21 16:28:59 -0700 23) func providerSource(configs []*cliconfig.ProviderInstallation, services *disco.Disco) (getproviders.Source, tfdiags.Diagnostics) {
```

 * *Найдите все коммиты, в которых была изменена функция* **globalPluginDirs**.
```
└─$ git grep 'func globalPluginDirs(.*)'
plugins.go:func globalPluginDirs() []string {
```
```
└─$  git log -L :globalPluginDirs:plugins.go  -s --oneline                                                         
78b1220558 Remove config.go and update things using its aliases
52dbf94834 keep .terraform.d/plugins for discovery
41ab0aef7a Add missing OS_ARCH dir to global plugin paths
66ebff90cd move some more plugin search path logic to command
8364383c35 Push plugin discovery down into command package
```
 * *Кто автор функции* **synchronizedWriters**?
```
└─$ git log -S "func synchronizedWriters" --oneline
bdfea50cc8 remove unused
5ac311e2a9 main: synchronize writes to VT100-faker on Windows
```
```
└─$ git show 5ac311e2a9 -s
commit 5ac311e2a91e381e2f52234668b49ba670aa0fe5
Author: Martin Atkins <mart@degeneration.co.uk>
Date:   Wed May 3 16:25:41 2017 -0700
```
*В качестве решения ответьте на вопросы и опишите, как были получены эти ответы*?
