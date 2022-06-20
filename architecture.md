Архитектура `Scheduler` в обобщенном виде представляет собой взаимодействие 3-х блоков: компонент `Scheduler`, компонент `Workspace` - сетка дат, компонент `Appointments` - события на сетке.
Остальные модули реализуют особенности логики построения событий и сетки дат.
`recurrence` - модуль построения повторяющихся событий (создан на основе RRule). Файл: `recurrence.js`

Диаграмма ниже иллюстрирует порождающие и ассоциативные связи между объектами.

@startuml
title Scheduler objects

object timezone
object recurrence
object virtualization
object resources

scheduler --> workspaces
scheduler --> appointments

workspaces..> timezone
workspaces..> resources
workspaces ..> virtualization
appointments ..> timezone
appointments ..> recurrence
appointments ..> resources
appointments ..> virtualization

@enduml


