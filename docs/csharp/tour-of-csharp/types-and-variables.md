---
title: "C#-Typen und Variablen – Überblick über C# | Microsoft-Dokumentation"
description: "Erfahren Sie mehr über das Definieren von Typen und Deklarieren von Variablen in C#."
keywords: .NET, Csharp, Typ, Verweistyp, Werttyp
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: f8a8051e-0049-43f1-b594-9c84cc7b1224
ms.translationtype: Human Translation
ms.sourcegitcommit: 4437ce5d344cf06d30e31911def6287999fc6ffc
ms.openlocfilehash: 5c22d1087d27b03cfbf71d319a72e9e02203e9f2
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017

---

<a id="types-and-variables" class="xliff"></a>

# Typen und Variablen

Es gibt zwei Arten von Typen in C#: *Werttypen* und *Verweistypen*. Variablen von Werttypen enthalten ihre Daten direkt, Variablen von Verweistypen speichern hingegen Verweise auf ihre Daten – letztere werden als Objekte bezeichnet. Mit Verweistypen können zwei Variablen auf das gleiche Objekt verweisen, und so können an einer Variablen durchgeführte Vorgänge das Objekt beeinflussen, auf das die andere Variable verweist. Bei Werttypen besitzt jede Variable eine eigene Kopie der Daten, und auf eine Variable angewendete Vorgänge können die andere Variable nicht beeinflussen (außer im Fall von `ref`- und `out`-Parametervariablen).

C#-Werttypen sind weiter unterteilt in *einfache Typen*, *Enumerationstypen*, *Strukturtypen* und *auf NULL festlegbare Werttypen*. C#-Verweistypen sind weiter unterteilt in *Klassentypen*, *Schnittstellentypen*, *Arraytypen* und *Delegattypen*.

Im Folgenden finden Sie eine Übersicht des C#-Typsystems.

* Werttypen
    - Einfache Typen
        * Ganzzahlig mit Vorzeichen: `sbyte`, `short`, `int`,`long`
        * Ganzzahlig ohne Vorzeichen: `byte`, `ushort`, `uint`,`ulong`
        * Unicode-Zeichen: `char`
        * IEEE-Gleitkomma: `float`, `double`
        * Dezimalwert mit hoher Genauigkeit: `decimal`
        * Boolesch: `bool`
    - Enumerationstypen
        * Benutzerdefinierte Typen der Form `enum E {...}`
    - Strukturtypen
        * Benutzerdefinierte Typen der Form `struct S {...}`
    - Auf NULL festlegbare Werttypen
        * Erweiterungen aller anderen Werttypen mit einem `null`-Wert
* Verweistypen
    - Klassentypen
        * Ultimative Basisklasse aller anderen Typen:`object`
        * Unicode-Zeichenfolgen: `string`
        * Benutzerdefinierte Typen der Form `class C {...}`
    - Schnittstellentypen
        * Benutzerdefinierte Typen der Form `interface I {...}`
    - Arraytypen
        * Ein- und mehrdimensional, z.B. `int[]` und`int[,]`
    - Delegattypen
        * Benutzerdefinierte Typen der Form `delegate int D(...)`

Die acht Ganzzahltypen unterstützen 8-Bit-, 16-Bit, 32-Bit- und 64-Bit-Werte mit oder ohne Vorzeichen.

Die zwei Gleitkommatypen `float` und `double` werden jeweils im 32-Bit-IEC-60559-Format mit einfacher Genauigkeit und 64-Bit-IEC-60559-Format mit doppelter Genauigkeit dargestellt.

Der `decimal`-Typ ist ein für Finanz-und Währungsberechnungen geeigneter 128-Bit-Datentyp.

Der `bool`-Typ von C# dient zur Darstellung boolescher Werte – Werte, die entweder `true` oder `false` sind.

Zur Zeichen- und Zeichenfolgenverarbeitung in C# wird die Unicode-Codierung verwendet. Der `char`-Typ stellt eine UTF-16-Codeeinheit dar und der `string`-Typ eine Folge von UTF-16-Codeeinheiten.

