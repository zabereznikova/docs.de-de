---
title: Generische Prozeduren in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- generic methods [Visual Basic], type inference
- generics [Visual Basic], type inference
- procedures [Visual Basic], generic
- generic procedures
- type inference, generics
- generic methods [Visual Basic]
- type inference
- generics [Visual Basic], procedures
- generic procedures [Visual Basic], type inference
ms.assetid: 95577b28-137f-4d5c-a149-919c828600e5
ms.openlocfilehash: 9a88a979a6b46f897e5f04f4481d4a23e245b165
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45569462"
---
# <a name="generic-procedures-in-visual-basic"></a>Generische Prozeduren in Visual Basic
Ein *generische Prozedur*auch Namens eine *generische Methode*, wird eine Prozedur mit mindestens einem Typparameter definiert. Dadurch wird den aufrufenden Code auf die Datentypen, die Anforderungen jedes Mal passen sie die Prozedur aufruft.  
  
 Eine Prozedur ist nicht generisch, einfach aufgrund der innerhalb einer generischen Klasse oder eine generische Struktur definiert wird. Um generisch sein, muss die Prozedur mindestens einen Typparameter, zusätzlich zum normalen Parameter ausführen, dauert es möglicherweise. Module kann generische Prozeduren enthält, oder einer generischen Klasse oder Struktur nicht generischen Prozeduren und eine nicht generische Klasse, Struktur, enthalten.  
  
 Eine generische Prozedur können dessen Typparameter in der normalen Parameterliste, ihren Rückgabetyp, wenn sie über ein, und in der Prozedur Code verfügt.  
  
## <a name="type-inference"></a>Typableitung  
 Sie können eine generische Prozedur aufrufen, ohne Angabe von Typargumenten überhaupt. Wenn Sie auf diese Weise aufrufen, versucht der Compiler, um zu bestimmen, die entsprechenden Datentypen Übergabe an die Prozedur Typargumente. Dies wird als bezeichnet *Typrückschluss*. Der folgende Code zeigt einen Aufruf in die leitet der Compiler, dass er Typ übergeben soll `String` an den Typparameter `t`.  
  
 [!code-vb[VbVbalrDataTypes#15](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_1.vb)]  
  
 Wenn der Compiler die Typargumente aus dem Kontext des Aufrufs nicht ableiten kann, wird ein Fehler gemeldet. Eine mögliche Ursache für einen derartigen Fehler ist ein Array Rank-Konflikt. Nehmen wir beispielsweise an, dass Sie einen normalen Parameter als Array von einem Typparameter definieren. Rufen Sie die generische Prozedur bewirkt, dass ein Array von einem abweichenden Rang (Anzahl der Dimensionen) angeben, des Konflikts Typrückschluss fehlschlagen. Der folgende Code zeigt einen Aufruf in das ein zweidimensionales Array an eine Prozedur übergeben wird, das ein eindimensionales Array erwartet.  
  
```vb  
Public Sub demoSub(Of t)(ByVal arg() As t)
End Sub

Public Sub callDemoSub()
    Dim twoDimensions(,) As Integer
    demoSub(twoDimensions)
End Sub
```
  
 Sie können den Typrückschluss aufrufen, nur, indem Sie alle Typargumente auslassen. Wenn Sie ein Typargument angeben, müssen Sie alle angeben.  
  
 Typrückschluss ist nur für generische Prozeduren unterstützt. Typrückschluss für generische Klassen, Strukturen, Schnittstellen oder Delegaten kann nicht aufgerufen werden.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel definiert einen generischen `Function` Verfahren zum Suchen eines bestimmten Elements in einem Array. Er definiert einen Typparameter und wird verwendet, um die beiden Parameter in der Parameterliste zu erstellen.  
  
### <a name="code"></a>Code  
 [!code-vb[VbVbalrDataTypes#14](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_2.vb)]  
  
### <a name="comments"></a>Kommentare  
 Das obige Beispiel erfordert die Möglichkeit, vergleichen `searchValue` für jedes Element `searchArray`. Um dies zu garantieren, schränkt sie die Typparameter `T` zum Implementieren der <xref:System.IComparable%601> Schnittstelle. Der Code verwendet die <xref:System.IComparable%601.CompareTo%2A> -Methode anstelle der `=` -Operator, da keine Garantie, die ein Typargument besteht für angegeben `T` unterstützt die `=` Operator.  
  
 Sie können testen, die `findElement` Prozedur durch den folgenden Code.  
  
 [!code-vb[VbVbalrDataTypes#13](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_3.vb)]  
  
 Der vorherigen Aufrufe von `MsgBox` anzeigen bzw. "0", "1" und "-1".  
  
## <a name="see-also"></a>Siehe auch  
 [Generische Typen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Gewusst wie: Definieren einer Klasse, die für unterschiedliche Datentypen die gleiche Funktionalität bereitstellen kann](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)  
 [Gewusst wie: Verwenden einer generischen Klasse](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [Verfahren](../../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Parameter und Argumente von Prozeduren](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [Typliste](../../../../visual-basic/language-reference/statements/type-list.md)  
 [Parameterliste](../../../../visual-basic/language-reference/statements/parameter-list.md)
