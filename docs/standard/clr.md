---
title: Common Language Runtime (CLR)
description: Common Language Runtime (CLR)
keywords: .NET, .NET Core
author: rpetrusha
ms.author: ronpet
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 7704d9c9-e5fa-4969-a423-081cce0e21e6
translationtype: Human Translation
ms.sourcegitcommit: bb50b160a685d494ba47b3ca583f6fc35fa3ef3e
ms.openlocfilehash: 779b4bc43465833fa92e85d42156a232f390f7c2

---

# <a name="common-language-runtime-clr"></a>Common Language Runtime (CLR)

.NET Framework stellt eine als Common Language Runtime bezeichnete Laufzeitumgebung bereit, die Code ausführt und Dienste für die Erleichterung des Entwicklungsprozesses bereitstellt.

Compiler und Tools machen die Funktionen der Common Language Runtime verfügbar und ermöglichen das Schreiben von Code, mit dem die Vorteile dieser verwalteten Ausführungsumgebung genutzt werden können. Mit einem Sprachcompiler für die Common Language Runtime entwickelter Code wird "verwalteter Code" genannt. Dieser nutzt Features wie sprachübergreifende Integration, sprachübergreifende Ausnahmebehandlung, erhöhte Sicherheit, Unterstützung bei der Versionserstellung und Bereitstellung, ein vereinfachtes Modell für die Interaktion von Komponenten sowie Debug- und Profilerstellungsdienste.

> [!NOTE]
> Compiler und Tools sind in der Lage, eine von der Common Language Runtime nutzbare Ausgabe zu erzeugen, da sowohl das Typsystem, das Format der Metadaten als auch die Laufzeitumgebung (das virtuelle Ausführungssystem) von einem öffentlichen Standard definiert werden, dem ECMA-Standard für die Common Language Infrastructure. Weitere Informationen finden Sie unter [ECMA C# und Common Language Infrastructure Standards](https://www.visualstudio.com/en-us/mt639507).

Damit die Common Language Runtime Dienste für verwalteten Code bereitstellen kann, müssen Sprachcompiler Metadaten ausgeben, mit denen die Typen, Member und Verweise im Code beschrieben werden. Metadata werden gemeinsam mit dem Code gespeichert. Jede PE (Portable Executable)-Datei der Common Language Runtime, die geladen werden kann, enthält Metadaten. Die Laufzeit verwendet Metadaten zum Suchen und Laden von Klassen, Anordnen von Instanzen im Speicher, Auflösen von Methodenaufrufen, Generieren von systemeigenem Code, Erzwingen von Sicherheit und zum Festlegen von Begrenzungen im Laufzeitkontext.

Die Laufzeit behandelt automatisch das Objektlayout und verwaltet Verweise auf Objekte. Diese werden nach Verwendung freigegeben. Objekte, deren Lebensdauer auf diese Weise verwaltet wird, werden als verwaltete Daten bezeichnet. Durch die Garbage Collection werden Speicherverluste sowie einige weitere verbreitete Programmierfehler vermieden. Wenn verwalteter Code verwendet wird, können in einer .NET Framework-Anwendung verwaltete Daten, nicht verwaltete Daten oder beides gleichzeitig verwendet werden. Da Sprachcompiler ihre eigenen Typen, z. B. primitive Typen, bereitstellen, wissen Sie möglicherweise nicht (oder müssen nicht wissen), ob die Daten verwaltet werden.

Die Common Language Runtime erleichtert das Entwerfen von Komponenten und Anwendungen, deren Objekte sprachübergreifend interagieren. In unterschiedlichen Sprachen geschriebene Objekte können miteinander kommunizieren. Ihr Verhalten kann in hohem Maße integriert werden. Sie können z. B. eine Klasse definieren und dann in einer anderen Sprache eine Klasse von der ursprünglichen Klasse ableiten oder eine Methode für diese aufrufen. Sie können außerdem eine Instanz einer Klasse an die in einer anderen Sprache geschriebene Methode einer Klasse übergeben. Diese sprachübergreifende Integration wird durch die Verwendung eines von der Common Language Runtime definierten allgemeinen Typsystems durch Sprachcompiler und Tools für die Common Language Runtime ermöglicht. Hierbei werden die Regeln der Common Language Runtime für die Definition neuer Typen, das Erstellen, Verwenden und Beibehalten von Typen sowie für die Typenbindung befolgt.

Sämtliche verwalteten Komponenten enthalten als Teil der jeweiligen Metadaten Informationen über die Komponenten und Ressourcen, für die sie erstellt wurden. Mit diesen Informationen stellt die Common Language Runtime sicher, dass die Komponente oder Anwendung über die angegebenen Versionen aller erforderlichen Elemente verfügt. Dadurch kommt es seltener zu einer Unterbrechung der Ausführung des Codes aufgrund einer Abhängigkeit, deren Voraussetzungen nicht erfüllt sind. Informationen über die definierten Typen (sowie deren Abhängigkeiten) werden gemeinsam mit dem Code als Metadaten gespeichert, wodurch die Replikation und das Entfernen von Komponenten wesentlich vereinfacht werden.

Die Funktionen der Laufzeit werden durch Sprachcompiler und Tools auf eine Weise verfügbar gemacht, dass sie von Entwicklern einfach und intuitiv verwendet werden können. Dies hat zur Folge, dass einige Features der Laufzeit möglicherweise in unterschiedlichen Umgebungen unterschiedlich wahrgenommen werden. Die Wahrnehmung der Laufzeit hängt von den verwendeten Sprachcompilern und Tools ab. In Folgenden sind einige Vorteile der Common Language Runtime aufgeführt: 

* Die problemlose Verwendung in anderen Sprachen entwickelter Komponenten.

* Erweiterbare Typen, die von einer Klassenbibliothek bereitgestellt werden.

* Neue Sprachfunktionen wie Vererbung, Schnittstellen und Überladen für objektorientiertes Programmieren.

* Unterstützung für explizites Freethreading zum Erstellen skalierbarer Multithreadanwendungen.

* Unterstützung für strukturierte Ausnahmebehandlung.

* Unterstützung für benutzerdefinierte Attribute.

* Garbage Collection.

* Verwendung von Delegaten anstelle von Funktionszeigern zur Verbesserung der Typsicherheit.

## <a name="versions-of-the-common-language-runtime"></a>Versionen der Common Language Runtime

Die Versionsnummer von .NET Framework entspricht nicht unbedingt der Versionsnummer der enthaltenen CLR. Die folgende Tabelle zeigt, wie die beiden Versionsnummern zusammenhängen. 

.NET Framework-Version | Enthält CLR-Version 
---------------------- | --------------------
1.0 | 1.0
1.1 | 1.1
2.0 | 2.0
3.0 | 2.0
3.5 | 2.0
4 | 4
4.5 (inklusive 4.5.1 und 4.5.2) | 4
4.6 (einschließlich 4.6.1 und 4.6.2) | 4

## <a name="see-also"></a>Siehe auch

[Automatische Speicherverwaltung](garbagecollection/index.md)

 




<!--HONumber=Nov16_HO3-->


