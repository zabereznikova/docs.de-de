---
title: "&#39;&lt;name1&gt;&#39; is ambiguous, imported from the namespaces or types &#39;&lt;name2&gt;&#39; | Microsoft Docs"
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
  - "vbc30561"
  - "bc30561"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30561"
ms.assetid: 761091f7-1018-4299-b481-3966a4a2c126
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;name1&gt;&#39; is ambiguous, imported from the namespaces or types &#39;&lt;name2&gt;&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Sie haben einen Namen angegeben, der mehrdeutig ist und dadurch einen Konflikt mit einem anderen Namen verursacht.  Für den [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Compiler wurden keine Regeln zur Konfliktlösung implementiert, sodass Sie die Mehrdeutigkeit des Namens selbst auflösen müssen.  
  
 **Fehler\-ID:** BC30561  
  
### So beheben Sie diesen Fehler  
  
1.  Machen Sie den Namen eindeutig, indem Sie Namespaceimporte entfernen.  
  
2.  Kennzeichnen Sie den Namen vollständig.  
  
## Siehe auch  
 [Imports Statement \(.NET Namespace and Type\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md)