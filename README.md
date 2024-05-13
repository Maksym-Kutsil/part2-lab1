------find_kth_largest------ Рівень 2 Варіант 3 Напишіть функцію для пошуку k-того найбільшого елемента в заданому масиві цілих чисел. Параметр k задається на вхід функції і визначає порядковий номер найбільшого елемента, який потрібно знайти. Наприклад, якщо k = 1, програма повинна знайти найбільший елемент в масиві. Якщо k = 2, програма повинна знайти другий за величиною елемент, і так далі. Умови задачі: Масив цілих чисел передається у вашу функцію. Розмір масиву повинен бути не менше k. Програма повинна вивести k-тий найбільший елемент і його позицію (індекс) в масиві. Приклад введення та виведення результату: Вхідний масив:[15, 7, 22, 9, 36, 2, 42, 18] Задане k: 3 Знайдений 3-й найбільший елемент: 22 Позиція 3-го найбільшого елемента в масиві: 2

Для перевірки виконання роботи реалізованого алгоритму слід використати бібліотеку unittest .

------min_eating_time------ Рівень 2, Варіант 3. Горила Джекі із зоопарку Мюнхена любить їсти банани. На складі зоопарку є N кошиків (piles) з бананами, у і-тому кошику є певна кількість бананів Х. Кошики знаходяться під охороною, але охорона здійснює обхід зоопарку на Н годин, протягом якого Джекі може поласувати своєю улюбленою стравою. Джекі може з'їсти за годину К бананів. Кожну годину вона вибирає кошик з бананами і їсть К бананів звідти. Якщо кошик має менше, ніж К бананів, вона з'їдає всі банани з нього і більше не буде їсти бананів протягом цієї години. Джекі любить їсти повільно, але все ж хочеться закінчити споживання всіх бананів, перш ніж охоронці повернуться. Напишіть функцію, яка повертає мінімальне ціле число К, яке дозволить Джекі з'їсти всі банани на складі протягом Н годин, поки повернеться охорона.

Приклад 1: piles = [3,6,7,11], H = 8 Результат: 4

Приклад 2: piles = [30,11,23,4,20], H = 5 Результат: 30

Приклад 3: piles = [30,11,23,4,20], H = 6 Результат: 23

Важливо: 1 <= piles.length <= 10^4 piles.length <= H <= 10^9 1 <= piles[i] <= 10^9

Для перевірки виконання роботи реалізованого алгоритму слід використати бібліотеку unittest та перевірити роботу вашої функції на прикладах, наведених вище

Для заданого бінарного дерева реалізуйте функцію, яка обчислює та повертає значення максимального діаметра у бінарному дереві - найвіддаленішу відстань між двома листками. Максимальний діаметр у бінарному дереві визначає найбільшу відстань між будь-якою парою листків (кінцевих вузлів) у дереві. Діаметр вимірюється як кількість ребер, які потрібно пройти, щоб дістатися одного листка від іншого. Максимальний діаметр не обов'язково має включати в себе кореневий вузол

Нехай у вас задане бінарне дерево такого вигляду:

        1
       /  \
      3    2
     / \
    7   4
   /     \
  8       5
 /         \
9           6
Для даного дерева максимальний діаметр становить 6: 9 -> 8 -> 7 -> 3 -> 4 -> 5 -> 6 - для проходження від листка 9 до листка 6 слід пройти 6 ребер.

Реалізована вами функція binary_tree_diameter(tree: BinaryTree) -> int отримує на вхід корінь бінарного дерева та повертає максимальний діаметр дерева.

Клас, який описує бінарне дерево (та будь який вузол дерева) має вигляд:

class BinaryTree:
    def __init__(self, value, left=None, right=None):
        self.value = value
        self.left = left
        self.right = right
Реалізація даної задачі не вимагає написання коду вставки чи виділення елементів з бінарного дерева. У тесті ви можете створити достатню кількість елементів класу BinaryTree наступним чином:

