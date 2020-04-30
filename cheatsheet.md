# Kotlin Mutiplatform mobile cheatsheet

## suspend недоступен в swift
При компиляции kotlin в ios framework нужно учитывать, что suspend-функции, использованные в публичном интерфейсе, автоматически стираются. Это происходит потому что в objective-c (и swift) нет аналога suspend-функций. По этой причине рекомендуется держать всю работу с kotlin-coroutines внутри kotlin.  
Если же требуется вызывать suspend-функцию из swift/objective-c, то можно в ios-specific коде сделать экстеншен-функцию принимающую callback, а внутри функции запускать корутину например на GlobalScope. При чем это можно делать не вручную, а использовать плагин, генерирующий такую функцию автоматически, например - [Recast](https://github.com/andrewemery/recast), [kotlin-native-suspend-function-callback](https://github.com/feilfeilundfeil/kotlin-native-suspend-function-callback).

## abstract недоступен в swift
При компиляции Kotlin в iOS-framework нужно учитывать, что abstract class'ы станут в Objective-C (и Swift) обычными классами. Это происходит из-за того, что в Objective-C и Swift нет абстрактных классов. Поэтому Xcode при компиляции никак не проверит реализовал ли разработчик абстрактный метод или нет. Если абстрактный метод останется не реализованным то в рантайме будет выброшено исключение. 
Рекомендуется просто не выносить абстрактные классы в публичный интерфейс. Их можно использовать внутри kotlin, а наружу можно выдать интерфейс, который требуется с нативной стороны реализовать.

## Strict memory model у Kotlin/Native
В Kotlin/Native модель памяти имеет жесткие ограничения на работу с объектами из разных потоков. 
Коротко - поток может работать с объектом только если объект не изменяемый либо объект привязан именно к этому потоку. 
Для работы данных между потоками нужно использовать либо механизм [заморозки (freeze) объекта](https://github.com/JetBrains/kotlin-native/blob/master/CONCURRENCY.md#object-transfer-and-freezing), чтобы превратить объект в немутабельный и его можно было безопасно читать с любого потока. Либо использовать механизм [передачи владения объектом](https://github.com/JetBrains/kotlin-native/blob/master/CONCURRENCY.md#object-subgraph-detachment) чтобы право читать и менять объект перешло на другой поток.
Сильно более подробно указано в [документации](https://github.com/JetBrains/kotlin-native/blob/master/CONCURRENCY.md) и при необходмости работать с многопоточностью в Kotlin/Native обязательно нужно ознакомиться и с документацией и с серией статей - [Practical Kotlin Native Concurrency](https://dev.to/touchlab/practical-kotlin-native-concurrency-ac7). 
