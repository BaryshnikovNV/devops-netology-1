# devops-netology

Hello world!

В каталоге [terraform](https://github.com/BaryshnikovNV/version-control-systems/blob/main/1-git-vcs/terraform) создан файл `.gitignore` с конфигурацией [Terraform.gitignore](https://github.com/BaryshnikovNV/version-control-systems/blob/main/1-git-vcs/terraform/Terraform.gitignore). В результате внутри каталога terraform git не будет учитывать любые изменения для файлов/каталогов:

* Все подкаталоги `.terraform`.
* Файлы с расширением `.tfstate` и `.tfstate.*`.
* Файл лога `crash.log`.
* Файлы с расширением `.tfvars` (файлы с чувствительными данными).
* Файлы переопределения `override.tf` и др.
* Файлы командной строки `.terraformrc` и `terraform.rc`.