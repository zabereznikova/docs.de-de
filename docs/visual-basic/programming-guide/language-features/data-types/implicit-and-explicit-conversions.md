---
title: Implizite und explizite Konvertierungen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [Visual Basic], type
- variables [Visual Basic], changing data type
- casting
- conversions [Visual Basic], data type
- type conversion [Visual Basic], implicit conversions
- CType function [Visual Basic], conversions
- casting, data types
- data type conversion [Visual Basic], explicit
- type conversion [Visual Basic], explicit conversions
- data types [Visual Basic], casting
- conversions [Visual Basic], implicit
- explicit data type conversions [Visual Basic]
- conversions [Visual Basic]
- changing data types [Visual Basic]
- conversions [Visual Basic], explicit
- data type conversion [Visual Basic], implicit
- implicit data type conversions [Visual Basic]
ms.assetid: 77de1659-af8a-492c-967e-e7ef60ccce66
ms.openlocfilehash: 4bcf2d76a2983294f244b72f286842a92fb5e64e
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512865"
---
# <a name="implicit-and-explicit-conversions-visual-basic"></a>Implizite und explizite Konvertierungen (Visual Basic)

Eine *implizite Konvertierung* erfordert keine besondere Syntax im Quellcode. Im folgenden Beispiel konvertiert Visual Basic den Wert von `k` implizit in einen Gleit Komma Wert mit einfacher Genauigkeit, bevor `q`er dem zugewiesen wird.

```vb
Dim k As Integer
Dim q As Double
' Integer widens to Double, so you can do this with Option Strict On.
k = 432
q = k
```

Eine *explizite Konvertierung* verwendet ein Typkonvertierungs Schlüsselwort. Visual Basic stellt mehrere solche Schlüsselwörter bereit, die einen Ausdruck in Klammern in den gewünschten Datentyp umwandeln. Diese Schlüsselwörter fungieren wie Funktionen, aber der Compiler generiert den Code Inline, sodass die Ausführung etwas schneller ist als bei einem Funktions Aufruf.

In der folgenden Erweiterung des vorherigen Beispiels konvertiert das `CInt` -Schlüsselwort den Wert von `q` zurück in eine `k`ganze Zahl, bevor Sie diesem zugewiesen wird.

```vb
' q had been assigned the value 432 from k.
q = Math.Sqrt(q)
k = CInt(q)
' k now has the value 21 (rounded square root of 432).
```

## <a name="conversion-keywords"></a>Konvertierungsschlüsselwörter

Die folgende Tabelle zeigt die verfügbaren Konvertierungs Schlüsselwörter.

