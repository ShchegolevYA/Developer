[![logo](https://github.com/ShchegolevYA/Developer/blob/main/Aleo/Leo/png/Hello_Leo.png)](https://developer.aleo.org/leo/hello)

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

# Привет Leo (Hello Leo)
Используйте интерфейс командной строки Leo `(CLI)` для создания нового проекта. Для этого в вашем терминале выполните следующие команды:
```
leo new hello
cd hello
```
Это создает каталог со следующей структурой:
```
hello/
├── program.json # Your program manifest
├── README.md # Your program description
├── build/
├── inputs/
│ ├── hello.in # Your program inputs
└── src/
  └── main.leo # Your program file
```
Запустим проект.

## Нулевое знание (Zero Knowledge (Zk)) в одной строке
Команда `leo run` скомпилирует и выполнит программу. Для этого в вашем терминале выполните следующую команду:
```
leo run main
```
**вывод консоли:**
```
Leo Compiled 'main.leo' into Aleo instructions
⏳ Compiling 'hello.aleo'...

 • Loaded universal setup (in 100 ms)
 • Built 'main' (in 1000 ms)

     Build ✅ Built 'hello.aleo' (in "/hello/build")
 • Loaded universal setup (in 100 ms)
🚀 Executing 'hello.aleo/main'...

 • Executing 'hello.aleo/main'...
 • Executed 'main' (in 1000 ms)

➡️  Output

 • 3u32

 Executing ✅ Executed 'hello.aleo/main' (in "/hello/build")
```
> `Поздравляем!` Вы только что запустили свою первую программу `Leo`.

Давайте пройдемся по синтаксису файла программы, которую мы только что выполнили.

`Program.json` — это файл манифеста `Leo`, который настраивает наш пакет.

**Program.json**
```
{
    "program": "hello.aleo",
    "version": "0.0.0",
    "description": "",
    "development": {
        "private_key": "APrivateKey1zkp2VZTNU45XjpcRDbe5yg3b5L7XVvB4zrFPtw1NAYvmhJx",
        "address": "aleo15egrwaxaherd70ca0aln3th7ry7dmtfeggf8jm3saxeddpa6dsqsye9u3m"
    },
    "license": "MIT"
}
```
Идентификатор программы (ID) в `program` — это официальное имя, которое другие разработчики смогут найти после того, как вы опубликуете свою программу.
```
"program": "hello.aleo",
```
Все файлы в текущем пакете будут скомпилированы с указанной версией (`version`) Leo.
```
"version": "0.0.0",
```
## Синтаксис для схем

Откройте `src/main.leo`. Файл `main.leo` — это точка входа в проект Leo. Он часто содержит функцию с именем `main`. Давайте разберем структуру файла Leo.

**src/main.leo**
```
// The 'hello' program.
program hello.aleo {
    transition main(public a: u32, b: u32) -> u32 {
        let c: u32 = a + b;
        return c;
    }
}
```
`program hello.aleo {` определяет имя [программы](https://developer.aleo.org/leo/language#program-scope) внутри файла Leo. Идентификатор программы должен соответствовать файлу манифеста `program.json`.
Ключевое слово `transition` указывает на определение функции [перехода](https://developer.aleo.org/leo/language#transition-function) в Leo. Наша функция **hello** `main` принимает входные данные `a` с типом `u32` и общедоступной (`public`) видимостью, а также входные данные `b` с типом `u32` и частной (`private`) видимостью (по умолчанию). Программа возвращает один результат с типом `u32`. Тело функции перехода заключено в фигурные скобки `{ }`. В Leo принято размещать открывающую фигурную скобку на той же строке, что и определение функции, добавляя между ними один пробел.
```
transition main(public a: u32, b: u32) -> u32 {
```
Внутри основной функции мы объявляем переменную `c` с типом `u32` и устанавливаем ее равной сумме переменных `a` и `b`. Компилятор Leo проверит, что типы `a` и `b` равны и что результат сложения имеет тип `u32`.
```
let c: u32 = a + b;
```

> `ПОЛЕЗНО!` Мы разработали Leo с верой в то, что разработчики тоже люди и могут ошибаться. Попробуйте изменить тип любой переменной и посмотрите, что рекомендует Leo с полезными сообщениями об ошибках.

Наконец, мы возвращаем переменную `c`. Leo проверит, соответствует ли тип `c` типу возвращаемого значения функции `u32`.
```
return c;
```
## Подключение программных входов
Компилятор Leo создаст **схему** из программы **main.leo.** Откройте **inputs/hello.in.** Файлы, оканчивающиеся на **.in**, предоставляют входные данные для программы. Вы также можете указать аргументы программы через [командную строку](https://developer.aleo.org/leo/commands#leo-run).

**inputs/hello.in**
```
// The program input for hello/src/main.leo
[main]
public a: u32 = 1u32;
b: u32 = 2u32;
```
Входной файл начинается с раздела, заключенного в квадратные скобки `[ ]`. `main` внутри квадратных скобок указывает на то, что мы определяем входные данные для функции перехода `main`. Вы можете определить только входные данные для [функций перехода](https://developer.aleo.org/leo/language#transition-function).
```
[main]
```
Синтаксис входного назначения аналогичен явному назначению переменной в обычных файлах `.leo`. Здесь мы присваиваем значение `1` типа `u32` общедоступному (`public`) входу с именем `a`. Мы также присваиваем значение `2` типа `u32` входу (закрытому по умолчанию) с именем `b`. Компилятор Лео извлечет эти значения и предоставит их в качестве входных данных для схемы во время проверки.
```
public a: u32 = 1u32;
b: u32 = 2u32;
```
Теперь давайте воспользуемся Leo CLI и посмотрим, какие команды мы можем запускать в нашей программе.

Ранее мы запускали программу с помощью `leo run`. Эта команда запускает несколько других команд интерфейса командной строки Leo перед проверкой доказательства.

## Рассмотрим команды подробнее шаг за шагом

Давайте рассмотрим каждую команду, вызываемую `leo run`, и лучше поймем, что происходит под капотом. Сначала удалите все файлы сборки следующей командой:
```
leo clean
```
**вывод консоли:**
```
Leo cleaned the build directory (in "/build/")
```
### 1. Комлируем программый файл
Команда `leo build` компилирует программный файл `main.leo`. Лео проверит синтаксис программы и создаст файл `main.aleo`.
```
leo build
```
Каталог **build** будет хранить все файлы, сгенерированные Leo CLI.

**вывод консоли:**
```
Leo ✅ Compiled 'main.leo' into Aleo instructions (in "/hello/build/main.aleo")
Leo ✅ Built 'hello.aleo' (in "/hello/build")
```
### 2. Запуск

Команда `leo run` запускает программу `/build/main.aleo` Aleo с помощью Aleo SDK. Для получения дополнительной информации прочитайте [документацию](https://developer.aleo.org/aleo) по Aleo SDK.
```
leo run
```

**вывод консоли:**

```
Leo ✅ Compiled 'main.leo' into Aleo instructions (in "/hello/build/main.aleo")
⏳ Compiling 'hello.aleo'...

 • Loaded universal setup (in 100 ms)
 • Built 'main' (in 1000 ms)

 Leo ✅ Built 'hello.aleo' (in "/hello/build")
 • Loaded universal setup (in 100 ms)
🚀 Executing 'hello.aleo/main'...

 • Executing 'hello.aleo/main'...
 • Executed 'main' (in 1000 ms)

➡️  Output

 • 3u32

 Leo ✅ Executed 'hello.aleo/main' (in "/hello/build")
```

Команда `leo run` попытается проверить доказательство, только если все предыдущие шаги выполнены успешно. Под капотом Leo [CLI](https://developer.aleo.org/leo/commands) проверяет наличие существующих файлов `.prover`, `.verifier` и `.avm` в каталоге **build** перед выполнением каждой команды. Это гарантирует, что мы не запускаем ненужные команды.

## Следующие шаги
Чтобы узнать больше о языке Leo и его синтаксисе, перейдите [сюда](https://developer.aleo.org/leo/language).

Чтобы узнать больше о том, как использовать Leo CLI, перейдите [сюда](https://developer.aleo.org/leo/commands).
