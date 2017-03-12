---
title: "&lt;type1&gt;&#39;&lt;typename&gt;&#39; must implement &#39;&lt;membername&gt;&#39; for interface &#39;&lt;interfacename&gt;&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30154"
  - "bc30154"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30154"
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# &lt;type1&gt;&#39;&lt;typename&gt;&#39; must implement &#39;&lt;membername&gt;&#39; for interface &#39;&lt;interfacename&gt;&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

"\<Typname\>" muss "\<Membername\>" für die "\<Schnittstellenname\>"\-Schnittstelle implementieren.Die implementierende Eigenschaft muss übereinstimmende ReadOnly\- oder WriteOnly\-Spezifizierer aufweisen.  
  
 Eine Klasse oder Struktur soll eine Schnittstelle implementieren. Dabei wird jedoch eine Prozedur, Eigenschaft oder ein Ereignis, die bzw. das von der Schnittstelle definiert wird, nicht implementiert.  Jeder Member der Schnittstelle muss implementiert werden.  
  
 **Fehler\-ID:** BC30154  
  
### So beheben Sie diesen Fehler  
  
1.  Deklarieren Sie einen Member mit demselben Namen und derselben Signatur wie in der Schnittstelle definiert.  Fügen Sie mindestens eine der Anweisungen `End Function`, `End Sub` oder `End Property` ein.  
  
2.  Fügen Sie am Ende der Anweisung `Function`, `Sub`, `Property` oder `Event` eine `Implements`\-Klausel an.  Beispiele:  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  Vergewissern Sie sich beim Implementieren einer Eigenschaft, dass `ReadOnly` oder `WriteOnly` wie in der Schnittstellendefinition verwendet wird.  
  
4.  Deklarieren Sie bei Bedarf beim Implementieren einer Eigenschaft die `Get`\-Prozedur bzw. die `Set`\-Prozedur.  
  
## Siehe auch  
 [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md)   
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)