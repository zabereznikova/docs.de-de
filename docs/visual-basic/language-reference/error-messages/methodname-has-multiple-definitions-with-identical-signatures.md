---
title: "&#39;&lt;methodname&gt;&#39; has multiple definitions with identical signatures | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30269"
  - "bc30269"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30269"
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# &#39;&lt;methodname&gt;&#39; has multiple definitions with identical signatures
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Eine `Function`\- oder `Sub`\-Prozedurdeklaration verwendet den gleichen Prozedurnamen und die gleiche Argumentliste wie eine vorherige Deklaration.  Eine mögliche Ursache ist der Versuch, die Originalprozedur zu überladen.  Überladene Prozeduren müssen unterschiedliche Argumentlisten haben.  
  
 **Fehler\-ID:** BC30269  
  
### So beheben Sie diesen Fehler  
  
-   Ändern Sie den Prozedurnamen oder die Argumentliste, oder entfernen Sie die doppelte Deklaration.  
  
## Siehe auch  
 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Considerations in Overloading Procedures](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)