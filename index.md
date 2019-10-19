# Kotlin Mobile MultiPlatform
## Полезные ресурсы
* [https://kotlinlang.slack.com](https://kotlinlang.slack.com) (#kotlin-native , #multiplatform)
* [https://kotlinlang.org/docs/reference/multiplatform.html](https://kotlinlang.org/docs/reference/multiplatform.html)
* [https://kotlinlang.org/docs/reference/building-mpp-with-gradle.html](https://kotlinlang.org/docs/reference/building-mpp-with-gradle.html)
* [https://kotlinlang.org/docs/reference/native/concurrency.html](https://kotlinlang.org/docs/reference/native/concurrency.html)
* [https://kotlinlang.org/docs/reference/native/objc_interop.html](https://kotlinlang.org/docs/reference/native/objc_interop.html)
* [https://kotlinlang.org/docs/reference/native/faq.html](https://kotlinlang.org/docs/reference/native/faq.html)
* [https://medium.com/@kpgalligan](https://medium.com/@kpgalligan)

## Еще полезные ресурсы, от IceRock
* Телеграм канал с новостями по mobile multiplatform, обзором библиотек и кейсов из разработки - [https://t.me/kotlinmpp](https://t.me/kotlinmpp)
* Блог в medium - [https://medium.com/@icerock](https://medium.com/@icerock)
  * [Опыт работы с Kotlin Multiplatform за 10 месяцев](https://medium.com/@icerock/%D0%BE%D0%BF%D1%8B%D1%82-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%8B-%D1%81-kotlin-multiplatform-%D0%B7%D0%B0-10-%D0%BC%D0%B5%D1%81%D1%8F%D1%86%D0%B5%D0%B2-435a7e08e52d) - хронологический разбор с чем мы столкнулись за первые 10 месяцев работы с Kotlin MultiPlatform.
* GitHub - [https://github.com/icerockdev](https://github.com/icerockdev)
  * [https://github.com/icerockdev/mobile-multiplatform-education](https://github.com/icerockdev/mobile-multiplatform-education) - пошаговое создание мультиплатформенного проекта с нуля (1 коммит - 1 шаг), проект ведется в пределах внутреннего обучения сотрудников, но по коммитам можно и внешним людям обучаться (в будущем будет codelabs сделаны).

## Проекты примеры
* [https://github.com/JetBrains/kotlinconf-app](https://github.com/JetBrains/kotlinconf-app) - официальное приложение KotlinConf - backend, android, ios с общим кодом;
* [https://github.com/Kotlin/mpp-example](https://github.com/Kotlin/mpp-example) - официальный пример от JB мобильного MPP проекта (android + ios);
* [https://github.com/touchlab/DroidconKotlin](https://github.com/touchlab/DroidconKotlin) - приложение для конференции DroidCon от TouchLab (android + ios);
* [https://github.com/SimonSchubert/Newsout](https://github.com/SimonSchubert/Newsout) - пример новостного приложения (android + ios) с базой данных;
* [https://github.com/sergiocasero/votlin-app](https://github.com/sergiocasero/votlin-app) - фулстек приложение для конференции - backend, android, ios, frontend с общим кодом;
* [https://github.com/adrianbukros/github-multiplatform-example](https://github.com/adrianbukros/github-multiplatform-example) - простой пример мобильного приложения (android + ios) с использованием kodein для DI и Timber для логов.
* [https://github.com/cmota/commit19](https://github.com/cmota/commit19) - приложение конференции (android + ios);
* [https://github.com/cmota/droidconLX](https://github.com/cmota/droidconLX) - приложение для конференции DroidCon (android + ios) с базой данных;
* [https://github.com/wiyarmir/kotlin-multiplatform-mobile-template](https://github.com/wiyarmir/kotlin-multiplatform-mobile-template) - шаблон мобильного мультиплатформенного проекта;
* [https://github.com/webfactorymk/kotlin-multiplatform-currency-converter](https://github.com/webfactorymk/kotlin-multiplatform-currency-converter) - пример под мобилки с модульностью;
* [https://github.com/russhwolf/multiplatform-hello](https://github.com/russhwolf/multiplatform-hello) - мобилки, бекенд, юниттесты;
* [https://github.com/jarroyoesp/KotlinMultiPlatform](https://github.com/jarroyoesp/KotlinMultiPlatform) - android, ios, web app, desktop jvm app, ktor, serialization, sqldelight, mockk;
* [https://github.com/Karumi/KotlinMultiplatformApp](https://github.com/Karumi/KotlinMultiplatformApp) - android, ios, ktor, coroutines, serialization, detekt, ktlint;
* [https://github.com/jeremyrempel/gitnotes](https://github.com/jeremyrempel/gitnotes) - network, mobile;
* [https://github.com/petrumo/KotlinMultiplatformMVI](https://github.com/petrumo/KotlinMultiplatformMVI) - mvi mobile, android, ios;

## Официальные библиотеки
* [https://github.com/Kotlin/kotlinx.coroutines](https://github.com/Kotlin/kotlinx.coroutines) - для работы с асинхронным кодом (пока без поддержки многопоточности в K/N);
* [https://github.com/Kotlin/kotlinx.serialization](https://github.com/Kotlin/kotlinx.serialization) - сериализация json, cbor, protobuf для общего кода;
* [https://github.com/ktorio/ktor](https://github.com/ktorio/ktor) - сетевой клиент для общего кода.

## Библиотеки от community
### Architecture
* [https://github.com/icerockdev/moko-mvvm](https://github.com/icerockdev/moko-mvvm) - архитектурные компоненты MVVM для mobile multiplatform;
* [https://github.com/reduxkotlin/redux-kotlin](https://github.com/reduxkotlin/redux-kotlin) - redux для общего кода;
* [https://github.com/oolong-kt/oolong](https://github.com/oolong-kt/oolong) - MVU архитектурные компоненты;
* [https://github.com/DrewCarlson/kotlin-mobius](https://github.com/DrewCarlson/kotlin-mobius) - [Mobius](https://github.com/spotify/mobius) от spotify в multiplatform вариации;
* [https://github.com/adevone/summer](https://github.com/adevone/summer) - mvp компоненты;

### Storage
* [https://github.com/russhwolf/multiplatform-settings](https://github.com/russhwolf/multiplatform-settings) - работа с SharedPreferences/UserDefaults из общего кода;
* [https://github.com/florent37/Multiplatform-Preferences](https://github.com/florent37/Multiplatform-Preferences) - работа с SharedPreferences/UserDefaults из общего кода;
* [https://github.com/square/sqldelight](https://github.com/square/sqldelight) - база данных для общего кода (с генерацией DAO);
* [https://github.com/netguru/Kissme](https://github.com/netguru/Kissme) - защищенное key-value хранилище;
* [https://github.com/suparngp/kotlin-multiplatform-projects/tree/master/fs](https://github.com/suparngp/kotlin-multiplatform-projects/tree/master/fs) - работа с файловой системой;
* [https://github.com/touchlab/SQLiter/tree/master/SQLiter](https://github.com/touchlab/SQLiter/tree/master/SQLiter) - прямой доступ к SQLite;

### Reactive
* [https://github.com/icerockdev/moko-mvvm](https://github.com/icerockdev/moko-mvvm) - LiveData с операторами;
* [https://github.com/badoo/Reaktive](https://github.com/badoo/Reaktive) - Rx для общего кода (с поддержкой многопоточности в K/N);
* [https://github.com/lightningkite/reacktive](https://github.com/lightningkite/reacktive) - реактивщина, но без многопоточности;
* [https://github.com/noheltcj/RxCommon](https://github.com/noheltcj/RxCommon) - реактивщина, без многопоточности;
* [https://github.com/andrewemery/livedata](https://github.com/andrewemery/livedata) - прямой конверт LiveData в mpp;
* [https://github.com/mirego/trikot.streams](https://github.com/mirego/trikot.streams) - реактивные потоки, с многопоточностью;
* [https://github.com/florent37/Multiplatform-LiveData](https://github.com/florent37/Multiplatform-LiveData) - порт LiveData в mpp;

### Multithreading
* [https://github.com/Autodesk/coroutineworker](https://github.com/Autodesk/coroutineworker) - многопоточные корутины;
* [https://github.com/touchlab/Stately/](https://github.com/touchlab/Stately/) - разные типы данных для работы в многопоточном режиме в K/N;
* [https://github.com/suparngp/kotlin-multiplatform-projects/tree/master/concurrency](https://github.com/suparngp/kotlin-multiplatform-projects/tree/master/concurrency) - многопоточность для общего кода в стиле требований K/N;

### Networking
* [https://github.com/icerockdev/moko-network](https://github.com/icerockdev/moko-network) - генерация ktor-client api из OpenAPI спецификации;
* [https://github.com/yshrsmz/kgql](https://github.com/yshrsmz/kgql) - GraphQL в общем коде - jvm/android/ios;
* [https://github.com/lightningkite/kommunicate](https://github.com/lightningkite/kommunicate) - сетевая библиотека для [http](http) запросов и вебсокетов от комьюнити;

### DateTime
* [https://github.com/korlibs/klock](https://github.com/korlibs/klock) - работа с датами и временем, включая таймзоны и форматирование;
* [https://github.com/fluidsonic/fluid-time](https://github.com/fluidsonic/fluid-time) - работа с датами и временем, включая таймзоны;
* [https://github.com/lightningkite/lokalize](https://github.com/lightningkite/lokalize) - информация о локали и простая работа со временем (без таймзон);
* [https://github.com/MrAsterisco/Time](https://github.com/MrAsterisco/Time) - duration api;

### Logging
* [https://github.com/AAkira/Napier](https://github.com/AAkira/Napier) - библиотека логирования для общего кода (Timber like);
* [https://github.com/korlibs/klogger](https://github.com/korlibs/klogger) - библиотека логирования для общего кода;
* [https://github.com/florent37/Multiplatform-Log](https://github.com/florent37/Multiplatform-Log) - логгер;

### Math
* [https://github.com/ionspin/kotlin-multiplatform-bignum](https://github.com/ionspin/kotlin-multiplatform-bignum) - поддержка больших чисел (android, ios);
* [https://github.com/lightningkite/recktangle](https://github.com/lightningkite/recktangle) - геометрические классы для математических расчетов;
* [https://github.com/korlibs/kbignum](https://github.com/korlibs/kbignum) - bigint, bigdecimal;

### Dependency Injection
* [https://github.com/Kodein-Framework/Kodein-DI](https://github.com/Kodein-Framework/Kodein-DI) - DI работающий в рантайме.

### Mobile specific
* [https://github.com/icerockdev/moko-resources](https://github.com/icerockdev/moko-resources) - доступ к ресурсам локализации из общего кода;
* [https://github.com/icerockdev/moko-permissions](https://github.com/icerockdev/moko-permissions) - работа с рантайм разрешениями из общего кода;
* [https://github.com/icerockdev/moko-media](https://github.com/icerockdev/moko-media) - получение фото/видео из общего кода;
* [https://github.com/Reedyuk/blue-falcon](https://github.com/Reedyuk/blue-falcon) - работа с Bluetooth LE;

### Others
* [https://github.com/icerockdev/moko-core](https://github.com/icerockdev/moko-core) - базовые классы для mobile multiplatform;
* [https://github.com/suparngp/kotlin-multiplatform-projects/tree/master/cache](https://github.com/suparngp/kotlin-multiplatform-projects/tree/master/cache) - inmem кеширование для общего кода;
* [https://github.com/sellmair/kompass](https://github.com/sellmair/kompass) - роутинг в общем коде (но пока нет нормального примера под айос);
* [https://github.com/benasher44/uuid](https://github.com/benasher44/uuid) - генерация UUID;
* [https://github.com/korlibs/krypto](https://github.com/korlibs/krypto) - secureRandom, sha1, sha256, md5, hash, aes;
* [https://github.com/korlibs/korim](https://github.com/korlibs/korim) - работа с изображениями разных форматов из общего кода;
* [https://github.com/korlibs/korau](https://github.com/korlibs/korau) - работа с аудио файлами разных форматов из общего кода;
* [https://github.com/florent37/Multiplatform-Bus](https://github.com/florent37/Multiplatform-Bus) - eventbus;

## Полезные плагины
* [https://github.com/icerockdev/mobile-multiplatform-gradle-plugin](https://github.com/icerockdev/mobile-multiplatform-gradle-plugin) - плагин для упрощения настройки mobile multiplatform проектов;android, но для общего кода;
* [https://github.com/Kotlin/dokka](https://github.com/Kotlin/dokka) - генератор документации к kotlin коду;
* [https://github.com/whyoleg/kamp](https://github.com/whyoleg/kamp) - набор предзаполненной конфигурации для mpp проектов;
* [https://github.com/Foso/MpApt](https://github.com/Foso/MpApt) - annotation processor для mpp.

### Configuration
* [https://github.com/gmazzo/gradle-buildconfig-plugin](https://github.com/gmazzo/gradle-buildconfig-plugin) - генерация конфигурации;
* [https://github.com/yshrsmz/BuildKonfig](https://github.com/yshrsmz/BuildKonfig) - генерация класса конфигурации как BuildConfig в android;
* [https://github.com/Karumi/Hagu](https://github.com/Karumi/Hagu) - еще один генератор конфигурации;

### Coroutines
* [https://github.com/andrewemery/recast](https://github.com/andrewemery/recast) - генерация функций с callback из suspend функций в kotlin/native;
* [https://github.com/feilfeilundfeil/kotlin-native-suspend-function-callback](https://github.com/feilfeilundfeil/kotlin-native-suspend-function-callback) - генерация функций с callback из suspend функций в kotlin/native.
