# ScanLab - открытая альтернатива поисковому сервису shodanhq.com

Суть такова: сканируешь диапазоны nmap'ом, заливаешь в базу ScanLab и просматриваешь отчёты с крутым графоном!

Как и в знаменитом (в узких кругах) поисковике shodan, в scanlab можно находить камеры, роутеры, светофоры, холодильники и подобные устройства, подключенные к интернету.
Гибкий поисковый синтаксис позволит проще откапывать в куче мусорных отчётов нужные результаты.
Если ShodanHQ использует свой простой сканер портов, то в ScanLab используется вся мощь NMAP.
Плюс к этому, ScanLab бесплатен и открыт, ты можешь скачать и установить его себе в виртуалку или на VPS.

В ScanLab так же имеются оригинальные фичи: тэги, система рейтинга хостов, удобный и умный консольный клиент.
Тэги сделаны, чтобы проще искать разные типы девайсов в сети: камеры, роутеры, принтеры и т.д. помечаются соответствующим тэгом.
Рейтинг и избранное сделаны, чтобы сохранять интересные устройства для последующего изучения. Добавление и удаление из избранного соответственно увеличивает и уменьшает рейтинг хоста.
С консольным клиентом все еще интереснее! 
В первую очередь, клиент используется для загрузки готовых отчётов nmap в базу, но так же умеет сам сканировать и загружать результаты на сервер.
Уникальный ScanLab Mode в клиенте умеет очень быстро сканировать множество подсетей.
А еще в нём есть возможность генерировать случайные IP и домены для сканирования.

Что такое ScanLab Mode?
Это такой крутой режим сканирования, реализованный специально для главной базы ScanLab.
Суть в том, что в этом режиме мы по очереди сканируем одну и ту же цель на ОДИН порт (например -p 80) без определения его живучести (-Pn).
Таким образом, каждая цель сканируется по очереди на определённые в конфиге порты и с определённым набором NSE скриптов. 
Такой подход существенно увеличивает скорость и количество лута по сравнению с обчными сканами.
Однако, этот режим стоит применять исключительно для сканирования больших диапазонов и подсетей.
Если генерируешь случайные IP или домены, то эффективнее сканировать в обычном режиме.

Если ты умеешь в быдлокодинг, можешь добавить какие-то фичи и кинуть в разработчика pull request.
Наиболее приоритетной задачей для разработки сейчас является полностью кроссплатформенный графический клиент.
Так же реквестируется кулхацкер, который пошерстит по исходникам и рискнёт найти уязвимости в этом идеально безопасном коде.
