## Logging System

* Motivation

  * 现有100台服务器，每台均会生成log，用一台额外的专门服务器同于收集汇总这些log，设计一个这样的系统，同时该log服务器还要满足一些数据查询需求（比如差一段时间内某些异常抛出的次数）（Nvidia interview summary）

  * 设计一个日志收集系统，手机端网页端的client发送数据过来，然后有两种使用场景，一种是data analyst需要用原始数据写sql做分析，另一种dashboard，可以拉时间条，显示时间段里的统计数量（word by a friend）

* Functional Requirement

* Non Functional Requirement

* sharding key

* Reference

  * [System Design Mock Interview - Design distributed metrics logging system](https://www.youtube.com/watch?v=aiSoZBfFk0M)

