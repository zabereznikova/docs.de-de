---
title: 'Vorgehensweise: Erstellen einer Add-Erweiterungsmethode für einen Auflistungsinitialisierer'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: 4dbe6146b70181864a6717146071f9b93a1f583e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414568"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a>Gewusst wie: Erstellen einer Add-Erweiterungsmethode für einen Auflistungsinitialisierer (Visual Basic)
Wenn Sie einen Auflistungsinitialisierer zum Erstellen einer Auflistung verwenden, sucht der Visual Basic Compiler nach einer Methode des Auflistungs `Add` Typs, für den die Parameter für die `Add` Methode mit den Typen der Werte im sammlungsinitialisierer verglichen werden. Diese `Add` Methode wird verwendet, um die Auflistung mit den Werten aus dem Auflistungsinitialisierer aufzufüllen.  
  
 Wenn keine übereinstimmende `Add` Methode vorhanden ist und Sie den Code für die Auflistung nicht ändern können, können Sie eine Erweiterungsmethode mit dem Namen hinzufügen, die `Add` die für den Auflistungsinitialisierer erforderlichen Parameter annimmt. Dies ist in der Regel erforderlich, wenn Sie sammlungsinitialisierer für generische Auflistungen verwenden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie dem generischen Typ eine Erweiterungsmethode hinzugefügt <xref:System.Collections.Generic.List%601> wird, sodass ein Auflistungsinitialisierer zum Hinzufügen von Objekten des Typs verwendet werden kann `Employee` . Die Erweiterungsmethode ermöglicht Ihnen die Verwendung der gekürzten sammlungsinitialisierersyntax.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Sammlungsinitialisierer](index.md)
- [Vorgehensweise: Erstellen einer Auflistung für einen Auflistungsinitialisierer](how-to-create-a-collection-used-by-a-collection-initializer.md)
