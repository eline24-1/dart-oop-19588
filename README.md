# Dart OOP Assignment: Kigali Bus Card

Name: Loriana Eline
Student ID: 19588

 My numbers
- D = 88, L = 8
- Starting balance = 1880 RWF
- Bus fare = 288 RWF
- Student discount = 18%

 Output of main.dart
Error: name too short
Owner: Loriana Eline | Balance: 1880 RWF
Owner: Loriana Eline | Balance: 1880 RWF
Error: top-up must be 500 to 50000 RWF
Topped up 2000 RWF
Paid 288 RWF
Paid 288 RWF
Owner: Loriana Eline | Balance: 3304 RWF
Student discount: 51 RWF
Paid 237 RWF
Owner: Loriana Eline | Balance: 1643 RWF
Student card: 18% off

 Part 1: Why no setter for balance?
There is no setter for the balance because the balance should not be changed directly. Without a setter, nobody can write `card.balance = 1000000`. The balance can only change through `topUp` and `pay`, which check the rules first.

 Part 2: What does ~/ do?
The `~/` operator is integer division in Dart. It divides two numbers and keeps only the whole number, without the decimal part.
- `print(237 * 17 / 100);` prints `40.29`, because `/` gives a decimal number.
- `print(237 * 17 ~/ 100);` prints `40`, because `~/` drops the decimal part.

 Part 4: Bug table
| Bug | The line | Why it is wrong | My fix |
|---|---|---|---|
| 1 | String _brand; and int _battery; | The variables have no starting values| String _brand = ''; and int _battery = 0;
| 2 | SmartPhone(String brand, int battery, String system) { | The constructor does not call the parent constructor| Add : super(brand, battery) before {.
| 3 | @override void restart() | There is no restart() method in the parent class| Add a restart() method in the Phone class.
| 4 | p.battery = 100;| There is no setter to change the battery value| Add a setter that allows values from 0 to 100.
| 5 | print(p.battery()); | A getter does not need parentheses | print(p.battery);
| Not a bug | `Phone p = new Phone('Tecno', 50);` | The word `new` is optional in Dart, but it is still allowed and works fine. | Nothing to change |

 Part 5
My prediction: It prints 1 and then 5.
For `a`, `add()` makes `_items` 1, and the setter refuses -5 because it is negative, so it stays 1.
For `b`, `BigBag.add()` calls `super.add()` two times, so each `add()` adds 2. After two calls `_items` is 4, then I add 1 to get 5.

Real output: 1 and 5 (printed on two lines)
Was I right? Yes, my prediction was right: `a` stays at 1 because the setter refuses -5, and `b` reaches 5 because each `BigBag.add()` adds 2.
