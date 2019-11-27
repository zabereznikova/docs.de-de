---
title: Arraykonvertierungen
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
ms.openlocfilehash: 622ebe8a77f2dfbeb35e0408be48622d93d409c6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345861"
---
# <a name="array-conversions-visual-basic"></a>Arraykonvertierungen (Visual Basic)
Sie können einen Arraytyp in einen anderen Arraytyp konvertieren, wenn die folgenden Bedingungen erfüllt sind:  
  
- **Gleicher Rang.** Die Ränge der beiden Arrays müssen identisch sein, d. h., Sie müssen über die gleiche Anzahl von Dimensionen verfügen. Die Längen der jeweiligen Dimensionen müssen jedoch nicht identisch sein.  
  
- **Der Element Datentyp.** Die Datentypen der Elemente beider Arrays müssen Verweis Typen sein. Sie können ein `Integer` Array nicht in ein `Long` Array oder sogar in ein `Object` Array konvertieren, da mindestens ein Werttyp beteiligt ist. Weitere Informationen finden Sie unter [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
- **Konvertierbarkeit.** Eine Konvertierung, die erweitert oder einschränkend ist, muss zwischen den Elementtypen der beiden Arrays möglich sein. Ein Beispiel, bei dem diese Anforderung nicht erfüllt wird, ist eine versuchte Konvertierung zwischen einem `String` Array und einem Array einer Klasse, die von <xref:System.Attribute?displayProperty=nameWithType>abgeleitet wurde. Diese beiden Typen haben nichts gemeinsam, und es besteht keine Konvertierung zwischen Ihnen.  
  
 Eine Konvertierung von einem Arraytyp in einen anderen wird erweitert oder einschränkend, abhängig davon, ob die Konvertierung der entsprechenden Elemente zunimmt oder einschränkend ist. Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## <a name="conversion-to-an-object-array"></a>Konvertieren in ein Objekt Array  
 Wenn Sie ein `Object` Array deklarieren, ohne es zu initialisieren, wird der Elementtyp `Object`, solange es nicht initialisiert bleibt. Wenn Sie es auf ein Array einer bestimmten Klasse festlegen, wird der Typ dieser Klasse benötigt. Allerdings ist der zugrunde liegende Typ weiterhin `Object`, und Sie können ihn anschließend auf ein anderes Array einer nicht verknüpften Klasse festlegen. Da alle Klassen von `Object`abgeleitet werden, können Sie den Elementtyp des Arrays von einer beliebigen Klasse in eine beliebige andere Klasse ändern.  
  
 Im folgenden Beispiel ist keine Konvertierung zwischen Typen `student` und `String`vorhanden, beide werden jedoch von `Object`abgeleitet, sodass alle Zuweisungen gültig sind.  
  
```vb  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### <a name="underlying-type-of-an-array"></a>Zugrunde liegender Typ eines Arrays  
 Wenn Sie ein Array ursprünglich mit einer bestimmten Klasse deklariert haben, ist der zugrunde liegende Elementtyp diese Klasse. Wenn Sie anschließend ein Array einer anderen Klasse festlegen, muss eine Konvertierung zwischen den beiden Klassen erfolgen.  
  
 Im folgenden Beispiel ist `students` ein `student` Array. Da zwischen `String` und `student`keine Konvertierung vorhanden ist, schlägt die letzte Anweisung fehl.  
  
```vb  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Typkonvertierungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Konvertierungen zwischen Zeichenfolgen und anderen Typen](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [Gewusst wie: Konvertieren eines Objekts in einen anderen Typ in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [Datentypen](../../../../visual-basic/language-reference/data-types/index.md)
- [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
