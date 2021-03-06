.. title: AltLinux постепенно переходит на systemd
.. slug: altlinux-постепенно-переходит-на-systemd
.. date: 2012-08-22 15:17:39
.. tags: altlinux, systemd, debian, upstart, openrc, canonical
.. category:
.. link:
.. description:
.. type: text
.. author: Peter Lemenkov

Одобряем `действия
соотечественников <http://forum.altlinux.org/index.php?topic=24357.0>`__!

А в списке рассылки Debian был `предложен конвертер из формата service-файлов
для systemd в традиционные SysV-скрипты
<https://thread.gmane.org/gmane.linux.debian.devel.general/175854>`__, что
теоретически устранит последнее препятствие перед переходом Debian на systemd
(переходу препятствовали сборки с альтернативными устаревшими или
неработоспособными ядрами Unix-подобных систем).

Для тех, кто не в курсе, в debian-devel с зимы-весны 2012 года обсуждают
переход на новый init. Т.к. всем уже понятно, что SysV, это устаревшая система
(с этим полный консенсус), то споры идут лишь о том, на что переходить? Сейчас
всерьез рассматривают переход на Upstart или Systemd. Большинство, за
исключением иногда заскакивающих на обсуждение соотечественников, высказывается
в пользу systemd, особенно в свете последних событий, когда приостановка
разработки Upstart серьезно понизила его шансы на внедрение.

Малочисленная оппозиция `предлагает еще и
OpenRC <https://thread.gmane.org/gmane.linux.debian.devel.bugs.general/981820>`__,
однако против него выдвигают возражения - он не приносит реальных
улучшений, и его до сих пор даже не включили в Debian. В общем посмотрим
- все еще сохраняется интрига, т.к. у Upstart тоже есть сторонники
(например, Canonical, хотя они и не развивают его больше).

Новость активно обсуждается аналитиками `на OpenNET.ru
<https://www.opennet.ru/opennews/art.shtml?num=34623>`__ и `на Linux.org.ru
<https://www.linux.org.ru/forum/talks/8131760>`__.
