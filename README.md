# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #4 выполнил:
- Кармацкий Савелий Андреевич
- РИ210942
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | # | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Структура отчета

- Данные о работе: название работы, фио, группа, выполненные задания.
- Цель работы.
- Задание 1.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 2.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 3.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Выводы.
- ✨Magic ✨

## Цель работы

Ознакомиться с перцептроном

## Задание 1 В проекте Unity реализовать перцептрон, который умеет производить вычисления:
+ OR 
![Image alt](https://raw.githubusercontent.com/Karmatsky/DA-in-GameDev-lab4/main/OR.png)
+ AND
![Image alt](https://raw.githubusercontent.com/Karmatsky/DA-in-GameDev-lab4/main/AND.png)
+ NAND
![Image alt](https://raw.githubusercontent.com/Karmatsky/DA-in-GameDev-lab4/main/NAND.png)
+ XOR
![Image alt](https://raw.githubusercontent.com/Karmatsky/DA-in-GameDev-lab4/main/XOR.png)

## Задание 2 Построить графики зависимости количества эпох от ошибки обучения. Указать от чего зависит необходимое количество эпох обучения

Построены графики зависимости количества эпох от ошибки обучения для каждой логической операции(OR, AND, NAND и XOR). Графики totalError(AND) и totalError(NAND) совпадают, поэтому на скрине не видно красного графика totalError(AND). Мы видим, что для всех логичских операций(кроме XOR, так как он сложный) необходимо почти одинаковое количество эпох, чтобы totalerror был ближе к 0.

![Image alt](https://raw.githubusercontent.com/Karmatsky/DA-in-GameDev-lab4/main/graphics.png)

Вывод: необходимое количество эпох обучения зависит от bias - смещение и weights - веса. Доказательство можно увидеть в коде ниже:

```cs
double DotProductBias(double[] v1, double[] v2) 
	{
		if (v1 == null || v2 == null)
			return -1;
	 
		if (v1.Length != v2.Length)
			return -1;
	 
		double d = 0;
		for (int x = 0; x < v1.Length; x++)
		{
			d += v1[x] * v2[x];
		}

		d += bias;
	 
		return d;
	}

	double CalcOutput(int i)
	{
		double dp = DotProductBias(weights,ts[i].input);
		if(dp > 0) return(1);
		return (0);
	}
```

## Задание 3 Построить визуальную модель работы перцептрона на сцене Unity

## Выводы
В ходе данной лабораторной работы, я познакомился с перцептроном: изучил его код, произвел вычисления с помощью логических операций. Обнаружил, что с помощью одного перцептрона нельзя найти данные через XOR, так как XOR нелинейноделимая.

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