Hier sind die numerischen Typen von C# zusammengefasst.

* Ganzzahlig mit Vorzeichen
    - `sbyte`: 8 Bit, Bereich von -128 - 127
    - `short`: 16 Bit, Bereich von -32.768 - 32.767
    - `int`: 32 Bit, Bereich von -2.147.483.648 - 2.147.483.647
    - `long`: 64 Bit, Bereich von -9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807
* Ganzzahlig ohne Vorzeichen
    - `byte`: 8 Bit, Bereich von 0 - 255
    - `ushort`: 16 Bit, Bereich von 0 - 65.535
    - `uint`: 32 Bit, Bereich von 0 - 4.294.967.295
    - `ulong`: 64 Bit, Bereich von -0 - 18.446.744.073.709.551.615
* Gleitkomma
    - `float`: 32 Bit, Bereich von 1,5 × 10<sup>-45</sup> - 3,4 × 10<sup>38</sup>, Genauigkeit von 7 Stellen
    - `double`: 64 Bit, Bereich von 5,0 × 10<sup>-324</sup> - 1,7 × 10<sup>308</sup>, Genauigkeit von 15 Stellen
* Decimal
    - `decimal`: 128 Bit, Bereich mindestens -7,9 × 10<sup>-28</sup> - 7,9 x 10<sup>28</sup> mit einer Genauigkeit von mindestens 28 Stellen
    
C#-Programme verwenden *Typdeklarationen*, um neue Typen zu erstellen. Eine Typdeklaration gibt den Namen und die Member des neuen Typs an. Fünf Typkategorien von C# sind benutzerdefinierbar: Klassentypen, Strukturtypen, Schnittstellentypen, Enumerationstypen und Delegattypen.

Ein `class`-Typ definiert eine Datenstruktur, die Datenmember (Felder) und Funktionsmember (Methoden, Eigenschaften usw.) enthält. Klassentypen unterstützen einzelne Vererbung und Polymorphie. Dies sind Mechanismen, durch die abgeleitete Klassen erweitert und Basisklassen spezialisiert werden können.

Ein `struct`-Typ ähnelt einem Klassentyp, da er eine Struktur mit Datenmembern und Funktionsmembern darstellt. Allerdings sind Strukturen im Gegensatz zu Klassen Werttypen und erfordern in der Regel keine Heapzuordnung. Strukturtypen unterstützen keine benutzerdefinierte Vererbung, und alle Strukturtypen erben implizit vom Typ `object`.

Ein `interface`-Typ definiert einen Vertrag als benannter Satz öffentlicher Funktionsmember. Eine `class` oder `struct`, die eine `interface` implementiert, muss Implementierungen der Funktionsmember der Schnittstelle bereitstellen. Eine `interface` kann von mehreren Basisschnittstellen erben, und eine `class` oder `struct` kann mehrere Schnittstellen implementieren.

Ein `delegate`-Typ stellt Verweise auf Methoden mit einer bestimmten Parameterliste und dem Rückgabetyp dar. Delegate ermöglichen die Behandlung von Methoden als Entitäten, die Variablen zugewiesen und als Parameter übergeben werden können. Delegate werden analog zu Funktionstypen von funktionalen Sprachen bereitgestellt. Sie ähneln auch dem Konzept von Funktionszeigern, die Sie in einigen anderen Sprachen finden. Im Gegensatz zu Funktionszeigern sind Delegate allerdings objektorientiert und typsicher.

Die Typen, `class`, `struct`, `interface` und `delegate` unterstützen generische Typen, wobei sie mit anderen Typen parametrisiert werden können.

Ein `enum`-Typ ist ein eigenständiger Typ mit einer benannten Konstante. Jeder `enum`-Typ verfügt über einen zugrunde liegenden Typ, der einer der acht ganzzahligen Typen sein muss. Der Satz von Werten eines `enum`-Typs ist mit dem Satz von Werten des zugrunde liegenden Typs identisch.

