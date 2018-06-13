---
title: 'Gewusst wie: Erstellen einer Auflistung für einen Auflistungsinitialisierer (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: 6158b6f02d95260e2955e77d732fae8b8d9d5e04
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654160"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a>Gewusst wie: Erstellen einer Auflistung für einen Auflistungsinitialisierer (Visual Basic)
Wenn Sie einen Auflistungsinitialisierer verwenden, um eine Sammlung erstellen, sucht Visual Basic-Compiler für eine `Add` Methode des Auflistungstyps, für die die Parameter für die `Add` Methode überein, die die Typen der Werte im Auflistungsinitialisierer. Dies `Add` Methode beim Auffüllen der Auflistung mit den Werten aus den Auflistungsinitialisierer verwendet wird.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine `OrderCollection` Sammlung mit einem öffentlichen `Add` Methode, mit der ein Auflistungsinitialisierer zum Hinzufügen von Objekten des Typs `Order`. Die `Add` Methode können Sie die gekürzte Auflistungsinitialisierersyntax zu verwenden.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_3.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_4.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Auflistungsinitialisierer](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 [Gewusst wie: Erstellen einer Add-Erweiterungsmethode für einen Auflistungsinitialisierer](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
