---
title: .NET-Klassenbibliotheken
description: Erfahren Sie wie Sie mit Klassenbibliotheken nützliche Funktionalität in Module gruppieren, die von mehreren Anwendungen verwendet werden können.
author: richlander
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: a67484c3-fe92-44d8-8fa3-36fa2071d880
ms.openlocfilehash: e2fd0237556f877af64708674f00e9efddf95869
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209642"
---
# <a name="net-class-libraries"></a>.NET-Klassenbibliotheken

Klassenbibliotheken sind das Konzept der [freigegebenen Bibliothek](https://en.wikipedia.org/wiki/Library_%28computing%29#Shared_libraries) für .NET. Sie können damit nützliche Funktionalität auf Module verteilen, die von mehreren Anwendungen verwendet werden können. Sie können auch verwendet werden, um Funktionalität zu laden, die beim Start der Anwendung nicht benötigt wird bzw. nicht bekannt ist. Klassenbibliotheken werden mithilfe des [.NET Assembly-Dateiformats](assembly/file-format.md) beschriebenen.

Es gibt drei Arten von Klassenbibliotheken, die Sie verwenden können:

* **Plattformspezifische** Klassenbibliotheken haben Zugriff auf alle APIs einer bestimmten Plattform (z.B. .NET Framework, Xamarin iOS), können jedoch nur von Apps und Bibliotheken verwendet werden, deren Ziel diese Plattform ist.
* **Portable** Klassenbibliotheken haben Zugriff auf eine Teilmenge der APIs und können von Apps und Bibliotheken verwendet werden, deren Ziel mehrere Plattformen sind.
* **.NET Standard**-Klassenbibliotheken führen das Konzept plattformspezifischer und portabler Bibliotheken in einem einzelnen Modell zusammen, das das Beste aus beiden Welten bietet.

## <a name="platform-specific-class-libraries"></a>Plattformspezifische Klassenbibliotheken

Plattformspezifische Bibliotheken sind an eine einzige .NET-Implementierung gebunden (z.B. .NET Framework unter Windows) und können daher wichtige Abhängigkeiten von einer bekannten Ausführungsumgebung annehmen. Eine solche Umgebung stellt einen bekannten Satz von APIs (.NET- und BS-APIs) bereit, verwaltet den erwarteten Status (z.B. Windows-Registrierung) und macht ihn verfügbar.

Entwickler, die plattformspezifische Bibliotheken erstellen, können die zugrunde liegende Plattform voll ausnutzen. Die Bibliotheken werden immer nur auf der jeweiligen Plattform ausgeführt, sodass Plattformüberprüfungen oder andere Formen bedingten Codes überflüssig sind (Modulo-Single Sourcing-Code für mehrere Plattformen).

Plattformspezifische Bibliotheken waren der primäre Klassenbibliothekstyp für .NET Framework. Auch als andere .NET-Implementierungen aufkamen, blieben plattformspezifische Bibliotheken der dominierende Bibliothekstyp.

## <a name="portable-class-libraries"></a>Portable Klassenbibliotheken

Portable Bibliotheken werden auf mehreren .NET-Implementierungen unterstützt. Sie können dennoch Abhängigkeiten von einer bekannten Ausführungsumgebung annehmen, die Umgebung ist jedoch eine synthetische, die durch die Schnittmenge konkreter .NET-Implementierungen gebildet wird. Verfügbar gemachte APIs und Plattformannahmen sind eine Teilmenge dessen, was einer plattformspezifischen Bibliothek zur Verfügung stünde.

Wenn Sie eine portable Bibliothek erstellen, wählen Sie eine Plattformkonfiguration. Die Plattformkonfiguration ist ein Satz von Plattformen, die Sie unterstützen müssen (z. B. .NET Framework 4.5+, Windows Phone 8.0+). Je höher die Zahl der Plattformen ist, für deren Unterstützung Sie sich entscheiden, desto weniger APIs und Plattformannahmen sind möglich, der kleinste gemeinsame Nenner. Dieses Merkmal erscheint vielleicht auf den ersten Blick verwirrend, da Benutzer häufig denken: „Mehr ist besser“ und dann feststellen müssen, dass eine höhere Zahl unterstützter Plattformen zu weniger verfügbaren APIs führt.

Viele Bibliotheksentwickler sind von der Produktion mehrerer plattformspezifischer Bibliotheken aus einer Quelle (mit bedingten Kompilierungsdirektiven) zu portablen Bibliotheken gewechselt. Es gibt [mehrere Ansätze](https://blog.stephencleary.com/2012/11/portable-class-library-enlightenment.html) für den Zugriff auf plattformspezifische Funktionalität in portablen Bibliotheken, wobei das Lockvogelangebot im Moment das gängigste Verfahren ist.

## <a name="net-standard-class-libraries"></a>.NET Standard-Klassenbibliotheken

.NET Standard-Bibliotheken sind ein Ersatz für plattformspezifische und portable Bibliothekenkonzepte. Sie sind plattformspezifisch in dem Sinne, dass sie die gesamte Funktionalität der zugrunde liegenden Plattform (keine synthetischen Plattformen oder Plattformschnittmengen) verfügbar machen. Sie sind portabel in dem Sinne, dass sie auf allen unterstützenden Plattformen funktionieren.

.NET Standard macht einige _Bibliotheksverträge_ verfügbar. .NET-Implementierungen müssen jeden Vertrag entweder vollständig oder überhaupt nicht unterstützen. Jede Implementierung unterstützt deshalb eine bestimmte Menge an .NET Standard-Verträgen. Die logische Konsequenz ist, dass jede .NET Standard-Klassenbibliothek auf den Plattformen unterstützt wird, die ihre Vertragsverpflichtungen unterstützt.

Der .NET Standard macht nicht die gesamte Funktionalität von .NET Framework verfügbar (dies ist auch nicht das Ziel), aber er macht viele weitere APIs als portable Klassenbibliotheken verfügbar. Mit der Zeit werden weitere APIs hinzugefügt.

Die folgenden Plattformen unterstützen .NET Standard-Bibliotheken:

* .NET Core
* .NET Framework
* Mono
* Xamarin.iOS, Xamarin.Mac, Xamarin.Android
* Universelle Windows-Plattform (UWP)
* Windows
* Windows Phone
* Windows Phone Silverlight

Weitere Informationen finden Sie unter [.NET Standard](net-standard.md).

## <a name="mono-class-libraries"></a>Mono-Klassenbibliotheken

Klassenbibliotheken, einschließlich der drei zuvor beschriebenen Typen von Bibliotheken, werden unter Mono unterstützt. Mono ist häufig (richtigerweise) als eine plattformübergreifende Implementierung von .NET Framework angesehen worden. Dies lag teilweise daran, dass plattformspezifische .NET Framework-Bibliotheken in der Mono-Runtime ohne Änderung oder erneute Kompilierung ausgeführt werden konnten. Dieses Merkmal existierte vor der Erstellung portabler Klassenbibliotheken, und es war naheliegend, so binäre Portabilität zwischen .NET Framework und Mono zu ermöglichen (obwohl es nur in einer Richtung funktionierte).