C# unterstützt ein- und mehrdimensionale Arrays beliebigen Typs. Im Gegensatz zu den oben aufgeführten Typen müssen Arraytypen nicht deklariert werden, bevor sie verwendet werden können. Stattdessen werden Arraytypen erstellt, indem hinter einen Typnamen eckige Klammern gesetzt werden. Beispielsweise ist `int[]` ein eindimensionales Array von `int`, `int[,]` ein zweidimensionales Array von `int` und `int[][]` ein eindimensionales Array des eindimensionalen Arrays von `int`.

Auf NULL festlegbare Werttypen müssen auch nicht deklariert werden, bevor sie verwendet werden können. Für jeden nicht auf NULL festlegbaren Werttypen `T` gibt es einen entsprechenden auf NULL festlegbaren Werttypen `T?`, der einen zusätzlichen Wert enthalten kann, `null`. Beispielsweise ist `int?` ein Typ, der jeden 32-Bit-Ganzzahlwert oder den Wert `null` enthalten kann.

Das C#-Typsystem ist dahingehend vereinheitlicht, dass ein Wert eines beliebigen Typs als `object` behandelt werden kann. Jeder Typ in C# ist direkt oder indirekt vom `object`-Klassentyp abgeleitet, und `object` ist die ultimative Basisklasse aller Typen. Werte von Verweistypen werden als Objekte behandelt, indem die Werte einfach als Typ `object` angezeigt werden. Werte von Werttypen werden durch Ausführen von *Boxing*- und *Unboxingvorgängen* als Objekte behandelt. Im folgenden Beispiel wird ein `int`-Wert in ein `object` und wieder in einen `int`-Wert konvertiert.

[!code-csharp[Boxing](../../../samples/snippets/csharp/tour/types-and-variables/Program.cs#L1-L10)]

Wenn ein Wert eines Werttyps in den Typ `object` konvertiert wird, wird eine auch „Box“ genannte `object`-Instanz zum Speichern des Werts zugeordnet, und der Wert wird in diese Box kopiert. Wenn umgekehrt ein `object`-Verweis in einen Werttyp umgewandelt wird, wird überprüft, ob das `object`, auf das verwiesen wird, eine Box des korrekten Datentyps ist, und bei erfolgreicher Überprüfung wird der Wert in der Box kopiert.

Aus dem einheitlichen C#-Typensystem resultiert, dass Werttypen „bei Nachfrage“ Objekte werden können. Aufgrund der Vereinheitlichung können Bibliotheken für allgemeine Zwecke, die den Typ `object` verwenden, sowohl mit Verweis- als auch Werttypen verwendet werden.

Es gibt mehrere Arten von *Variablen* in C#, einschließlich Feldern, Arrayelementen, lokalen Variablen und Parametern. Variablen stellen Speicherorte dar, und jede Variable hat einen Typ, der bestimmt, welche Werte in der Variablen gespeichert werden können, wie unten gezeigt.

* Nicht auf NULL festlegbarer Werttyp
    - Ein Wert genau dieses Typs
* Auf NULL festlegbarer Werttyp
    - Ein `null`-Wert oder ein Wert genau dieses Typs
* object
    - Ein `null`-Verweis, ein Verweis auf ein Objekt eines beliebigen Verweistyps oder ein Verweis auf einen geschachtelten Wert eines beliebigen Werttyps
* Klassentyp
    - Ein `null`-Verweis, ein Verweis auf eine Instanz dieses Klassentyps oder ein Verweis auf eine Instanz einer Klasse, die von diesem Klassentyp abgeleitet ist
* Schnittstellentyp
    - Ein `null`-Verweis, ein Verweis auf eine Instanz eines Klassentyps, der diesen Schnittstellentyp implementiert, oder ein Verweis auf einen geschachtelten Wert eines Werttyps, der diesen Schnittstellentyp implementiert
* Arraytyp
    - Ein `null`-Verweis, ein Verweis auf eine Instanz dieses Arraytyps oder ein Verweis auf eine Instanz eines kompatiblen Arraytyps
* Delegattyp
    - Ein `null`-Verweis oder ein Verweis auf eine Instanz eines kompatiblen Delegattyp

>[!div class="step-by-step"]
[Zurück](program-structure.md)
[Weiter](expressions.md)

