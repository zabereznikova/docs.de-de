---
title: "Let Clause (Visual Basic) | Microsoft Docs"
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
  - "vb.QueryLet"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "queries [Visual Basic], Let"
  - "Let clause"
  - "Let statement"
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Let Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Berechnet einen Wert und weist ihn einer neuen Variable in der Abfrage zu.  
  
## Syntax  
  
```  
Let variable = expression [, ...]  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`variable`|Erforderlich.  Ein Alias, der verwendet werden kann, um auf die Ergebnisse des angegebenen Ausdrucks zu verweisen.|  
|`expression`|Erforderlich.  Ein Ausdruck, der ausgewertet und der angegebenen Variable zugewiesen wird.|  
  
## Hinweise  
 Durch die `Let`\-Klausel können Werte für jedes Abfrageergebnis berechnet werden. Außerdem kann auf diese durch einen Alias verwiesen werden.  Der Alias kann in anderen Klauseln verwendet werden, z. B. in der `Where`\-Klausel.  Durch die `Let`\-Klausel kann eine Abfrageanweisung erstellt werden, die einfacher zu lesen ist, da ein Alias für die Ausdrucksklausel angegeben werden kann, die in die Abfrage aufgenommen wird. Der Alias kann jedes Mal ersetzt werden, wenn die Ausdrucksklausel verwendet wird.  
  
 Sie können beliebig viele `variable`\-Zuweisungen und `expression`\-Zuweisungen in die `Let`\-Klausel aufnehmen.  Trennen Sie jede Zuweisung durch ein Komma \(,\) ab.  
  
## Beispiel  
 Im folgenden Codebeispiel wird die `Let`\-Klausel verwendet, um 10 Prozent Rabatt auf die Produkte zu berechnen.  
  
 [!code-vb[VbSimpleQuerySamples#16](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/VbSimpleQuerySamples/QuerySamples1.vb#16)]  
  
## Siehe auch  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Where Clause](../../../visual-basic/language-reference/queries/where-clause.md)