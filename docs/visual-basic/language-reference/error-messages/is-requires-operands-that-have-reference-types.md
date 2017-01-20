---
title: "&#39;Is&#39; requires operands that have reference types, but this operand has the value type &#39;&lt;typename&gt;&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30020"
  - "vbc30020"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30020"
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Is&#39; requires operands that have reference types, but this operand has the value type &#39;&lt;typename&gt;&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Der `Is`\-Vergleichsoperator bestimmt, ob zwei Objektvariablen auf dieselbe Instanz verweisen.  Diese Vergleichsmethode ist für Werttypen nicht definiert.  
  
 **Fehler\-ID:** BC30020  
  
### So beheben Sie diesen Fehler  
  
-   Verwenden Sie für den Vergleich von zwei Werttypen den geeigneten arithmetischen Vergleichsoperator oder den Operator `Like`.  
  
## Siehe auch  
 [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md)   
 [Like Operator](../../../visual-basic/language-reference/operators/like-operator.md)   
 [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md)