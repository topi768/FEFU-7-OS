# Лабораторная работа 2

Библиотека на C++98 для запуска программы без ожидания её завершения и последующего ожидания с получением кода завершения

Нужны CMake 3.16 или новее и компилятор GCC (MinGW с `mingw32-make` для Windows), доступные в `PATH`

Команды ниже выполняются из корневой папки репозитория

## Windows (PowerShell)

```powershell
cd 2
cmake -S . -B build-windows -G "MinGW Makefiles"
cmake --build build-windows
cd build-windows
.\process_test.exe .\child.exe
```

## Linux

```sh
cd 2
cmake -S . -B build-linux
cmake --build build-linux
cd build-linux
./process_test ./child
```

## Проверка

`process_test` запускает отдельную программу `child`, продолжает выполнение, затем ждёт её завершения и выводит полученный код

`child` работает около трёх секунд и завершается с кодом `5`

В конце ожидается:

```text
Родитель: код завершения дочерней программы = 5
```

Для проверки ошибки запуска замените путь к `child` на несуществующий файл

После изменения исходников повторите `cmake --build build-windows` или `cmake --build build-linux` из папки `2`, затем снова запустите утилиту из папки сборки
