---
title: Operator New (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.new
- vb.NewConstraint
helpviewer_keywords:
- constraints, Visual Basic generic types
- generics [Visual Basic], constraints
- constraints, New keyword [Visual Basic]
- New constraint
- New keyword [Visual Basic]
ms.assetid: d7d566d7-fe0e-4336-91f7-641a542de4d0
ms.openlocfilehash: 36cf71529b1f81c27881638d788117222c37171d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955883"
---
# <a name="new-operator-visual-basic"></a>Operator New (Visual Basic)
Führt eine `New` -Klausel ein, um eine neue Objektinstanz zu erstellen, gibt eine Konstruktoreinschränkung für einen Typparameter `Sub` an oder identifiziert eine Prozedur als Klassenkonstruktor.  
  
## <a name="remarks"></a>Hinweise  
 In einer Deklaration oder Zuweisungsanweisung `New` muss eine-Klausel eine definierte Klasse angeben, aus der die Instanz erstellt werden kann. Dies bedeutet, dass die Klasse einen oder mehrere Konstruktoren verfügbar machen muss, auf die der aufrufenden Code zugreifen kann.  
  
 Sie können eine `New` -Klausel in einer Deklarations Anweisung oder einer Zuweisungsanweisung verwenden. Wenn die Anweisung ausgeführt wird, wird der entsprechende Konstruktor der angegebenen Klasse aufgerufen, wobei alle von Ihnen bereitgestellten Argumente übergeben werden. Dies wird im folgenden Beispiel veranschaulicht, indem Instanzen `Customer` einer Klasse erstellt werden, die über zwei Konstruktoren verfügt, eine, die keine Parameter annimmt, und eine Klasse, die einen String-Parameter annimmt.  
  
 [!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]  
  
 Da Arrays Klassen sind, `New` kann eine neue Array Instanz erstellen, wie in den folgenden Beispielen gezeigt.  
  
 [!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]  
  
 Der Common Language Runtime (CLR) löst einen <xref:System.OutOfMemoryException> Fehler aus, wenn nicht genügend Arbeitsspeicher vorhanden ist, um die neue Instanz zu erstellen.  
  
> [!NOTE]
> Das `New` -Schlüsselwort wird auch in Typparameter Listen verwendet, um anzugeben, dass der angegebene Typ einen zugänglichen Parameter losen Konstruktor verfügbar machen muss. Weitere Informationen zu Typparametern und Einschränkungen finden Sie unter [Type List](../../../visual-basic/language-reference/statements/type-list.md).  
  
 Zum Erstellen einer konstruktorprozedur für eine Klasse legen Sie den Namen einer `Sub` Prozedur auf das `New` Schlüsselwort fest. Weitere Informationen finden [Sie unter Objekt Lebensdauer: Die Art und Weise, wie](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)Objekte erstellt und zerstört werden.  
  
 Das `New`-Schlüsselwort kann in den folgenden Kontexten verwendet werden:  
  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.OutOfMemoryException>
- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
- [Typliste](../../../visual-basic/language-reference/statements/type-list.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Objekt Lebensdauer: Erstellen und zerstören von Objekten](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
