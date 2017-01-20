---
title: "Type &#39;&lt;typename&gt;&#39; has no constructors | Microsoft Docs"
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
  - "bc30251"
  - "vbc30251"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30251"
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Type &#39;&lt;typename&gt;&#39; has no constructors
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Ein Typ unterstützt nicht den Aufruf von `Sub New()`.  Eine mögliche Ursache ist ein beschädigter Compiler oder eine fehlerhafte Binärdatei.  
  
 **Fehler\-ID:** BC30251  
  
### So beheben Sie diesen Fehler  
  
1.  Wenn sich der Typ in einem anderen Projekt oder in einer referenzierten Datei befindet, installieren Sie das Projekt oder die Datei erneut.  
  
2.  Wenn sich der Typ im gleichen Projekt befindet, kompilieren Sie die Assembly mit dem Typ neu.  
  
3.  Wenn der Fehler erneut auftritt, installieren Sie den [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Compiler neu.  
  
4.  Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.  
  
## Siehe auch  
 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Sprechen Sie mit uns](/visual-studio/ide/talk-to-us)