---
title: Einführung in C# - Leitfaden für C#
description: Neu bei C#? Lernen Sie die Grundlagen der Sprache kennen.
ms.date: 04/05/2019
ms.openlocfilehash: e2d7af3a35dc9d4fdeddf9eb742d155ab33094b4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711661"
---
# <a name="a-tour-of-the-c-language"></a>Überblick über C#

C# (Aussprache „C Sharp“) ist eine einfache, moderne, objektorientierte und typsichere Programmiersprache. C# hat seine Wurzeln in der C-Sprachenfamilie und ist Programmierern, die mit C, C++, Java und JavaScript arbeiten, sofort vertraut.

Diese Einführung bietet einen Überblick über die wichtigsten Komponenten der Sprache (C# 7 und höher). Wenn Sie die Sprache anhand von interaktiven Beispielen kennenlernen möchten, arbeiten Sie die Tutorials auf der Seite [Einführung in C#](../tutorials/intro-to-csharp/index.md) durch.

C# ist eine objektorientierte Sprache, umfasst allerdings auch Unterstützung für eine ***komponentenorientierte*** Programmierung. Die Softwareentwicklung von heute beruht zunehmend auf Softwarekomponenten in Form von eigenständigen und selbstbeschreibenden Funktionspaketen. Wichtig bei solchen Komponenten ist, dass sie für ein Programmiermodell mit Eigenschaften, Methoden und Ereignissen stehen. Sie verfügen über Attribute, die deklarative Informationen zur Komponente bereitstellen, und lassen sich in ihre eigene Dokumentation integrieren. C# bietet Sprachkonstrukte zur direkten Unterstützung für diese Konzepte, wodurch C# zu einer sehr natürlichen Sprache wird, in der Softwarekomponenten erstellt und verwendet werden.

Mehrere C#-Funktionen helfen beim Entwickeln stabiler und dauerhafter Anwendungen: ***Garbage Collection*** fordert automatisch Arbeitsspeicher zurück, der von nicht reagierenden und nicht verwendeten Objekten blockiert wird. ***Ausnahmebehandlung*** bietet einen strukturierten und erweiterbaren Ansatz zur Fehlererkennung und Wiederherstellung. Die ***typsichere*** Gestaltung der Sprache macht das Lesen in nicht initialisierten Variablen, das Indizieren von Arrays jenseits ihrer Grenzen oder das Durchführen nicht geprüfter Typumwandlungen unmöglich.

C# verfügt über ein ***einheitliches Typsystem***. Alle C#-Typen, einschließlich primitiver Typen wie `int` und `double`, erben von einem einzelnen `object`-Stammtyp. Daher verwenden alle Typen einen Satz allgemeiner Vorgänge, und Werte eines beliebigen Typs können gespeichert, übertragen und konsistent ausgeführt werden. Darüber hinaus unterstützt C# benutzerdefinierte Verweistypen und Werttypen und ermöglicht so die dynamische Zuordnung von Objekten sowie die Inlinespeicherung einfacher Strukturen.

Um sicherzustellen, dass C#-Programme und -Bibliotheken im Lauf der Zeit kompatibel weiterentwickelt werden können, wurde bei der Entwicklung von C# viel Wert auf ***Versionsverwaltung*** gelegt. Viele Programmiersprachen schenken diesem Problem wenig Beachtung, und in dieser Sprache geschriebene Programme stürzen daher häufiger als notwendig ab, wenn neuere Versionen abhängiger Bibliotheken eingeführt werden. Zu den Aspekten der Entwicklung von C#, die direkt von Überlegungen bei der Versionskontrolle beeinflusst wurden, gehören die separaten `virtual`- und `override`-Modifizierer, die Regeln für die Überladungsauflösung und die Unterstützung für explizite Schnittstellenmember-Deklarationen.

## <a name="hello-world"></a>Hello World

Das Programm „Hello, World“ wird für gewöhnlich zur Einführung einer Programmiersprache verwendet. Hier ist es in C#:

[!code-csharp[Hello World](~/samples/snippets/csharp/tour/hello/Program.cs)]

C#-Quelldateien weisen in der Regel die Dateierweiterung `.cs` auf. Unter der Annahme, dass das Programm „Hello, World“ in der Datei *hello.cs* gespeichert ist, kann das Programm möglicherweise über die Befehlszeile kompiliert werden:

```console
csc hello.cs
```

Dadurch wird eine ausführbare Assembly mit der Bezeichnung *hello.exe* generiert. Die Ausgabe, die von dieser Anwendung generiert wird, wenn sie ausgeführt wird:

```console
Hello, World
```

> [!IMPORTANT]
> Der `csc`-Befehl wird für das vollständige Framework kompiliert und ist möglicherweise nicht auf allen Plattformen verfügbar.

Das Programm „Hello, World“ wird mit einer `using`-Richtlinie gestartet, die auf den `System`-Namespace verweist. Namespaces bieten eine hierarchische Möglichkeit zum Organisieren von C#-Programmen und -Bibliotheken. Namespaces enthalten Typen und andere Namespaces. Beispiel: Der `System`-Namespace enthält eine Reihe von Typen, wie etwa die `Console`-Klasse, auf die im Programm verwiesen wird, und eine Reihe anderer Namespaces, wie etwa `IO` und `Collections`. Eine `using`-Richtlinie, die auf einen bestimmten Namespace verweist, ermöglicht die nicht qualifizierte Nutzung der Typen, die Member dieses Namespace sind. Aufgrund der `using`-Direktive kann das Programm `Console.WriteLine` als Abkürzung für `System.Console.WriteLine` verwenden.

Die `Hello`-Klasse, die vom Programm „Hello, World“ deklariert wird, verfügt über einen einzelnen Member: die `Main`-Methode. Die `Main`-Methode wird mit dem static-Modifizierer deklariert. Auch wenn Instanzmethoden mit dem Schlüsselwort `this` auf eine bestimmte einschließende Objektinstanz verweisen können, agieren statische Methoden ohne Verweis auf ein bestimmtes Objekt. Gemäß der Konvention fungiert eine statische Methode mit der Bezeichnung `Main` als Einstiegspunkt eines Programms.

Die Ausgabe des Programms wird anhand der `WriteLine`-Methode der `Console`-Klasse im `System`-Namespace generiert. Diese Klasse wird anhand der Standardklassenbibliotheken bereitgestellt, auf die standardmäßig automatisch vom Compiler verwiesen wird.

## <a name="elements-of-the-c-language"></a>Elemente in C#

Es gibt noch viel mehr über C# zu erfahren. Die folgenden Themen bieten eine Übersicht über die Elemente der C#-Sprache. Diese Übersichten bieten grundlegende Informationen zu allen Elementen der Sprache und die erforderlichen Informationen für tiefere Einblicke:

- [Programmstruktur](program-structure.md)
  - Lernen Sie die organisatorischen Schlüsselkonzepte in der C#-Sprache kennen: ***Programme***, ***Namespaces***, ***Typen***, ***Member*** und ***Assemblys***.
- [Typen und Variablen](types-and-variables.md)
  - Erfahren Sie mehr über ***Werttypen***, ***Verweistypen*** und ***Variablen*** in der C#-Sprache.
- [Ausdrücke](expressions.md)
  - ***Ausdrücke*** bestehen aus ***Operanden*** und ***Operatoren***. Ausdrücke generieren einen Wert.
- [Anweisungen](statements.md)
  - Sie verwenden ***Anweisungen***, um die Aktionen eines Programms auszudrücken.
- [Klassen und Objekte](classes-and-objects.md)
  - ***Klassen*** sind die grundlegendsten der C#-Typen. ***Objekte*** sind Instanzen einer Klasse. Klassen werden mit ***Membern*** erstellt, die auch in diesem Thema behandelt werden.
- [Strukturen](structs.md)
  - ***Strukturen*** sind Datenstrukturen, bei denen es sich im Gegensatz zu Klassen um Werttypen handelt.
- [Arrays](arrays.md)
  - Ein ***Array*** ist eine Datenstruktur, die eine Anzahl von Variablen enthält, auf die über berechnete Indizes zugegriffen wird.
- [Schnittstellen](interfaces.md)
  - Eine ***Schnittstelle*** definiert einen Vertrag, der von Klassen und Strukturen implementiert werden kann. Eine Schnittstelle kann Methoden, Eigenschaften, Ereignisse und Indexer enthalten. Eine Schnittstelle stellt keine Implementierungen der von ihr definierten Member bereit. Sie gibt lediglich die Member an, die von Klassen oder Strukturen bereitgestellt werden müssen, die die Schnittstelle implementieren.
- [Delegaten](delegates.md)
  - Ein ***Delegattyp*** stellt Verweise auf Methoden mit einer bestimmten Parameterliste und dem Rückgabetyp dar. Delegate ermöglichen die Behandlung von Methoden als Entitäten, die Variablen zugewiesen und als Parameter übergeben werden können. Delegate ähneln dem Konzept von Funktionszeigern, die Sie in einigen anderen Sprachen finden. Im Gegensatz zu Funktionszeigern sind Delegate allerdings objektorientiert und typsicher.
- [Attribute](attributes.md)
  - ***Attribute*** ermöglichen Programmen das Angeben zusätzlicher deklarativer Informationen zu Typen, Member und andere Entitäten.
  
> [!NOTE]
> Diese Artikel gelten für C# 7.0 und höher. Einige Funktionen stehen in früheren Versionen möglicherweise nicht zur Verfügung.

> [!div class="step-by-step"]
> [Nächste](program-structure.md)
