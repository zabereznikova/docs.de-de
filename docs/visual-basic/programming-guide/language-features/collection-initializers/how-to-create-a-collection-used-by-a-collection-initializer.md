---
title: 'Vorgehensweise: Erstellen einer Auflistung für einen Auflistungsinitialisierer'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: 7cba290b92f41125a93d1ed022e4db5ef62da789
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414555"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a>Gewusst wie: Erstellen einer Auflistung für einen Auflistungsinitialisierer (Visual Basic)
Wenn Sie einen Auflistungsinitialisierer zum Erstellen einer Auflistung verwenden, sucht der Visual Basic Compiler nach einer Methode des Auflistungs `Add` Typs, für den die Parameter für die `Add` Methode mit den Typen der Werte im sammlungsinitialisierer verglichen werden. Diese `Add` Methode wird verwendet, um die Auflistung mit den Werten aus dem Auflistungsinitialisierer aufzufüllen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine-Auflistung `OrderCollection` , die eine öffentliche `Add` Methode enthält, die ein Auflistungsinitialisierer zum Hinzufügen von Objekten des Typs verwenden kann `Order` . Mit der- `Add` Methode können Sie die gekürzte sammlungsinitialisierersyntax verwenden.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#4)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#3)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Sammlungsinitialisierer](index.md)
- [Vorgehensweise: Erstellen einer Add-Erweiterungsmethode für einen Auflistungsinitialisierer](how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
