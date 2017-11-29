---
title: "Gewusst wie: Erstellen einer Add-Erweiterungsmethode für einen Auflistungsinitialisierer (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d19ac8b03b992eb9b09b5cb45fdcceadad3a822a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a>Gewusst wie: Erstellen einer Add-Erweiterungsmethode für einen Auflistungsinitialisierer (Visual Basic)
Wenn Sie einen Auflistungsinitialisierer verwenden, um eine Sammlung erstellen, sucht Visual Basic-Compiler für eine `Add` Methode des Auflistungstyps, für die die Parameter für die `Add` Methode überein, die die Typen der Werte im Auflistungsinitialisierer. Dies `Add` Methode beim Auffüllen der Auflistung mit den Werten aus den Auflistungsinitialisierer verwendet wird.  
  
 Wenn kein übereinstimmender `Add` Methode vorhanden ist und den Code für die Sammlung kann nicht geändert, können Sie eine Erweiterungsmethode namens hinzufügen `Add` , akzeptiert der Parameter, die für den Auflistungsinitialisierer erforderlich sind. Dies ist in der Regel an, was Sie tun, wenn Sie Auflistungsinitialisierer für generische Auflistungen verwenden müssen.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie die generische Erweiterungsmethode hinzuzufügende <xref:System.Collections.Generic.List%601> geben, sodass ein Auflistungsinitialisierer verwendet werden kann, um Objekte eines Typs hinzuzufügen `Employee`. Die Erweiterungsmethode können Sie die gekürzte Auflistungsinitialisierersyntax zu verwenden.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_3.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Auflistungsinitialisierer](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 [Gewusst wie: Erstellen einer Auflistung für einen Auflistungsinitialisierer](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
