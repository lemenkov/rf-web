.. title: Новости пакета util-linux (снова)
.. slug: Новости-пакета-util-linux-снова
.. date: 2012-09-17 16:36:30
.. tags: util-linux, systemd
.. category:
.. link:
.. description:
.. type: text
.. author: Peter Lemenkov

`Мы уже сообщали о новостях в этом пакете утилит
</content/Новости-пакета-util-linux>`__, и пришло время для новой порции.
Мэйнтейнер и основной разработчик пакета `util-linux
<https://en.wikipedia.org/wiki/Util-linux>`__, инженер Red Hat и участник
Fedora, `Karel Zak <https://www.openhub.net/accounts/kzak>`__, вновь поделился
`информацией о последних нововведениях
<http://karelzak.blogspot.com/2012/09/util-linux-222.html>`__:

- Утилиты mount, umount и swapon теперь принимают PARTLABEL и PARTUUID
  спецификации. Похоже, что задавать физическое имя раздела скоро будет совсем
  не нужно.

- Утилита dmesg теперь по передаче параметра --follow переключается в режим
  непрерывного чтения из устройства */dev/kmsg*. Необходимые изменения в
  ядерную подсистему ведения журнала, чтоб такое его поведение было вообще
  возможно, предложил и реализовал разработчик udev и systemd `Kay Sievers
  <https://www.openhub.net/accounts/kaysievers>`__, о чем `мы уже писали
  </content/Бинарные-логи-в-ядре>`__. Теперь в ядре ведутся бинарные логи,
  между прочим.

- Продолжается поглощение SysVinit-утилит, которые теперь доработаны под нужды
  systemd - в пакет включены sulogin и utmpdump.

- Включена утилита eject, которая была полностью переписана.

- Утилита lslocks заменила lslk

- Доработана утилита findmnt, которая теперь может показывать точки
  монтирования в зависимости от процесса (это активно используется в systemd,
  например). Также в следующей версии (2.23) планируется добавить параметр
  --unshared-tasks, позволяющий показать все процессы с приватными точками
  монтирования (также используется в systemd).

- Добавлен новый формат вывода утилиты lsblk - в виде обратного дерева.

- Переписана утилита fdisk - теперь все готово для поддержки GPT в следующей
  версии (2.23).

- Полностью удалена поддержка cryptoloop. Вместо нее рекомендуется использовать
  dm-crypt.

Отдельно Karel отмечает, что удалось добиться хорошего взаимодействия с
коллективами разработчиков других проектов (coreutils, procps-ng,
systemd), что улучшило процесс разработки. А разработчики init-системы
вашего дистрибутива координируют свою работу с командами базовых пакетов
Linux?
