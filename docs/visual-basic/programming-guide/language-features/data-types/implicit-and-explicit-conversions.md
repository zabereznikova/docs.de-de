---
title: Implizite und explizite Konvertierungen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- conversions, type
- variables [Visual Basic], changing data type
- casting
- conversions, data type
- type conversion, implicit conversions
- CType function, conversions
- casting, data types
- data type conversion, explicit
- type conversion, explicit conversions
- data types [Visual Basic], casting
- conversions, implicit
- explicit data type conversions
- conversions
- changing data types
- conversions, explicit
- data type conversion, implicit
- implicit data type conversions
ms.assetid: 77de1659-af8a-492c-967e-e7ef60ccce66
caps.latest.revision: 25
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 24c434df4be480c290b3e4e36bd9f294d12b99ef
ms.lasthandoff: 03/13/2017

---
# <a name="implicit-and-explicit-conversions-visual-basic"></a>Implizite und explizite Konvertierungen (Visual Basic)
Ein *implizite Konvertierung* ist eine besondere Syntax in den Quellcode nicht erforderlich. Im folgenden Beispiel [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] implizit konvertiert den Wert der `k` in einen Gleitkommawert mit einfacher Genauigkeit-Wert vor der Zuweisung zu `q`.  
  
```  
Dim k As Integer  
Dim q As Double  
' Integer widens to Double, so you can do this with Option Strict On.  
k = 432  
q = k  
```  
  
 Ein *explizite Konvertierung* verwendet das Schlüsselwort Typ konvertieren. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]bietet mehrere solcher Schlüsselwörter, die einen Ausdruck in Klammern, um den gewünschten Datentyp umgewandelt werden. Diese Schlüsselwörter Verhalten sich wie Funktionen, aber der Compiler generiert den Code Inline, damit die Ausführung etwas schneller als bei einem Aufruf der Funktion ist.  
  
 In der folgenden Erweiterung des vorherigen Beispiels die `CInt` Schlüsselwort konvertiert den Wert der `q` wieder in eine ganze Zahl vor der Zuweisung zu `k`.  
  
```  
' q had been assigned the value 432 from k.  
q = Math.Sqrt(q)  
k = CInt(q)  
' k now has the value 21 (rounded square root of 432).  
```  
  
## <a name="conversion-keywords"></a>Konvertierungsschlüsselwörter  
 Die folgende Tabelle zeigt die verfügbaren Konvertierungsschlüsselwörter zusammengefasst.  
  
