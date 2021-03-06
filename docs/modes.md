Полетные режимы
===

Режим полетного контроллера определяет, как именно коптер (или другое ТС) должно себя вести: каким обрзом интерпретировать входящие команды и сигналы с пульта.

PX4
---

Основная статья: https://dev.px4.io/en/concept/flight_modes.html

### Ручное управление (MANUAL)

При ручном управлении пилот управляет квадрокоптером напрямую. GPS, данные с компьютерного зрения и барометр не используются. Для полетов в этих режимах необходимы хорошие навыки пилотирования мультикоптеров.

* **MANUAL** — сигналы с пульта идут напрямую в миксер и на моторы. Управление газом и соотношением скорости вращения передней/задней, правой/левой парой моторов. Этот режим практически не используется для полетов, так как поддерживать стабильное состояние коптера слишком сложно.

* **STABILIZED** — режим стабилизации горизонтального положения. Управление газом, углами наклона коптера по тангажу и крену, угловой скоростью по рысканью.

* **ACRO** — управление газом и угловой скоростью коптера по тангажу, крену и рысканью. Используется дрон-рейсерами и в шоу 3D-пилотирования для выполнения трюков.

* **RATTITUDE** — в центре правый стик аналогичен STABILIZED, по краям переходит в режим ACRO.

### С использованием дополнительных датчиков (ASSISTED)

* **ALTCTL** — управление скоростью изменения высоты полета, углами по тангажу и крену и угловой скоростью по рысканью. Используется барометр (или иной датчик высоты).

* **POSCTL** — управление скоростями набора высоты, скоростью движения вперед/назад и вправо/влево, угловой скоростью по рысканью. Наиболее простой для полетов режим. Используется барометр, GPS, компьютерное зрение, другие датчики.


### Автоматический полет (AUTO)

TODO

### Управление с внешнего компьютера

* **OFFBOARD** — режим для полета по командам MAVLink. Управление с внешнего компьютера (например, Raspberry Pi).

Основные используемые пакеты MAVLink:

* MAV_CMD_COMPONENT_ARM_DISARM
* [SET_POSITION_TARGET_LOCAL_NED](https://pixhawk.ethz.ch/mavlink/#SET_POSITION_TARGET_LOCAL_NED)
* [SET_ATTITUDE_TARGET](https://pixhawk.ethz.ch/mavlink/#SET_ATTITUDE_TARGET)

См: [Управление коптером с помощью пакета MAVROS](mavros.md)
