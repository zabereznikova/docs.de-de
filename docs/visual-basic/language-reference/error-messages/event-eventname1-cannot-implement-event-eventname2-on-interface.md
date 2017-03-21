---
title: "Ereignis &quot;&lt;eventname1&gt;&quot;kann nicht implementieren Ereignis&quot;&lt;eventname2&gt;&quot;auf der Schnittstelle&quot;&lt;Schnittstelle&gt;&quot; da ihre Delegattypen&lt;delegate1&gt;&quot;und&quot;&lt;delegate2&gt;&quot; stimmen nicht überein | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31423
- bc31423
dev_langs:
- VB
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
caps.latest.revision: 6
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: b6253b3e9ad07c3715c55a8cfd0891792b45a452
ms.lasthandoff: 03/13/2017

---
# <a name="event-39lteventname1gt39-cannot-implement-event-39lteventname2gt39-on-interface-39ltinterfacegt39-because-their-delegate-types-39ltdelegate1gt39-and-39ltdelegate2gt39-do-not-match"></a>Ereignis "&lt;eventname1&gt;"kann nicht implementieren Ereignis"&lt;eventname2&gt;"auf der Schnittstelle"&lt;Schnittstelle&gt;' da ihre Delegattypen&lt;delegate1&gt;"und"&lt;delegate2&gt;' stimmen nicht überein
[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]kann ein Ereignis nicht implementieren, da der Delegattyp des Ereignisses nicht dem Typ des Ereignisses in der Schnittstelle des Delegaten übereinstimmt. Dieser Fehler kann auftreten, wenn Sie mehrere Ereignisse in einer Schnittstelle definieren und anschließend versuchen, sie mit demselben Ereignis zu implementieren. Ein Ereignis kann zwei oder mehrere Ereignisse nur implementieren, wenn alle implementierten Ereignisse mit der `As` -Syntax deklariert werden und denselben Delegattyp angeben.  
  
 **Fehler-ID:** BC31423  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Implementieren Sie die Ereignisse separat.  
  
     – oder –  
  
-   Definieren Sie die Ereignisse in der Schnittstelle mithilfe der `As` Syntax und den gleichen Delegattyp angeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)
