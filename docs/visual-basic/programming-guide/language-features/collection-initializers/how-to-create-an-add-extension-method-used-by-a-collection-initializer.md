---
title: 'Gewusst wie: Erstellen einer Add-Erweiterungsmethode für einen Auflistungsinitialisierer'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: 6d5f9d38b413b79f111a14ec3829c57a9797ce54
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346715"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a>Gewusst wie: Erstellen einer Add-Erweiterungsmethode für einen Auflistungsinitialisierer (Visual Basic)
Wenn Sie einen Auflistungsinitialisierer zum Erstellen einer Auflistung verwenden, sucht der Visual Basic Compiler nach einer `Add` Methode des Auflistungs Typs, für den die Parameter für die `Add`-Methode mit den Typen der Werte im Auflistungsinitialisierer identisch sind. Diese `Add` Methode wird verwendet, um die Auflistung mit den Werten aus dem Auflistungsinitialisierer aufzufüllen.  
  
 Wenn keine übereinstimmende `Add` Methode vorhanden ist und Sie den Code für die Auflistung nicht ändern können, können Sie eine Erweiterungsmethode mit dem Namen `Add` hinzufügen, die die für den Auflistungsinitialisierer erforderlichen Parameter annimmt. Dies ist in der Regel erforderlich, wenn Sie sammlungsinitialisierer für generische Auflistungen verwenden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie eine Erweiterungsmethode dem generischen <xref:System.Collections.Generic.List%601>-Typ hinzugefügt wird, sodass ein Auflistungsinitialisierer zum Hinzufügen von Objekten des Typs `Employee`verwendet werden kann. Die Erweiterungsmethode ermöglicht Ihnen die Verwendung der gekürzten sammlungsinitialisierersyntax.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a>Siehe auch

- [Auflistungsinitialisierer](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Gewusst wie: Erstellen einer Auflistung für einen Auflistungsinitialisierer](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