root = BinaryTree(3)
root.left = BinaryTree(9)
root.right = BinaryTree(20)

Реалізуйте структуру даних "черга з пріоритетами" на основі бінарного дерева binary tree, в якому батьківський елемент має вищий пріоритет, ніж елемент справа, або нижчий або рівний пріоритет, ніж пріоритет його лівої дитини.

Операції, які підтримує ваша черга:

Вставка елемента з заданим значенням та пріоритетом до черги.
Видалення та повернення елемента з найвищим пріоритетом з черги.
Перегляд черги без її зміни.
Для реалізації такої черги з пріоритетами слід використати окремий клас Node, де кожен елемент буде мати два поля: значення та пріоритет. При вставці елемента до черги, його потрібно розмістити у відповідному порядку з урахуванням пріоритету.

Назва файлу реалізації - binary_tree_priority_queue.py

Дано лабіринт у формі двійкової прямокутної матриці, знайдіть найкоротший шлях у лабіринті від заданої точки до вказаного пункту призначення.


Шлях можна побудувати лише з використанням комірок, які містіть 1.  В будь-який момент ми можемо рухатися лише на один крок в одному з чотирьох напрямків:

Go Top: (x, y) ——> (x – 1, y)

Go Left: (x, y) ——> (x, y – 1)

Go Down: (x, y) ——> (x + 1, y)

Go Right: (x, y) ——> (x, y + 1)


Наприклад, розглянемо наступну двійкову матрицю. Якщо початкова точка  має координати (0, 0), а  пункт призначення = (7, 5), тоді найкоротший шлях від джерела до пункту призначення має довжину 12


 [ 1  1  1  1  1  0  0  1  1  1 ]

 [ 0  1  1  1  1  1  0  1  0  1 ]

 [ 0  0  1  0  1  1  1  0  0  1 ]

 [ 1  0  1  1  1  0  1  1  0  1 ]

 [ 0  0  0  1  0  0  0  1  0  1 ]

 [ 1  0  1  1  1  0  0  1  1  0 ]

 [ 0  0  0  0  1  0  0  1  0  1 ]

 [ 0  1  1  1  1  1  1  1  0  0 ]

 [ 1  1  1  1  1  0  0  1  1  1 ]

 [ 0  0  1  0  0  1  1  0  0  1 ]


Вхідні дані містяться у файлі input.txt у форматі:

0, 0 #початкова точка

7, 5 #точка призначення

10,10 # кількість рядків та стовпчиків у матриці

 [ 1  1  1  1  1  0  0  1  1  1 ]

 [ 0  1  1  1  1  1  0  1  0  1 ]

 [ 0  0  1  0  1  1  1  0  0  1 ]

 [ 1  0  1  1  1  0  1  1  0  1 ]

 [ 0  0  0  1  0  0  0  1  0  1 ]

 [ 1  0  1  1  1  0  0  1  1  0 ]

 [ 0  0  0  0  1  0  0  1  0  1 ]

 [ 0  1  1  1  1  1  1  1  0  0 ]

 [ 1  1  1  1  1  0  0  1  1  1 ]

 [ 0  0  1  0  0  1  1  0  0  1 ]



Результуючий файл має містити значення найкоротшого шляху від початкової точки до точки призначення

Весілля та племена

Вождь Ваі-Ву з острова Пасхи вирішив поміняти традиції одруження на острові.

Раніше усі одружувались всередині свого племені.  Але після курсу біології на Coursera 
Ваі-Ву дізнався, що змішування генів - це корисна штука.  Тому він попросив усіх голів племен підготувати списки молодих хлопців/дівчат, і спробує організувати шлюби між племенами.

Вашим завдання буде проаналізувати списки, та сказати Ваі-Ву скільки можливих пар з різних племен він може скласти.

