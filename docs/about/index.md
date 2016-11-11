---
title: "Info über .NET"
description: .NET-Produkte
keywords: .NET, .NET Core
author: richlander
manager: wpickett
ms.date: 06/23/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 2e38e9d9-8284-46ee-a15f-199adc4f26f4
translationtype: Human Translation
ms.sourcegitcommit: 15c55a87beb64f265a164db918c7721c7690fadf
ms.openlocfilehash: 52c9993e0d82429e429ba2f2c2c7c851cf901942

---

# <a name="about-net"></a>Info über .NET

> In den Tutorials unter [„Erste Schritte mit .NET Core“](../core/getting-started.md) finden Sie Informationen zum Erstellen einer einfachen .NET Core-Anwendung. Es dauert nur wenige Minuten, bis Ihre erste App funktioniert und ausgeführt wird.

.NET ist eine Entwicklungsplattform für allgemeine Zwecke. .NET kann für alle Arten von Apps oder Arbeitsauslastungen verwendet werden, bei denen Lösungen für allgemeine Zwecke zum Einsatz kommen. Es bietet verschiedene wichtige und für viele Entwickler attraktive Features, wie z.B. automatische Speicherverwaltung und moderne Programmiersprachen, die das effiziente Erstellen hochwertiger Anwendungen erleichtern. .NET ermöglicht eine allgemeine Programmierumgebung mit vielen praktischen Features und stellt gleichzeitig einen detaillierten Zugriff auf native Arbeitsspeicher und APIs bereit.

C#, F# und Visual Basic sind gängige Sprachen, in denen für die .NET-Plattform entwickelt wird. Bekannte Features der .NET-Sprachen sind z.B. das asynchrone Programmiermodell, LINQ (Language Integrated Query, sprachintegrierte Abfrage), generische Typen und die Reflektion des Typsystems. Die Sprachen bietet auch herausragende Optionen sowohl für die objektorientierte als auch für die funktionale Programmierung.

Zwischen diesen Sprachen bestehen erhebliche Unterschiede hinsichtlich der Philosophie und der Syntax, es gibt aber auch eine Symmetrie aufgrund des gemeinsamen Typsystems. Dieses Typsystem wird von der zugrunde liegenden Laufzeitumgebung bereitgestellt. .NET basiert auf dem Konzept einer Common Language Runtime (also einer gemeinsamen Laufzeitumgebung für verschiedene Sprachen), die die Anforderungen verschiedener Sprachen – z.B. dynamischer und statisch typisierter Sprachen – unterstützen und Interoperabilität zwischen den Sprachen ermöglichen kann. Es ist z.B. möglich, eine Auflistung von `People`-Objekten ohne Verlust bei Semantik oder Leistung zwischen verschiedenen Sprachen zu übergeben.

Es sind viele [.NET-Implementierungen und -Produkte](products.md) verfügbar, basierend auf offenen [.NET-Standards](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md), die die Grundlagen der Plattform spezifizieren. Die Implementierungen sind für verschiedene Anwendungstypen (z.B. Desktop, mobil, Spiele, Cloud) separat optimiert und unterstützen eine Vielzahl von Chips (z.B. x86/x64, ARM) und Betriebssysteme (z.B. Windows, Linux, iOS, Android, macOS). Open Source ist auch ein wichtiger Bestandteil des .NET-Ökosystems: Es stehen viele .NET-Implementierungen und Bibliotheken mit von der OSI genehmigten Lizenzen zur Verfügung.

