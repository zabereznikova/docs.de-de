---
title: Umwandlung und Konvertierungen (F#)
description: Erfahren Sie, wie die Programmiersprache f# Konvertierungsoperatoren für arithmetische Konvertierungen zwischen primitiven Typen von verschiedenen bereitstellt.
ms.date: 05/16/2016
ms.openlocfilehash: aca1a2523130ee485a7e7c9a6a45a410904cb246
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43784542"
---
# <a name="casting-and-conversions-f"></a>Umwandlung und Konvertierungen (F#)

Dieses Thema beschreibt die Unterstützung für Typumwandlungen in f#.

## <a name="arithmetic-types"></a>Arithmetische Typen

F# bietet Konvertierungsoperatoren für arithmetische Konvertierungen zwischen verschiedenen primitive Typen, z. B. zwischen ganzzahligen und Gleitkommatypen. Die integrale und Char-Konvertierungsoperatoren überprüft haben und die unchecked-Formulare der Gleitkommawert, Operatoren und die `enum` Konvertierungsoperator nicht der Fall. Die unchecked-Formen werden in definierten `Microsoft.FSharp.Core.Operators` und die checked-Formen in definiert `Microsoft.FSharp.Core.Operators.Checked`. Die checked-Formen Überlauf überprüfen und generieren eine Laufzeitausnahme aus, wenn der resultierende Wert die Grenzwerte des Zieltyps überschreitet.

Die einzelnen Operatoren verfügt über den gleichen Namen wie der Name des Zieltyps. In den folgenden Code, in denen die Typen explizit mit Anmerkungen versehen werden, z. B. `byte` wird mit zwei unterschiedliche Bedeutungen angezeigt. Das erste Vorkommen ist der Typ und der zweite Operator für die Konvertierung.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

Die folgende Tabelle zeigt die Konvertierungsoperatoren, die in f# definiert.

|Operator|Beschreibung|
|--------|-----------|
|`byte`|Konvertieren Sie in Byte, ein 8-Bit-Typ ohne Vorzeichen.|
|`sbyte`|Konvertieren Sie in Byte mit Vorzeichen.|
|`int16`|Konvertieren Sie in eine 16-Bit-Ganzzahl mit Vorzeichen.|
|`uint16`|Konvertieren Sie in eine 16-Bit-Ganzzahl ohne Vorzeichen.|
|`int32, int`|Konvertieren Sie in eine 32-Bit-Ganzzahl mit Vorzeichen.|
|`uint32`|Konvertieren Sie in eine 32-Bit-Ganzzahl ohne Vorzeichen.|
|`int64`|Konvertieren Sie in eine 64-Bit-Ganzzahl mit Vorzeichen.|
|`uint64`|Konvertieren Sie in eine 64-Bit-Ganzzahl ohne Vorzeichen.|
|`nativeint`|Konvertieren Sie in eine systemeigene ganze Zahl.|
|`unativeint`|Konvertieren Sie in eine systemeigene ganze Zahl.|
|`float, double`|Konvertieren Sie in eine Gleitkommazahl mit doppelter Genauigkeit-IEEE-64-Bit-Gleitkommazahl.|
|`float32, single`|Konvertieren Sie in eine Gleitkommazahl mit einfacher Genauigkeit-IEEE-32-Bit.|
|`decimal`|Konvertieren in `System.Decimal`.|
|`char`|Konvertieren in `System.Char`, ein Unicode-Zeichen.|
|`enum`|Für einen enumerierten Typ zu konvertieren.|
Zusätzlich zur integrierten primitiven Typen können Sie diese Operatoren mit Typen, die implementieren `op_Explicit` oder `op_Implicit` Methoden mit den geeigneten Signaturen. Z. B. die `int` Konvertierungsoperator funktioniert mit jeder Typ, der eine statische Methode enthält `op_Explicit` , die den Typ als Parameter akzeptiert und gibt `int`. Als eine spezielle Ausnahme als allgemeine Regel, dass Methoden, durch den Rückgabetyp überladen werden, hierzu können Sie für `op_Explicit` und `op_Implicit`.

## <a name="enumerated-types"></a>Enumerationstypen

Die `enum` Operator ist ein generischer Operator, der einen Typparameter verwendet, die den Typ des darstellt der `enum` zu konvertieren. Geben Sie beim Konvertieren in ein enumerierter Typ, Typrückschluss versucht, den Typ bestimmen die `enum` , die Sie zum konvertieren möchten. Im folgenden Beispiel ist die Variable `col1` ist nicht explizit mit Anmerkungen versehen, aber der Typ nicht von der höheren Gleichheitstest abgeleitet ist. Aus diesem Grund kann der Compiler folgern, dass Sie in das Konvertieren einer `Color` Enumeration. Alternativ können Sie eine typanmerkung angeben wie bei `col2` im folgenden Beispiel.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]

Sie können den Zieltyp für die Enumeration auch explizit als einen Typparameter, wie im folgenden Code angeben:

```fsharp
let col3 = enum<Color> 3
```

