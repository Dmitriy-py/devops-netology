# Домашнее задание к занятию «Системы контроля версий»
### Дмитрий Климов

## .gitignore

Файл `.gitignore` используется для указания Git, какие файлы и каталоги следует игнорировать. Благодаря `.gitignore` в корне репозитория и в каталоге `terraform`, следующие типы файлов будут автоматически исключены из отслеживания Git:

*   **В корне репозитория:** (`.gitignore`)
*   
*   **В каталоге `terraform`:** Файлы исключаются по следующим правилам:
    *   `*.tfstate`: Игнорируются все файлы, имена которых заканчиваются на `.tfstate`.
    *   `*.tfstate.backup`: Игнорируются все файлы, имена которых заканчиваются на `.tfstate.backup`.
    *   `*.tfvars`: Игнорируются все файлы, имена которых заканчиваются на `.tfvars`.
    *   `*.auto.tfvars`: Игнорируются все файлы, имена которых заканчиваются на `.auto.tfvars`.
    *   `*.auto.tfvars.json`: Игнорируются все файлы, имена которых заканчиваются на `.auto.tfvars.json`.
    *   `.terraform/`: Игнорируется каталог с именем `.terraform` и все его содержимое.
    *   `*.terraform`: Игнорируются все файлы, имена которых заканчиваются на `.terraform`
    *   `*.terraform/bin/`: Игнорируются все файлы внутри каталога `bin`, который находится внутри каталога `.terraform`.

Это помогает поддерживать чистоту репозитория, избегать случайного коммита файлов, которые должны генерироваться или управляться отдельно от основного кода.



<img width="1920" height="1080" alt="Снимок экрана (1489)" src="https://github.com/user-attachments/assets/c18230fc-bc62-4624-9937-64b7aef55170" />

<img width="1920" height="1080" alt="Снимок экрана (1490)" src="https://github.com/user-attachments/assets/b3c7be58-0913-47e9-b85c-ab607b4a88e4" />

<img width="1920" height="1080" alt="Снимок экрана (1491)" src="https://github.com/user-attachments/assets/2cbf247d-2793-4fef-b5aa-778b7eab261f" />

<img width="1920" height="1080" alt="Снимок экрана (1492)" src="https://github.com/user-attachments/assets/d6cabb1f-627d-4b0d-b200-ae94294482e6" />

<img width="1920" height="1080" alt="Снимок экрана (1493)" src="https://github.com/user-attachments/assets/04826b20-cf04-4e23-bfe7-03f1b360d8ab" />

<img width="1920" height="1080" alt="Снимок экрана (1494)" src="https://github.com/user-attachments/assets/1af8d7e4-4f9c-42c0-b205-093a3d47213f" />

<img width="1920" height="1080" alt="Снимок экрана (1495)" src="https://github.com/user-attachments/assets/2ec00122-f500-45f2-b1e7-1ab02969fab1" />

<img width="1920" height="1080" alt="Снимок экрана (1500)" src="https://github.com/user-attachments/assets/4ecbbf87-1860-41b3-b3e4-b1ed9f13718c" />

<img width="1920" height="1080" alt="Снимок экрана (1501)" src="https://github.com/user-attachments/assets/f4e42fa8-0558-4efa-9331-6df89245b20f" />




