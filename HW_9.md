//*Задача 64: Задайте значение N. Напишите программу, которая выведет все натуральные числа в промежутке от N до 1. Выполнить с помощью рекурсии.
N = 5 -> "5, 4, 3, 2, 1"
N = 8 -> "8, 7, 6, 5, 4, 3, 2, 1"*/

Console.WriteLine("Введите число: ");
int endsings = int.Parse(Console.ReadLine()!);
Console.WriteLine(Answer(1, endsings));

//*Задача 66: Задайте значения M и N. Напишите программу, которая найдёт сумму натуральных элементов в промежутке от M до N.
M = 1; N = 15 -> 120
M = 4; N = 8. -> 30*/

Console.WriteLine("Введите первое число: ");
int alpha = int.Parse(Console.ReadLine()!);
Console.WriteLine("Введите второе число: ");
int omega = int.Parse(Console.ReadLine()!);

Console.WriteLine($"Сумма цифр в промежутке от {alpha} до {omega} - {Calc(alpha, omega)}");

//*Задача 68: Напишите программу вычисления функции Аккермана с помощью рекурсии. Даны два неотрицательных числа m и n.
m = 2, n = 3 -> A(m,n) = 9
m = 3, n = 2 -> A(m,n) = 29*/

Console.WriteLine("Введите число m: ");
int m = int.Parse(Console.ReadLine()!);
Console.WriteLine("Введите число n: ");
int n = int.Parse(Console.ReadLine()!);
Console.WriteLine(Akk(m, n));

//CTWDN
string Answer(int alpha, int numbers){
    if(alpha == numbers) return numbers.ToString();
    return (numbers +", "+ Answer(alpha, numbers - 1));
}

//Calculum
int Calc(int alpha, int omega){
    if(alpha == omega + 1) return 0;
    return (alpha + Calc(alpha + 1, omega));
}

//Akker
int Akk(int m, int n){
    if(m == 0) return n + 1;
    if(m > 0 && n == 0) return Akk(m - 1, 1);
    return (Akk(m - 1, Akk(m, n - 1)));
}