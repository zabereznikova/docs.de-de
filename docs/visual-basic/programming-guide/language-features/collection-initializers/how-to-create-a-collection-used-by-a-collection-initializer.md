---
title: "How to: Create a Collection Used by a Collection Initializer (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "collection initializers [Visual Basic]"
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Create a Collection Used by a Collection Initializer (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Wenn Sie eine Auflistung mithilfe eines Auflistungsinitialisierers erstellen, sucht der Visual Basic\-Compiler nach einer `Add`\-Methode des Auflistungstyps, für den die Parameter der `Add`\-Methode mit den Typen der Werte im Auflistungsinitialisierer übereinstimmen.  Diese `Add`\-Methode wird verwendet, um die Auflistung mit den Werten des Auflistungsinitialisierers aufzufüllen.  
  
## Beispiel  
 Im folgenden Beispiel wird eine `OrderCollection`\-Auflistung gezeigt, die eine öffentliche `Add`\-Methode enthält, die ein Auflistungsinitialisierer verwenden kann, um Objekte des Typs `Order` hinzuzufügen.  Die `Add`\-Methode ermöglicht es Ihnen, die gekürzte Auflistungsinitialisierersyntax zu verwenden.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-_3.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-_4.vb)]  
  
## Siehe auch  
 [Collection Initializers](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)   
 [How to: Create an Add Extension Method Used by a Collection Initializer](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)