
# ReportLab2

# Part1

## 1. Создайте пустой репозиторий на сервисе github.com (или gitlab.com, или bitbucket.com).

https://github.com/Dark13Night/lab02.git

![image](https://user-images.githubusercontent.com/112771541/224359235-9eb22115-9ba6-4159-adbc-97cbe62acf6e.png)


## 2. Выполните инструкцию по созданию первого коммита на странице репозитория, созданного на предыдещем шаге.
```
$ echo "# lab02" >> README.md
$ git init
$ git add README.md
$ git commit -m "first commit"
$ git branch -M main
$ git remote add origin https://github.com/Dark13Night/lab02.git
$ git push -u origin main
```
![image](https://user-images.githubusercontent.com/112771541/224359330-796f6ce9-c3dd-42a7-9a89-705419c6c0c4.png)

![image](https://user-images.githubusercontent.com/112771541/224359399-83e0624b-13e0-43cf-b3e5-5aa666000242.png)

## 3. Создайте файл hello_world.cpp в локальной копии репозитория (который должен был появиться на шаге 2). Реализуйте программу Hello world на языке C++ используя плохой стиль кода. Например, после заголовочных файлов вставьте строку using namespace std;.
```
#include <iostream>

using namespace std;

int main(int argc, char** argv) {

   cout << "Hello world" << endl;
}
```

![image](https://user-images.githubusercontent.com/112771541/224359513-5c405c9a-a4bc-4772-a811-6af5d7fb52d8.png)

## 4. Добавьте этот файл в локальную копию репозитория.
```
$ git add Hello world.cpp
```
## 5. Закоммитьте изменения с осмысленным сообщением.
```
$ git commit -m "This is first file"
```

![image](https://user-images.githubusercontent.com/112771541/224359807-e84e060c-e7e7-42e1-b515-d1878bd2784b.png)

## 6. Изменитьте исходный код так, чтобы программа через стандартный поток ввода запрашивалось имя пользователя. А в стандартный поток вывода печаталось сообщение Hello world from @name, где @name имя пользователя.
```
include <iostream>
include <string>
using namespace std;
int main() {
cout << "Hello world!";
string name;
cout << "Please enter name";
cin >> name;
cout << "Hello world from " << name;
}
```
## 7. Закоммитьте новую версию программы. Почему не надо добавлять файл повторно git add?
```
$ git add Hello world.cpp
$ git commit -m "updated Hello world.cpp"
```
![image](https://user-images.githubusercontent.com/112771541/224359879-1a8c935d-30d8-4ec0-9a6f-ff929ee208d9.png)

## 8. Запуште изменения в удалёный репозиторий.
```
$ git push origin main
```
## 9. Проверьте, что история коммитов доступна в удалёный репозитории.

![image](https://user-images.githubusercontent.com/112771541/224360703-e77cd6d5-e2fe-4b56-8c45-d686487f09db.png)

# Part 2

## 1. В локальной копии репозитория создайте локальную ветку patch1.
```
$ git branch patch1
$ git checkout patch1
```
## 2. Внесите изменения в ветке patch1 по исправлению кода и избавления от using namespace std;.
```
include <iostream>
include <string>
int main() {
std::string name;
std::cout << "Please enter name";
std::cin >> name;
std::cout << "Hello world from " << name;
}
```
![image](https://user-images.githubusercontent.com/112771541/224361108-4c0940f6-3272-43a4-b325-f5ce8734a8a0.png)

## 3. commit, push локальную ветку в удалённый репозиторий.
```
$ git add Hello world.cpp
$ git commit -m "patched Hello world.cpp"
$ git push origin patch1
```

## 4. Проверьте, что ветка patch1 доступна в удалёный репозитории.

![image](https://user-images.githubusercontent.com/112771541/224361286-f0146f37-184f-4fad-acbd-6963d8fdaab6.png)

## 5. Создайте pull-request patch1 -> master.

![image](https://user-images.githubusercontent.com/112771541/224361370-848e580b-83ef-448a-b6b9-febd7c2913c5.png)

## 6. В локальной копии в ветке patch1 добавьте в исходный код комментарии.
```
include <iostream>
include <string>
int main() {
std::string name;
std::cout << "Please enter name";
std::cin >> name; //введите имя
std::cout << "Hello world from " << name;
}
```
![image](https://user-images.githubusercontent.com/112771541/224361469-fa181960-a794-4edb-a373-6dcd25ffda4a.png)

## 7. commit, push.
```
$ git add Hello world.cpp
$ git commit -m "added comment"
$ git push origin patch1
```
![image](https://user-images.githubusercontent.com/112771541/224361641-b92d27d2-a94b-4490-b664-7843fa822d05.png)

## 8. Проверьте, что новые изменения есть в созданном на шаге 5 pull-request.

![image](https://user-images.githubusercontent.com/112771541/224361559-3efa83ee-8f8d-46d1-8761-c9d933898440.png)

## 9. В удалённый репозитории выполните слияние PR patch1 -> master и удалите ветку patch1 в удаленном репозитории.

![image](https://user-images.githubusercontent.com/112771541/224361744-3f1a76f6-bc1c-4d93-b755-cf934a7b4adf.png)

## 10. Локально выполните pull.
```
$ git checkout main
$ git pull origin main
```
![image](https://user-images.githubusercontent.com/112771541/224361876-b51f7303-96c4-423b-81ed-d73dab7c57b1.png)

## 11. С помощью команды git log просмотрите историю в локальной версии ветки master.
```
$ git log
```
![image](https://user-images.githubusercontent.com/112771541/224361951-1af56036-5767-4fef-ba79-5cc8b2e2d447.png)

## 12. Удалите локальную ветку patch1.
```
$ git branch -d patch1
```
![image](https://user-images.githubusercontent.com/112771541/224362442-6ebd3ecb-ebd7-4fb0-a051-9add363900b3.png)

# Part 3

## 1. Создайте новую локальную ветку patch2.
```
$ git branch patch2
$ git checkout patch2
```
## 2. Измените code style с помощью утилиты clang-format. Например, используя опцию -style=Mozilla.
```
$ sudo apt install clang-format
$ clang-format "/home/kali/lab02/Hello world.cpp" -style=Mozilla -i "/home/kali/lab02/Hello world.cpp"
```
![image](https://user-images.githubusercontent.com/112771541/224362580-1c81cfd6-42d8-42fe-991a-be262d09508e.png)

![image](https://user-images.githubusercontent.com/112771541/224362615-f29947b1-a2c6-4daa-81e2-c0b19a930dc1.png)


## 3. commit, push, создайте pull-request patch2 -> master.
```
$ git add Hello world.cpp
$ git commit -m "changed codestyle"
$ git push origin patch2
```

![image](https://user-images.githubusercontent.com/112771541/224362676-f9a0fbb0-dce8-4b66-8f0e-bb07f0cbf8d4.png)


## 4. В ветке master в удаленном репозитории измените комментарии, например, расставьте знаки препинания, переведите комментарии на другой язык.

![image](https://user-images.githubusercontent.com/112771541/224362772-b67c5757-de6f-4c5c-9b2c-749d3cb2ce2c.png)


## 5. Убедитесь, что в pull-request появились конфликтны.

![image](https://user-images.githubusercontent.com/112771541/224362813-0b267b27-c0f9-4f71-a871-82efba8b4e4c.png)


## 6. Для этого локально выполните pull + rebase (точную последовательность команд, следует узнать самостоятельно). Исправьте конфликты.
```
$ git pull origin main --rebase
```
```
include<iostream> include<string>
int
main()
{
  std::string name;
  std::cout << "Please enter name";
  std::cin >> name; //enter the name
  std::cout << "Hello world from " << name;
}
```
```
$ git rebase --continue
```
![image](https://user-images.githubusercontent.com/112771541/224363044-cb5788ad-53b7-4263-9957-0e2030504f0b.png)

![image](https://user-images.githubusercontent.com/112771541/224362887-f5c06c55-8a61-4ca1-a6d0-acc17175a882.png)

## 7. Сделайте force push в ветку patch2
```
$ git push -f origin patch2
```
## 8. Убедитель, что в pull-request пропали конфликтны.

![Uploading image.png…]()


## 9. Вмержите pull-request patch2 -> master.

![Uploading image.png…]()

