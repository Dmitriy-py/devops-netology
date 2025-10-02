# Домашнее задание к занятию «Ветвления в Git»

### ` Дмитрий Климов `

## Задание «Ветвление, merge и rebase»

### **Часть 1. Начальная подготовка**

**Шаг 1. Создание каталога `branching` и файлов `merge.sh`, `rebase.sh`**

**Содержимое `branching/merge.sh` :**
    ```bash
    #!/bin/bash
    # display command line options

    count=1
    for param in "$*"; do
        echo "\$* Parameter #$count = $param"
        count=$(( $count + 1 ))
    done
    ```
3.  **Содержимое `branching/rebase.sh` :**
    ```bash
    #!/bin/bash
    # display command line options

    count=1
    for param in "$*"; do
        echo "\$* Parameter #$count = $param"
        count=$(( $count + 1 ))
    done
    ```

<img width="1920" height="1080" alt="Снимок экрана (1539)" src="https://github.com/user-attachments/assets/6f6c772f-4427-4d7f-b580-da21b1f66c03" />

<img width="1920" height="1080" alt="Снимок экрана (1541)" src="https://github.com/user-attachments/assets/06a2eea5-d0ba-482a-b2ee-89837e0341b6" />

<img width="1920" height="1080" alt="Снимок экрана (1542)" src="https://github.com/user-attachments/assets/0c302f55-a957-49f6-b922-984b37f40d2d" />

<img width="1920" height="1080" alt="Снимок экрана (1543)" src="https://github.com/user-attachments/assets/2b416f22-092b-4c52-9847-40cc40d6d0c9" />

<img width="1920" height="1080" alt="Снимок экрана (1544)" src="https://github.com/user-attachments/assets/e4493f1b-039e-4be6-9153-e683d5044d2f" />

<img width="1920" height="1080" alt="Снимок экрана (1546)" src="https://github.com/user-attachments/assets/1c4f830a-5c4d-44bd-97b8-6f34889fa665" />

<img width="1920" height="1080" alt="Снимок экрана (1547)" src="https://github.com/user-attachments/assets/7d69cd66-0956-44a5-b33f-a386e1f8b799" />

<img width="1920" height="1080" alt="Снимок экрана (1549)" src="https://github.com/user-attachments/assets/0a7715a5-a713-4146-a104-83a978ea9172" />

<img width="1920" height="1080" alt="Снимок экрана (1550)" src="https://github.com/user-attachments/assets/5fbda66d-ea39-48e3-884b-7854b9058ba0" />

<img width="1920" height="1080" alt="Снимок экрана (1551)" src="https://github.com/user-attachments/assets/23795a92-21e4-4515-bdf6-37ec61d2d234" />

<img width="1920" height="1080" alt="Снимок экрана (1552)" src="https://github.com/user-attachments/assets/efc7f647-1f5d-4f92-bea0-382cfa85a34a" />

<img width="1920" height="1080" alt="Снимок экрана (1553)" src="https://github.com/user-attachments/assets/28e0b35a-88c6-4c01-a8c7-d07289041f07" />

<img width="1920" height="1080" alt="Снимок экрана (1554)" src="https://github.com/user-attachments/assets/72f1e0f9-a8a4-4786-8c80-fbfe9f13181e" />

<img width="1920" height="1080" alt="Снимок экрана (1555)" src="https://github.com/user-attachments/assets/a455f523-7d6b-47e3-a453-b828a1e07661" />

<img width="1920" height="1080" alt="Снимок экрана (1556)" src="https://github.com/user-attachments/assets/f4ff3969-0d40-4bf2-9f87-8ffa451785f2" />

<img width="1920" height="1080" alt="Снимок экрана (1557)" src="https://github.com/user-attachments/assets/15a355a6-1e8e-43fa-ba06-927b6a1665d1" />

<img width="1920" height="1080" alt="Снимок экрана (1558)" src="https://github.com/user-attachments/assets/e8975bef-8392-4d8a-bd9f-35ea7300220e" />

