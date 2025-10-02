# Домашнее задание к занятию «Ветвления в Git»

### ` Дмитрий Климов `

## Задание «Ветвление, merge и rebase»

### **Часть 1. Начальная подготовка**

**Шаг 1. Создание каталога `branching` и файлов `merge.sh`, `rebase.sh`**

**Содержимое `branching/merge.sh` :**
   
    ```
    bash
    #!/bin/bash
    # display command line options

    count=1
    for param in "$*"; do
        echo "\$* Parameter #$count = $param"
        count=$(( $count + 1 ))
    done
    ```
**Содержимое `branching/rebase.sh` :**

     ```
     bash
    #!/bin/bash
    # display command line options

    count=1
    for param in "$*"; do
        echo "\$* Parameter #$count = $param"
        count=$(( $count + 1 ))
    done
    ```

**Шаг 2. Создание коммита `prepare for merge and rebase` и отправка его в `main`**

<img width="1920" height="1080" alt="Снимок экрана (1539)" src="https://github.com/user-attachments/assets/6f6c772f-4427-4d7f-b580-da21b1f66c03" />

<img width="1920" height="1080" alt="Снимок экрана (1541)" src="https://github.com/user-attachments/assets/d9cfac39-b513-40ed-99a4-de013c552210" />

### **Часть 2. Подготовка файла `merge.sh` (ветка `git-merge`)**

**Шаг 1. Создание ветки `git-merge`**

1.  **Команда создания ветки:**
    ```bash
    git switch -c git-merge
    ```

**Шаг 2-3. Изменение `merge.sh` ( `@ instead *` )**

1.  **Измененное содержимое `branching/merge.sh`:**
    ```bash
    #!/bin/bash
    # display command line options

    count=1
    for param in "$@"; do
        echo "\$@ Parameter #$count = $param"
        count=$(( $count + 1 ))
    done
    ```
2.  **Команды коммита и пуша:**
    ```bash
    git add branching/merge.sh
    git commit -m "merge: @ instead *"
    git push -u origin git-merge
    git push -u gitlab git-merge
    ```

**Шаг 4-5. Изменение `merge.sh` ( `use shift` )**

1.  **Измененное содержимое `branching/merge.sh`:**
    ```bash
    #!/bin/bash
    # display command line options

    count=1
    while [[ -n "$1" ]]; do
        echo "Parameter #$count = $1"
        count=$(( $count + 1 ))
        shift
    done
    ```
2.  **Команды коммита и пуша:**
    ```bash
    git add branching/merge.sh
    git commit -m "merge: use shift"
    git push origin git-merge
    git push gitlab git-merge
    ```

---


<img width="1920" height="1080" alt="Снимок экрана (1546)" src="https://github.com/user-attachments/assets/1c4f830a-5c4d-44bd-97b8-6f34889fa665" />

### **Часть 3. Изменения в `main`**

**Шаг 1-2. Возврат в `main` и изменение `rebase.sh`**

1.  **Команда возврата в `main`:**
    ```bash
    git checkout main
    ```
2.  **Измененное содержимое `branching/rebase.sh`:**
    ```bash
    #!/bin/bash
    # display command line options

    count=1
    for param in "$@"; do
        echo "\$@ Parameter #$count = $param"
        count=$(( $count + 1 ))
    done

    echo "====="
    ```

**Шаг 3. Отправка измененной `main`**

1.  **Команды коммита и пуша:**
    ```bash
    git add branching/rebase.sh
    git commit -m "main: added echo separator"
    git push origin main
    git push gitlab main
    ```

---

### **Часть 4. Подготовка файла `rebase.sh` (ветка `git-rebase`)**

**Шаг 1-2. Создание ветки `git-rebase` от коммита `prepare for merge and rebase`**

1.  **Команды:**
    ```bash
    git checkout ee8b901
    git switch -c git-rebase
    ```

**Шаг 3-4. Изменение `rebase.sh` ( `git-rebase 1` )**

1.  **Измененное содержимое `branching/rebase.sh`:**
    ```bash
    #!/bin/bash
    # display command line options

    count=1
    for param in "$@"; do
        echo "Parameter: $param"
        count=$(( $count + 1 ))
    done
    ```
2.  **Команды коммита и пуша:**
    ```bash
    git add branching/rebase.sh
    git commit -m "git-rebase 1"
    git push -u origin git-rebase -f
    git push -u gitlab git-rebase -f
    ```

**Шаг 5-6. Изменение `rebase.sh` ( `git-rebase 2` )**

1.  **Измененное содержимое `branching/rebase.sh`:**
    ```bash
    #!/bin/bash
    # display command line options

    count=1
    for param in "$@"; do
        echo "Next parameter: $param"
        count=$(( $count + 1 ))
    done
    ```
2.  **Команды коммита и пуша:**
    ```bash
    git add branching/rebase.sh
    git commit -m "git-rebase 2"
    git push origin git-rebase -f
    git push gitlab git-rebase -f
    ```

---


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

