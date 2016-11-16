---
title: .NET-Klassenbibliotheken
description: .NET-Klassenbibliotheken
keywords: .NET, .NET Core
author: richlander
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: a67484c3-fe92-44d8-8fa3-36fa2071d880
translationtype: Human Translation
ms.sourcegitcommit: 62fdb3e60b206728d86220076867eb8fd68af82e
ms.openlocfilehash: 8ed35197078e43f096931adb18c454004f83cccf

---

# <a name="net-class-libraries"></a>.NET-Klassenbibliotheken

Klassenbibliotheken sind das Konzept der [freigegebenen Bibliothek](http://en.wikipedia.org/wiki/Library_%28computing%29#Shared_libraries) für .NET. Sie können damit nützliche Funktionalität auf Module verteilen, die von mehreren Anwendungen verwendet werden können. Sie können auch verwendet werden, um Funktionalität zu laden, die beim Start der Anwendung nicht benötigt wird bzw. nicht bekannt ist. Klassenbibliotheken werden mithilfe des [.NET Assembly-Dateiformats](assembly-format.md) beschriebenen.

Es gibt drei Arten von Klassenbibliotheken, die Sie verwenden können:

*   **Plattformspezifische** Klassenbibliotheken haben Zugriff auf alle APIs einer bestimmten Plattform (z.B. .NET Framework, Xamarin iOS), können jedoch nur von Apps und Bibliotheken verwendet werden, deren Ziel diese Plattform ist.
*   **Portable** Klassenbibliotheken haben Zugriff auf eine Teilmenge der APIs und können von Apps und Bibliotheken verwendet werden, deren Ziel mehrere Plattformen sind.
*   **.NET Core**-Klassenbibliotheken führen das plattformspezifische und Portable-Bibliotheken-Konzept in einem einzelnen Modell zusammen, das das Beste von beidem bietet.

## <a name="platformspecific-class-libraries"></a>Plattformspezifische Klassenbibliotheken

Plattformspezifische Bibliotheken sind an eine einzige .NET-Plattform gebunden (z.B. .NET Framework unter Windows) und können daher wichtige Abhängigkeiten von einer bekannten Ausführungsumgebung annehmen. Eine solche Umgebung stellt einen bekannten Satz von APIs (.NET- und BS-APIs) bereit, verwaltet den erwarteten Status (z.B. Windows-Registrierung) und macht ihn verfügbar.

Entwickler, die plattformspezifische Bibliotheken erstellen, können die zugrunde liegende Plattform voll ausnutzen. Die Bibliotheken werden immer nur auf der jeweiligen Plattform ausgeführt, sodass Plattformüberprüfungen oder andere Formen bedingten Codes überflüssig sind (Modulo-Single Sourcing-Code für mehrere Plattformen).

Plattformspezifische Bibliotheken waren der primäre Klassenbibliothekstyp für .NET Framework. Auch als andere .NET-Plattformen aufkamen, blieben plattformspezifische Bibliotheken der dominierende Bibliothekstyp.

## <a name="portable-class-libraries"></a>Portable Klassenbibliotheken

Portable Bibliotheken werden auf mehreren .NET-Plattformen unterstützt. Sie können dennoch Abhängigkeiten von einer bekannten Ausführungsumgebung annehmen, die Umgebung ist jedoch eine synthetische, die durch die Schnittmenge einer Reihe konkreter .NET-Plattformen gebildet wird. Dies bedeutet, dass es sich bei verfügbar gemachten APIs und Plattformannahmen um eine Teilmenge dessen handelt, was einer plattformspezifischen Bibliothek zur Verfügung stünde.

Wenn Sie eine portable Bibliothek erstellen, wählen Sie eine Plattformkonfiguration. Dabei handelt es sich um den Satz von Plattformen, die Sie unterstützen müssen (z.B. .NET Framework 4.5 +, Windows Phone 8.0 +). Je höher die Zahl der Plattformen ist, für deren Unterstützung Sie sich entscheiden, desto weniger APIs und Plattformannahmen sind möglich, der kleinste gemeinsame Nenner. Dieses Merkmal erscheint vielleicht auf den ersten Blick verwirrend, da Benutzer häufig denken: „Mehr ist besser“; doch dann stellen sie fest, dass eine höhere Zahl unterstützter Plattformen zu weniger verfügbaren APIs führt.

Viele Bibliotheksentwickler sind von der Produktion mehrerer plattformspezifischer Bibliotheken aus einer Quelle (mit bedingten Kompilierungsdirektiven) zu portablen Bibliotheken gewechselt. Es gibt [mehrere Ansätze](http://blog.stephencleary.com/2012/11/portable-class-library-enlightenment.html) für den Zugriff auf plattformspezifische Funktionalität in portablen Bibliotheken, wobei das [Lockvogelangebot](http://log.paulbetts.org/the-bait-and-switch-pcl-trick/) im Moment das gängigste Verfahren ist.

### <a name="net-core-class-libraries"></a>.NET Core-Klassenbibliotheken

.NET Core-Bibliotheken sind ein Ersatz für plattformspezifische und portable Bibliothekenkonzepte. Sie sind plattformspezifisch in dem Sinne, dass sie die gesamte Funktionalität der zugrunde liegenden Plattform (keine synthetischen Plattformen oder Plattformschnittmengen) verfügbar machen. Sie sind portabel in dem Sinne, dass sie auf allen unterstützenden Plattformen funktionieren.

.NET Core macht eine Reihe von _Bibliotheksverträgen_ verfügbar. .NET-Plattformen müssen jeden Vertrag entweder vollständig oder überhaupt nicht unterstützen. Daher unterstützt jede Plattform eine Reihe von .NET Core-Verträgen. Die logische Konsequenz ist, dass jede .NET Core-Klassenbibliothek auf den Plattformen unterstützt wird, die ihre Vertragsverpflichtungen unterstützt.

.NET Core-Verträge machen nicht die gesamte Funktionalität von .NET Framework verfügbar (dies ist auch nicht das Ziel), sie machen jedoch viele weitere APIs als Portable Klassenbibliotheken verfügbar. Mit der Zeit werden weitere APIs hinzugefügt.

Die folgenden Plattformen unterstützen .NET Core-Klassenbibliotheken:

*   .NET Core
*   ASP.NET Core
*   .NET Framework 4.5+
*   Windows Store-Apps
*   Windows Phone 8+

### <a name="mono-class-libraries"></a>Mono-Klassenbibliotheken

Klassenbibliotheken, einschließlich der drei oben beschriebenen Typen von Bibliotheken, werden unter Mono unterstützt. Mono ist häufig (richtigerweise) als eine plattformübergreifende Implementierung von Microsoft .NET Framework angesehen worden. Dies lag teilweise daran, dass plattformspezifische .NET Framework-Bibliotheken in der Mono-Runtime ohne Änderung oder erneute Kompilierung ausgeführt werden konnten. Dieses Merkmal existierte vor der Erstellung portabler Klassenbibliotheken, und es war naheliegend, so binäre Portabilität zwischen .NET Framework und Mono zu ermöglichen (obwohl es nur in einer Richtung funktionierte).



<!--HONumber=Nov16_HO1-->


