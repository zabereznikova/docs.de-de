---
title: Umwandlung und Konvertierungen (F#)
description: Hier erfahren Sie, wie der Programmiersprache f# Konvertierungsoperatoren für arithmetische Konvertierungen zwischen verschiedenen primitiven Typen.
ms.date: 05/16/2016
ms.openlocfilehash: ba3cbed91bf6510a34bcb7ba89d34b0ea6b82711
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="casting-and-conversions-f"></a>Umwandlung und Konvertierungen (F#)

Dieses Thema beschreibt die Unterstützung für Konvertierungen in F# erläutert werden.

## <a name="arithmetic-types"></a>Arithmetische Typen
F# bietet Konvertierungsoperatoren für arithmetische Konvertierungen zwischen verschiedenen primitive Typen, z. B. zwischen Ganzzahl- und Gleitkommatypen. Konvertierungsoperatoren integrale und Char überprüft haben und die unchecked-Formulare der Gleitkommawert Operatoren und die `enum` Konvertierungsoperator nicht der Fall. Die unchecked-Formen werden in definiert `Microsoft.FSharp.Core.Operators` und die aktivierten Formularen werden im definiert `Microsoft.FSharp.Core.Operators.Checked`. Die überprüften Formulare auf Überläufe überprüfen und generieren eine Laufzeitausnahme, wenn der resultierende Wert die Grenzen des Zieltyps überschreitet.

Jede dieser Operatoren verfügt über den gleichen Namen wie der Name des Zieltyps. In den folgenden Code, in denen die Typen explizit mit Anmerkungen versehen werden, z. B. `byte` mit zwei verschiedenen Bedeutungen angezeigt. Das erste Vorkommen ist der Typ und der zweite Operator für die Konvertierung.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

Die folgende Tabelle zeigt die Konvertierungsoperatoren, die in f# definiert.

|Operator|Beschreibung|
|--------|-----------|
|`byte`|Konvertieren Sie in Byte, ein 8-Bit-Typ ohne Vorzeichen.|
|`sbyte`|Konvertieren Sie in einen Bytewert mit Vorzeichen.|
|`int16`|Konvertieren Sie in eine 16-Bit-Ganzzahl mit Vorzeichen.|
|`uint16`|Konvertieren Sie in eine 16-Bit-Ganzzahl ohne Vorzeichen.|
|`int32, int`|Konvertieren Sie in eine 32-Bit-Ganzzahl mit Vorzeichen.|
|`uint32`|Konvertieren Sie in eine 32-Bit-Ganzzahl ohne Vorzeichen.|
|`int64`|Konvertieren Sie in eine 64-Bit-Ganzzahl mit Vorzeichen.|
|`uint64`|Konvertieren Sie in eine 64-Bit-Ganzzahl ohne Vorzeichen.|
|`nativeint`|Konvertieren Sie in eine systemeigene ganze Zahl.|
|`unativeint`|Konvertieren Sie in eine systemeigene Ganzzahl ohne Vorzeichen.|
|`float, double`|Konvertieren Sie in eine mit doppelter Genauigkeit IEEE-64-Bit-Gleitkommazahl.|
|`float32, single`|Konvertieren Sie in eine 32-Bit mit einfacher Genauigkeit IEEE-Gleitkommazahl.|
|`decimal`|Konvertieren in `System.Decimal`.|
|`char`|Konvertieren in `System.Char`, ein Unicode-Zeichen.|
|`enum`|Für einen enumerierten Typ zu konvertieren.|
Zusätzlich zu den integrierten Grundtypen, können Sie diese Operatoren mit Typen, die implementieren `op_Explicit` oder `op_Implicit` Methoden mit den entsprechenden Signaturen. Z. B. die `int` Konvertierungsoperator funktioniert mit jeder Typ, der eine statische Methode bietet `op_Explicit` , die den Typ als Parameter akzeptiert und gibt `int`. Als eine besondere Ausnahme, die allgemeine Regel, durch den Rückgabetyp Methoden nicht überladen werden können, Sie hierzu für `op_Explicit` und `op_Implicit`.

## <a name="enumerated-types"></a>Enumerationstypen
Die `enum` Operator ist ein generischer Operator, der einen Typparameter ausgeführt wird, die den Typ des darstellt der `enum` zu konvertieren. Wenn für einen enumerierten Typ konvertiert werden, geben Sie mithilfe eines Rückschlusses versucht zu ermitteln, welche die `enum` , die Sie zum konvertieren möchten. Im folgenden Beispiel wird die Variable `col1` nicht explizit kommentiert, aber der Typ nicht von der höheren Gleichheitstest abgeleitet ist. Aus diesem Grund kann der Compiler folgern, dass Sie zum Konvertieren einer `Color` Enumeration. Alternativ können Sie eine typanmerkung angeben wie bei `col2` im folgenden Beispiel.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]
    
Sie können den Zieltyp für die Enumeration auch explizit wie ein Typparameter, wie im folgenden Code gezeigt angeben:

```fsharp
let col3 = enum<Color> 3
```

Beachten Sie, dass die Enumeration Arbeit wandelt nur, wenn der zugrunde liegende Typ der Enumeration mit dem konvertierten Typ kompatibel ist. Im folgenden Code wird die Konvertierung schlägt fehl, aufgrund des Konflikts zwischen Kompilieren `int32` und `uint32`.

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

Weitere Informationen finden Sie unter [Enumerationen](enumerations.md).

## <a name="casting-object-types"></a>Umwandeln von Objekttypen
Konvertierung zwischen Typen in einer Objekthierarchie ist grundlegend für objektorientiertes Programmieren. Es gibt zwei grundlegende Typen von Konvertierungen: die Umwandlung (Upcasting) und nach unten (Downcasting) umwandeln. Umwandlung einer Hierarchie bedeutet das Umwandeln von einer abgeleiteten Objektverweis auf ein Basisobjekt Verweis. Eine solche Umwandlung funktioniert auf alle Fälle als in der Vererbungshierarchie der abgeleiteten Klasse die Basisklasse ist. Umwandeln in eine Hierarchie, aus einem Basisobjekt-Verweis auf einen abgeleiteten Objektverweis erfolgreich ist, nur dann, wenn das Objekt tatsächlich eine Instanz des Typs richtige Ziel (abgeleitet) oder ein Typ, der den Zieltyp abgeleitet ist.

F# stellt Operatoren für diese Typen von Konvertierungen. Die `:>` -Operator wandelt der Hierarchie nach oben und der `:?>` -Operator wandelt innerhalb der Hierarchie nach unten.

### <a name="upcasting"></a>Umwandeln
In vielen objektorientierten Sprachen erfolgt Upcasting implizit. in F# erläutert werden sind die Regeln etwas anders. Upcasting wird automatisch angewendet werden, wenn Sie Argumente auf einen Objekttyp an Methoden übergeben. Allerdings wird für gebundene Let-Funktionen in einem Modul Upcasting nicht automatisch wiederhergestellt, wenn der Parametertyp als einen flexiblen Typ deklariert ist. Weitere Informationen finden Sie unter [Flexible Typen](flexible-Types.md).

Die `:>` -Operator führt eine statische umgewandelt, was bedeutet, dass der Erfolg der Umwandlung zur Kompilierzeit bestimmt wird. Wenn eine Umwandlung mit `:>` erfolgreich kompiliert, es ist keine zulässige Umwandlung und verfügt über keine Chance Fehler zur Laufzeit.

Sie können auch die `upcast` Operator, um eine solche Konvertierung auszuführen. Der folgende Ausdruck gibt eine Konvertierung der Hierarchie nach oben an:

```fsharp
upcast expression
```

Wenn Sie die upcast-Operator verwenden, versucht der Compiler den Typ abzuleiten, den Sie aus dem Kontext konvertieren sind. Wenn der Compiler kann nicht den Zieltyp bestimmt ist, meldet der Compiler einen Fehler aus.

### <a name="downcasting"></a>Downcasting
Die `:?>` -Operator führt eine dynamische Umwandlung, was bedeutet, dass der Erfolg der Umwandlung zur Laufzeit bestimmt wird. Eine Umwandlung mit den `:?>` Operator nicht zur Kompilierzeit; aktiviert ist, aber zur Laufzeit wird versucht, auf den angegebenen Typ umgewandelt. Wenn das Objekt mit dem Zieltyp kompatibel ist, ist die Umwandlung erfolgreich. Wenn das Objekt nicht mit dem Zieltyp kompatibel ist, löst die Laufzeit eine `InvalidCastException`.

Sie können auch die `downcast` Operator, um eine dynamische typkonvertierung auszuführen. Der folgende Ausdruck gibt eine Konvertierung in der Hierarchie auf einen Typ, der vom Programmkontext abgeleitet wird:

```fsharp
downcast expression
```

Wie bei der `upcast` -Operator, wenn der Compiler einen bestimmten Zieltyp aus dem Kontext ableiten kann meldet einen Fehler.

Der folgende Code veranschaulicht die Verwendung der `:>` und `:?>` Operatoren. Im Code wird veranschaulicht, die die `:?>` Operator wird am besten verwendet werden, wenn Sie wissen, dass die Konvertierung erfolgreich ausgeführt wird, da löst `InvalidCastException` , wenn die Konvertierung schlägt fehl. Wenn Sie nicht wissen, dass eine Konvertierung ist erfolgreich, einen Typtest, die verwendet eine `match` Ausdruck ist besser, da der Aufwand für das Auslösen einer Ausnahme vermieden werden.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

Da generischen Operatoren `downcast` und `upcast` Typrückschluss zum Bestimmen des Typs Argument- und Rückgabetypen, im obigen Code, ersetzen Sie

```fsharp
let base1 = d1 :> Base1
```

durch

```fsharp
let base1 = upcast d1
```

Im vorherigen Code den Argumenttyp und Rückgabetypen sind `Derived1` und `Base1`zugeordnet.

Weitere Informationen zu Typtests finden Sie unter [Übereinstimmungsausdrücken](match-Expressions.md).

## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)
