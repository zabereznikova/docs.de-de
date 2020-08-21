---
title: Einführung in C# - Leitfaden für C#
description: Neu bei C#? Lernen Sie die Grundlagen der Sprache kennen.
ms.date: 08/06/2020
ms.openlocfilehash: 9fa292e8e85832d831f36cf0f21512aa0cf32580
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656227"
---
# <a name="a-tour-of-the-c-language"></a>Überblick über C#

C# (Aussprache „C Sharp“) ist eine moderne, objektorientierte und typsichere Programmiersprache. C# hat seine Wurzeln in der C-Sprachenfamilie und ist Programmierern, die mit C, C++, Java und JavaScript arbeiten, sofort vertraut. Diese Einführung bietet einen Überblick über die wichtigsten Komponenten der Sprache in C# 8 und früheren Versionen. Wenn Sie die Sprache anhand von interaktiven Beispielen kennenlernen möchten, arbeiten Sie die Tutorials auf der Seite [Einführung in C#](../tutorials/intro-to-csharp/index.md) durch.

C# ist eine objektorientierte,  ***komponentenorientierte*** Programmiersprache. C# bietet Sprachkonstrukte zur direkten Unterstützung dieser Konzepte, was C# zu einer natürlichen Sprache macht, in der Softwarekomponenten erstellt und verwendet werden. Seit Veröffentlichung wurden C# Features hinzugefügt, um neue Workloads und Methoden zur Gestaltung von Software zu unterstützen.

Einige C#-Features helfen beim Entwickeln stabiler und dauerhafter Anwendungen. Die [***Garbage Collection***](../../standard/garbage-collection/index.md) gibt Arbeitsspeicher automatisch frei, der von unerreichbaren nicht verwendeten Objekten belegt wird. Die [***Ausnahmebehandlung***](../programming-guide/exceptions/index.md) bietet einen strukturierten und erweiterbaren Ansatz zur Fehlererkennung und Wiederherstellung. [***Lambda-Ausdrücke***](../language-reference/operators/lambda-expressions.md) unterstützen funktionale Programmiertechniken. Die [***Abfragesyntax***](../linq/index.md) schafft ein einheitliches Muster für das Arbeiten mit Daten aus beliebigen Quellen. Dank Sprachunterstützung für [***asynchrone Vorgänge***](../programming-guide/concepts/async/index.md) wird eine Syntax für den Aufbau verteilter Systeme bereitgestellt. Der [***Musterabgleich***](..//pattern-matching.md) bietet eine Syntax, mit der sich Daten und Algorithmen in modernen verteilten Systemen leicht voneinander trennen lassen. C# bietet ein [***einheitliches Typsystem***](../programming-guide/types/index.md). Alle C#-Typen, einschließlich primitiver Typen wie `int` und `double`, erben von einem einzelnen `object`-Stammtyp. Allen Typen teilen sich eine Reihe allgemeiner Vorgänge. Werte jeglicher Art können einheitlich gespeichert, transportiert und bearbeitet werden. Darüber hinaus unterstützt C# benutzerdefinierte Verweis- und Werttypen. C# ermöglicht die dynamische Zuteilung von Objekten und die Inlinespeicherung schlanker Strukturen.

In C# dient die ***Versionsverwaltung*** zum Sicherstellen, dass sich Programme und Bibliotheken im Laufe der Zeit kompatibel weiterentwickeln können. Zu den Aspekten der Entwicklung von C#, die direkt von Überlegungen bei der Versionskontrolle beeinflusst wurden, gehören die separaten `virtual`- und `override`-Modifizierer, die Regeln für die Überladungsauflösung und die Unterstützung für explizite Schnittstellenmember-Deklarationen.

## <a name="hello-world"></a>Hello World

Das Programm „Hello, World“ wird für gewöhnlich zur Einführung einer Programmiersprache verwendet. Hier ist es in C#:

:::code language="csharp" interactive="try-dotnet" source="./snippets/shared/HelloWorld.cs":::

