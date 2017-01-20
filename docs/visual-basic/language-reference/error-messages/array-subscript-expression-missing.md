---
title: "Array subscript expression missing | Microsoft Docs"
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
  - "bc30306"
  - "vbc30306"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30306"
ms.assetid: 3c0d9732-ee37-436f-a1df-29d65712f48a
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Array subscript expression missing
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

In einer Arrayinitialisierung fehlen ein Subscript oder mehrere Subscripts zur Definition der Arraygrenzen.  Zum Beispiel könnte die Anweisung den Ausdruck `myArray (5,5,,10)` enthalten, in dem das dritte Subscript fehlt.  
  
 **Fehler\-ID:** BC30306  
  
### So beheben Sie diesen Fehler  
  
-   Geben Sie das fehlende Subscript an.  
  
## Siehe auch  
 [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)