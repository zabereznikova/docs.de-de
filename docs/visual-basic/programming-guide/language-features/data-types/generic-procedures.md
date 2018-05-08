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
ms.openlocfilehash: 686087e4520ea5e6e69e5906c628af3ad54749da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="generic-procedures-in-visual-basic"></a>Generische Prozeduren in Visual Basic
Ein *generische Prozedur*auch Namens eine *generische Methode*, wird eine Prozedur mit mindestens einem Typparameter definiert. Dadurch wird den aufrufenden Code ein, um die Datentypen, die Anforderungen anzupassen, jedes Mal der Prozedur aufrufen.  
  
 Eine Prozedur ist nicht generisch, einfach durch innerhalb einer generischen Klasse oder eine generische Struktur definiert wird. Um generisch sein, muss die Prozedur über mindestens einen Typparameter, zusätzlich zum normalen Parameter dauern dauern kann. Modul kann generische Prozeduren enthalten, oder einer generischen Klasse oder Struktur nicht generischen Prozeduren und eine nicht generische Klasse, Struktur, enthalten.  
  
 Eine generische Prozedur können dessen Typparameter angegeben in der normalen Parameterliste, ihren Rückgabetyp, wenn sie ein, und in der Prozedur Code verfügt.  
  
## <a name="type-inference"></a>Typableitung  
 Sie können eine generische Prozedur aufrufen, ohne Angabe von Typargumenten an. Wenn Sie auf diese Weise aufrufen, versucht der Compiler die entsprechenden Datentypen Übergabe an die Prozedur Typargumente bestimmen. Hierbei spricht *Typrückschluss*. Der folgende Code zeigt einen Aufruf in die leitet der Compiler, dass er Typ übergeben soll `String` an den Typparameter `t`.  
  
 [!code-vb[VbVbalrDataTypes#15](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_1.vb)]  
  
 Wenn der Compiler die Typargumente aus dem Kontext des Aufrufs ableiten kann, meldet er einen Fehler. Eine mögliche Ursache für einen derartigen Fehler gibt ein Array-Rank-Konflikt. Nehmen Sie beispielsweise an, dass Sie als ein Array eines Typparameters einen normalen Parameter definieren. Wenn Sie die generische Prozedur aufrufen, führt dazu, dass ein Array eines abweichenden Rang (Anzahl der Dimensionen) angeben, des Konflikts Typrückschluss fehlschlagen. Der folgende Code zeigt einen Aufruf in dem ein zweidimensionales Array an eine Prozedur übergeben wird, das ein eindimensionales Array erwartet.  
  
 `Public Sub demoSub(Of t)(ByVal arg() As t)`  
  
 `End Sub`  
  
 `Public Sub callDemoSub()`  
  
 `Dim twoDimensions(,) As Integer`  
  
 `demoSub(twoDimensions)`  
  
 `End Sub`  
  
 Typrückschluss kann nur durch das Weglassen der Typargumente aufgerufen werden. Wenn Sie ein Typargument angeben, müssen Sie alle angeben.  
  
 Typrückschluss wird nur für generische Prozeduren unterstützt. Typrückschluss auf generische Klassen, Strukturen, Schnittstellen und Delegaten kann nicht aufgerufen werden.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel definiert einen generischen `Function` Verfahren, um ein bestimmtes Element in einem Array zu ermitteln. Er definiert einen Typparameter und verwendet, um die beiden Parameter in der Parameterliste zu erstellen.  
  
### <a name="code"></a>Code  
 [!code-vb[VbVbalrDataTypes#14](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_2.vb)]  
  
### <a name="comments"></a>Kommentare  
 Das obige Beispiel erfordert, dass vergleichen `searchValue` für jedes Element `searchArray`. Um dies zu garantieren, wird den Typparameter `T` zum Implementieren der <xref:System.IComparable%601> Schnittstelle. Der Code verwendet die <xref:System.IComparable%601.CompareTo%2A> -Methode anstelle der `=` -Operator, da keine Garantie, die ein Type-Argument besteht für angegeben `T` unterstützt die `=` Operator.  
  
 Sie können testen, die `findElement` Prozedur durch den folgenden Code.  
  
 [!code-vb[VbVbalrDataTypes#13](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_3.vb)]  
  
 Die vorangehenden Aufrufe von `MsgBox` "0", "1" und "-1" bzw. anzuzeigen.  
  
## <a name="see-also"></a>Siehe auch  
 [Generische Typen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Gewusst wie: Definieren einer Klasse, die für unterschiedliche Datentypen die gleiche Funktionalität bereitstellen kann](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)  
 [Gewusst wie: Verwenden einer generischen Klasse](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [Verfahren](../../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Parameter und Argumente von Prozeduren](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [Typliste](../../../../visual-basic/language-reference/statements/type-list.md)  
 [Parameterliste](../../../../visual-basic/language-reference/statements/parameter-list.md)
