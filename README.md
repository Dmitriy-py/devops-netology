# Домашнее задание к занятию «Системы контроля версий»
### Дмитрий Климов

## .gitignore

Файл `.gitignore` используется для указания Git, какие файлы и каталоги следует игнорировать. Благодаря `.gitignore` в корне репозитория и в каталоге `terraform`, следующие типы файлов будут автоматически исключены из отслеживания Git:

*   **В корне репозитория:** (`.gitignore`)
*   **В каталоге `terraform`:** Файлы, связанные с Terraform, такие как:
*   **Файлы состояния Terraform (`*.tfstate`, `*.tfstate.backup`):** Это самые важные файлы. Они содержат текущее состояние инфраструктуры, которое Terraform управляет. Эти файлы могут содержать чувствительную информацию (например, IP-адреса, имена ресурсов) и должны          храниться отдельно от кода, часто в удаленных бекендах.
*   **Файлы переменных (`*.tfvars`, `*.auto.tfvars`, `*.auto.tfvars.json`):** Эти файлы содержат значения переменных, используемые Terraform. Подобно файлам состояния, они могут содержать конфиденциальные данные (например, ключи API, пароли) и не должны попадать в             репозиторий.
*   **Кешированные файлы Terraform (`.terraform/`):** Это каталог, который Terraform создает для хранения загруженных провайдеров и модулей. Он может быть большим и легко восстанавливается из других источников, поэтому его лучше игнорировать.
*   **Временные файлы Terraform (`*.terraform`):** Это различные временные файлы, которые Terraform может создавать в процессе работы.
*   **Исполняемые файлы Terraform (`*.terraform/bin/`):** Иногда Terraform может устанавливать исполняемые файлы в эту директорию.

### Это помогает поддерживать чистоту репозитория, избегать случайного коммита чувствительных данных или файлов, которые должны генерироваться или управляться отдельно от основного кода.



<img width="1920" height="1080" alt="Снимок экрана (1489)" src="https://github.com/user-attachments/assets/c18230fc-bc62-4624-9937-64b7aef55170" />

<img width="1920" height="1080" alt="Снимок экрана (1490)" src="https://github.com/user-attachments/assets/b3c7be58-0913-47e9-b85c-ab607b4a88e4" />

<img width="1920" height="1080" alt="Снимок экрана (1491)" src="https://github.com/user-attachments/assets/2cbf247d-2793-4fef-b5aa-778b7eab261f" />

<img width="1920" height="1080" alt="Снимок экрана (1492)" src="https://github.com/user-attachments/assets/d6cabb1f-627d-4b0d-b200-ae94294482e6" />

<img width="1920" height="1080" alt="Снимок экрана (1493)" src="https://github.com/user-attachments/assets/04826b20-cf04-4e23-bfe7-03f1b360d8ab" />

<img width="1920" height="1080" alt="Снимок экрана (1494)" src="https://github.com/user-attachments/assets/1af8d7e4-4f9c-42c0-b205-093a3d47213f" />

<img width="1920" height="1080" alt="Снимок экрана (1495)" src="https://github.com/user-attachments/assets/2ec00122-f500-45f2-b1e7-1ab02969fab1" />

<img width="1920" height="1080" alt="Снимок экрана (1500)" src="https://github.com/user-attachments/assets/4ecbbf87-1860-41b3-b3e4-b1ed9f13718c" />

<img width="1920" height="1080" alt="Снимок экрана (1501)" src="https://github.com/user-attachments/assets/f4e42fa8-0558-4efa-9331-6df89245b20f" />




