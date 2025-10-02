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

### **Часть 5. Промежуточный итог и Merge**

**Промежуточный итог: Схема коммитов**

<img width="1920" height="1080" alt="Снимок экрана (1549)" src="https://github.com/user-attachments/assets/0a7715a5-a713-4146-a104-83a978ea9172" />

**Merge ветки `git-merge` в `main`**

1.  **Команды слияния и пуша:**
    ```bash
    git checkout main
    git merge git-merge

<img width="1920" height="1080" alt="Снимок экрана (1550)" src="https://github.com/user-attachments/assets/2c49b458-a1a2-4016-a096-8d9cd79217ce" />


    git push origin main
    git push gitlab main
    ```

 ### **Часть 6. Rebase и финальное слияние**

**Шаг 1-6. Rebase ветки `git-rebase` на `main` и разрешение конфликтов**

1.  **Команды и выводы:**
    ```bash
    git checkout git-rebase
    git rebase -i main

<img width="1920" height="1080" alt="Снимок экрана (1552)" src="https://github.com/user-attachments/assets/408185f4-ca14-4d48-9ecf-a89d6ae0abf5" />

    nano branching/rebase.sh
    git add branching/rebase.sh
    git rebase --continue

<img width="1920" height="1080" alt="Снимок экрана (1553)" src="https://github.com/user-attachments/assets/3b8b0e73-eddf-4945-a7fd-6cbe305a70ac" />


    nano branching/rebase.sh
    git add branching/rebase.sh
    git rebase --continue

<img width="1920" height="1080" alt="Снимок экрана (1554)" src="https://github.com/user-attachments/assets/ca94405d-ab18-4c11-87ef-beaf32de12f0" />

    ```

1.  **Содержимое `branching/rebase.sh` после разрешения всех конфликтов (финальная версия в `git-rebase`):**
    ```bash
    #!/bin/bash
    # display command line options

    count=1
    for param in "$@"; do
        echo "Next parameter: $param"
        count=$(( $count + 1 ))
    done

    echo "====="
    ```

**Шаг 7-8. Отправка перебазированной ветки `git-rebase` с `force`**

1.  **Команды и выводы:**
    ```bash
    git push -u origin git-rebase # Ожидаемая ошибка rejected

<img width="1920" height="1080" alt="Снимок экрана (1555)" src="https://github.com/user-attachments/assets/421392de-3d21-42ac-93f2-70832bf7007c" />

    
    git push -u origin git-rebase -f # Принудительная отправка

<img width="1920" height="1080" alt="Снимок экрана (1556)" src="https://github.com/user-attachments/assets/2bf9722c-26fb-444e-8c17-aec3b5549ac0" />


    ```

  **Шаг 9. Слияние `git-rebase` в `main`**

1.  **Команды слияния и пуша:**
    ```bash
    git checkout main
    git merge git-rebase
    # Вывод: Merge made by the 'ort' strategy. branching/rebase.sh | 2 +-
    git push origin main
    git push gitlab main
    ```

<img width="1920" height="1080" alt="Снимок экрана (1558)" src="https://github.com/user-attachments/assets/2fceaaf6-75b8-47b7-87d6-7158d8376e6f" />


<img width="1920" height="1080" alt="Снимок экрана (1559)" src="https://github.com/user-attachments/assets/3f731a00-bbe0-4960-87f4-345929240983" />


<img width="1920" height="1080" alt="Снимок экрана (1560)" src="https://github.com/user-attachments/assets/44cb43e0-7e85-448c-8863-2fed95f9052b" />



