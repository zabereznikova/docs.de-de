---
title: Umwandlung und Konvertierungen
description: Erfahren Sie, wie die Programmiersprache F# Konvertierungsoperatoren für arithmetische Konvertierungen zwischen primitiven Typen von verschiedenen bereitstellt.
ms.date: 02/20/2020
ms.openlocfilehash: 5f9727d14a7ae070e0f0f71fa0a0abe04f662071
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543585"
---
# <a name="casting-and-conversions-f"></a>Umwandlung und Konvertierungen (F#)

Dieses Thema beschreibt die Unterstützung für Typumwandlungen in F#.

## <a name="arithmetic-types"></a>Arithmetische Typen

F#stellt Konvertierungs Operatoren für arithmetische Konvertierungen zwischen verschiedenen primitiven Typen bereit, z. b. zwischen Integer-und Gleit Komma Typen. Der ganzzahlige und der Char-Konvertierungs Operator haben die Formulare aktiviert und deaktiviert. die Gleit Komma Operatoren und der `enum` Konvertierungs Operator nicht. Die nicht aktivierten Formulare werden in `Microsoft.FSharp.Core.Operators` definiert, und die überprüften Formulare werden in `Microsoft.FSharp.Core.Operators.Checked`definiert. Die aktivierten Formulare überprüfen auf Überlauf und generieren eine Lauf Zeit Ausnahme, wenn der resultierende Wert die Begrenzungen des Zieltyps überschreitet.

Jeder dieser Operatoren hat denselben Namen wie der Name des Zieltyps. Beispielsweise wird im folgenden Code, in dem die Typen explizit mit Anmerkungen versehen werden, `byte` mit zwei verschiedenen Bedeutungen angezeigt. Das erste Vorkommen ist der-Typ, und der zweite ist der Konvertierungs Operator.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

Die folgende Tabelle zeigt die Konvertierungsoperatoren, die in F# definiert.

|Operator|Beschreibung|
|--------|-----------|
|`byte`|Konvertieren in Byte, einen 8-Bit-Typ ohne Vorzeichen.|
|`sbyte`|In signiertes Byte konvertieren.|
|`int16`|Konvertieren in eine 16-Bit-Ganzzahl mit Vorzeichen.|
|`uint16`|Konvertieren in eine 16-Bit-Ganzzahl ohne Vorzeichen.|
|`int32, int`|Konvertiert in eine 32-Bit-Ganzzahl mit Vorzeichen.|
|`uint32`|Konvertiert in eine 32-Bit-Ganzzahl ohne Vorzeichen.|
|`int64`|Konvertiert in eine 64-Bit-Ganzzahl mit Vorzeichen.|
|`uint64`|Konvertiert in eine 64-Bit-Ganzzahl ohne Vorzeichen.|
|`nativeint`|In eine systemeigene ganze Zahl konvertieren.|
|`unativeint`|Konvertiert in eine native Ganzzahl ohne Vorzeichen.|
|`float, double`|Konvertieren in eine 64-Bit-IEEE-Gleit Komma Zahl mit doppelter Genauigkeit.|
|`float32, single`|Konvertieren in eine 32-Bit-IEEE-Gleit Komma Zahl mit einfacher Genauigkeit.|
|`decimal`|In `System.Decimal`konvertieren.|
|`char`|Konvertieren Sie in `System.Char`, ein Unicode-Zeichen.|
|`enum`|Konvertieren in einen enumerierten Typ.|

Zusätzlich zu den integrierten primitiven Typen können Sie diese Operatoren mit Typen verwenden, die `op_Explicit` oder `op_Implicit` Methoden mit entsprechenden Signaturen implementieren. Beispielsweise arbeitet der `int` Konvertierungs Operator mit jedem Typ, der eine statische Methoden `op_Explicit` bereitstellt, die den Typ als Parameter annimmt und `int`zurückgibt. Als besondere Ausnahme von der allgemeinen Regel, dass Methoden nicht durch den Rückgabetyp überladen werden können, können Sie dies für `op_Explicit` und `op_Implicit`tun.

## <a name="enumerated-types"></a>Enumerierte Typen

Der `enum`-Operator ist ein generischer Operator, der einen Typparameter annimmt, der den Typ des `enum` darstellt, in den konvertiert werden soll. Beim Konvertieren in einen enumerierten Typ versucht der Typrückschluss, den Typ des `enum` zu bestimmen, in den konvertiert werden soll. Im folgenden Beispiel wird die Variable `col1` nicht explizit mit Anmerkungen versehen, aber der Typ wird aus dem späteren Gleichheits Test abgeleitet. Daher kann der Compiler ableiten, dass Sie in eine `Color` Enumeration wandeln. Alternativ können Sie eine Typanmerkung angeben, wie `col2` im folgenden Beispiel gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]

Sie können den zielenumerationstyp auch explizit als Typparameter angeben, wie im folgenden Code:

```fsharp
let col3 = enum<Color> 3
```

Beachten Sie, dass die enumerationsumwandlungen nur funktionieren, wenn der zugrunde liegende Typ der Enumeration mit dem Typ kompatibel ist, der konvertiert wird. Im folgenden Code kann die Konvertierung aufgrund des Konflikts zwischen `int32` und `uint32`nicht kompiliert werden.

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