Das Programm „Hello, World“ wird mit einer `using`-Richtlinie gestartet, die auf den `System`-Namespace verweist. Namespaces bieten eine hierarchische Möglichkeit zum Organisieren von C#-Programmen und -Bibliotheken. Namespaces enthalten Typen und andere Namespaces. Beispiel: Der `System`-Namespace enthält eine Reihe von Typen, wie etwa die `Console`-Klasse, auf die im Programm verwiesen wird, und eine Reihe anderer Namespaces, wie etwa `IO` und `Collections`. Eine `using`-Richtlinie, die auf einen bestimmten Namespace verweist, ermöglicht die nicht qualifizierte Nutzung der Typen, die Member dieses Namespace sind. Aufgrund der `using`-Direktive kann das Programm `Console.WriteLine` als Abkürzung für `System.Console.WriteLine` verwenden.

Die `Hello`-Klasse, die vom Programm „Hello, World“ deklariert wird, verfügt über einen einzelnen Member: die `Main`-Methode. Die `Main`-Methode wird mit dem Modifizierer `static` deklariert. Auch wenn Instanzmethoden mit dem Schlüsselwort `this` auf eine bestimmte einschließende Objektinstanz verweisen können, agieren statische Methoden ohne Verweis auf ein bestimmtes Objekt. Gemäß Konvention fungiert eine statische Methode mit der Bezeichnung `Main` als Einstiegspunkt eines C#-Programms.

Die Ausgabe des Programms wird anhand der `WriteLine`-Methode der `Console`-Klasse im `System`-Namespace generiert. Diese Klasse wird anhand der Standardklassenbibliotheken bereitgestellt, auf die standardmäßig automatisch vom Compiler verwiesen wird.

## <a name="types-and-variables"></a>Typen und Variablen

Es gibt zwei Arten von Typen in C#: *Werttypen* und *Verweistypen*. Variablen von Werttypen enthalten ihre Daten direkt, Variablen von Verweistypen speichern hingegen Verweise auf ihre Daten – letztere werden als Objekte bezeichnet. Dank Verweistypen können zwei Variablen auf das gleiche Objekt verweisen. So können auf eine Variable angewendete Vorgänge das Objekt beeinflussen, auf das die andere Variable verweist. Bei Werttypen besitzen die Variablen jeweils eigene Kopien der Daten. Auf eine Variable angewendete Vorgänge können sich nicht auf die andere Variable auswirken (außer im Fall der Parametervariablen `ref` und `out`).

Ein ***Bezeichner*** ist ein Variablenname. Ein Bezeichner ist eine Sequenz von Unicode-Zeichen ohne Leerzeichen. Ein Bezeichner kann ein in C# reserviertes Wort sein, wenn ihm das Präfix `@` vorangestellt ist. Das kann bei der Interaktion mit anderen Sprachen nützlich sein.

C#-Werttypen sind weiter unterteilt in *einfache Typen*, *Enumerationstypen*, *Strukturtypen* und *Nullable-Werttypen*. C#-Verweistypen sind weiter unterteilt in *Klassentypen*, *Schnittstellentypen*, *Arraytypen* und *Delegattypen*.

Im Folgenden finden Sie eine Übersicht des C#-Typsystems.

