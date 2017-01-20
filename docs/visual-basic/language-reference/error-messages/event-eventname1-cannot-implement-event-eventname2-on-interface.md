---
title: "Event &#39;&lt;eventname1&gt;&#39; cannot implement event &#39;&lt;eventname2&gt;&#39; on interface &#39;&lt;interface&gt;&#39; because their delegate types &#39;&lt;delegate1&gt;&#39; and &#39;&lt;delegate2&gt;&#39; do not match | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31423"
  - "bc31423"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31423"
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Event &#39;&lt;eventname1&gt;&#39; cannot implement event &#39;&lt;eventname2&gt;&#39; on interface &#39;&lt;interface&gt;&#39; because their delegate types &#39;&lt;delegate1&gt;&#39; and &#39;&lt;delegate2&gt;&#39; do not match
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] kann ein Ereignis nicht implementieren, weil der Delegattyp des Ereignisses nicht mit dem Delegattyp des Ereignisses in der Schnittstelle übereinstimmt.  Dieser Fehler kann auftreten, wenn Sie mehrere Ereignisse in einer Schnittstelle definieren und anschließend versuchen, sie mit demselben Ereignis zu implementieren.  Ein Ereignis kann zwei oder mehrere Ereignisse nur implementieren, wenn alle implementierten Ereignisse mithilfe der `As`\-Syntax deklariert werden und den gleichen Delegattyp angeben.  
  
 **Fehler\-ID:** BC31423  
  
### So beheben Sie diesen Fehler  
  
-   Implementieren Sie die Ereignisse separat.  
  
     \- oder \-  
  
-   Definieren Sie die Ereignisse in der Schnittstelle mithilfe der `As`\-Syntax, und geben Sie den gleichen Delegattyp an.  
  
## Siehe auch  
 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Events](../../../visual-basic/programming-guide/language-features/events/events.md)