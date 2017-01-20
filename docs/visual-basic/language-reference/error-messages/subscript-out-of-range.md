---
title: "Subscript out of range (Visual Basic) | Microsoft Docs"
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
  - "vbrID9"
dev_langs: 
  - "VB"
ms.assetid: d0344a65-ec02-4caf-8d3c-9977392ca353
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Subscript out of range (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Ein Arrayfeldindex ist ungültig, weil er außerhalb des zulässigen Bereichs liegt.  Der niedrigste Indexwert für eine Dimension beträgt immer 0, während der höchste Indexwert für eine Dimension durch die `GetUpperBound`\-Methode zurückgegeben wird.  
  
### So beheben Sie diesen Fehler  
  
-   Ändern Sie den Index so, dass er innerhalb des gültigen Bereichs liegt.  
  
## Siehe auch  
 <xref:System.Array.GetUpperBound%2A?displayProperty=fullName>   
 [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)