<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <title>Лабораторная работа №1</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
            background-color: lightgray
        }
        button {
            background-color: white;
            display: block;
            margin: 10px auto;
            padding: 10px 20px;
            font-size: 15px;
            cursor: pointer;
        }
    </style>
</head>
<body>

<h1>Лабораторная работа №1 JavaScript</h1>

<button onclick="task1()">Задание 1</button>
<button onclick="task2()">Задание 2</button>
<button onclick="task3()">Задание 3</button>
<button onclick="task4()">Задание 4</button>
<button onclick="task5()">Задание 5</button>
<button onclick="task6()">Задание 6</button>
<button onclick="task7()">Задание 7</button>

<script>
function task1() {
    let day = prompt("Введите день недели на русском:");

    switch(day.toLowerCase()) {
        case "понедельник": alert("Monday"); break;
        case "вторник": alert("Tuesday"); break;
        case "среда": alert("Wednesday"); break;
        case "четверг": alert("Thursday"); break;
        case "пятница": alert("Friday"); break;
        case "суббота": alert("Saturday"); break;
        case "воскресенье": alert("Sunday"); break;
        default: alert("Неизвестный день!");
    }
}

function task2() {
    let score = 0;

    for (let i = 1; i <= 10; i++) {
        let a = Math.floor(Math.random() * 10);
        let b = Math.floor(Math.random() * 10);
        let answer = prompt(`Вопрос ${i}: ${a} + ${b} = ?`);

        if (parseInt(answer) === a + b) {
            score++;
        }
    }

    let grade = Math.floor(score / 2);
    alert(`Правильных ответов: ${score}\nОценка: ${grade}`);
}

function task3() {
    let candidate = {
        name: prompt("Имя:"),
        surname: prompt("Фамилия:"),
        birthYear: parseInt(prompt("Год рождения:")),
        specialty: prompt("Специальность:"),
        experience: parseInt(prompt("Стаж работы:")),
        languages: prompt("Языки программирования (через пробел):").split(" ")
    };

    let age = new Date().getFullYear() - candidate.birthYear;

    if (
        age > 18 &&
        candidate.experience > 2 &&
        candidate.specialty.toLowerCase() === "разработчик" &&
        candidate.languages.includes("JavaScript")
    ) {
        candidate.status = "соответствует";
    }

    console.log(candidate);
    alert("Данные выведены в консоль (F12)");
}

function task4() {
    let n = parseInt(prompt("Введите число (0 < x <= 10):"));
    let fact = 1;

    for (let i = 1; i <= n; i++) {
        fact *= i;
    }

    alert(`Факториал: ${fact}`);
}

function task5() {
    let num = parseInt(prompt("Введите трехзначное число:"));

    let sum = Math.floor(num / 100) +
    Math.floor((num % 100) / 10) +(num % 10);
    alert(`Сумма цифр: ${sum}`);
}

function task6() {
    let binary = prompt("Введите двоичное число:");
    let decimal = parseInt(binary, 2);
    alert(`Десятичное число: ${decimal}`);
}

function task7() {
    let hex = prompt("Введите шестнадцатеричное число:");
    let decimal = parseInt(hex, 16);
    alert(`Десятичное число: ${decimal}`);
}
</script>

</body>
</html>
