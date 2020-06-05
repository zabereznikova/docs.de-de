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
ms.openlocfilehash: 2efc0410b9d4bb663e1ff19d5a5456d7ff2c99bd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84394064"
---
# <a name="generic-procedures-in-visual-basic"></a>Generische Prozeduren in Visual Basic
Eine *generische Prozedur*, auch als *generische Methode*bezeichnet, ist eine Prozedur, die mit mindestens einem Typparameter definiert wird. Dadurch kann der aufrufenden Code die Datentypen bei jedem Aufruf der Prozedur an Ihre Anforderungen anpassen.  
  
 Eine Prozedur ist nicht generisch, weil Sie lediglich in einer generischen Klasse oder einer generischen Struktur definiert ist. Um generisch zu sein, muss die Prozedur zusätzlich zu den normalen Parametern, die Sie annehmen kann, mindestens einen Typparameter annehmen. Eine generische Klasse oder Struktur kann nicht generische Prozeduren enthalten, und eine nicht generische Klasse, Struktur oder ein Modul kann generische Prozeduren enthalten.  
  
 Eine generische Prozedur kann die Typparameter in der normalen Parameterliste in Ihrem Rückgabetyp verwenden, wenn Sie über eine verfügt, und in Ihrem Prozedur Code.  
  
## <a name="type-inference"></a>Typableitung  
 Sie können eine generische Prozedur ohne Angabe von Typargumenten aufgerufen werden. Wenn Sie diese Methode auf diese Weise aufzurufen, versucht der Compiler, die entsprechenden Datentypen zu bestimmen, die an die Typargumente der Prozedur übergeben werden. Dies wird als *Typrückschluss*bezeichnet. Der folgende Code zeigt einen-Befehl, in dem der Compiler ausleitet, dass der Typ `String` an den Typparameter übergeben werden soll `t` .  
  
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
  
### <a name="description"></a>BESCHREIBUNG  
 Im folgenden Beispiel wird eine generische `Function` Prozedur definiert, um ein bestimmtes Element in einem Array zu finden. Er definiert einen Typparameter und verwendet ihn, um die beiden Parameter in der Parameterliste zu erstellen.  
  
### <a name="code"></a>Code  
 [!code-vb[VbVbalrDataTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#14)]  
  
### <a name="comments"></a>Kommentare  
 Das vorherige Beispiel erfordert die Möglichkeit, mit `searchValue` jedem Element von zu vergleichen `searchArray` . Um diese Möglichkeit zu gewährleisten, schränkt Sie den Typparameter ein, `T` um die- <xref:System.IComparable%601> Schnittstelle zu implementieren. Der Code verwendet die- <xref:System.IComparable%601.CompareTo%2A> Methode anstelle des- `=` Operators, da es keine Garantie gibt, dass ein für angegebenes Typargument `T` den-Operator unterstützt `=` .  
  
 Sie können die `findElement` Prozedur mit dem folgenden Code testen.  
  
 [!code-vb[VbVbalrDataTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#13)]  
  
 Der vorherige Aufruf von `MsgBox` zeigt "0", "1" und "-1" an.  
  
## <a name="see-also"></a>Weitere Informationen

- [Generische Typen in Visual Basic (Visual Basic)](generic-types.md)
- [Vorgehensweise: Definieren einer Klasse, die für unterschiedliche Datentypen die gleiche Funktionalität bereitstellen kann](how-to-define-a-class-that-can-provide-identical-functionality.md)
- [Vorgehensweise: Verwenden einer generischen Klasse](how-to-use-a-generic-class.md)
- [Vorgehensweisen](../procedures/index.md)
- [Parameter und Argumente von Prozeduren](../procedures/procedure-parameters-and-arguments.md)
- [Type List](../../../language-reference/statements/type-list.md)
- [Parameterliste](../../../language-reference/statements/parameter-list.md)
