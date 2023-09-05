# Домашнее задание к занятию "`Инструменты Git`" - `Барышников Никита`

### 1. Найдите полный хеш и комментарий коммита, хеш которого начинается на `aefea`

Решение:

Для нахождения полного хеша и комментария коммита, хеш которого начинается на `aefea` используем команду
```
git show --no-patch --pretty=format:"Hash: %H Comment: %s" aefea
```

Скриншот-1 - Скриншот результата вывода команды git show --no-patch --pretty=format:"Hash: %H Comment: %s" aefea
![Скриншот-1](https://github.com/BaryshnikovNV/version-control-systems/blob/main/14.4-git-tools/img/14.4.1_Скриншот_полного_хеша_и_комментария_коммита.png)

Таким образом, полный хеш коммита `aefead2207ef7e2aa5dc81a34aedf0cad4c32545`, а комментарий коммита `Update CHANGELOG.md`.

---

### 2. Какому тегу соответствует коммит `85024d3`?

Решение:

Для нахождения тега коммита `85024d3` воспользуемся командой
```
git show --no-patch 85024d3
```

Скриншот-2 - Скриншот результата вывода команды git show --no-patch 85024d3
![Скриншот-2](https://github.com/BaryshnikovNV/version-control-systems/blob/main/14.4-git-tools/img/14.4.2_Скриншот_тега_коммита_85024d3.png)

Тег `v0.12.23`

---

### 3. Сколько родителей у коммита `b8d720`? Напишите их хеши.

Решение:

Для нахождения родителей коммита `b8d720` воспользуемся командой
```
git show --pretty=format:"Hash: %H%nParents: %P" b8d720
```

Скриншот-3 - Скриншот результата вывода команды git show --pretty=format:"Hash: %H%nParents: %P" b8d720
![Скриншот-3](https://github.com/BaryshnikovNV/version-control-systems/blob/main/14.4-git-tools/img/14.4.3_Скриншот_вывода_родителей_коммита_b8d720.png)

Коммит `b8d720` иммет 2 родителей с коммитами `56cd7859e05c36c06b56d013b55a252d0bb7e158` и `9ea88f22fc6269854151c571162c5bcf958bee2b`.

---

### 4. Перечислите хеши и комментарии всех коммитов, которые были сделаны между тегами v0.12.23 и v0.12.24.

Решение:

Для вывода всех хешей и комментарий всех коммитов, которые были сделаны между тегами v0.12.23 и v0.12.24 воспользуемся командой
```
git log --pretty=oneline v0.12.23...v0.12.24
```

Скриншот-4 - Скриншот результата вывода команды git log --pretty=oneline v0.12.23...v0.12.24
![Скриншот-4](https://github.com/BaryshnikovNV/version-control-systems/blob/main/14.4-git-tools/img/14.4.4_Скриншот_вывода_хешей_и_комментарий.png)

Все коммиты и хешы между тегами v0.12.23 и v0.12.24 представлены на скриншоте 4.

---

### 5. Найдите коммит, в котором была создана функция `func providerSource`, её определение в коде выглядит так: `func providerSource(...)` (вместо троеточия перечислены аргументы).

Решение:

Для нахождения коммита, в котором была создана функция `func providerSource` воспользуемся командой 
```
git log -S 'func providerSource(' --oneline
```

Скриншот-5 - Скриншот результата вывода команды git log -S 'func providerSource(' --oneline
![Скриншот-5](https://github.com/BaryshnikovNV/version-control-systems/blob/main/14.4-git-tools/img/14.4.5_Скриншот_вывода_коммита_в_котором_была_создана_функция_func_providerSource.png)

Коммит в котором была создана функция `func providerSource` имеет хеш 8c928e8358.

---

### 6. Найдите все коммиты, в которых была изменена функция `globalPluginDirs`.

Решение:

Для нахождения коммитов, в которых была изменена функция `globalPluginDirs` воспользуемся командами 
```
git grep -n 'func globalPluginDirs('
```
и
```
git log --no-patch --oneline -L :globalPluginDirs:plugins.go
```

Скриншот-6 - Скриншот вывода команд для нахождения коммитов, в которых была изменена функция `globalPluginDirs`
![Скриншот-6](https://github.com/BaryshnikovNV/version-control-systems/blob/main/14.4-git-tools/img/14.4.6_Скриншот_вывода_команд_для_нахождения_всех_коммитов_в_которых_была_изменена_функция_globalPluginDir.png)

Коммиты в которых была изменена функция `globalPluginDirs` представлены на скриншоте 6.

---

### 7. Кто автор функции `synchronizedWriters`?

Решение:

Для автора функция `synchronizedWriters` воспользуемся командой 
```
git log -S 'func synchronizedWriters(' --pretty=format:"%h %an %ad %s"
```

Скриншот-7 - Скриншот результата вывода команды git log -S 'func synchronizedWriters(' --pretty=format:"%h %an %ad %s"
![Скриншот-7](https://github.com/BaryshnikovNV/version-control-systems/blob/main/14.4-git-tools/img/14.4.7_Скриншот_вывода_команды_для_нахождения_автора_функции.png)

Автор функции `synchronizedWriters` является Martin Atkins.

---