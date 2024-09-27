## Памятка по использованию cmake для работы с языками C и C++

### Проверка наличия cmake

> cmake --versions

Если cmake не установлен, то его следует установить

## Заполнение файла cmake (порядок и описание для чего используется)

Минимальная версия cmake
> cmake_minimun_required(VERSIONS 3.25.0)

Описание проекта

>project(**MyProject** VERSIONS 0.1.0 LANGUAGES C CXX)

Указываем имя, версию нашего продукта, и языки (CXX - это с++)

Также мы можем добавить в проект сторонние библиотеки из гитхаб или другого источника, для этого пропишем зависимость

> include(FetchContent)
>FetchContent_Declare(
>    fmt
>   GIT_REPOSITORY https://github.com/fmtlib/fmt.git
>   GIT_TAG 10.1.1
>)

>FetchContent_MakeAvalible(fmt)

>add_executable(MyProject main.cpp)

>taget_link_libraries(MyProject PRIVATE fmt::fmt)


### Описания зависимостей в cmake указаны в CMakeLists.txt

Для запуска файла потребуется зайти в команды, выполнить cmake:skan for kit для поиска компиляторов
Потом cmake:set a kit для выбора нужного компилятора
Далее cmake:build для сборки проекта