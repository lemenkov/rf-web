.. title: Предложены радикальные (разумеется!) изменения в работу сети в Linux.
.. slug: Предложены-радикальные-разумеется-изменения-в-работу-сети-в-linux
.. date: 2012-08-29 23:42:08
.. tags:
.. category:
.. link:
.. description:
.. type: text
.. author: Peter Lemenkov

**Это архивная статья**


`Olaf Kirch <http://www.linkedin.com/pub/olaf-kirch/3/365/41>`__,
участник коммьюнити SUSE, матерый Linux-хакер (с начала 1990х), и автор
`неоднократно переиздававшихся книг по настройке и администрированию
сети в Linux <http://www.oreillynet.com/pub/au/408>`__, предложил
сегодня на рассмотрение сообщества Fedora свою давно вынашиваемую идею -
`полностью переписать userspace стек управления сетью в
Linux <https://thread.gmane.org/gmane.linux.redhat.fedora.devel/168121>`__,
учитывая накопленный за два десятка лет опыт. Новая архитектура сетевой
подсистемы позволит, как считает Olaf, полностью отказаться как от
неподдерживаемой мешанины bash-скриптов (`давным давно устаревших
ifup/ifdown и прочего <http://busybox.net/~vda/no_ifup.txt>`__), так и
от критикуемого за сложность и такую же неподдерживаемость
NetworkManager. В предложенной им архитектуре сетевой стек четко
разделяется на несколько слоев, сущности внутри которых конфигурируются
с помощью XML ( все таки, наверное, бинарный реестр настроек подошел бы
более лучше - изменяемый командами в консоли наподобие *defaults write
com.apple.finder AppleShowAllFiles TRUE*).
Предложение уже получило как критические отзывы (от инженера Red Hat и
текущего мэйнтейнера busybox, `Denys
Vlasenko <http://busybox.net/~vda/resume/denys_vlasenko.htm>`__), так и
сдержанно заинтересованные ответы. Мы будем следить за развитием
событий.

PS Olaf работает начальником в Novell, и если вы нашли в его предложении
архитектурные проблемы, или у вас есть идеи, как сделать лучше, то
присылайте ему ваше резюме. Ваш шанс на трудоустройство, аналитики!
