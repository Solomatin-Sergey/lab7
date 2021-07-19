[![Build Status](https://www.travis-ci.com/Solomatin-Sergey/lab7.svg?branch=main)](https://www.travis-ci.com/Solomatin-Sergey/lab7)
# lab7
## Изучение систем управления пакетами на примере Hunter
### Task.
> Создайте cвой hunter-пакет.

> Выполнение задания.

>> Для использования hunter-пакета для приложения hello_world в папке проекта создана папка download_file и в неё командой $wget https://raw.githubusercontent.com/cpp-pm/gate/master/cmake/HunterGate.cmake -O download_file/HunterGate.cmake загружен файл HunterGate.cmake - файл, который подгрузит сам пакетный менеджер.

>> в файл CMakeLists.txt были добавлены следующие строки:

```
HunterGate(
    URL "https://github.com/cpp-pm/hunter/archive/v0.23.251.tar.gz"
    SHA1 "5659b15dc0884d4b03dbd95710e6a1fa0fc3258d"
)
```
```
hunter_add_package(Boost)

find_package(Boost CONFIG REQUIRED)
```
```
target_link_libraries(hello_world PUBLIC Boost::boost formatter_ex)
```
// HunterGate - шлюз, который скачивает согласно URL последнюю версию hunter.

>> Наконец, был создан файл .travis.yml (с его содержанием можно ознакомиться выше).