Формат списків племен:
Кожен юнак/дівчина - це ціле число
Юнаки - непарні числа, дівчата - парні
У кожному рядку - два числа, які означають що юнак чи дівчина належать до одного племені.  Наприклад:
	
		1 2
		2 4
		3 5

	Описує два племені - в одному є хлопець 1 та двоє дівчат 2 та 4, а в іншому племені - двоє хлопців 3 та 5.

Вхідні дані:
	Перший рядок містить кількість пар N
	Наступні N рядків містять пари людей з різних племен

Вихідні дані:
	Кількість можливих комбінацій пар таких, що хлопець і дівчина походять з різних племен.

Обмеження:
	0 < N < 10000
Приклади:
In:
3
1 2
	2 4
	3 5
Out:
	4 (Можливі пари - 2/3, 2/5, 4/3, 4/5)

In:
5
1 2
	2 4
	1 3
	3 5
	8 10
Out:
	6 (Можливі пари - 1/8, 1/10,  3/8, 3/10,  5/8, 5/10)

 
Створити функцію на мові програмування Python, яка приймає дві стрічки: "haystack" (довільний текст) та "needle" (шукана стрічка). Програма повинна знайти кінцевий індекс останнього входження стрічки "needle" в стрічці "haystack" та повернути цей індекс та кількість порівнянь символів, яку виконала ваша функція, використовуючи  naive-метод (метод повного перебору) пошуку підстрічки у стрічці


Компанія "Квітка" має у Львові багато магазинів, де вони продають квіти. Також, вони мають квіткові ферми, де ці квіти вирощують з метою продажу. Наближається день Матері, а згодом - свято останнього дзвоника. В них є інформація про всі дороги, що ведуть від їх ферм до магазинів, та максимальна кількість машин, які можуть проїхати цими дорогами протягом дня з урахуванням щільності руху. Власники компанії намагаються зрозуміти, скільки саме машин квітів вони зможуть доставити з своїх ферм до магазинів протягом одного дня і звернулись до вас за допомогою., щоб ви порахували яку максимальну кількість машин квітів власники компанії зможуть привезти за день.

Вхідні дані:

файл roads.csv, який містить:
список ферм F1, F2, F3 в першій лінійці
список магазинів S1, S2, S3, S4, S5 - в другій лінійці
список доріг між перехрестями та відстань між ними у форматі: Х1, Х2, 4. цей запис означає, що між перехрестями Х1 та Х2 за день максимально може проїхати 4 автомобілі. Запис Х2, S1, 10 означає, що від перехрестя Х2 до магазину S1 може проїхати 10 автомобілів за день.
Вихідні дані:

Максимальна кількість автомобілів, які зможуть проїхати протягом дня з квіткових ферм до квіткових магазинів.


Ланцюжок зi слiв 88889
Код задачi: WCHAIN
Двоє учасникiв грають у лiнгвiстичну гру. На початку гри дано список iз N слiв.
Перший гравець обирає довiльне слово w1 i викреслює з нього одну довiльну лiтеру
так, щоб отримати iнше слово w2 з цього списку. Пiсля цього хiд переходить до
iншого гравця, i вiн намагається зробити те саме зi словом w2.
Гра завершується в одному з двох випадкiв:
• Залишається слово з однiєї лiтери.
• Неможливо викреслити жодну лiтеру так, щоб отримати iнше слово зi словника.

Визначте довжину максимального ланцюжка, якого можна досягти в цiй грi при
заданих словах.
Вхiднi данi
Вхiдний файл wchain .in складається з N + 1 рядкiв.
• Перший рядок мiстить N — кiлькiсть слiв у словнику, 1 ≤ N ≤ 105
.

• Кожен з наступних N рядкiв мiстить слово довжиною вiд 1 до 50 символiв, яке
складається з малих латинських лiтер вiд a до z.
Вихiднi данi
Вихiдний файл wchain .out повинен мiстити одне число — довжина максимального
ланцюжка.