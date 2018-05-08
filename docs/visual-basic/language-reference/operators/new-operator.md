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
ms.openlocfilehash: 0fe511b2c16681d7bab7eeda7c121fcbbaa2f5dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="new-operator-visual-basic"></a>Operator New (Visual Basic)
Führt eine `New` -Klausel, um eine neue Objektinstanz erstellt gibt eine Konstruktoreinschränkung für einen Typparameter, oder gibt einen `Sub` Prozedur als ein Klassenkonstruktor.  
  
## <a name="remarks"></a>Hinweise  
 In einer Deklaration oder zuweisungsanweisung eine `New` -Klausel muss eine definierte Klasse, von dem die Instanz erstellt werden kann. Dies bedeutet, dass die Klasse einen oder mehrere Konstruktoren verfügbar machen muss, die der aufrufende Code zugreifen kann.  
  
 Sie können eine `New` -Klausel in einer deklarationsanweisung oder eine zuweisungsanweisung. Wenn die Anweisung ausgeführt wird, ruft es den entsprechenden Konstruktor der angegebenen Klasse, und übergeben von Argumenten, die Sie angegeben haben. Das folgende Beispiel zeigt dies durch Erstellen von Instanzen von einem `Customer` Klasse, die zwei Konstruktoren aufweist, eine, die keine Parameter akzeptiert und eine, die einen Zeichenfolgenparameter annimmt.  
  
 [!code-vb[VbVbalrKeywords#11](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_1.vb)]  
  
 Da Arrays Klassen sind `New` können eine neue Arrayinstanz erstellen, wie in den folgenden Beispielen gezeigt.  
  
 [!code-vb[VbVbalrKeywords#12](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_2.vb)]  
  
 Löst die common Language Runtime (CLR) eine <xref:System.OutOfMemoryException> Fehlermeldung, wenn nicht genügend zum Erstellen der neuen Instanz Arbeitsspeicher.  
  
> [!NOTE]
>  Die `New` -Schlüsselwort wird auch in Typparameterlisten verwendet, um anzugeben, dass der angegebene Typ einen zugänglichen parameterlosen Konstruktor verfügbar machen muss. Weitere Informationen über Typparameter und Einschränkungen finden Sie unter [Typliste](../../../visual-basic/language-reference/statements/type-list.md).  
  
 Um eine Konstruktorprozedur für eine Klasse zu erstellen, legen Sie den Namen des eine `Sub` Vorgehensweise der `New` Schlüsselwort. Weitere Informationen finden Sie unter [Objektlebensdauer: wie Objekte erstellen und zerstören sind](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
 Das `New`-Schlüsselwort kann in den folgenden Kontexten verwendet werden:  
  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.OutOfMemoryException>  
 [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)  
 [Typliste](../../../visual-basic/language-reference/statements/type-list.md)  
 [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Objektlebensdauer: Erstellen und Zerstören von Objekten](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
