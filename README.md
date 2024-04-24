# spbu-fundamentals-of-algorithms
Materials for the practicum for "Fundamentals of Algorithms" course at SpbU

## Getting started

Set up your environment

### VSCode

Go to `Run and Debug` in the left panel, create a new launch file, select `Python File` and add the following field:
```yaml
"env": {
    "PYTHONPATH": "${workspaceFolder}${pathSeparator}${env:PYTHONPATH}"
}
```


### MacOs (homebrew or python.app)
Go to `Terminal.app` and paste this command:
```bash
export PYTHONPATH=/Users/path_to_your_github_clone_directory:$PYTHONPATH
```
### MacOs (anaconda3 or miniconda)
Go to `Terminal.app` and paste this command:
```bash
conda develop /Users/path_to_your_github_clone_directory
```
Then you can check you PYTHONPATH with this command
```bash
python -c "import sys; print('\n'.join(sys.path))"
```
*Note: python inside your console and inside your PyCharm/Jupyter/DataSpell may be different so run commands in terminal of this app*

Another way to check your PYTHONPATH (most accurate)
paste this code (first line) in some .py file (for example: dfs.py (practicum_2) )and run the file
```python
print(sys.path) # you should see /Users/path_to_your_github_clone_directory
```

## Practicum 1

Изучение `python`, `numpy` и  `matplotlib`, необходимых для дальнейшей работы. Предполагается, что студент имеет базовые знания python.

План:
1. Выполнить `intro_to_numpy_and_matplotlib.ipynb`

## Practicum 2

Начало работы с графовыми и графовыми алгоритмами с помощью `networkx`.

План:
1. Выполнить `intro_to_networkx.ipynb`

Домашнее задание (базовый вариант):
1. Проверка на наличие циклов в ненаправленном графе: `practicum_2/homework/basic/cycles_in_undirected_graph.py`. Необходимо реализовать функцию `has_cycles`, которая принимает на вход объект графа и возвращает булевское значение, принимающее true при наличии цикла в графе. Предполагается, что, придя в узел n через ребро e в ненаправленном графе, мы можем пойти далее по любому ребру узла n, кроме e.

Домашнее задание (продвинутый вариант):
1. Проверка на наличие циклов в направленном графе: `practicum_2/homework/advanced/cycles_in_directed_graph.py`. Необходимо реализовать функцию `has_cycles`, которая принимает на вход объект графа и возвращает булевское значение, принимающее true при наличии цикла в графе. Предполагается, что, придя в узел n через ребро e в направленном графе, мы можем пойти далее по любому исходящему ребру узла n.

Дедлайн: 2024.04.06

## Practicum 3

Изучение классических графовых алгоритмов: BFS, DFS, алгоритма Прима для нахождения MST и алгоритма Дейкстры для нахождения кратчайших путей в графе. 

План:
1. Реализовать рекурсивный DFS в функции `dfs_recursive`, итерационный DFS в функции `dfs_iterative` и топологическую сортировку в функции `dfs_recursive_postorder` в файле `dfs.py`.
2. Реализовать алгоритм Прима в функции `prim_mst` в файле `mst.py`.
3. Реализовать базовый алгоритм Дейкстры в функции `dijkstra_sp` и ускорить его с помощью очереди с приоритетом в функции `dijkstra_sp_with_priority_queue` в файле `sp.py`.


Домашнее задание (базовый вариант):
1. Поиск пути в лабиринте: `practicum_3/homework/basic/bfs_maze.py`. Необходимо реализовать метод `Maze.solve`, который ищет путь в лабиринте. Лабиринт хранится в файле `practicum_3/homework/basic/maze_2.txt`, где символ `#` обозначает стену, а `O` и `X` вход и выход соответственно. Цель - построить путь от `O` к `X`. Под путем подразумевается последовательность символов `L` (шаг влево), `R` (шаг вправо), `U` (шаг вверх), `D` (шаг вниз). Например `LLDLLDDR`.
2. Проверка на корректность раскрытия скобок: `practicum_3/homework/basic/valid_parentheses.py`. Необходимо реализовать класс LIFO очереди `Stack` и затем реализовать функцию `are_parentheses_valid`, которая проверяет, содержит ли строка, переданная на вход и состоящая только из скобок `(`, `)`, `[`, `]`, `{`, `}`, корректно закрывающиеся/открывающиеся скобки. В файле `practicum_3/homework/basic/valid_parentheses_cases.yaml` содержатся корректные и некорректные примеры таких строк. 

Домашнее задание (продвинутый вариант):
1. Нахождение максимального потока в транспортной сети: `practicum_3/homework/advanced/max_flow.py`. Необходимо реализовать функцию `max_flow`, которая принимает на вход объект направленного взвешенного графа (транспортной сети) и возвращает значение максимального потока. Существует множество методов решения этой задачи, так что требуется найти наиболее быстрый метод из доступных. 

Дедлайн: 2024.04.20

## Practicum 4

Решение задач на графах с помощью линейного программирования.

План:
1. Изучить представление графовых задач в виде задач линейного программирования.
2. Поставить задачу линейного программирования в файле `practicum_4/sp_via_lp.py` для нахождения кратчайшего пути в графе и решить ее с помощью `scipy.optimize.linprog`.

## Practicum 5

Решение задач на графах с помощью метаэвристических алгоритмов.

План:
1. Изучить постановку задачи раскраски графов.
2. Изучить алгоритм Hill Climbing
3. Реализовать случайный поиск и Hill Climbing в файле `practicum_5/graph_coloring.py`

Домашнее задание (базовый вариант):
1. Обход бинарного дерева зигзагом: `practicum_5/homework/basic/binary_tree_zigzag_level_order_traversal.py`. Необходимо реализовать функцию `build_tree`, строящую дерево `BinaryTree` из списка, где узлы перечислены по слоям слева направо (см. [пример](https://leetcode.com/problems/binary-tree-zigzag-level-order-traversal)). Далее необходимо реализовать метод `BinaryTree.zigzag_level_order_traversal`, выполняющий обход зигзагом и возвращающий двумерный список, где первая размерность соответствует глубине дерева, а вторая - узлам на этой глубине. Под зигзагом подразумевается обход слева направо на нулевом уровне (корень), затем справа налево на первом уровне и так далее.

Домашнее задание (продвинутый вариант):
1. Раскраска графа с помощью имитации отжига: `practicum_5/homework/advanced/simulated_annealing.py`. Имитация отжига требует реализации двух объектов: оператора генерации новой точки (tweak) и расписания понижения температуры. Оба объекта реализуются по вашему усмотрению. Цель состоит в нахождении наилучшего решения (с точки зрения ожидаемой скорости сходимости к наименьшему количеству конфликтов) для произвольных графов Эрдеша-Реньи со 100 узлами и $p \ll 1$.

Дедлайн: 2024.04.27
