---
title: "Implicit and Explicit Conversions (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "conversions, type"
  - "variables [Visual Basic], changing data type"
  - "casting"
  - "conversions, data type"
  - "type conversion, implicit conversions"
  - "CType function, conversions"
  - "casting, data types"
  - "data type conversion, explicit"
  - "type conversion, explicit conversions"
  - "data types [Visual Basic], casting"
  - "conversions, implicit"
  - "explicit data type conversions"
  - "conversions"
  - "changing data types"
  - "conversions, explicit"
  - "data type conversion, implicit"
  - "implicit data type conversions"
ms.assetid: 77de1659-af8a-492c-967e-e7ef60ccce66
caps.latest.revision: 25
caps.handback.revision: 25
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Implicit and Explicit Conversions (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Für *implizite Konvertierungen* ist keine spezielle Syntax im Quellcode erforderlich.  Im folgenden Beispiel konvertiert [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] den Wert von `k` implizit in einen Gleitkommawert einfacher Genauigkeit und weist den Wert anschließend `q` zu.  
  
```  
Dim k As Integer  
Dim q As Double  
' Integer widens to Double, so you can do this with Option Strict On.  
k = 432  
q = k  
```  
  
 Bei *expliziten Konvertierungen* wird ein Schlüsselwort zur Typkonvertierung verwendet.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] stellt mehrere solcher Schlüsselwörter bereit, mit denen ein in runden Klammern stehender Ausdruck in den gewünschten Datentyp konvertiert wird.  Diese Schlüsselwörter verhalten sich wie Funktionen, aber der Compiler generiert den Code inline, sodass die Ausführung etwas schneller als bei einem Funktionsaufruf erfolgt.  
  
 In der folgenden Erweiterung des oben stehenden Beispiels konvertiert das `CInt`\-Schlüsselwort den Wert von `q` vor der Zuweisung zu `k` wieder in eine ganze Zahl.  
  
```  
' q had been assigned the value 432 from k.  
q = Math.Sqrt(q)  
k = CInt(q)  
' k now has the value 21 (rounded square root of 432).  
```  
  
## Konvertierungsschlüsselwörter  
 In der folgenden Tabelle sind die verfügbaren Konvertierungsschlüsselwörter zusammengefasst.  
  
