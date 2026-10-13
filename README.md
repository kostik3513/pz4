# Практична робота №4

## Тема: Реалізація стеку
## Мета: ознайомитися з основами роботи зі стеком у C++ за допомогою стандартного контейнерного std::stack, вивчити основні операції стека: додавання, видалення, перегляд верхнього елемента, перевірка на порожність і очищення стека.

### Завдання 1

# <img width="1792" height="716" alt="Знімок екрана 2026-10-13 121510" src="https://github.com/user-attachments/assets/dabecb5b-739d-4432-b2e9-76bdda2436fe" />

```
#include <iostream>
#include <stack>
#include <string>

using namespace std;

int main() {
    stack<string> S;

    S.push("plum");
    S.push("peach");
    S.push("apricot");
    
    stack<string> tempStack = S;
    int count = 0;

    cout << "Елементи стека:" << endl;
    while (!tempStack.empty()) {
        string str = tempStack.top();
        count += str.length();
        cout << str << endl;
        tempStack.pop();
    }

    cout << "Загальна кількість символів: " << count << endl;
    cout << "Розмір оригінального стека (залишився повним): " << S.size() << endl;

    return 0;
}
```

### Завдання 2

# <img width="1717" height="605" alt="image" src="https://github.com/user-attachments/assets/b799a702-d0a6-43d0-b32a-d1dc336b8c90" />

```
#include <iostream>
#include <stack>

using namespace std;

int main() {
    stack<int> S;
    int sum = 0;
    S.push(5);
    S.push(9);
    S.push(12);
    S.push(15);
    S.push(20);

    cout << "Витягнуті елементи стека (у зворотному порядку): ";

    while (!S.empty()) {
        int num = S.top();
        cout << num << " ";
        sum += num;
        S.pop();
    }

    cout << endl;
    cout << "Сума чисел: " << sum << endl;

    return 0;
}
```

### Завдання 3

# <img width="1466" height="781" alt="image" src="https://github.com/user-attachments/assets/67c6f984-cbe5-4ece-a39c-b0e7eb029989" />

```
#include <iostream>
#include <stack>

using namespace std;

int main() {
    stack<int> S;
    int count = 0;
    int findNum;
    bool found = false;

    S.push(8);
    S.push(16);
    S.push(24);
    S.push(32);
    S.push(40);
    S.push(48);

    cout << "Введіть число для пошуку: ";
    cin >> findNum;

    cout << "Витягнуті елементи з стека: ";

    while (!S.empty()) {
        int num = S.top();
        cout << num << " ";
        count++;
        S.pop();

        if (num == findNum) {
            found = true;
            break; 
        }
    }

    cout << endl;
    if (found) {
        cout << "Число " << findNum << " знайдено!" << endl;
    } else {
        cout << "Число " << findNum << " не знайдено." << endl;
    }

    cout << "Кількість витягнутих елементів: " << count << endl;

    return 0;
} 
```

### Завдання 4

<img width="1540" height="692" alt="image" src="https://github.com/user-attachments/assets/adf603e3-f25c-40a4-9e65-948356a4f8f1" />

```
#include <iostream>
#include <stack>
#include <cstdlib>
#include <ctime>

using namespace std;

int main() {
    stack<int> S;
    const int size = 15;
    int minVal = 10;
    int maxVal = 50;

    int sum = 0;
    int count = 0;

    srand(time(0));

    for (int i = 0; i < size; i++) {
        int randomNum = minVal + rand() % (maxVal - minVal + 1);
        S.push(randomNum);
    }

    cout << "Елементи стека (витягуються з вершини):" << endl;

    while (!S.empty()) {
        int num = S.top();
        cout << num << " ";
        S.pop();

        if (num >= 20 && num <= 40 && num % 2 == 0) {
            sum += num;
            count++;
        }
    }

    cout << endl;

    if (count > 0) {
        cout << "Знайдено " << count << " парних чисел у діапазоні від 20 до 40." << endl;
        cout << "Середнє значення відфільтрованих чисел: " << static_cast<double>(sum) / count << endl;
    } else {
        cout << "Парних чисел у діапазоні від 20 до 40 не знайдено." << endl;
    }

    return 0;
}
```

### Завдання 5

# <img width="1380" height="582" alt="image" src="https://github.com/user-attachments/assets/d9095ebd-9bf2-4eac-8624-95550817fdcd" />

```
#include <iostream>
#include <string>
#include <stack>

using namespace std;

int main() {
    string word = "level";
    stack<char> s;

    for (char c : word) {
        s.push(c);
    }

    string reversedWord = "";

    while (!s.empty()) {
        reversedWord += s.top();
        s.pop();
    }

    cout << "Оригінал: " << word << endl;
    cout << "Навпаки:  " << reversedWord << endl;

    if (word == reversedWord) {
        cout << "Результат: Рядок є паліндромом!" << endl;
    } else {
        cout << "Результат: Рядок НЕ є паліндромом." << endl;
    }

    return 0;
}
```

### Висновок. Під час виконання практичної роботи № 4 було вивчено принцип роботи стека (LIFO) та опановано контейнер std::stack у C++. На прикладі Варіанта 3 реалізовано додавання, перегляд і вилучення елементів, пошук зі збереженням або зміною структури даних, генерацію та фільтрацію чисел, а також перевірку рядка на паліндром.
