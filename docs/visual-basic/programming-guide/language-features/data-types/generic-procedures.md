---
title: Generische Prozeduren
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
ms.openlocfilehash: 16a629e07cf711778b3d8d1863958ec7a6300649
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350084"
---
# <a name="generic-procedures-in-visual-basic"></a>Generische Prozeduren in Visual Basic
Eine *generische Prozedur*, auch als *generische Methode*bezeichnet, ist eine Prozedur, die mit mindestens einem Typparameter definiert wird. Dadurch kann der aufrufenden Code die Datentypen bei jedem Aufruf der Prozedur an Ihre Anforderungen anpassen.  
  
 Eine Prozedur ist nicht generisch, weil Sie lediglich in einer generischen Klasse oder einer generischen Struktur definiert ist. Um generisch zu sein, muss die Prozedur zusätzlich zu den normalen Parametern, die Sie annehmen kann, mindestens einen Typparameter annehmen. Eine generische Klasse oder Struktur kann nicht generische Prozeduren enthalten, und eine nicht generische Klasse, Struktur oder ein Modul kann generische Prozeduren enthalten.  
  
 Eine generische Prozedur kann die Typparameter in der normalen Parameterliste in Ihrem Rückgabetyp verwenden, wenn Sie über eine verfügt, und in Ihrem Prozedur Code.  
  
## <a name="type-inference"></a>Typableitung  
 Sie können eine generische Prozedur ohne Angabe von Typargumenten aufgerufen werden. Wenn Sie diese Methode auf diese Weise aufzurufen, versucht der Compiler, die entsprechenden Datentypen zu bestimmen, die an die Typargumente der Prozedur übergeben werden. Dies wird als *Typrückschluss*bezeichnet. Der folgende Code zeigt einen-Befehl, bei dem der Compiler ausleitet, dass der Typ `String` an den Typparameter `t`übergeben werden soll.  
  
 [!code-vb[VbVbalrDataTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#15)]  
  
 Wenn der Compiler die Typargumente aus dem Kontext des Aufrufes nicht ableiten kann, meldet er einen Fehler. Eine mögliche Ursache für diesen Fehler ist ein Array Rang Konflikt. Angenommen, Sie definieren einen normalen Parameter als Array eines Typparameters. Wenn Sie die generische Prozedur zum Bereitstellen eines Arrays mit einem anderen Rang (Anzahl von Dimensionen) aufzurufen, bewirkt der Konflikt, dass der Typrückschluss fehlschlägt. Der folgende Code zeigt einen-Befehl, bei dem ein zweidimensionales Array an eine Prozedur mit einem eindimensionalen Array übermittelt wird.  
  
```vb  
Public Sub demoSub(Of t)(ByVal arg() As t)
End Sub

Public Sub callDemoSub()
    Dim twoDimensions(,) As Integer
    demoSub(twoDimensions)
End Sub
```
  
 Sie können den Typrückschluss nur aufrufen, indem Sie alle Typargumente weglassen. Wenn Sie ein Typargument angeben, müssen Sie alle angeben.  
  
 Der Typrückschluss wird nur für generische Prozeduren unterstützt. Sie können den Typrückschluss nicht für generische Klassen, Strukturen, Schnittstellen oder Delegaten aufrufen.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Im folgenden Beispiel wird eine generische `Function` Prozedur definiert, um ein bestimmtes Element in einem Array zu suchen. Er definiert einen Typparameter und verwendet ihn, um die beiden Parameter in der Parameterliste zu erstellen.  
  
### <a name="code"></a>Code  
 [!code-vb[VbVbalrDataTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#14)]  
  
### <a name="comments"></a>Comments  
 Das vorherige Beispiel erfordert die Möglichkeit, `searchValue` mit jedem Element `searchArray`zu vergleichen. Um diese Möglichkeit zu gewährleisten, schränkt Sie den Typparameter `T` ein, um die <xref:System.IComparable%601>-Schnittstelle zu implementieren. Der Code verwendet die <xref:System.IComparable%601.CompareTo%2A>-Methode anstelle des `=`-Operators, da es keine Garantie gibt, dass ein für `T` bereitgestelltes Typargument den `=`-Operator unterstützt.  
  
 Sie können die `findElement` Prozedur mit dem folgenden Code testen.  
  
 [!code-vb[VbVbalrDataTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#13)]  
  
 Mit den obigen Aufrufen von `MsgBox` werden "0", "1" und "-1" angezeigt.  
  
## <a name="see-also"></a>Siehe auch

- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Gewusst wie: Definieren einer Klasse, die für unterschiedliche Datentypen die gleiche Funktionalität bereitstellen kann](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)
- [Gewusst wie: Verwenden einer generischen Klasse](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Verfahren](../../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Parameter und Argumente von Prozeduren](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [Typliste](../../../../visual-basic/language-reference/statements/type-list.md)
- [Parameterliste](../../../../visual-basic/language-reference/statements/parameter-list.md)