|Schlüsselwort für Typkonvertierung|Konvertiert einen Ausdruck in einen-Datentyp.|Zulässige Datentypen von zu konvertierenden Ausdrücken|
|---|---|---|
|`CBool`|[Boolean-Datentyp](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`und enumerierten Typen), `String`,`Object`|
|`CByte`|[Byte-Datentyp](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|Ein beliebiger numerischer `SByte` Typ (einschließlich und enumerierten `String`Typen), `Boolean`,,`Object`|
|`CChar`|[Char-Datentyp](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`String`, `Object`|
|`CDate`|[Date-Datentyp](../../../../visual-basic/language-reference/data-types/date-data-type.md)|`String`, `Object`|
|`CDbl`|[Double-Datentyp](../../../../visual-basic/language-reference/data-types/double-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`und `String`enumerierten Typen), `Boolean`,,`Object`|
|`CDec`|[Decimal-Datentyp](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`und `String`enumerierten Typen), `Boolean`,,`Object`|
|`CInt`|[Integer-Datentyp](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`und `String`enumerierten Typen), `Boolean`,,`Object`|
|`CLng`|[Long-Datentyp](../../../../visual-basic/language-reference/data-types/long-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`und `String`enumerierten Typen), `Boolean`,,`Object`|
|`CObj`|[Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)|Beliebiger Typ|
|`CSByte`|[SByte-Datentyp](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|Ein beliebiger numerischer `Byte` Typ (einschließlich und enumerierten `String`Typen), `Boolean`,,`Object`|
|`CShort`|[Short-Datentyp](../../../../visual-basic/language-reference/data-types/short-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`und `String`enumerierten Typen), `Boolean`,,`Object`|
|`CSng`|[Single-Datentyp](../../../../visual-basic/language-reference/data-types/single-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`und `String`enumerierten Typen), `Boolean`,,`Object`|
|`CStr`|[String-Datentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`und enumerierten Typen) `Date`, `Boolean`, `Char`, `Char` ,,`Object`|
|`CType`|Nach dem Komma (`,`) angegebener Typ|Beim Konvertieren in einen *elementaren Datentyp* (einschließlich eines Arrays eines elementaren Typs) werden dieselben Typen wie für das entsprechende Konvertierungs Schlüsselwort zulässig.<br /><br /> Beim umstellen in einen zusammen *gesetzten Datentyp*werden die Schnittstellen implementiert, die implementiert werden, und die Klassen, von denen Sie erbt.<br /><br /> Beim umstellen in eine Klasse oder Struktur, für die Sie überladen `CType`haben, diese Klasse oder Struktur.|
|`CUInt`|[UInteger-Datentyp](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`und `String`enumerierten Typen), `Boolean`,,`Object`|
|`CULng`|[ULong-Datentyp](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`und `String`enumerierten Typen), `Boolean`,,`Object`|
|`CUShort`|[UShort-Datentyp](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`und `String`enumerierten Typen), `Boolean`,,`Object`|

## <a name="the-ctype-function"></a>Die CType-Funktion

Die [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) arbeitet mit zwei Argumenten. Der erste ist der Ausdruck, der konvertiert werden soll, und der zweite ist der Ziel Datentyp oder die Objektklasse. Beachten Sie, dass das erste Argument ein Ausdruck und kein Typ sein muss.

`CType`ist eine *Inline Funktion*, d. h., der kompilierte Code führt die Konvertierung aus, oft ohne einen Funktions aufzurufen. Dadurch wird die Leistung verbessert.

Einen Vergleich von `CType` mit den anderen Schlüsselwörtern für die Typkonvertierung finden Sie unter [DirectCast-Operator](../../../../visual-basic/language-reference/operators/directcast-operator.md) und [TryCast-Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md).

### <a name="elementary-types"></a>Elementare Typen

Das folgende Beispiel veranschaulicht die Verwendung von `CType`.

```vb
k = CType(q, Integer)
' The following statement coerces w to the specific object class Label.
f = CType(w, Label)
```

### <a name="composite-types"></a>Zusammengesetzte Typen

Sie können verwenden `CType` , um Werte in zusammengesetzte Datentypen sowie in elementare Typen zu konvertieren. Sie können es auch verwenden, um eine Objektklasse in den Typ einer ihrer Schnittstellen umzuwandeln, wie im folgenden Beispiel gezeigt.

```vb
' Assume class cZone implements interface iZone.
Dim h As Object
' The first argument to CType must be an expression, not a type.
Dim cZ As cZone
' The following statement coerces a cZone object to its interface iZone.
h = CType(cZ, iZone)
```

### <a name="array-types"></a>Array Typen

`CType`kann auch Array Datentypen konvertieren, wie im folgenden Beispiel gezeigt.

```vb
Dim v() As classV
Dim obArray() As Object
' Assume some object array has been assigned to obArray.
' Check for run-time type compatibility.
If TypeOf obArray Is classV()
    ' obArray can be converted to classV.
    v = CType(obArray, classV())
End If
```

Weitere Informationen und ein Beispiel finden Sie unter [Array Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).

### <a name="types-defining-ctype"></a>Typen, die CType definieren

Sie können für `CType` eine von Ihnen definierte Klasse oder Struktur definieren. Dies ermöglicht es Ihnen, Werte in den und aus dem Typ der Klasse oder Struktur zu konvertieren. Weitere Informationen und ein Beispiel finden [Sie unter Gewusst wie: Definieren Sie einen Konvertierungs Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).

> [!NOTE]
> Die mit einem Konvertierungs Schlüsselwort verwendeten Werte müssen für den Ziel Datentyp gültig sein, oder es tritt ein Fehler auf. Wenn Sie z. b. versuchen, eine `Long` in eine `Integer`zu konvertieren `Long` , muss der Wert von innerhalb des gültigen Bereichs für den `Integer` -Datentyp liegen.

> [!CAUTION]
> Die `CType` Angabe von für die Konvertierung von einem Klassentyp in einen anderen schlägt zur Laufzeit fehl, wenn der Quelltyp nicht vom Zieltyp abgeleitet ist. Bei einem solchen Fehler wird <xref:System.InvalidCastException> eine Ausnahme ausgelöst.

Wenn einer der Typen jedoch eine Struktur oder Klasse ist, die Sie definiert haben, und wenn Sie für diese `CType` Struktur oder Klasse definiert haben, kann eine Konvertierung erfolgreich durchgeführt werden, wenn Sie die `CType`Anforderungen Ihres erfüllt. Weitere Informationen finden Sie unter [How to: Definieren Sie einen Konvertierungs Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).

Das Ausführen einer expliziten Konvertierung wird auch *als Umwandlung* eines Ausdrucks in einen bestimmten Datentyp oder eine bestimmte Objektklasse bezeichnet.

## <a name="see-also"></a>Siehe auch

- [Typkonvertierungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Konvertierungen zwischen Zeichenfolgen und anderen Typen](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [Vorgehensweise: Konvertieren eines Objekts in einen anderen Typ in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Datentypen](../../../../visual-basic/language-reference/data-types/index.md)
- [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