Beachten Sie, dass die Enumeration Arbeit umgewandelt wird, nur, wenn der zugrunde liegende Typ der Enumeration mit dem konvertierten Typ kompatibel ist. Im folgenden Code wird die Konvertierung schlägt fehl, kompilieren Sie aufgrund der fehlenden Übereinstimmung zwischen `int32` und `uint32`.

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

Weitere Informationen finden Sie unter [Enumerationen](enumerations.md).

## <a name="casting-object-types"></a>Umwandlung von Objekttypen

Konvertierung zwischen Typen in einer Objekthierarchie ist elementar für objektorientierte Programmierung. Es gibt zwei grundlegende Arten von Konvertierungen: Typumwandlung nach oben (umwandeln) und nach unten (Downcasting) umwandeln. Typumwandlung, eine Hierarchie bedeutet, dass die Umwandlung von einer abgeleiteten Objektverweis auf ein Basisobjekt-Verweis. Eine solche Umwandlung ist garantiert funktioniert nur, wenn in der Vererbungshierarchie der abgeleiteten Klasse die Basisklasse ist. Umwandeln in eine Hierarchie, aus einem Basisobjekt-Verweis auf ein abgeleitetes Objekt-Verweis ist erfolgreich, nur dann, wenn das Objekt tatsächlich eine Instanz des Typs richtige Ziel (abgeleitete) oder ein Typ, der den Zieltyp abgeleitet ist.

F# stellt Operatoren für diese Arten von Konvertierungen bereit. Die `:>` -Operator wandelt der Hierarchie, und die `:?>` Operator Abwärtsumwandlung in der Hierarchie.

### <a name="upcasting"></a>Umwandeln

In vielen objektorientierten Sprachen erfolgt die Upcasting implizit. in f# sind die Regeln unterscheiden. Umwandeln wird automatisch angewendet, wenn Sie auf einen Objekttyp Argumente an Methoden übergeben. Allerdings erfolgt umwandeln für Let gebundenen-Funktionen in einem Modul nicht automatisch, es sei denn, der der Parametertyp als einen flexiblen Typ deklariert ist. Weitere Informationen finden Sie unter [Flexible Typen](flexible-Types.md).

Die `:>` -Operator führt eine statische Umwandlung, was bedeutet, dass der Erfolg der Umwandlung zur Kompilierzeit bestimmt ist. Wenn eine Umwandlung mit `:>` erfolgreich kompiliert, es ist keine zulässige Umwandlung und zur Laufzeit kein Fehler auftreten kann.

Sie können auch die `upcast` Operator, um eine solche Konvertierung auszuführen. Der folgende Ausdruck gibt eine Konvertierung der Hierarchie nach oben an:

```fsharp
upcast expression
```

Wenn Sie die upcast-Operator verwenden, versucht der Compiler, den Typ abzuleiten, die, den Sie aus dem Kontext zu konvertieren. Wenn der Compiler kann nicht den Zieltyp bestimmt ist, meldet der Compiler einen Fehler aus.

### <a name="downcasting"></a>Typumwandlung

Die `:?>` -Operator führt eine dynamische Umwandlung, was bedeutet, dass der Erfolg der Umwandlung zur Laufzeit bestimmt wird. Eine Umwandlung mit den `:?>` Operator nicht zur Kompilierzeit; aktiviert ist, aber zur Laufzeit wird versucht, das in den angegebenen Typ umgewandelt. Wenn das Objekt mit dem Zieltyp kompatibel ist, ist die Umwandlung erfolgreich. Wenn das Objekt nicht mit dem Zieltyp kompatibel ist, löst die Laufzeit eine `InvalidCastException`.

Sie können auch die `downcast` Operator beim Ausführen einer Konvertierung von Typ "dynamic". Der folgende Ausdruck gibt eine Konvertierung in der Hierarchie auf einen Typ, der vom Programmkontext abgeleitet wird:

```fsharp
downcast expression
```

Wie bei der `upcast` -Operator, wenn der Compiler einen bestimmten Zieltyp aus dem Kontext ableiten kann ein Fehler gemeldet.

Der folgende Code veranschaulicht die Verwendung der `:>` und `:?>` Operatoren. Im Code wird veranschaulicht, die die `:?>` Operator wird am besten verwendet werden, wenn Sie wissen, dass die Konvertierung erfolgreich ausgeführt wird, da es löst `InvalidCastException` , wenn die Konvertierung schlägt fehl. Wenn Sie nicht wissen, dass eine Konvertierung ist erfolgreich, einen Typtest, die verwendet eine `match` Ausdruck ist besser, da es sich um den Aufwand für das Auslösen einer Ausnahme verhindert.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

Da generischen Operatoren `downcast` und `upcast` Typrückschluss zum Bestimmen des Typs Argument- und Rückgabetypen, im obigen Code, Sie können ersetzen

```fsharp
let base1 = d1 :> Base1
```

durch

```fsharp
let base1 = upcast d1
```

Im vorherigen Code den Typ des Arguments und Rückgabetypen sind `Derived1` und `Base1`bzw.

Weitere Informationen zu Typtests finden Sie unter [Vergleichsausdrücke](match-Expressions.md).

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
