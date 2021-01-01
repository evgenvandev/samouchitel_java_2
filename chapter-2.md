## Глава 2. Объектно-ориентированное программирование в Java
# Листинг 2.1. Нахождение корня нелинейного уравнения методом бисекции
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
    
  }
}
```
