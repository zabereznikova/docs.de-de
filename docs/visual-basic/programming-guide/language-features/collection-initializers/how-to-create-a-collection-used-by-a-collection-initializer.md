---
title: 'Gewusst wie: Erstellen einer Auflistung für einen Auflistungsinitialisierer'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: 5eaf9e828455bf2accda86ab52a1ce645f10b9ee
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349051"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a>Gewusst wie: Erstellen einer Auflistung für einen Auflistungsinitialisierer (Visual Basic)
Wenn Sie einen Auflistungsinitialisierer zum Erstellen einer Auflistung verwenden, sucht der Visual Basic Compiler nach einer `Add` Methode des Auflistungs Typs, für den die Parameter für die `Add`-Methode mit den Typen der Werte im Auflistungsinitialisierer identisch sind. Diese `Add` Methode wird verwendet, um die Auflistung mit den Werten aus dem Auflistungsinitialisierer aufzufüllen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine `OrderCollection` Auflistung, die eine öffentliche `Add` Methode enthält, die ein Auflistungsinitialisierer zum Hinzufügen von Objekten des Typs `Order`verwenden kann. Die `Add`-Methode ermöglicht es Ihnen, die gekürzte sammlungsinitialisierersyntax zu verwenden.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#4)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#3)]  
  
## <a name="see-also"></a>Siehe auch

- [Auflistungsinitialisierer](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Gewusst wie: Erstellen einer Add-Erweiterungsmethode für einen Auflistungsinitialisierer](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
