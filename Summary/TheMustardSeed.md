<html>
<body>

<head>
    <meta charset="UTF-8">
    <title>The Mustard Seeds</title>
</head>

<h2 id='pageTop'>The Mustard Seeds</h2>
<div>
    <fieldset>
        <legend>Апликушки</legend>
        <p>
            Структура Апликушек сделана на основе Budget Reporting Departments (LEVEL 1).
            Апликушки в три уровня по принципу:
            1.1 Консолидированный по году
            1.2 Budget Reporting Department (один из многих типа LEVEL 1)
            1.3 Общий Dimension2 из мапинга Budget Reporting Department
        </p>
        <p>
            Апликушки генерятся локальным скриптом из Budget and Balances (переделаем под RB) с учетом мапинга. Алгоритм
            пока НЕ батч и без интерфейса. Данные залиты пока не все и криво (некоторые ВВ не подпадают ни под какой
            мапинг или попадаются под несколько мапинг-правил).
        </p>
    </fieldset>

    <br/>

    <fieldset>
        <legend>Линия факта</legend>
        <p>
            Факт получаем из ФФ интеграции FFRB => CBRB => CB Entries => Reports
        </p>
    </fieldset>

    <br/>

    <fieldset>
        <legend>Отчетная часть</legend>
        <p>
            Budget Reporting Departments всех уровней дублируются в СВ (ссылка в Home)
        </p>
        <p>
            CBalance которые относятся к рулам c навзаниями LVL1...LVL3 генерятся локальным скриптом без интерфейса НЕ
            батч. Они используют мапинг Budget Reporting Departments (LEVEL 1... LEVEL 1) Чтобы из CB Entries сделать
            CBalance правильной принадлежности к одному из Budget Reporting Departments
        </p>
        <p>
            СВ Репорты лучше открывать LVL2 или LVL3 они не такие огромные как LVL1
        </p>
    </fieldset>

    <br/>

    <fieldset>
        <legend>Другое</legend>
        <p>
            Дашборды сделаны на все три LVL Budget Reporting Departments
        </p>
        <p>
            Нужен модуль для анализа мапинга - дубирования/пропуски
        </p>
    </fieldset>

    <br/>


</div>
<br/>


<br/>
<hr/>
<div>

    <p><a href="https://cloudbudgetinc.github.io/Documentation/Summary">Back</a></p>
</div>

<button onclick="topFunction()" id="myBtn" title="Go to top">Top</button>

<script>
    let mybutton = document.getElementById("myBtn");
    window.onscroll = function () {
        scrollFunction()
    };

    function scrollFunction() {
        mybutton.style.display = document.body.scrollTop > 20 || document.documentElement.scrollTop > 20 ? "block" : "none";
    }

    function topFunction() {
        document.body.scrollTop = 0;
        document.documentElement.scrollTop = 0;
    }
</script>

<style>

    #pageTop {
        text-align: center;
        font-weight: bold;
    }

    #myBtn {
        display: none;
        position: fixed;
        bottom: 20px;
        right: 30px;
        z-index: 99;
        font-size: 18px;
        border: 1px solid #b5e853;
        outline: none;
        background-color: #171717;
        color: #b5e853;
        cursor: pointer;
        padding: 15px;
        border-radius: 4px;
    }

    #myBtn:hover {
        background-color: #181818;
    }


    fieldset {
        font-family: sans-serif;
        border: 5px solid #1F497D;
        background: #ddd;
        border-radius: 5px;
        padding: 15px;
        color: #505050;
        box-shadow: 8px -8px 17px 0px rgba(0,0,0,0.75);
    }

    fieldset legend {
        background: #1F497D;
        color: #fff;
        padding: 5px 10px;
        font-size: 16px;
        border-radius: 5px;
        margin-left: 20px;
        box-shadow: 8px -8px 17px 0px rgba(0,0,0,0.75);
    }
</style>


</body>
</html>