||||  
|-|-|-|  
|Typkonvertierungsschlüsselwort|Konvertierung eines Ausdrucks in Datentyp|Zulässige Datentypen für zu konvertierenden Ausdruck|  
|`CBool`|[Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Ein beliebiger numerischer Typ \(einschließlich `Byte`, `SByte` und Enumerationstypen\), `String`, `Object`|  
|`CByte`|[Byte Data Type](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|Ein beliebiger numerischer Typ \(einschließlich `SByte` und Enumerationstypen\), `Boolean`, `String`, `Object`|  
|`CChar`|[Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`String`, `Object`|  
|`CDate`|[Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md)|`String`, `Object`|  
|`CDbl`|[Double Data Type](../../../../visual-basic/language-reference/data-types/double-data-type.md)|Ein beliebiger numerischer Typ \(einschließlich `Byte`, `SByte` und Enumerationstypen\), `Boolean`, `String`, `Object`|  
|`CDec`|[Decimal Data Type](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|Ein beliebiger numerischer Typ \(einschließlich `Byte`, `SByte` und Enumerationstypen\), `Boolean`, `String`, `Object`|  
|`CInt`|[Integer Data Type](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|Ein beliebiger numerischer Typ \(einschließlich `Byte`, `SByte` und Enumerationstypen\), `Boolean`, `String`, `Object`|  
|`CLng`|[Long Data Type](../../../../visual-basic/language-reference/data-types/long-data-type.md)|Ein beliebiger numerischer Typ \(einschließlich `Byte`, `SByte` und Enumerationstypen\), `Boolean`, `String`, `Object`|  
|`CObj`|[Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)|Beliebiger Typ|  
|`CSByte`|[SByte Data Type](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|Ein beliebiger numerischer Typ \(einschließlich `Byte` und Enumerationstypen\), `Boolean`, `String`, `Object`|  
|`CShort`|[Short Data Type](../../../../visual-basic/language-reference/data-types/short-data-type.md)|Ein beliebiger numerischer Typ \(einschließlich `Byte`, `SByte` und Enumerationstypen\), `Boolean`, `String`, `Object`|  
|`CSng`|[Single Data Type](../../../../visual-basic/language-reference/data-types/single-data-type.md)|Ein beliebiger numerischer Typ \(einschließlich `Byte`, `SByte` und Enumerationstypen\), `Boolean`, `String`, `Object`|  
|`CStr`|[String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md)|Ein beliebiger numerischer Typ \(einschließlich `Byte`, `SByte` und Enumerationstypen\), `Boolean`, `Char`, `Char`\-Array, `Date`, `Object`|  
|`CType`|Nach dem Komma \(`,`\) angegebener Typ|Bei der Konvertierung in einen *elementaren Datentyp* \(einschließlich eines Arrays eines elementaren Typs\) dieselben Typen, die für das entsprechende Konvertierungsschlüsselwort zulässig sind<br /><br /> Bei der Konvertierung in einen *zusammengesetzten Datentyp* die implementierten Schnittstellen und die Klassen, von denen geerbt wird<br /><br /> Bei der Konvertierung in eine Klasse oder Struktur, auf die Sie `CType` überladen haben, die betreffende Klasse oder Struktur|  
|`CUInt`|[UInteger Data Type](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|Ein beliebiger numerischer Typ \(einschließlich `Byte`, `SByte` und Enumerationstypen\), `Boolean`, `String`, `Object`|  
|`CULng`|[ULong Data Type](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|Ein beliebiger numerischer Typ \(einschließlich `Byte`, `SByte` und Enumerationstypen\), `Boolean`, `String`, `Object`|  
|`CUShort`|[UShort Data Type](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|Ein beliebiger numerischer Typ \(einschließlich `Byte`, `SByte` und Enumerationstypen\), `Boolean`, `String`, `Object`|  
  
## Die CType\-Funktion  
 Die [CType\-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) wird auf zwei Argumente angewendet.  Das erste Argument ist der zu konvertierende Ausdruck, das zweite der Zieldatentyp oder die Objektklasse.  Das erste Argument muss ein Ausdruck sein, kein Typ.  
  
 `CType` ist eine *Inlinefunktion*. Das heißt, dass der kompilierte Code die Konvertierung ausführt, in vielen Fällen auch ohne Funktionsaufruf.  Dies führt zu einer Leistungssteigerung.  
  
 Einen Vergleich von `CType` mit den anderen Typkonvertierungsschlüsselwörtern finden Sie unter [DirectCast Operator](../../../../visual-basic/language-reference/operators/directcast-operator.md) und [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md).  
  
### Elementare Typen  
 Das folgende Beispiel veranschaulicht die Verwendung von `CType`.  
  
```  
k = CType(q, Integer)  
' The following statement coerces w to the specific object class Label.  
f = CType(w, Label)  
```  
  
### Zusammengesetzte Typen  
 Mithilfe von `CType` können Sie Werte sowohl in zusammengesetzte Datentypen als auch in elementare Typen konvertieren.  Darüber hinaus können Sie damit eine Objektklasse in den Typ einer der dazugehörigen Schnittstellen konvertieren, wie im folgenden Beispiel dargestellt.  
  
```  
' Assume class cZone implements interface iZone.  
Dim h As Object  
' The first argument to CType must be an expression, not a type.  
Dim cZ As cZone  
' The following statement coerces a cZone object to its interface iZone.  
h = CType(cZ, iZone)  
```  
  
### Arraytypen  
 Außerdem können mit `CType` Arraytypen konvertiert werden, wie im folgenden Beispiel dargestellt.  
  
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
  
 Weitere Informationen und ein Beispiel finden Sie unter [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).  
  
### Typen, die CType definieren  
 Sie können `CType` auf einer Klasse oder einer Struktur definieren, die Sie definiert haben.  Damit können Sie Werte in den Typ der Klasse oder Struktur konvertieren bzw. aus diesem Typ konvertieren.  Weitere Informationen und ein Beispiel finden Sie unter [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
> [!NOTE]
>  Die mit einem Konvertierungsschlüsselwort verwendeten Werte müssen für den Zieldatentyp gültig sein. Andernfalls tritt ein Fehler auf.  Wenn Sie beispielsweise versuchen, `Long` in `Integer` zu konvertieren, muss der Wert von `Long` innerhalb des gültigen Bereichs für den `Integer`\-Datentyp liegen.  
  
> [!CAUTION]
>  Wenn der Ausgangstyp nicht aus dem Zieltyp abgeleitet wird, tritt bei der Verwendung von `CType` zur Konvertierung von einem Klassentyp in einen anderen ein Fehler auf.  Durch einen solchen Fehler wird eine <xref:System.InvalidCastException>\-Ausnahme ausgelöst.  
  
 Wenn es sich bei einem dieser Typen jedoch um eine von Ihnen definierte Struktur oder Klasse handelt und Sie `CType` in der betreffenden Struktur oder Klasse definiert haben, kann eine Konvertierung durchgeführt werden, wenn sie den Anforderungen von `CType` entspricht.  Weitere Informationen finden Sie unter [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
 Explizite Konvertierungen werden auch als *Umwandlung* eines Ausdrucks in einen gegebenen Datentyp oder eine Objektklasse bezeichnet.  
  
## Siehe auch  
 [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Conversions Between Strings and Other Types](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)   
 [How to: Convert an Object to Another Type in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)