.. title: Вышло пятое обновление RHEL 6 (и десятое RHEL5)
.. slug: Вышло-пятое-обновление-rhel-6-и-десятое-rhel5
.. date: 2013-10-07 09:53:14
.. tags: rhel, патенты, legal, ptp, namespaces, containers, openssh, ecc, openssl, nss, virtualization, qemu, glusterfs, ФСТЭК
.. category:
.. link:
.. description:
.. type: text
.. author: Peter Lemenkov

*УПД немного поспешили - это пока еще бета RHEL 6.5.*

Несколько дней назад вышло пятое обновление RHEL6. `Среди изменений
<https://access.redhat.com/site/documentation/en-US/Red_Hat_Enterprise_Linux/6-Beta/html-single/6.5_Release_Notes/>`__
можно выделить следующие:

- Включение средств для работы с протоколом PTPD, о включении которых в Fedora
  `мы уже говорили
  </content/Истекли-патенты-на-ptp-precision-time-protocol>`__.

- Network namespaces для контейнеров.

- Еще один шаг в сторону отказа от MD5 - возможность выбора между SHA1 и MD5 в
  SCTP

- Обновление OpenSSL до версии 1.0.1

-  Поддержка аутентификации с помощью смарт-карт в OpenSSH

- Долгожданная (пока частичная) поддержка Elliptic Curve Crypto, о чем мы вам
  `рассказали полтора месяца назад
  </content/Новости-об-elliptic-curve-cryptogtaphy-в-fedora>`__.

  Частично в OpenSSL, полностью в NSS, т.к. он модульный, плюс добавлена
  возможность легкой пересборки OpenSSL и установки в параллель (легкой по
  сравнению с прежней ситуацией) - теперь можно добавить остальные алгоритмы,
  например GOST.

- Общие системные сертификаты. Теперь nss, openssl, и прочие приложения и
  библиотеки, использующие криптографические сертификаты (например, для HTTPS)
  по умолчанию настроены на использование единого хранилища.

- Сильно улучшена совместимость системы виртуализации с проприетарными
  виртуализационными системами и популярной проприетарной гостевой операционной
  системой.

- Qemu собран с поддержкой GlusterFS и CPU hot-plugging

- Добавлена поддержка "заморозки" файловой системы (например, на время бэкапа)

- Включение LVM Thin Provisioning, фичи, `запланированной и уже доступной в
  Fedora 20 </content/И-опять-новые-фичи-fedora-20>`__

- Обновление сертификации FIPS

- И наверное самое важное для российских корпоративных пользователей -
  получение сертификации ФСТЭК на эту и все прочие версии RHEL6.

~~Ждем CentOS 6~~. Ну и для legacy систем, вышло обновление `RHEL 5.10
<https://access.redhat.com/site/documentation/en-US/Red_Hat_Enterprise_Linux/5/html-single/5.10_Release_Notes/index.html>`__,
которое уже `обсуждается на OpenNET.ru
<https://www.opennet.ru/opennews/art.shtml?num=38048>`__.
