# Домашнее задание к занятию «Инструменты Git»

## ` Дмитрий Климов `

## Задание

В клонированном репозитории:

Найдите полный хеш и комментарий коммита, хеш которого начинается на aefea.

## Ответьте на вопросы.

1. Какому тегу соответствует коммит 85024d3?
2. Сколько родителей у коммита b8d720? Напишите их хеши.
3. Перечислите хеши и комментарии всех коммитов, которые были сделаны между тегами v0.12.23 и v0.12.24.
4. Найдите коммит, в котором была создана функция func providerSource, её определение в коде выглядит так: func                    providerSource(...) (вместо троеточия перечислены аргументы).
5. Найдите все коммиты, в которых была изменена функция globalPluginDirs.
6. Кто автор функции synchronizedWriters?


## Ответы:

## 1. Найдите полный хеш и комментарий коммита, хеш которого начинается на aefea:

### Команда: ### ` git show aefea `
### Вывод:
```
commit aefead2207ef7e2aa5dc81a34aedf0cad4c32545
Author: Alisdair McDiarmid <alisdair@users.noreply.github.com>
Date:   Thu Jun 18 10:29:58 2020 -0400

    Update CHANGELOG.md


```

### Полный хеш: ` aefead2207ef7e2aa5dc81a34aedf0cad4c32545 `
### Комментарий: ` Update CHANGELOG.md `

## 2. Какому тегу соответствует коммит 85024d3?

### Команда: ### ` git log 85024d3 --oneline `
### Вывод:
```
85024d3100 (tag: v0.12.23) v0.12.23

```

### коммит 85024d3 соответствует тегу: ` v0.12.23 `

## 3. Сколько родителей у коммита b8d720? Напишите их хеши.

### Команда: ### ` git show b8d720 `
### Вывод:

```
commit b8d720f8340221f2146e4e4870bf2ee0bc48f2d5
Merge: 56cd7859e0 9ea88f22fc
Author: Chris Griggs <cgriggs@hashicorp.com>
Date:   Tue Jan 21 17:45:48 2020 -0800

```
Merge: 56cd7859e0 9ea88f22fc- указывает на количество родителей 2

### Команда: ### ` git show b8d720^1 `
### Вывод:

```
commit 56cd7859e05c36c06b56d013b55a252d0bb7e158
Merge: 58dcac4b79 ffbcf55817
Author: Chris Griggs <cgriggs@hashicorp.com>
Date:   Mon Jan 13 13:19:09 2020 -0800

```
### Узнали полный хеш коммита-1

### Команда: ### ` git show b8d720^2 `
### Вывод:

```
commit 9ea88f22fc6269854151c571162c5bcf958bee2b
Author: Chris Griggs <cgriggs@hashicorp.com>
Date:   Tue Jan 21 17:08:06 2020 -0800

```
### Узнали полный хеш коммита-2

### Родителей двое
### Хеш первого: ` 56cd7859e05c36c06b56d013b55a252d0bb7e158 `
### Хеш второго: ` 9ea88f22fc6269854151c571162c5bcf958bee2b `

## 5. Перечислите хеши и комментарии всех коммитов, которые были сделаны между тегами v0.12.23 и v0.12.24.

### Команда: ### ` git log v0.12.23..v0.12.24 --pretty=format:"%H %s" `
### Вывод:

```
33ff1c03bb960b332be3af2e333462dde88b279e v0.12.24
b14b74c4939dcab573326f4e3ee2a62e23e12f89 [Website] vmc provider links
3f235065b9347a758efadc92295b540ee0a5e26e Update CHANGELOG.md
6ae64e247b332925b872447e9ce869657281c2bf registry: Fix panic when server is unreachable
5c619ca1baf2e21a155fcdb4c264cc9e24a2a353 website: Remove links to the getting started guide's old location
06275647e2b53d97d4f0a19a0fec11f6d69820b5 Update CHANGELOG.md
d5f9411f5108260320064349b757f55c09bc4b80 command: Fix bug when using terraform login on Windows
4b6d06cc5dcb78af637bbb19c198faff37a066ed Update CHANGELOG.md
dd01a35078f040ca984cdd349f18d0b67e486c35 Update CHANGELOG.md
225466bc3e5f35baa5d07197bbc079345b77525e Cleanup after v0.12.23 release

```
### Коммитов, которые были сделаны между тегами v0.12.23 и v0.12.24

#### 33ff1c03bb960b332be3af2e333462dde88b279e ` v0.12.24 `
#### b14b74c4939dcab573326f4e3ee2a62e23e12f89 ` [Website] vmc provider links `
#### 3f235065b9347a758efadc92295b540ee0a5e26e ` Update CHANGELOG.md `
#### 6ae64e247b332925b872447e9ce869657281c2bf ` registry: Fix panic when server is unreachable `
#### 5c619ca1baf2e21a155fcdb4c264cc9e24a2a353 ` website: Remove links to the getting started guide's old location `
#### 06275647e2b53d97d4f0a19a0fec11f6d69820b5 ` Update CHANGELOG.md `
#### d5f9411f5108260320064349b757f55c09bc4b80 ` command: Fix bug when using terraform login on Windows `
#### 4b6d06cc5dcb78af637bbb19c198faff37a066ed ` Update CHANGELOG.md `
#### dd01a35078f040ca984cdd349f18d0b67e486c35 ` Update CHANGELOG.md `
#### 225466bc3e5f35baa5d07197bbc079345b77525e ` Cleanup after v0.12.23 release `

## 6. Найдите коммит, в котором была создана функция func providerSource, её определение в коде выглядит так: func                    providerSource(...) (вместо троеточия перечислены аргументы).

<img width="1920" height="1080" alt="Снимок экрана (1571)" src="https://github.com/user-attachments/assets/784063bb-7b17-4c76-aa0b-c330c5f17afa" />

### Коммит, в котором была создана функция func providerSource
### ` commit 8c928e83589d90a031f811fae52a81be7153e82f `

## 7. Найдите все коммиты, в которых была изменена функция globalPluginDirs.

<img width="1920" height="1080" alt="Снимок экрана (1572)" src="https://github.com/user-attachments/assets/e6b6ac13-53ef-4a59-b6f8-1bec6b0c2208" />

### коммиты, в которых была изменена функция globalPluginDirs
* #### ` 22a2580e93170eac46621ab97decaec989d52edb `
* #### ` 35a058fb3ddfae9cfee0b3893822c9a95b920f4c `
* #### ` c0b17610965450a89598da491ce9b6b5cbd6393f `
* #### ` 8364383c359a6b738a436d1b7745ccdce178df47 `

 ## 8. Кто автор функции synchronizedWriters?

<img width="1920" height="1080" alt="Снимок экрана (1573)" src="https://github.com/user-attachments/assets/a87992fb-0a09-4628-acd2-ad05906328dd" />

### Author: ` Martin Atkins <mart@degeneration.co.uk> ` так как у него был самый ранний коммит с этой функцией...



