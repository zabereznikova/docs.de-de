---
title: Delegatklasse&lt;Classname&gt;&quot; hat keine Invoke-Methode ein Ausdruck dieses Typs das Ziel eines Methodenaufrufs | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30220
- bc30220
dev_langs:
- VB
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ddc5ef0f0b3e9baa58f17dafb727e250c0fba9fd
ms.lasthandoff: 03/13/2017

---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>Delegatklasse&lt;Classname&gt;' hat keine Invoke-Methode ein Ausdruck dieses Typs das Ziel eines Methodenaufrufs
Ein Aufruf von `Invoke` über einen Delegaten ist fehlgeschlagen, da `Invoke` nicht in der Delegatklasse implementiert ist.  
  
 **Fehler-ID:** BC30220  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass eine Instanz der Delegatklasse mit erstellt wurde eine `Dim` -Anweisung, und dass eine Prozedur der Delegatinstanz mit zugewiesen wurde die `AddressOf` Operator.  
  
2.  Suchen Sie den Code, der die Delegatklasse implementiert, und stellen Sie sicher, dass er implementiert die `Invoke` Verfahren.  
  
## <a name="see-also"></a>Siehe auch  
 [Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)
