---
title: Arraykonvertierungen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], converting type
- type conversion [Visual Basic], arrays
- conversions [Visual Basic], type
- arrays [Visual Basic], data types
- conversions [Visual Basic], data type
- object arrays [Visual Basic], converting type
- data type conversion [Visual Basic], array conversions
- conversions [Visual Basic], array types
- object arrays
ms.assetid: fceff7d2-a1b7-44c7-b9aa-8bd831d8a444
ms.openlocfilehash: 93e6365a70f52f730b016cd4d4ac9382baeeba55
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43396548"
---
# <a name="array-conversions-visual-basic"></a>Arraykonvertierungen (Visual Basic)
Sie können einen Arraytyp in einen anderen Arraytyp konvertieren, sofern Sie die folgenden Bedingungen erfüllen:  
  
-   **Gleich Rang.** Die Zahl der die beiden Arrays müssen identisch sein, also verfügen, müssen die gleiche Anzahl von Dimensionen. Die Länge der jeweiligen Dimensionen müssen allerdings nicht identisch sein.  
  
-   **Datentyp des Elements.** Die Datentypen der Elemente beider Arrays müssen Referenztypen sein. Sie können nicht konvertiert werden ein `Integer` array an eine `Long` array oder sogar um eine `Object` array, da mindestens ein Werttyp ist. Weitere Informationen finden Sie unter [Werttypen und Referenztypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
-   **Die Konvertierung.** Eine Konvertierung, erweiternd oder einschränkend, muss zwischen den Elementtypen der beiden Arrays sein. Ein Beispiel, das diese Anforderung nicht erfüllt, wird ein Versuch einer Konvertierung zwischen einem `String` Array und einem Array von einer Klasse abgeleitet <xref:System.Attribute?displayProperty=nameWithType>. Diese beiden Typen haben nichts gemeinsam, und keine Konvertierung jeglicher Art, die zwischen ihnen vorhanden ist.  
  
 Eine Konvertierung von einem Arraytyp ist erweiternde oder einschränkende, je nachdem, ob die Konvertierung der jeweiligen Elemente erweiternde oder einschränkende ist. Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## <a name="conversion-to-an-object-array"></a>Konvertierung in ein Objektarray  
 Wenn Sie deklarieren eine `Object` Array ohne Initialisierung hinzuzufügen, den Elementtyp `Object` solange er nicht initialisiert ist. Wenn Sie es in ein Array von einer bestimmten Klasse festlegen, dauert es für den Typ dieser Klasse. Die zugrunde liegende Typ ist jedoch weiterhin `Object`, können Sie ihn anschließend in ein anderes Array einer unabhängigen Klasse festlegen. Da alle Klassen abgeleitet `Object`, können Sie Elementtyp des Arrays aus einer Klasse in einer beliebigen anderen Klasse ändern.  
  
 Im folgenden Beispiel keine Konvertierungen zwischen Typen `student` und `String`, aber beide abgeleitet `Object`, sodass alle Zuweisungen gültig sind.  
  
```  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### <a name="underlying-type-of-an-array"></a>Der zugrunde liegende Typ eines Arrays  
 Wenn Sie ursprünglich ein Array mit einer bestimmten Klasse deklarieren, ist die zugrunde liegende Elementtyp dieser Klasse. Wenn Sie anschließend auf ein Array von einer anderen Klasse festlegen, muss eine Konvertierung zwischen den beiden Klassen vorhanden sein.  
  
 Im folgenden Beispiel `students` ist eine `student` Array. Da keine Konvertierung vorhanden, zwischen ist `String` und `student`, die letzte Anweisung schlägt fehl.  
  
```  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Typkonvertierung in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Konvertierungen zwischen Zeichenfolgen und anderen Typen](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [Vorgehensweise: Konvertieren eines Objekts in einen anderen Typ in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [Datentypen](../../../../visual-basic/language-reference/data-types/index.md)  
 [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
