.. title: Новости systemd/Linux-платформы
.. slug: Новости-systemdlinux-платформы-0
.. date: 2015-03-14 19:53:35
.. tags: ubuntu, canonical, systemd, erlang, rabbitmq, amqp, openstack, voip, rhel
.. category:
.. link:
.. description:
.. type: text
.. author: Peter Lemenkov

**Это архивная статья**


С окончательным переходом Ubuntu на systemd на нашего товарища, инженера
Canonical, Martin Pitt, рекой потекли багрепорты. Его, конечно, это не
пугает, и он `бесстрашно смеется над
опасностью <https://plus.google.com/+MartinPitti/posts/GDXUmyAkh8n>`__.
Конечно, если бы его начальство не упиралось бессмысленно, то у них бы
сейчас была бы и IVI-версия, и версия для телефона, и версия для
телевизора. Ну, будем надеяться, что от самодельного аналога Wayland они
откажутся оперативнее, без попыток навязать свое нестандартное решение
другим, в т.ч. в материнский дистрибутив. Все равно ведь придется
отказываться, так что тянуть?

Мы пока неторопливо добавляем поддержку systemd в сервисы. Конечно, речь
не идет о том, чтобы переводить на исключительное использование systemd
- поддержка огораживается ifdef-ами, т.к. еще есть Mac OS X и FreeBSD.
Но если вы используете Linux-дистрибутив, которые уже все перешли на
systemd, за исключением нескольких отмирающих или узкоспецифичных
дистрибутивов, то вы можете заметить улучшенную интеграцию сервисов с
systemd. Недавно была добавлена `в Apache поддержка журналирования с
помощью
Journald <https://httpd.apache.org/docs/trunk/mod/mod_journald.html>`__.
Новый функционал доступен начиная с версии 2.5, и пока есть какие-то
проблемы с производительностью, но можно надеяться, что `способ
перенаправления журнала Apache в
Journald <https://harald.hoyer.xyz/2013/11/07/redirecting-apache-access_log-and-error_log-to-the-systemd-journal/>`__
скоро будет неактуален.

AMQP-сервер RabbitMQ, написанный на Erlang и популярный при
проектировании облачных систем на базе OpenStack, начиная с `версии
3.5.0 <https://www.rabbitmq.com/release-notes/README-3.5.0.txt>`__ имеет
штатную поддержку
`systemd-notify <https://github.com/rabbitmq/rabbitmq-server/pull/52>`__.
Мы `тестировали эту функциональность около
полугода </content/erlang-и-systemd>`__, и теперь перенесли в апстрим,
что позволит и другим дистрибутивам решить ряд проблем.

Мы работаем и над интеграцией не столь широко использующихся сервисов.
Например, широко известный в узких кругах VoIP-разработчиков и
архитекторов RTPproxy недавно получил (`раз pull
request <https://github.com/sippy/rtpproxy/pull/11>`__ и `два pull
request <https://github.com/sippy/rtpproxy/pull/14>`__) поддержку
systemd, о чем теперь официально объявлено в `анонсе недавно вышедшей
версии 2.0.0 <https://github.com/sippy/rtpproxy/releases/tag/v2.0.0>`__.

Не все так гладко в других проектах, где разработчики, предлагающие
патчи для лучшей работы с systemd, порой наталкиваются на необъяснимую
агрессию со стороны upstream-разработчиков. Например, включение
небольшого патча для systemd в
`Polipo <http://www.pps.univ-paris-diderot.fr/~jch/software/polipo/>`__
идет уже несколько лет. `Автор Polipo был против включения в 2012
году <https://thread.gmane.org/gmane.comp.web.polipo.user/2840/focus=2871>`__,
выкатив ряд надуманных возражений (зависимость от хидеров из systemd,
затем, уже после отказа от них, он начал всерьез упоминать про runit, и
притворяться, что размер патча слишком большой, чтоб его просмотреть).
Прошла пара лет, и он уже после дежурных проклятий в сторону systemd, на
которые мы внимания уже не обращаем, `пообещал заревьюить
его <https://thread.gmane.org/gmane.comp.web.polipo.user/3332/focus=3334>`__,
да так и замылил это дело. Но разработчики не сдаются, и `вновь оформили
pull request <https://github.com/jech/polipo/pull/54>`__ - вода камень
точит. Вообще, проблема в том, что Polipo, это нынешний де-факто
фронтэнд-модуль для Tor, и хотелось бы, чтоб его интеграция в
systemd/Linux платформу была бы получше. Раньше использовали Privoxy, но
потом перешли на Polipo, хотя их функциональность различается, и можно
было бы использовать одновременно оба.

Мы уже говорили, что systemd в RHEL 7 и производных дистрибутивах
слишком стар - в нем, например, нет поддержки конфигурирования сети.
`Lukáš Nykrýn <https://www.openhub.net/accounts/lnykryn>`__ подготовил
специальный репозиторий для RHEL7 с самой новой версией systemd, `о чем
мы вам уже говорили </content/Новости-systemd>`__. На днях `он обновил
systemd до версии
219 <https://plus.google.com/+LukášNykrýn/posts/2L5toMPCA7b>`__.
Некоторые наши коллеги уже вовсю используют его сборку в
production-системах, наслаждаясь возможностями по управлению сетью. К
сожалению, код очень экспериментальный, и `порой на ровном месте
возникают не очень понятные
эффекты <https://thread.gmane.org/gmane.comp.sysutils.systemd.devel/28075>`__.

Нас, конечно, проблемы не пугают!

.. image:: http://sharomet.ru/wa-data/public/shop/products/54/86/18654/images/6134/6134.750x0.jpg
   :align: center
   :target: http://sharomet.ru/shevron-slaboumie-i-otvaga/
