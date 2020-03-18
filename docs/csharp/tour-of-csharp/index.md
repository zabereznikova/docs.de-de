---
title: Einführung in C# - Leitfaden für C#
description: Neu bei C#? Lernen Sie die Grundlagen der Sprache kennen.
ms.date: 02/26/2020
ms.openlocfilehash: bf5a200f2ee777698ae8564f348ffc117d9abab0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79156843"
---
# <a name="a-tour-of-the-c-language"></a>Überblick über C#

C# (Aussprache „C Sharp“) ist eine moderne, objektorientierte und typsichere Programmiersprache. C# hat seine Wurzeln in der C-Sprachenfamilie und ist Programmierern, die mit C, C++, Java und JavaScript arbeiten, sofort vertraut.

Diese Einführung bietet einen Überblick über die wichtigsten Komponenten der Sprache in C# 8 und früheren Versionen. Wenn Sie die Sprache anhand von interaktiven Beispielen kennenlernen möchten, arbeiten Sie die Tutorials auf der Seite [Einführung in C#](../tutorials/intro-to-csharp/index.md) durch.

C# ist eine objektorientierte Sprache, umfasst allerdings auch Unterstützung für eine ***komponentenorientierte*** Programmierung. Die Softwareentwicklung von heute beruht zunehmend auf Softwarekomponenten in Form von eigenständigen und selbstbeschreibenden Funktionspaketen. Das wichtigste Merkmal dieser Komponenten ist, dass sie ein Programmiermodell mit Eigenschaften, Methoden und Ereignissen darstellen. Sie besitzen Attribute, die deklarative Informationen zur Komponente bereitstellen. Sie enthalten eine eigene Dokumentation. C# bietet Sprachkonstrukte zur direkten Unterstützung für diese Konzepte, was C# zu einer natürlichen Sprache macht, in der Softwarekomponenten erstellt und verwendet werden.

Einige C#-Funktionen helfen beim Entwickeln stabiler und dauerhafter Anwendungen. Die ***Garbage Collection*** gibt automatisch Arbeitsspeicher frei, der von nicht erreichbaren und nicht verwendeten Objekten belegt wird. Die ***Ausnahmebehandlung*** bietet einen strukturierten und erweiterbaren Ansatz zur Fehlererkennung und Wiederherstellung. Das ***typsichere*** Design der Sprache macht es unmöglich, nicht initialisierte Variablen auszulesen, Arrays über ihre Grenzen hinaus zu indizieren oder nicht überprüfte Typumwandlungen durchzuführen.

C# verfügt über ein ***einheitliches Typsystem***. Alle C#-Typen, einschließlich primitiver Typen wie `int` und `double`, erben von einem einzelnen `object`-Stammtyp. Daher verwenden alle Typen einen Satz allgemeiner Vorgänge, und Werte eines beliebigen Typs können gespeichert, übertragen und konsistent ausgeführt werden. Darüber hinaus unterstützt C# benutzerdefinierte Verweistypen und Werttypen und ermöglicht so die dynamische Zuordnung von Objekten sowie die Inlinespeicherung einfacher Strukturen.

Um sicherzustellen, dass C#-Programme und -Bibliotheken im Lauf der Zeit kompatibel weiterentwickelt werden können, wurde bei der Entwicklung von C# viel Wert auf ***Versionsverwaltung*** gelegt. Viele Programmiersprachen berücksichtigen dieses Problem nur geringfügig. Deshalb stürzen in anderen Sprachen geschriebene Programme daher häufiger ab, wenn neuere Versionen abhängiger Bibliotheken eingeführt werden. Zu den Aspekten der Entwicklung von C#, die direkt von Überlegungen bei der Versionskontrolle beeinflusst wurden, gehören die separaten `virtual`- und `override`-Modifizierer, die Regeln für die Überladungsauflösung und die Unterstützung für explizite Schnittstellenmember-Deklarationen.

In neueren Versionen wurden auch neue Programmierparadigmen in C# aufgenommen. C# enthält jetzt Features, die Methoden für die funktionale Programmierung wie Lambdaausdrücke unterstützen. Andere neue Features unterstützen die Trennung von Daten und Algorithmen, z. B. der Musterabgleich.

## <a name="hello-world"></a>Hello World

Das Programm „Hello, World“ wird für gewöhnlich zur Einführung einer Programmiersprache verwendet. Hier ist es in C#:

[!code-csharp[Hello World](~/samples/snippets/csharp/tour/hello/Program.cs)]

C#-Quelldateien weisen in der Regel die Dateierweiterung `.cs` auf. Laden Sie zunächst das [.NET Core SDK](https://dotnet.microsoft.com/download) herunter, und installieren Sie es, um dieses Programm zu erstellen. Führen Sie dann den Befehl `dotnet new console -o hello` aus, um ein neues Programm und ein Buildskript zu erstellen. Das Programm und das Buildskript befinden sich in den Dateien `Program.cs` bzw. `hello.csproj`. Sie können die Anwendung mit den `run`-Befehlen erstellen und ausführen:

```dotnetcli
cd hello
dotnet run
```

Das Programm erzeugt die folgende Ausgabe:

```console
Hello, World!
```

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
