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
ms.openlocfilehash: 8a0909641b653a1800bdf3f50ec1dfe993411824
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="implicit-and-explicit-conversions-visual-basic"></a>Implizite und explizite Konvertierungen (Visual Basic)
Ein *implizite Konvertierung* erfordert keine spezielle Syntax im Quellcode. Im folgenden Beispiel Visual Basic implizit konvertiert den Wert der `k` in einen Gleitkommawert mit einfacher Genauigkeit-Wert vor der Zuweisung zu `q`.  
  
```  
Dim k As Integer  
Dim q As Double  
' Integer widens to Double, so you can do this with Option Strict On.  
k = 432  
q = k  
```  
  
 Ein *explizite Konvertierung* einen Typkonvertierungsschlüsselwort verwendet. Visual Basic bietet mehrere solcher Schlüsselwörter, die einen Ausdruck in Klammern einschließen, um den gewünschten Datentyp umgewandelt werden. Diese Schlüsselwörter Verhalten sich wie Funktionen, aber damit Ausführung etwas schneller als bei einem Funktionsaufruf ist, generiert der Compiler den Code Inline.  
  
 In der folgenden Erweiterung des vorhergehenden Beispiels die `CInt` Schlüsselwort konvertiert den Wert der `q` wieder in eine ganze Zahl vor der Zuweisung zu `k`.  
  
```  
' q had been assigned the value 432 from k.  
q = Math.Sqrt(q)  
k = CInt(q)  
' k now has the value 21 (rounded square root of 432).  
```  
  
## <a name="conversion-keywords"></a>Konvertierungsschlüsselwörter  
 Die folgende Tabelle zeigt die verfügbaren Konvertierungsschlüsselwörter.  
  
