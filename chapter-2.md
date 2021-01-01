## Глава 2. Объектно-ориентированное программирование в Java
#### Листинг 2.1. Нахождение корня нелинейного уравнения методом бисекции
```java
class Bisection2{
  private static double final EPS = 1e-8;  // Константа класса
  private double a = 0.0, b = 1.5, root;  // Закрытые поля экземпляра
  
  // Метод доступа к полю root
  public double getRoot(){
    return root;
  }
  
  private double f(double x){
    return x * x * x - 3 * x * x + 3;  // Можно написать что-то другое
  }
  
  // Параметров у метода нет - метод работает с полями экземпляра
  private void bisect(){
    // Локальная переменная - не поле
    double y = 0.0;
    do{
      root = 0.5 * (a + b);
      y = f(root);
      if(Math.abs(y) < EPS) break;  // Корень найден. Выходим из цикла
      
      // Если на концах отрезка [a; root] функция имеет разные знаки:
      if(f(a) * y < 0.0){
        // Значит, корень здесь, и мы переносим точку b в точку root
        b = root;
      } else {
        // В противном случае:
        // переносим точку a в точку root
        a = root;
      }
    } while(Math.abs(b - a) >= EPS);
  }
  
  // Точка входа в программу:
  public static void main(String[] args){
    Bisection2 b2 = new Bisection2();
    b2.bisect();
    // Обращаемся к корню через метод доступа
    System.out.println("x = " + b2.getRoot() + ", f() = " + b2.f(b2.getRoot()));
  }
}
```
