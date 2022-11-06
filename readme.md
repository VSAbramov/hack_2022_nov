# Запуск чз Docker
* установить docker и docker-compose
* распаковать архив
* зайти в папку hackaton
* выполнить из терминала команду docker-compose build
* после её завершение docker-compose up
* открыть браузер и вбить в адресной строке 0.0.0.0:8000


# Запуск вручную
* распаковать архив
* зайти в папку hackaton
* в консоли pip3 install -r requirements.txt
* зайти в hackaton/backend/server
* выполнить ./manage.py runserver
* открыть браузер и вбить в адресной строке127.0.0.1:8000


```mermaid
flowchart TB
	node1[(данные c хакатона)] --> snode1
	node2[(данные с координатами с data.mos.ru)] --> snode2
	
	subgraph подготовка_данных
	 snode2([парсер координат]) -->
	 snode1([обработчик])
	end
	
	подготовка_данных  --> node3{back end}
	subgraph Django	
	  node3 <--> node4[[front end]]
	end
```