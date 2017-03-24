---
title: "&#39;Dir&#39; function must first be called with a &#39;PathName&#39; argument | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrDIR_IllegalCall"
dev_langs: 
  - "VB"
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# &#39;Dir&#39; function must first be called with a &#39;PathName&#39; argument
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Ein Erstaufruf der `Dir`\-Funktion enthält kein `PathName`\-Argument.  Der erste Aufruf von `Dir` muss `PathName` enthalten. Bei allen folgenden Aufrufen von `Dir` wird das nächste Element auch ohne Parameter abgerufen.  
  
### So beheben Sie diesen Fehler  
  
1.  Geben Sie bei diesem Funktionsaufruf ein `PathName`\-Argument an.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>