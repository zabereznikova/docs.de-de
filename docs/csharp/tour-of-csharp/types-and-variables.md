---
title: C#-Typen und -Variablen – Überblick über C#
description: Erfahren Sie mehr über das Definieren von Typen und Deklarieren von Variablen in C#.
ms.date: 04/24/2020
ms.assetid: f8a8051e-0049-43f1-b594-9c84cc7b1224
ms.openlocfilehash: 6a3bd3dc802f0d080fd96036067f709e62faf426
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141009"
---
# <a name="types-and-variables"></a>Typen und Variablen

Es gibt zwei Arten von Typen in C#: *Werttypen* und *Verweistypen*. Variablen von Werttypen enthalten ihre Daten direkt, Variablen von Verweistypen speichern hingegen Verweise auf ihre Daten – letztere werden als Objekte bezeichnet. Mit Verweistypen können zwei Variablen auf das gleiche Objekt verweisen, und so können an einer Variablen durchgeführte Vorgänge das Objekt beeinflussen, auf das die andere Variable verweist. Bei Werttypen besitzen die Variablen jeweils eigene Kopien der Daten. Auf eine Variable angewendete Vorgänge können sich nicht auf die andere Variable auswirken (außer im Fall der Parametervariablen `ref` und `out`).

C#-Werttypen sind weiter unterteilt in *einfache Typen*, *Enumerationstypen*, *Strukturtypen* und *Nullable-Werttypen*. C#-Verweistypen sind weiter unterteilt in *Klassentypen*, *Schnittstellentypen*, *Arraytypen* und *Delegattypen*.

Im Folgenden finden Sie eine Übersicht des C#-Typsystems.

- [Werttypen][ValueTypes]
  - [Einfache Typen][SimpleTypes]
    - Ganzzahlig mit Vorzeichen: `sbyte`, `short`, `int`,`long`
    - Ganzzahlig ohne Vorzeichen: `byte`, `ushort`, `uint`,`ulong`
    - Unicode-Zeichen: `char`
    - Binäres Gleitkomma (IEEE): `float`, `double`
    - Dezimale Gleitkommazahl mit hoher Genauigkeit: `decimal`
    - Boolesch: `bool`
  - [Enumerationstypen][EnumTypes]
    - Benutzerdefinierte Typen der Form `enum E {...}`
  - [Strukturtypen][StructTypes]
    - Benutzerdefinierte Typen der Form `struct S {...}`
  - [Auf NULL festlegbare Werttypen][NullableTypes]
    - Erweiterungen aller anderen Werttypen mit einem `null`-Wert
  - [Tupelwerttypen][TupleTypes]
    - Benutzerdefinierte Typen der Form `(T1, T2, ...)`
- [Verweistypen][ReferenceTypes]
  - [Klassentypen][ClassTypes]
    - Ultimative Basisklasse aller anderen Typen:`object`
    - Unicode-Zeichenfolgen: `string`
    - Benutzerdefinierte Typen der Form `class C {...}`
  - [Schnittstellentypen][InterfaceTypes]
    - Benutzerdefinierte Typen der Form `interface I {...}`
  - [Array types (Arraytypen)][ArrayTypes]
    - Ein- und mehrdimensional, z.B. `int[]` und`int[,]`
  - [Delegattypen][DelegateTypes]
    - Benutzerdefinierte Typen der Form `delegate int D(...)`

[ValueTypes]: ../language-reference/builtin-types/value-types.md
[SimpleTypes]: ../language-reference/builtin-types/value-types.md#built-in-value-types
[EnumTypes]: ../language-reference/builtin-types/enum.md
[StructTypes]: ../language-reference/builtin-types/struct.md
[NullableTypes]: ../language-reference/builtin-types/nullable-value-types.md
[TupleTypes]: ../tuples.md
[ReferenceTypes]: ../language-reference/keywords/reference-types.md
[ClassTypes]: ../language-reference/keywords/class.md
[InterfaceTypes]: ../language-reference/keywords/interface.md
[DelegateTypes]: ../language-reference/keywords/delegate.md
[ArrayTypes]: ../programming-guide/arrays/index.md

Weitere Informationen zu numerischen Typen finden Sie unter [Integrale Typen](../language-reference/builtin-types/integral-numeric-types.md) und [Tabelle für Gleitkommatypen](../language-reference/builtin-types/floating-point-numeric-types.md).

Der `bool`-Typ von C# dient zur Darstellung boolescher Werte. Dies sind Werte, die entweder `true` oder `false` sind.

Zur Zeichen- und Zeichenfolgenverarbeitung in C# wird die Unicode-Codierung verwendet. Der `char`-Typ stellt eine UTF-16-Codeeinheit dar und der `string`-Typ eine Folge von UTF-16-Codeeinheiten.

C#-Programme verwenden *Typdeklarationen*, um neue Typen zu erstellen. Eine Typdeklaration gibt den Namen und die Member des neuen Typs an. Fünf Typkategorien von C# sind benutzerdefinierbar: Klassentypen, Strukturtypen, Schnittstellentypen, Enumerationstypen und Delegattypen.

