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
ms.openlocfilehash: 1d20b01200d3f967e3355dc6e9651291003d140e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402004"
---
# <a name="array-conversions-visual-basic"></a>Arraykonvertierungen (Visual Basic)
Sie können einen Arraytyp in einen anderen Arraytyp konvertieren, wenn die folgenden Bedingungen erfüllt sind:  
  
- **Gleicher Rang.** Die Ränge der beiden Arrays müssen identisch sein, d. h., Sie müssen über die gleiche Anzahl von Dimensionen verfügen. Die Längen der jeweiligen Dimensionen müssen jedoch nicht identisch sein.  
  
- **Der Element Datentyp.** Die Datentypen der Elemente beider Arrays müssen Verweis Typen sein. Ein Array kann nicht `Integer` in ein- `Long` Array oder sogar in ein `Object` Array konvertiert werden, da mindestens ein Werttyp beteiligt ist. Weitere Informationen finden Sie unter [Werttypen und Verweis Typen](value-types-and-reference-types.md).  
  
- **Konvertierbarkeit.** Eine Konvertierung, die erweitert oder einschränkend ist, muss zwischen den Elementtypen der beiden Arrays möglich sein. Ein Beispiel, bei dem diese Anforderung nicht erfüllt wird, ist eine versuchte Konvertierung zwischen einem `String` -Array und einem Array einer von abgeleiteten Klasse <xref:System.Attribute?displayProperty=nameWithType> . Diese beiden Typen haben nichts gemeinsam, und es besteht keine Konvertierung zwischen Ihnen.  
  
 Eine Konvertierung von einem Arraytyp in einen anderen wird erweitert oder einschränkend, abhängig davon, ob die Konvertierung der entsprechenden Elemente zunimmt oder einschränkend ist. Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](widening-and-narrowing-conversions.md).  
  
## <a name="conversion-to-an-object-array"></a>Konvertieren in ein Objekt Array  
 Wenn Sie ein `Object` Array ohne Initialisierung deklarieren, ist dessen Elementtyp `Object` so lange, wie es nicht initialisiert wird. Wenn Sie es auf ein Array einer bestimmten Klasse festlegen, wird der Typ dieser Klasse benötigt. Der zugrunde liegende Typ ist jedoch immer noch `Object` , und Sie können ihn anschließend auf ein anderes Array einer nicht verknüpften Klasse festlegen. Da alle Klassen von abgeleitet `Object` werden, können Sie den Elementtyp des Arrays von einer beliebigen Klasse in eine beliebige andere Klasse ändern.  
  
 Im folgenden Beispiel gibt es keine Konvertierung zwischen Typen `student` und `String` , aber beide werden von abgeleitet `Object` , sodass alle Zuweisungen gültig sind.  
  
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
  
 Im folgenden Beispiel `students` ist ein- `student` Array. Da keine Konvertierung zwischen `String` und vorhanden `student` ist, schlägt die letzte Anweisung fehl.  
  
```vb  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Datentypen](index.md)
- [Typkonvertierung in Visual Basic](type-conversions.md)
- [Implizite und explizite Konvertierungen](implicit-and-explicit-conversions.md)
- [Konvertierungen zwischen Zeichenfolgen und anderen Typen](conversions-between-strings-and-other-types.md)
- [Gewusst wie: Konvertieren eines Objekts in einen anderen Typ in Visual Basic](how-to-convert-an-object-to-another-type.md)
- [Datentypen](../../../language-reference/data-types/index.md)
- [Type Conversion Functions](../../../language-reference/functions/type-conversion-functions.md)
- [Arrays](../arrays/index.md)