|Typkonvertierungsschlüsselwort|Konvertiert einen Ausdruck in den Datentyp|Zulässige Datentypen des Ausdrucks, der konvertiert werden|  
|---|---|---|  
|`CBool`|[Boolean-Datentyp](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `String`, `Object`|  
|`CByte`|[Byte-Datentyp](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|Alle numerischen Typen (einschließlich `SByte` und Enumerationstypen), `Boolean`, `String`, `Object`|  
|`CChar`|[Char-Datentyp](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`String`, `Object`|  
|`CDate`|[Date-Datentyp](../../../../visual-basic/language-reference/data-types/date-data-type.md)|`String`, `Object`|  
|`CDbl`|[Double-Datentyp](../../../../visual-basic/language-reference/data-types/double-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`, `Object`|  
|`CDec`|[Decimal-Datentyp](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`, `Object`|  
|`CInt`|[Integer-Datentyp](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`, `Object`|  
|`CLng`|[Long-Datentyp](../../../../visual-basic/language-reference/data-types/long-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`, `Object`|  
|`CObj`|[Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)|Beliebiger Typ|  
|`CSByte`|[SByte-Datentyp](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|Alle numerischen Typen (einschließlich `Byte` und Enumerationstypen), `Boolean`, `String`, `Object`|  
|`CShort`|[Short-Datentyp](../../../../visual-basic/language-reference/data-types/short-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`, `Object`|  
|`CSng`|[Single-Datentyp](../../../../visual-basic/language-reference/data-types/single-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`, `Object`|  
|`CStr`|[String-Datentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `Char`, `Char` Array `Date`, `Object`|  
|`CType`|Nach dem Komma angegeben Typ (`,`)|Beim Konvertieren in ein *elementaren Datentyp* (einschließlich ein Array von ein elementarer Typ), die gleiche Typen für das entsprechende Konvertierungsschlüsselwort zulässig sind<br /><br /> Beim Konvertieren in eine *zusammengesetzten Datentyp*, er implementiert, Schnittstellen und Klassen, die von der geerbt<br /><br /> Wenn eine Konvertierung in eine Klasse oder Struktur, auf denen Sie überladene haben `CType`, diese Klasse oder Struktur|  
|`CUInt`|[UInteger-Datentyp](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`, `Object`|  
|`CULng`|[ULong-Datentyp](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`, `Object`|  
|`CUShort`|[UShort-Datentyp](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`, `Object`|  
  
## <a name="the-ctype-function"></a>CType-Funktion  
 Die [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) arbeitet mit zwei Argumente. Der erste ist der Ausdruck konvertiert werden, und das zweite ist das Ziel Daten oder die Objektklasse. Beachten Sie, dass das erste Argument einen Ausdruck, der nicht für einen Typ sein muss.  
  
 `CType` ist ein *Inlinefunktion*, d. h. den kompilierten Code ist die Konvertierung, die häufigsten aufrufen, ohne eine Funktion generieren. Dies verbessert die Leistung.  
  
 Einen Vergleich der `CType` mit anderen Schlüsselwörter für die typkonvertierung, finden Sie unter [DirectCast-Operator](../../../../visual-basic/language-reference/operators/directcast-operator.md) und [TryCast-Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md).  
  
### <a name="elementary-types"></a>Elementare Datentypen  
 Das folgende Beispiel veranschaulicht die Verwendung von `CType`.  
  
```  
k = CType(q, Integer)  
' The following statement coerces w to the specific object class Label.  
f = CType(w, Label)  
```  
  
### <a name="composite-types"></a>Zusammengesetzte Typen  
 Sie können `CType` Werte in zusammengesetzten Datentypen als auch in elementare Typen konvertiert. Sie können es verwenden, um zu erzwingende eine Objektklasse in den Typ einer der Schnittstellen, wie im folgenden Beispiel.  
  
```  
' Assume class cZone implements interface iZone.  
Dim h As Object  
' The first argument to CType must be an expression, not a type.  
Dim cZ As cZone  
' The following statement coerces a cZone object to its interface iZone.  
h = CType(cZ, iZone)  
```  
  
### <a name="array-types"></a>Arraytypen  
 `CType` Array-Datentypen, wie im folgenden Beispiel können auch konvertieren.  
  
```  
Dim v() As classV  
Dim obArray() As Object  
' Assume some object array has been assigned to obArray.  
' Check for run-time type compatibility.  
If TypeOf obArray Is classV()  
    ' obArray can be converted to classV.  
    v = CType(obArray, classV())  
End If  
```  
  
 Weitere Informationen und ein Beispiel finden Sie unter [Arraykonvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).  
  
### <a name="types-defining-ctype"></a>Typen, die CType definieren  
 Sie können definieren, `CType` auf eine Klasse oder Struktur, die Sie definiert haben. Dadurch können Sie zum Konvertieren von Werten in und aus dem Typ der Klasse oder Struktur. Weitere Informationen und ein Beispiel finden Sie unter [wie: Definieren eines Konvertierungsoperators](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
> [!NOTE]
>  Werte, die mit einem Konvertierungsschlüsselwort verwendet, müssen für den Zieldatentyp gültig sein, oder ein Fehler auftritt. Z. B., wenn Sie versuchen, konvertieren Sie eine `Long` auf eine `Integer`, den Wert des der `Long` muss innerhalb des gültigen Bereichs für die `Integer` -Datentyp.  
  
> [!CAUTION]
>  Angeben von `CType` von einem Klassentyp nach einem anderen fehlschlägt, zur Laufzeit konvertiert werden, wenn der Quelltyp nicht aus dem Zieltyp abgeleitet ist. Solche Fehler löst eine <xref:System.InvalidCastException> Ausnahme.  
  
 Jedoch, wenn einer der Typen wird eine Struktur oder Klasse, die Sie definiert haben, und Sie definiert haben `CType` für diese Struktur oder Klasse, eine Konvertierung kann erfolgreich ausgeführt werden, wenn es sich um die Anforderungen erfüllt die `CType`. Finden Sie unter [wie: Definieren eines Konvertierungsoperators](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
 Eine explizite Konvertierung ist auch bekannt als *Umwandlung* ein Ausdruck auf eine angegebene Typ oder ein Objekt der Klasse.  
  
## <a name="see-also"></a>Siehe auch  
 [Konvertierungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Konvertierungen zwischen Zeichenfolgen und anderen Typen](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [Vorgehensweise: Konvertieren eines Objekts in einen anderen Typ in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
