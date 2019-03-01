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
ms.openlocfilehash: dda23ef3ff49bd32474f39f5ae1807e57bdc2a62
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980463"
---
# <a name="new-operator-visual-basic"></a>Operator New (Visual Basic)
Führt eine `New` -Klausel zum Erstellen einer neuen Objektinstanz gibt eine Konstruktoreinschränkung für einen Typparameter oder identifiziert eine `Sub` Prozedur als ein Klassenkonstruktor.  
  
## <a name="remarks"></a>Hinweise  
 In einer Deklaration oder zuweisungsanweisung eine `New` -Klausel muss angeben eine definierte Klasse, die von dem die Instanz erstellt werden kann. Dies bedeutet, dass die Klasse einen oder mehrere Konstruktoren verfügbar machen muss, die der aufrufende Code zugreifen können.  
  
 Sie können eine `New` -Klausel in einer deklarationsanweisung oder eine zuweisungsanweisung. Wenn die Anweisung ausgeführt wird, ruft er den entsprechenden Konstruktor der angegebenen Klasse und übergeben von Argumenten, die Sie angegeben haben. Das folgende Beispiel zeigt dies durch das Erstellen von Instanzen von einem `Customer` -Klasse, die zwei Konstruktoren, die keine Parameter akzeptiert und eine, die einen Zeichenfolgenparameter akzeptiert.  
  
 [!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]  
  
 Da Arrays Klassen sind `New` können eine neues Array-Instanz erstellen, wie in den folgenden Beispielen gezeigt.  
  
 [!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]  
  
 Löst die common Language Runtime (CLR) eine <xref:System.OutOfMemoryException> Fehler, wenn nicht genügend zum Erstellen der neuen Instanz Arbeitsspeicher.  
  
> [!NOTE]
>  Die `New` -Schlüsselwort wird auch in der Parameterliste des Typs verwendet, um anzugeben, dass der angegebene Typ der einen zugänglichen parameterlosen Konstruktor verfügbar machen muss. Weitere Informationen über Typparameter und Einschränkungen finden Sie unter [Typliste](../../../visual-basic/language-reference/statements/type-list.md).  
  
 Um eine Konstruktorprozedur für eine Klasse zu erstellen, legen Sie den Namen des eine `Sub` Vorgehensweise die `New` Schlüsselwort. Weitere Informationen finden Sie unter [Object Lifetime: Wie die Objekte erstellt und zerstört werden](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
 Das `New`-Schlüsselwort kann in den folgenden Kontexten verwendet werden:  
  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.OutOfMemoryException>
- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
- [Typliste](../../../visual-basic/language-reference/statements/type-list.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Objektlebensdauer: Wie die Objekte erstellt und zerstört werden](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