- Informationen zu [.NET](../standard/index.md)
- Informationen zu [C#](../csharp/index.md)
- Informationen zu [F#](../fsharp/index.md)
- Durchsuchen der [.NET-API-Bibliothek](../../api/index.md)
- [Einführung in die Common Language Runtime](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/intro-to-clr.md)

## <a name="fundamentals"></a>Grundlagen

**Mehrere Sprachen**: .NET bietet ein klar definiertes Typsystem sowie Dateiformate, Laufzeit, Framework und Tools, das/die von mehreren Sprachen genutzt werden können, sowohl für die Ausführung in der eigenen Sprache als auch für die Interoperabilität mit anderen Sprachen, die die gleichen Komponenten von .NET als gemeinsame Basis verwenden.

**Verwalteter Speicher**: .NET verwaltet den Arbeitsspeicher automatisch über einen Garbage Collector. Es wird sichergestellt, dass Sie immer auf aktive Objekte verweisen, sodass sich unangenehme Probleme wie Pufferüberläufe und Zugriffsverletzungen vermeiden lassen. Hierzu gehört auch die Überprüfung der Arraygrenzen.

**Typsicherheit**: Das primäre Modell von .NET für Funktionalität und Speicherdarstellung sind „Typen“. Typen definieren die Form und optional auch das Verhalten. Die Runtime stellt sicher, dass aufrufender Code für Typen nur gemäß ihrer Definition und der angegebenen Sichtbarkeit von Members ausgeführt werden kann, und sorgt so für konsistente, zuverlässige und sichere Ergebnisse.

## <a name="features"></a>Features

**Benutzerdefinierte Werttypen**: Werttypen sind eine nützliche Typkategorie, da sie die Semantik zum „Übergeben nach Werten“ bieten anstatt, wie es bei Klassen der Fall ist, zum „Übergeben nach Verweis“. Werttypen sind ganz offensichtlich sinnvoll für numerische Daten. .NET ermöglicht Werttypen sowohl für primitive Typen wie Ganzzahlen als auch für benutzerdefinierte Typen.

**Generische Typen**: Generische Typen sind Typen mit mindestens einem Typparameter, die pro Instanziierung angegeben werden können. Dies ist für viele Typen nützlich, die andernfalls, wie z.B. der Typ „Object“, Inhalte verfügbar machen oder mehrere Typdefinitionen benötigen würden. Beispielsweise kann eine bestimmte Instanziierung eines Auflistungstyps für Personen, GPS-Standorte oder Zeichenfolgen spezifiziert werden.

**Reflektion**: .NET definiert ein Metadatenformat, das die Typen in einer Binärdatei beschreibt. Das Reflektionssubsystem verwendet diese Daten und macht APIs zum Lesen und Instanziieren der Typen zur Laufzeit verfügbar. Diese Funktion ist sehr nützlich in dynamischen Szenarien, in denen es nicht möglich ist, die genaue Implementierung eines Programms bereits im Voraus zu kennen.

**Flexible Codegenerierung**: .NET schreibt keine bestimmte Vorgehensweise zum Transformieren von .NET-Binärdateien in Computercode vor. Hier werden verschiedene Methoden erfolgreich eingesetzt, wie z.B. JIT-Kompilierung (Just In Time), AOT-Kompilierung (Ahead Of Time) mit JIT-Fallback und AOT-Kompilierung ohne JIT-Fallback. Jede Strategie bietet eigene Vorteile, und es gibt sogar Möglichkeiten, mehrere dieser Strategien gemeinsam einzusetzen.

**Plattformübergreifend**: .NET war von Anfang an plattformübergreifend konzipiert. Das Binärformat und der Befehlssatz sind unabhängig von Betriebssystem, CPU und Zeigergröße. Eine im Jahr 2000 zur Ausführung auf einem 32-Bit-Computer unter Windows erstellte .NET-Binärdatei kann 2016 ohne Veränderung auf einem ARM64-Gerät unter iOS ausgeführt werden.

## <a name="open-source"></a>Quelle öffnen

Die [.NET Core](https://github.com/dotnet/core)- und [Mono](https://github.com/mono/mono)-Implementierungen von .NET sind Open Source und verwenden die MIT-Lizenz. Die Dokumentation verwendet die [Creative Commons CC-BY](https://creativecommons.org/licenses/by/4.0/)-Lizenz. .NET Core und Mono werden von Microsoft gesponsert, und viele Mitglieder der Community wirken daran mit. 

Diese Runtimes für allgemeine Zwecke können als Basis für akademische Forschungen, Schul- oder Universitätsprojekte oder für kommerzielle Produkte eingesetzt werden. Aufgrund ihrer offenen Natur können alle Benutzer zum Produktcode beitragen, indem sie einen Fehler melden oder eine neue Funktion anfordern.

## <a name="projects"></a>Projekte

- [CoreCLR](https://github.com/dotnet/coreclr): .NET-Runtime, verwendet von .NET Core.
- [Mono](https://github.com/mono/mono): .NET-Runtime, verwendet von Xamarin und anderen.
- [CoreFX](https://github.com/dotnet/coreclr): .NET-Klassenbibliotheken, verwendet von .NET Core und über eine Quellfreigabe bis zu einem gewissen Grad von Mono.
- [Roslyn](https://github.com/dotnet/roslyn): C#- und Visual Basic-Compiler, verwendet von den meisten .NET-Plattformen und -Tools. Macht APIs zum Lesen, Schreiben und Analysieren von Quellcode verfügbar.
- [F#](https://github.com/microsoft/visualfsharp): F#-Compiler.
- [Xamarin SDK](http://open.xamarin.com): Tools und Bibliotheken zum Schreiben von C#- und F#-Code für Android, iOS und macOS.

## <a name="standardized"></a>Standardisiert

.NET wird über offene [ECMA-Standards](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md) spezifiziert, die die Funktionalität von .NET beschreiben und zum Erstellen neuer Implementierungen verwendet werden können. Es gibt auch andere .NET-Implementierungen – hier sind Mono und Unity neben den Microsoft-Implementierungen die beliebtesten.




<!--HONumber=Nov16_HO1-->


