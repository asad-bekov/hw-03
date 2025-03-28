
# Домашнее задание «Система мониторинга Zabbix. Часть 2»

## Задание 1

**Создание шаблона в Zabbix с элементами данных для мониторинга загрузки CPU и RAM.**

1. В разделе **Конфигурация** → **Шаблоны** был создан новый шаблон.
2. Добавлены два элемента данных:
   - **CPU Load:** мониторинг загрузки CPU в процентах с использованием ключа `system.cpu.load[all,avg1]`.
   - **RAM Usage:** мониторинг использования RAM в процентах с использованием ключа `vm.memory.size[available]`.
3. Шаблон успешно сохранен и может быть привязан к хостам.

![Задание 1](https://github.com/asad-bekov/hw-03/blob/main/img/img1.png)

---

## Задание 2-3
**Добавление двух хостов в Zabbix и привязка шаблонов.**

1. На двух виртуальных машинах был установлен Zabbix Agent.
2. Добавлены хосты в Zabbix с именами `Asadbekov_AD-1` и `Asadbekov_AD-1`.
3. К каждому хосту привязаны два шаблона:
   - **Linux by Zabbix Agent**.
   - Шаблон, созданный в задании 1.
4. Убедились, что данные поступают в **Последние данные**.

![Задание 2-3](https://github.com/asad-bekov/hw-03/blob/main/img/img2.png)
![Задание 2-3](https://github.com/asad-bekov/hw-03/blob/main/img/img6.png)

---

## Задание 4
**Создание пользовательского дашборда.**

1. Перешел в раздел **Мониторинг** → **Дашборды**.
2. Создал новый дашборд, на котором размещены графики:
   - Загрузка CPU.
   - Использование RAM.
   - Доступность узла сети.
   - Часы.
3. Настроены удобные виджеты для отображения ключевых данных.

![Задание 4](https://github.com/asad-bekov/hw-03/blob/main/img/img3.png)

---

## Задание 5
**Создание карты и настройка триггера.**

1. В разделе **Конфигурация** → **Карты** создана новая карта.
2. Размещены два хоста из задания 2-3.
3. Между хостами настроена связь:
   - К связи привязан триггер, связанный с `agent.ping`.
   - При срабатывании триггера цвет линии меняется на красный пунктир.
4. Один из хостов был выключен, чтобы проверить срабатывание триггера. Связь отобразилась красной пунктирной линией.

![Задание 5](https://github.com/asad-bekov/hw-03/blob/main/img/img4.png)
![Задание 5](https://github.com/asad-bekov/hw-03/blob/main/img/img5.png)