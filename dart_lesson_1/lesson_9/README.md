# Классы: расширения/extension
Это способ дописать что-то в класс, к которому нет доступа.

Можно расширить **методы, операторы, сеттеры и геттеры**, но **не поля**.
Для расширений используем пару ключевых слов `extension ... on`.

К типу `int`  можно применить метод `toDouble`, но к строке такого метода не существует. Мы добавляем расширение функционала к абстрактному классу `String` (всё в дарте - объекты и классы) и прописываем метод, который позволяет превратить строку в дабл.


```dart
void main() {
  final a = 5;
  final b = '5';
  a.toDouble();
  final c = b.toDouble();
  print(c);
}

extension StringToDouble on String {
  double? toDouble() {
    return double.tryParse(this);
  }
}
```