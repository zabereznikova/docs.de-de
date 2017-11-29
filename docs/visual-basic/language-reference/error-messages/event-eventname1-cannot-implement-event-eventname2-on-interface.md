---
title: "Ereignis &#39; &lt;ereignisname1&gt;&#39; kann nicht implementieren, Ereignis &#39;&lt; ereignisname2&gt;&#39; Schnittstelle &#39;&lt; Schnittstelle&gt;&#39; da ihre Delegattypen &#39;&lt; Delegate1&gt;&#39; und &#39;&lt; delegate2&gt;&#39; stimmen nicht überein"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords: BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b0fcbbf8a6e23270e4dcbf9d813c773e1522a92a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="event-39lteventname1gt39-cannot-implement-event-39lteventname2gt39-on-interface-39ltinterfacegt39-because-their-delegate-types-39ltdelegate1gt39-and-39ltdelegate2gt39-do-not-match"></a>Ereignis &#39; &lt;ereignisname1&gt;&#39; kann nicht implementieren, Ereignis &#39;&lt; ereignisname2&gt;&#39; Schnittstelle &#39;&lt; Schnittstelle&gt;&#39; da ihre Delegattypen &#39;&lt; Delegate1&gt;&#39; und &#39;&lt; delegate2&gt;&#39; stimmen nicht überein
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]kann ein Ereignis nicht implementieren, da der Delegattyp des Ereignisses nicht den Delegattyp des Ereignisses in der Schnittstelle entspricht. Dieser Fehler kann auftreten, wenn Sie mehrere Ereignisse in einer Schnittstelle definieren und anschließend versuchen, sie mit demselben Ereignis zu implementieren. Ein Ereignis kann zwei oder mehrere Ereignisse nur implementieren, wenn alle implementierten Ereignisse mit der `As` -Syntax deklariert werden und denselben Delegattyp angeben.  
  
 **Fehler-ID:** BC31423  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Implementieren Sie die Ereignisse separat.  
  
     – oder –  
  
-   Definieren Sie die Ereignisse in der Schnittstelle mithilfe der `As` Syntax und den gleichen Delegattyp angeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)
