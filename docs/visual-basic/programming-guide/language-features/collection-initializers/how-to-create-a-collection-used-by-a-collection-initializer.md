---
title: 'Vorgehensweise: Erstellen einer Auflistung für einen Auflistungsinitialisierer (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: aaa367e5a1739f26e9b0458d8f2fc44462b73b7b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631723"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a>Vorgehensweise: Erstellen einer Auflistung für einen Auflistungsinitialisierer (Visual Basic)
Wenn Sie einen Auflistungsinitialisierer verwenden, um eine Sammlung erstellen, sucht Visual Basic-Compiler nach einer `Add` Methode des Auflistungstyps, für die die Parameter für die `Add` Methode entsprechen den Typen der Werte im Auflistungsinitialisierer. Dies `Add` Methode zum Auffüllen der Auflistung mit den Werten aus der Auflistungsinitialisierer verwendet wird.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine `OrderCollection` Sammlung mit einem öffentlichen `Add` -Methode, die einen Auflistungsinitialisierer, zum Hinzufügen von Objekten des Typs verwenden kann `Order`. Die `Add` Methode können Sie die gekürzte Auflistungsinitialisierersyntax zu verwenden.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_3.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_4.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [Auflistungsinitialisierer](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Vorgehensweise: Erstellen einer Add-Erweiterungsmethode, die von einem Auflistungsinitialisierer verwendet](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