- [Werttypen](../language-reference/builtin-types/value-types.md)
  - [Einfache Typen](../language-reference/builtin-types/value-types.md#built-in-value-types)
    - [Integral mit Vorzeichen](../language-reference/builtin-types/integral-numeric-types.md): `sbyte`, `short`, `int`, `long`
    - [Integral ohne Vorzeichen](../language-reference/builtin-types/integral-numeric-types.md): `byte`, `ushort`, `uint`, `ulong`
    - [Unicode-Zeichen](../../standard/base-types/character-encoding-introduction.md): `char`, das ein Zeichen als UTF-16-Codeeinheit darstellt
    - [Binäres Gleitkomma (IEEE)](../language-reference/builtin-types/floating-point-numeric-types.md): `float`, `double`
    - [Dezimale Gleitkommazahl mit hoher Genauigkeit](../language-reference/builtin-types/floating-point-numeric-types.md): `decimal`
    - Boolesch: `bool` dient zur Darstellung boolescher Werte, die entweder `true` oder `false` sind
  - [Enumerationstypen](../language-reference/builtin-types/enum.md)
    - Benutzerdefinierte Typen der Form `enum E {...}`. Ein `enum`-Typ ist ein eigenständiger Typ mit einer benannten Konstante. Jeder `enum`-Typ verfügt über einen zugrunde liegenden Typ, der einer der acht ganzzahligen Typen sein muss. Der Satz von Werten eines `enum`-Typs ist mit dem Satz von Werten des zugrunde liegenden Typs identisch.
  - [Strukturtypen](../language-reference/builtin-types/struct.md)
    - Benutzerdefinierte Typen der Form `struct S {...}`
  - [Auf NULL festlegbare Werttypen](../language-reference/builtin-types/nullable-value-types.md)
    - Erweiterungen aller anderen Werttypen mit einem `null`-Wert
  - [Tupelwerttypen](../language-reference/builtin-types/value-tuples.md)
    - Benutzerdefinierte Typen der Form `(T1, T2, ...)`
- [Verweistypen](../language-reference/keywords/reference-types.md)
  - [Klassentypen](../language-reference/keywords/class.md)
    - Ultimative Basisklasse aller anderen Typen:`object`
    - [Unicode-Zeichenfolgen](../../standard/base-types/character-encoding-introduction.md): `string`, die eine Sequenz von UTF-16-Codeeinheiten darstellt
    - Benutzerdefinierte Typen der Form `class C {...}`
  - [Schnittstellentypen](../language-reference/keywords/interface.md)
    - Benutzerdefinierte Typen der Form `interface I {...}`
  - [Array types (Arraytypen)](../programming-guide/arrays/index.md)
    - Ein- und mehrdimensional und verzweigt, z. B. `int[]`, `int[,]` und `int[][]`
  - [Delegattypen](../language-reference/builtin-types/reference-types.md#the-delegate-type)
    - Benutzerdefinierte Typen der Form `delegate int D(...)`

C#-Programme verwenden *Typdeklarationen*, um neue Typen zu erstellen. Eine Typdeklaration gibt den Namen und die Member des neuen Typs an. Fünf Typkategorien von C# sind benutzerdefinierbar: Klassentypen, Strukturtypen, Schnittstellentypen, Enumerationstypen und Delegattypen.

- Ein `class`-Typ definiert eine Datenstruktur, die Datenmember (Felder) und Funktionsmember (Methoden, Eigenschaften usw.) enthält. Klassentypen unterstützen einzelne Vererbung und Polymorphie. Dies sind Mechanismen, durch die abgeleitete Klassen erweitert und Basisklassen spezialisiert werden können.
- Ein `struct`-Typ ähnelt einem Klassentyp, da er eine Struktur mit Datenmembern und Funktionsmembern darstellt. Im Gegensatz zu Klassen sind Strukturen Werttypen, die in der Regel keine Heapzuordnung erfordern. Strukturtypen unterstützen keine benutzerdefinierte Vererbung, und alle Strukturtypen erben implizit vom Typ `object`.
- Ein `interface`-Typ definiert einen Vertrag als benannte Gruppe öffentlicher Member. Ein `class`- oder `struct`-Typ, der einen `interface`-Typ implementiert, muss Implementierungen der Member der Schnittstelle bereitstellen. Eine `interface` kann von mehreren Basisschnittstellen erben, und eine `class` oder `struct` kann mehrere Schnittstellen implementieren.
- Ein `delegate`-Typ stellt Verweise auf Methoden mit einer bestimmten Parameterliste und dem Rückgabetyp dar. Delegate ermöglichen die Behandlung von Methoden als Entitäten, die Variablen zugewiesen und als Parameter übergeben werden können. Delegate werden analog zu Funktionstypen von funktionalen Sprachen bereitgestellt. Außerdem ähneln sie konzeptionell Funktionszeigern, die es in einigen anderen Sprachen gibt. Im Gegensatz zu Funktionszeigern sind Delegaten objektorientiert und typsicher.

Die Typen, `class`, `struct`, `interface` und `delegate` unterstützen Generics, wodurch sie mit anderen Typen parametrisiert werden können.

C# unterstützt ein- und mehrdimensionale Arrays beliebigen Typs. Im Gegensatz zu den oben aufgeführten Typen müssen Arraytypen nicht deklariert werden, bevor sie verwendet werden können. Stattdessen werden Arraytypen erstellt, indem hinter einen Typnamen eckige Klammern gesetzt werden. Beispielsweise ist `int[]` ein eindimensionales Array von `int`, `int[,]` ein zweidimensionales Array von `int` und `int[][]` ein eindimensionales Array des eindimensionalen oder „verzweigten“ Arrays von `int`.

Nullable-Typen erfordern keine getrennte Definition. Für jeden Non-Nullable-Typ `T` gibt es einen entsprechenden Nullable-Typ `T?`, der einen zusätzlichen Wert, `null`, enthalten kann. Beispielsweise ist `int?` ein Typ, der jeden 32-Bit-Ganzzahlwert oder den Wert `null` enthalten kann. `string?` ist ein Typ, der beliebige `string`-Typen oder den Wert `null` enthalten kann.

Das C#-Typsystem ist dahingehend vereinheitlicht, dass ein Wert eines beliebigen Typs als `object` behandelt werden kann. Jeder Typ in C# ist direkt oder indirekt vom `object`-Klassentyp abgeleitet, und `object` ist die ultimative Basisklasse aller Typen. Werte von Verweistypen werden als Objekte behandelt, indem die Werte einfach als Typ `object` angezeigt werden. Werte von Werttypen werden durch Ausführen von *Boxing*- und *Unboxingvorgängen* als Objekte behandelt. Im folgenden Beispiel wird ein `int`-Wert in ein `object` und wieder in einen `int`-Wert konvertiert.

:::code language="csharp" source="./snippets/shared/Program.cs" ID="boxing" :::

Wenn ein Wert eines Werttyps einem `object`-Verweis zugewiesen wird, wird eine „Box“ zugeordnet, die den Wert enthalten soll. Bei dieser Box handelt es sich um eine Instanz eines Verweistyps, und der Wert wird in diese Box kopiert. Wenn umgekehrt ein `object`-Verweis in einen Werttyp umgewandelt wird, wird überprüft, ob der `object`-Typ, auf den verwiesen wird, eine Box des korrekten Werttyps ist. Nach erfolgreicher Überprüfung wird der Wert in der Box zum Werttyp kopiert.

Aus dem einheitlichen C#-Typensystem resultiert, dass Werttypen „bei Nachfrage“ als `object`-Verweise behandelt werden. Aufgrund der Vereinheitlichung können Bibliotheken für allgemeine Zwecke, die den Typ `object` verwenden, mit allen Typen verwendet werden können, die von `object` abgeleitet werden, wozu sowohl Verweis- als auch Werttypen zählen.

Es gibt mehrere Arten von *Variablen* in C#, einschließlich Feldern, Arrayelementen, lokalen Variablen und Parametern. Variablen stellen Speicherorte dar. Jede Variable hat, wie nachstehend gezeigt, einen Typ, der bestimmt, welche Werte in der Variablen gespeichert werden können.

- Nicht auf NULL festlegbarer Werttyp
  - Ein Wert genau dieses Typs
- Auf NULL festlegbarer Werttyp
  - Ein `null`-Wert oder ein Wert genau dieses Typs
- object
  - Ein `null`-Verweis, ein Verweis auf ein Objekt eines beliebigen Verweistyps oder ein Verweis auf einen geschachtelten Wert eines beliebigen Werttyps
- Klassentyp
  - Ein `null`-Verweis, ein Verweis auf eine Instanz dieses Klassentyps oder ein Verweis auf eine Instanz einer Klasse, die von diesem Klassentyp abgeleitet ist
- Schnittstellentyp
  - Ein `null`-Verweis, ein Verweis auf eine Instanz eines Klassentyps, der diesen Schnittstellentyp implementiert, oder ein Verweis auf einen geschachtelten Wert eines Werttyps, der diesen Schnittstellentyp implementiert
- Arraytyp
  - Ein `null`-Verweis, ein Verweis auf eine Instanz dieses Arraytyps oder ein Verweis auf eine Instanz eines kompatiblen Arraytyps
- Delegattyp
  - Ein `null`-Verweis oder ein Verweis auf eine Instanz eines kompatiblen Delegattyp

## <a name="program-structure"></a>Programmstruktur

Die wichtigsten Organisationskonzepte in C# sind [***Programme***](../programming-guide/inside-a-program/index.md), [***Namespaces***](../programming-guide/namespaces/index.md), [***Typen***](../programming-guide/types/index.md), [***Member***](../programming-guide/classes-and-structs/members.md) und [***Assemblys***](../../standard/assembly/index.md). Programme deklarieren Typen, die Member enthalten, und können in Namespaces organisiert werden. Klassen, Strukturen und Schnittstellen sind Beispiele von Typen. Felder, Methoden, Eigenschaften und Ereignisse sind Beispiele für Member. Wenn C#-Programme kompiliert werden, werden sie physisch in Assemblys gepackt. Assemblys haben in der Regel die Erweiterung `.exe` oder `.dll`, je nachdem, ob sie ***Anwendungen*** oder ***Bibliotheken*** implementieren.

Nehmen Sie als einfaches Beispiel eine Assembly, die den folgenden Code enthält:

:::code language="csharp" source="./snippets/shared/AcmeStack.cs":::

Der vollqualifizierte Name dieser Klasse ist `Acme.Collections.Stack`. Die Klasse enthält mehrere Member: ein Feld mit dem Namen `top`, zwei Methoden mit dem Namen `Push` und `Pop` sowie eine geschachtelte Klasse mit dem Namen `Entry`. Die `Entry`-Klasse enthält weitere drei Member: ein Feld mit dem Namen `next`, ein Feld mit dem Namen `data` und einen Konstruktor. `Stack` ist eine *generische* Klasse. Sie hat einen Typparameter, `T`, der bei seiner Verwendung durch einen konkreten Typ ersetzt wird.

> [!NOTE]
> Ein *Stapel* ist eine FILO-Sammlung (First In, Last Out). Neue Elemente werden am Anfang des Stapels hinzugefügt. Das Entfernen eines Elements erfolgt von oben im Stapel.

Assemblys enthalten ausführbaren Code in Form von Zwischensprachenanweisungen (Intermediate Language, IL) und symbolischen Informationen in Form von Metadaten. Vor der Ausführen konvertiert der JIT-Compiler (Just-In-Time) der .NET Common Language Runtime den IL-Code in einer Assembly in prozessorspezifischen Code.

Da eine Assembly eine selbstbeschreibende Funktionseinheit mit Code und Metadaten ist, besteht in C# keine Notwendigkeit für `#include`-Direktiven und Headerdateien. Die öffentlichen Typen und Member, die in einer bestimmten Assembly enthalten sind, werden einfach durch Verweisen auf die Assembly beim Kompilieren des Programms in einem C#-Programm verfügbar gemacht. Dieses Programm verwendet z.B. die `Acme.Collections.Stack`-Klasse aus der `acme.dll`-Assembly:

:::code language="csharp" source="./snippets/shared/StackUsage.cs":::

Um dieses Programm zu kompilieren, müssen Sie auf die Assembly *verweisen*, die die im vorherigen Beispiel definierte Stapelklasse enthält.

C#-Programme können in mehreren Quelldateien gespeichert werden. Bei der Kompilierung eines C#-Programms werden alle Quelldateien zusammen verarbeitet. Die Quelldateien können frei aufeinander verweisen. Konzeptionell ist das Ganze so, als ob alle Quelldateien vor der Verarbeitung zu einer großen Datei verkettet worden wären. Vorwärtsdeklarationen sind in C# nie erforderlich, da die Reihenfolge der Deklaration mit wenigen Ausnahmen unbedeutend ist. C# beschränkt eine Quelldatei weder auf die Deklaration eines einzigen öffentlichen Typs, noch muss der Name der Quelldatei mit einem in der Quelldatei deklarierten Typ übereinstimmen.

In weiteren Artikeln in dieser Einführung werden diese Organisationsblöcke erläutert.

>[!div class="step-by-step"]
>[Nächste](types.md)
