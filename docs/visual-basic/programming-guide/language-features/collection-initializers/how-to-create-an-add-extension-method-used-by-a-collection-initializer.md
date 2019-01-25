---
title: 'Vorgehensweise: Erstellen einer Add-Erweiterungsmethode, die einen Auflistungsinitialisierer (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: 3a1db8ede8162b329d546c0e712ef1c2df7d7883
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661671"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a>Vorgehensweise: Erstellen einer Add-Erweiterungsmethode, die einen Auflistungsinitialisierer (Visual Basic)
Wenn Sie einen Auflistungsinitialisierer verwenden, um eine Sammlung erstellen, sucht Visual Basic-Compiler nach einer `Add` Methode des Auflistungstyps, für die die Parameter für die `Add` Methode entsprechen den Typen der Werte im Auflistungsinitialisierer. Dies `Add` Methode zum Auffüllen der Auflistung mit den Werten aus der Auflistungsinitialisierer verwendet wird.  
  
 Wenn kein übereinstimmendes `Add` Methode vorhanden ist und Sie können den Code für die Sammlung können nicht ändern, können Sie eine Erweiterungsmethode namens hinzufügen `Add` , akzeptiert die Parameter, die den Auflistungsinitialisierer erforderlich sind. Dies ist normalerweise das, was Sie tun, wenn Sie die Auflistungsinitialisierer für generische Auflistungen verwenden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie eine Erweiterungsmethode zu den allgemeinen hinzufügen <xref:System.Collections.Generic.List%601> geben, damit ein Auflistungsinitialisierer verwendet werden kann, zum Hinzufügen von Objekten des Typs `Employee`. Die Erweiterungsmethode können Sie die gekürzte Auflistungsinitialisierersyntax zu verwenden.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_3.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [Auflistungsinitialisierer](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Vorgehensweise: Erstellen Sie von einem Auflistungsinitialisierer verwendete Auflistung](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
