[![logo](https://github.com/ShchegolevYA/Developer/blob/main/Aleo/Leo/png/Leo_Installation.png)](https://developer.aleo.org/leo)

<div style="text-align: center;">

[![Website](https://img.shields.io/badge/-Website-1A4468?style=for-the-badge&logo=Website&logoColor=27A0D9)]( https://www.aleo.org/)
[![GitHub](https://img.shields.io/badge/-GitHub-1A4468?style=for-the-badge&logo=GitHub&logoColor=12141D)](https://github.com/AleoHQ)
[![Twitter](https://img.shields.io/badge/-Twitter-1A4468?style=for-the-badge&logo=Twitter&logoColor=1C9DEB)](https://twitter.com/AleoHQ)
[![Community Twitter](https://img.shields.io/badge/-Community_Twitter-1A4468?style=for-the-badge&logo=Twitter&logoColor=1C9DEB)](https://twitter.com/aleocommunity)
[![LinkedIn](https://img.shields.io/badge/-LinkedIn-1A4468?style=for-the-badge&logo=linkedin&logoColor=007BB6)](https://www.linkedin.com/company/aleohq/)
[![YouTube](https://img.shields.io/badge/-YouTube-1A4468?style=for-the-badge&logo=YouTube&logoColor=FF0000)]( https://www.youtube.com/channel/UCS_HKT2heOC_q88YQLiJt0g)
[![Community_Forum](https://img.shields.io/badge/-Community_Forum-1A4468?style=for-the-badge&logo=Website&logoColor=27A0D9)](https://community.aleo.org/)
[![Community_Calendar](https://img.shields.io/badge/-Community_Calendar-1A4468?style=for-the-badge&logo=Website&logoColor=27A0D9)](https://www.aleo.org/community/calendar)
[![Developer_Documentation](https://img.shields.io/badge/-Developer_Documentation-1A4468?style=for-the-badge&logo=Website&logoColor=27A0D9)](https://developer.aleo.org/)
[![Community_Blog](https://img.shields.io/badge/-Community_Blog-1A4468?style=for-the-badge&logo=Website&logoColor=27A0D9)](https://medium.com/@AleoHQ)
[![Announcements_Blog](https://img.shields.io/badge/-Announcements_Blog-1A4468?style=for-the-badge&logo=Website&logoColor=27A0D9)](https://www.aleo.org/blog)


</div>


> `[ВНИМАНИЕ]` Язык Leo в настоящее время находится в активной разработке. Пожалуйста, следите за репозиторием на [GitHub](https://github.com/AleoHQ/leo) на предмет возможных критических изменений.

# Установка
## 1. Подготовка (установка необходимых компонентов)
### 1.1 Устанавливаем Git:
Скачиваем гид с [официального сайта](https://bit.ly/start-git) и устанавливаем на свой ПК.
### 1.2 Устанавливаем Rust:
Вы можете обратиться к [официальному источнику](https://bit.ly/start-rust)  или выполнить в терминале следующию команду: 
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
### 1.2 После установки проверяем версии:
```
git --version
cargo --version
```
> `[ВНИМАНИЕ]` Узнать актуальные версии можно здесь \> [bit.ly/start-git](https://bit.ly/start-git) и [bit.ly/start-rust.](https://bit.ly/start-rust)

## 2. Собираем Leo
Необходимо выполнить следующие команды:

Клонируем дерикторию с GitHub
```
git clone https://github.com/AleoHQ/leo
cd leo
```

Устанавливаем Leo
```
cargo install --path .
```
Это сгенерирует исполняемый файл `~/.cargo/bin/leo.`

Теперь вы можете использовать Leo, запустив команду:

```
leo
```
## 3. Подсветка синтаксиса IDE (интегрированной среды разработки)
Aleo поддерживает реализацию подсветки синтаксиса на разных платформах.

> `[ВАЖНО]` Если вы не видите необходимого вам редактора в этом списке, обратитесь на [GitHub.](https://github.com/AleoHQ/welcome/issues/new)

* [Sublime Text](https://developer.aleo.org/leo/tooling#sublime-text)
* [Visual Studio Code](https://developer.aleo.org/leo/tooling#vs-code)
* [Intellij](https://developer.aleo.org/leo/tooling#intellij)