Ein `class`-Typ definiert eine Datenstruktur, die Datenmember (Felder) und Funktionsmember (Methoden, Eigenschaften usw.) enthält. Klassentypen unterstützen einzelne Vererbung und Polymorphie. Dies sind Mechanismen, durch die abgeleitete Klassen erweitert und Basisklassen spezialisiert werden können.

Ein `struct`-Typ ähnelt einem Klassentyp, da er eine Struktur mit Datenmembern und Funktionsmembern darstellt. Im Gegensatz zu Klassen sind Strukturen Werttypen, die in der Regel keine Heapzuordnung erfordern. Strukturtypen unterstützen keine benutzerdefinierte Vererbung, und alle Strukturtypen erben implizit vom Typ `object`.

Ein `interface`-Typ definiert einen Vertrag als benannter Satz öffentlicher Funktionsmember. Ein `class`- oder `struct`-Typ, der einen `interface`-Typ implementiert, muss Implementierungen der Funktionsmember der Schnittstelle bereitstellen. Eine `interface` kann von mehreren Basisschnittstellen erben, und eine `class` oder `struct` kann mehrere Schnittstellen implementieren.

Ein `delegate`-Typ stellt Verweise auf Methoden mit einer bestimmten Parameterliste und dem Rückgabetyp dar. Delegate ermöglichen die Behandlung von Methoden als Entitäten, die Variablen zugewiesen und als Parameter übergeben werden können. Delegate werden analog zu Funktionstypen von funktionalen Sprachen bereitgestellt. Außerdem ähneln sie konzeptionell Funktionszeigern, die es in einigen anderen Sprachen gibt. Im Gegensatz zu Funktionszeigern sind Delegaten objektorientiert und typsicher.

Die Typen, `class`, `struct`, `interface` und `delegate` unterstützen Generics, wodurch sie mit anderen Typen parametrisiert werden können.

Ein `enum`-Typ ist ein eigenständiger Typ mit einer benannten Konstante. Jeder `enum`-Typ verfügt über einen zugrunde liegenden Typ, der einer der acht ganzzahligen Typen sein muss. Der Satz von Werten eines `enum`-Typs ist mit dem Satz von Werten des zugrunde liegenden Typs identisch.

C# unterstützt ein- und mehrdimensionale Arrays beliebigen Typs. Im Gegensatz zu den oben aufgeführten Typen müssen Arraytypen nicht deklariert werden, bevor sie verwendet werden können. Stattdessen werden Arraytypen erstellt, indem hinter einen Typnamen eckige Klammern gesetzt werden. Beispielsweise ist `int[]` ein eindimensionales Array von `int`, `int[,]` ein zweidimensionales Array von `int` und `int[][]` ein eindimensionales Array des eindimensionalen Arrays von `int`.

Auf NULL festlegbare Werttypen müssen auch nicht deklariert werden, bevor sie verwendet werden können. Für jeden nicht auf NULL festlegbaren `T`-Werttyp gibt es einen entsprechenden auf NULL festlegbaren `T?`-Werttyp, der einen zusätzlichen `null`-Wert enthalten kann. Beispielsweise ist `int?` ein Typ, der jeden 32-Bit-Ganzzahlwert oder den Wert `null` enthalten kann.

Das C#-Typsystem ist dahingehend vereinheitlicht, dass ein Wert eines beliebigen Typs als `object` behandelt werden kann. Jeder Typ in C# ist direkt oder indirekt vom `object`-Klassentyp abgeleitet, und `object` ist die ultimative Basisklasse aller Typen. Werte von Verweistypen werden als Objekte behandelt, indem die Werte einfach als Typ `object` angezeigt werden. Werte von Werttypen werden durch Ausführen von *Boxing*- und *Unboxingvorgängen* als Objekte behandelt. Im folgenden Beispiel wird ein `int`-Wert in ein `object` und wieder in einen `int`-Wert konvertiert.

[!code-csharp[Boxing](../../../samples/snippets/csharp/tour/types-and-variables/Program.cs#L1-L10)]

Wenn ein Wert eines Werttyps einem `object`-Verweis zugewiesen wird, wird eine „Box“ zugeordnet, die den Wert enthalten soll. Bei dieser Box handelt es sich um eine Instanz eines Verweistyps, und der Wert wird in diese Box kopiert. Wenn umgekehrt ein `object`-Verweis in einen Werttyp umgewandelt wird, wird überprüft, ob der `object`-Typ, auf den verwiesen wird, eine Box des korrekten Werttyps ist. Nach erfolgreicher Überprüfung wird der Wert in der Box zum Werttyp kopiert.

Aus dem einheitlichen C#-Typensystem resultiert, dass Werttypen „bei Nachfrage“ als `object`-Verweise behandelt werden. Aufgrund der Vereinheitlichung können Bibliotheken für allgemeine Zwecke, die den Typ `object` verwenden, mit allen Typen verwendet werden können, die von `object` abgeleitet werden, wozu sowohl Verweis- als auch Werttypen zählen.

Es gibt mehrere Arten von *Variablen* in C#, einschließlich Feldern, Arrayelementen, lokalen Variablen und Parametern. Variablen stellen Speicherorte dar, und jede Variable hat einen Typ, der bestimmt, welche Werte in der Variablen gespeichert werden können, wie unten gezeigt.

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

> [!div class="step-by-step"]
> [Zurück](program-structure.md)
> [Weiter](expressions.md)