|Die Konvertierungsschlüsselwort eingeben|Konvertiert einen Ausdruck in den Datentyp|Zulässige Datentypen für die zu konvertierende Ausdruck|  
|---|---|---|  
|`CBool`|[Boolean-Datentyp](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `String`,`Object`|  
|`CByte`|[Byte-Datentyp](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|Alle numerischen Typen (einschließlich `SByte` und Enumerationstypen), `Boolean`, `String`,`Object`|  
|`CChar`|[Char-Datentyp](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`String`, `Object`|  
|`CDate`|[Date-Datentyp](../../../../visual-basic/language-reference/data-types/date-data-type.md)|`String`, `Object`|  
|`CDbl`|[Double-Datentyp](../../../../visual-basic/language-reference/data-types/double-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`,`Object`|  
|`CDec`|[Decimal-Datentyp](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`,`Object`|  
|`CInt`|[Integer-Datentyp](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`,`Object`|  
|`CLng`|[Long-Datentyp](../../../../visual-basic/language-reference/data-types/long-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`,`Object`|  
|`CObj`|[Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)|Beliebiger Typ|  
|`CSByte`|[SByte-Datentyp](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|Alle numerischen Typen (einschließlich `Byte` und Enumerationstypen), `Boolean`, `String`,`Object`|  
|`CShort`|[Short-Datentyp](../../../../visual-basic/language-reference/data-types/short-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`,`Object`|  
|`CSng`|[Single-Datentyp](../../../../visual-basic/language-reference/data-types/single-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`,`Object`|  
|`CStr`|[String-Datentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `Char`, `Char` Array `Date`,`Object`|  
|`CType`|Nach dem Komma angegeben Typ (`,`)|Beim Konvertieren in ein *elementaren Datentyp* (einschließlich eines Arrays eines elementaren Typs), die gleichen Typen für das entsprechende Konvertierungsschlüsselwort zulässig sind<br /><br /> Beim Konvertieren in ein *zusammengesetzten Datentyp*, die implementierten Schnittstellen und die Klassen, von denen geerbt wird,<br /><br /> Bei der Konvertierung in eine Klasse oder Struktur, auf denen überlastete `CType`, Klasse oder Struktur|  
|`CUInt`|[UInteger-Datentyp](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`,`Object`|  
|`CULng`|[ULong-Datentyp](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`,`Object`|  
|`CUShort`|[UShort-Datentyp](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`,`Object`|  
  
## <a name="the-ctype-function"></a>CType-Funktion  
 Die [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) wirkt auf zwei Argumente. Die erste ist der Ausdruck konvertiert werden, und das zweite ist das Ziel Daten oder die Objektklasse. Beachten Sie, dass das erste Argument einen Ausdruck kein Typ sein muss.  
  
 `CType`ist ein *Inlinefunktion*, d. h. den kompilierten Code wird die Konvertierung, häufig ohne generiert eine Funktion aufrufen. Dies verbessert die Leistung.  
  
 Einen Vergleich der `CType` mit anderen Typkonvertierungsschlüsselwörter, finden Sie unter [DirectCast-Operator](../../../../visual-basic/language-reference/operators/directcast-operator.md) und [TryCast-Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md).  
  
### <a name="elementary-types"></a>Elementare Datentypen  
 Das folgende Beispiel veranschaulicht die Verwendung von `CType`.  
  
```  
k = CType(q, Integer)  
' The following statement coerces w to the specific object class Label.  
f = CType(w, Label)  
```  
  
### <a name="composite-types"></a>Zusammengesetzte Typen  
 Sie können `CType` , Werte in zusammengesetzte Datentypen als auch in elementare Typen konvertieren. Sie können es auch verwenden, umzuwandelnde eine Objektklasse in den Typ einer der Schnittstellen, wie im folgenden Beispiel.  
  
```  
' Assume class cZone implements interface iZone.  
Dim h As Object  
' The first argument to CType must be an expression, not a type.  
Dim cZ As cZone  
' The following statement coerces a cZone object to its interface iZone.  
h = CType(cZ, iZone)  
```  
  
### <a name="array-types"></a>Arraytypen  
 `CType`Array-Datentypen, wie im folgenden Beispiel können auch konvertieren.  
  
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
 Sie können definieren, `CType` für eine Klasse oder Struktur, die Sie definiert haben. Dadurch können Sie zum Konvertieren von Werten in und aus dem Typ der Klasse oder Struktur. Weitere Informationen und ein Beispiel finden Sie unter [Gewusst wie: Definieren eines Konvertierungsoperators](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
> [!NOTE]
>  Mit einem Konvertierungsschlüsselwort verwendeten Werte müssen für den Zieldatentyp gültig sein, oder ein Fehler auftritt. Beispielsweise, wenn Sie versuchen, konvertieren eine `Long` , ein `Integer`, den Wert des der `Long` muss innerhalb des gültigen Bereichs für die `Integer` -Datentyp.  
  
> [!CAUTION]
>  Angeben von `CType` von einem Klassentyp anderen schlägt zur Laufzeit fehl konvertieren, wenn der Typ nicht aus dem Zieltyp abgeleitet ist. Dieser Fehler wird ein <xref:System.InvalidCastException>Ausnahme.</xref:System.InvalidCastException>  
  
 Allerdings einen der Typen ist eine Struktur oder Klasse, die Sie definiert haben, und Sie definiert haben `CType` auf, die Struktur oder Klasse, eine Konvertierung möglich, wenn er die Anforderungen erfüllt Ihre `CType`. Finden Sie unter [Gewusst wie: Definieren eines Konvertierungsoperators](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
 Eine explizite Konvertierung ist auch bekannt als *Umwandlung* eines Ausdrucks in einen angegebenen Daten oder die Objektklasse.  
  
## <a name="see-also"></a>Siehe auch  
 [Typumwandlungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Konvertierungen zwischen Zeichenfolgen und anderen Typen](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)   
 [Gewusst wie: Konvertieren eines Objekts in einen anderen Typ in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