Weitere Informationen finden Sie unter [Enumerationen](enumerations.md).

## <a name="casting-object-types"></a>Umwandeln von Objekttypen

Die Konvertierung zwischen Typen in einer Objekthierarchie ist von grundlegender Bedeutung für objektorientierte Programmierung. Es gibt zwei grundlegende Typen von Konvertierungen: Umwandlung (Upcasting) und Umwandlung nach unten (Downcasting). Das Umwandeln einer Hierarchie bedeutet, dass ein abgeleiteter Objekt Verweis in einen Basisobjekt Verweis umgewandelt wird. Eine solche Umwandlung ist garantiert funktionsfähig, solange sich die Basisklasse in der Vererbungs Hierarchie der abgeleiteten Klasse befindet. Das Umwandeln einer Hierarchie aus einem Basisobjekt Verweis in einen abgeleiteten Objekt Verweis ist nur erfolgreich, wenn das Objekt tatsächlich eine Instanz des richtigen Ziel Typs (abgeleiteter Typ) oder eines Typs ist, der vom Zieltyp abgeleitet ist.

F#stellt Operatoren für diese Typen von Konvertierungen bereit. Der `:>`-Operator wandelt die Hierarchie um, und der `:?>` Operator wandelt die Hierarchie um.

### <a name="upcasting"></a>Umwandeln

In vielen objektorientierten Sprachen erfolgt die Upcasting implizit. in F# sind die Regeln unterscheiden. Upcasting wird automatisch angewendet, wenn Sie Argumente an Methoden für einen Objekttyp übergeben. Für Let-gebundene Funktionen in einem Modul ist umwandeln jedoch nicht automatisch, es sei denn, der Parametertyp wird als flexibler Typ deklariert. Weitere Informationen finden Sie unter [flexible Typen](flexible-Types.md).

Der `:>`-Operator führt eine statische Umwandlung aus, was bedeutet, dass der Erfolg der Umwandlung zur Kompilierzeit bestimmt wird. Wenn eine Umwandlung, die `:>` verwendet, erfolgreich kompiliert wird, handelt es sich um eine gültige Umwandlung, die zur Laufzeit nicht fehlerhaft ist.

Sie können auch den `upcast`-Operator verwenden, um eine solche Konvertierung durchzuführen. Der folgende Ausdruck gibt eine Konvertierung in der Hierarchie an:

```fsharp
upcast expression
```

Wenn Sie den umgewandelt-Operator verwenden, versucht der Compiler, den Typ, in den konvertiert werden soll, aus dem Kontext abzuleiten. Wenn der Compiler den Zieltyp nicht ermitteln kann, meldet der Compiler einen Fehler. Eine Typanmerkung ist möglicherweise erforderlich.

### <a name="downcasting"></a>Dass

Der `:?>`-Operator führt eine dynamische Umwandlung aus, was bedeutet, dass der Erfolg der Umwandlung zur Laufzeit bestimmt wird. Eine Umwandlung, die den `:?>` Operator verwendet, wird zur Kompilierzeit nicht geprüft. zur Laufzeit wird jedoch versucht, in den angegebenen Typ umzuwandeln. Wenn das Objekt mit dem Zieltyp kompatibel ist, ist die Umwandlung erfolgreich. Wenn das Objekt nicht mit dem Zieltyp kompatibel ist, löst die Laufzeit eine `InvalidCastException`aus.

Sie können auch den `downcast`-Operator verwenden, um eine dynamische Typkonvertierung durchzuführen. Der folgende Ausdruck gibt eine Konvertierung der Hierarchie nach unten in einen Typ an, der aus dem Programmkontext abgeleitet wird:

```fsharp
downcast expression
```

Wie beim `upcast`-Operator meldet der Compiler einen Fehler, wenn der Compiler keinen bestimmten Zieltyp aus dem Kontext ableiten kann. Eine Typanmerkung ist möglicherweise erforderlich.

Der folgende Code veranschaulicht die Verwendung der Operatoren "`:>`" und "`:?>`". Der Code veranschaulicht, dass der `:?>`-Operator am besten verwendet wird, wenn Sie wissen, dass die Konvertierung erfolgreich ist, da Sie `InvalidCastException` auslöst, wenn die Konvertierung fehlschlägt. Wenn Sie nicht wissen, dass eine Konvertierung erfolgreich durchgeführt werden kann, ist ein Typtest, der einen `match` Ausdruck verwendet, besser, da dadurch der Aufwand für das Erzeugen einer Ausnahme vermieden wird.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

Da generische Operatoren `downcast` und `upcast` auf den Typrückschluss zurückgreifen, um das Argument und den Rückgabetyp zu bestimmen, können Sie im obigen Code

```fsharp
let base1 = d1 :> Base1
```

mit

```fsharp
let base1: Base1 = upcast d1
```

Beachten Sie, dass eine Typanmerkung erforderlich ist, da die Basisklasse von `upcast` allein nicht bestimmt werden konnte.

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
