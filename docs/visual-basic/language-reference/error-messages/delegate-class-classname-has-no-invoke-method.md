---
title: Delegatklasse &#39; &lt;Classname&gt;&#39; hat Sie keine Invoke-Methode, damit ein Ausdruck dieses Typs kann nicht das Ziel eines Methodenaufrufs sein.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 55d0e2442807e25737d90ac4b45a59b9d3e73037
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>Delegatklasse &#39; &lt;Classname&gt;&#39; hat Sie keine Invoke-Methode, damit ein Ausdruck dieses Typs kann nicht das Ziel eines Methodenaufrufs sein.
Ein Aufruf von `Invoke` über einen Delegaten ist fehlgeschlagen, da `Invoke` nicht auf die Delegate-Klasse implementiert wird.  
  
 **Fehler-ID:** BC30220  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass eine Instanz der Delegatklasse mit erstellt wurde eine `Dim` -Anweisung und die Delegatinstanz mit eine Prozedur zugewiesen wurde die `AddressOf` Operator.  
  
2.  Suchen Sie den Code, der die Delegate-Klasse implementiert, und stellen Sie sicher, dass es implementiert die `Invoke` Prozedur.  
  
## <a name="see-also"></a>Siehe auch  
 [Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)
