---
title: "Type arguments could not be inferred from the delegate | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc36564"
  - "vbc36564"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36564"
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 5
---
# Type arguments could not be inferred from the delegate
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Eine Zuweisungsanweisung verwendet `AddressOf` zum Zuweisen der Adresse einer generischen Prozedur an einen Delegaten, stellt jedoch keine Typargumente für die generische Prozedur bereit.  
  
 Wenn Sie einen generischen Typ aufrufen, geben Sie i. d. R. für jeden Typparameter, der durch den generischen Typ definiert wird, ein Typargument an.  Wenn Sie keine Typargumente angeben, versucht der Compiler, die an die Typparameter zu übergebenden Typen abzuleiten.  Wenn der Kontext nicht genügend Informationen zum Ableiten der Typen durch den Compiler bietet, wird ein Fehler generiert.  
  
 **Fehler\-ID:** BC36564  
  
### So beheben Sie diesen Fehler  
  
-   Geben Sie die Typargumente für die generische Prozedur im `AddressOf`\-Ausdruck an.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Generic Procedures in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)   
 [Type List](../../../visual-basic/language-reference/statements/type-list.md)   
 [Erweiterungsmethoden](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)