---
title: "Take While Clause (Visual Basic) | Microsoft Docs"
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
  - "vb.QueryTakeWhile"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "queries [Visual Basic], Take While"
  - "Take While clause"
  - "Take While statement"
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Take While Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt Elemente in einer Auflistung zurück, solange eine angegebene Bedingung `true` ist, und überspringt dann die übrigen Elemente.  
  
## Syntax  
  
```  
Take While expression  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`expression`|Erforderlich.  Ein Ausdruck, der eine Bedingung darstellt, auf die Elemente getestet werden sollen.  Der Ausdruck muss einen `Boolean`\-Wert oder eine funktionale Entsprechung wie beispielsweise einen `Integer`\-Wert zurückgeben, um als `Boolean` ausgewertet zu werden.|  
  
## Hinweise  
 Mit der `Take While`\-Klausel werden Elemente vom Anfang eines Abfrageergebnisses bis zu der Stelle eingeschlossen, an der der vorgegebene `expression` den Wert `false` zurückgibt.  Sobald von `expression` der Wert `false` zurückgegeben wird, werden alle übrigen Elemente von der Abfrage nicht mehr berücksichtigt.  Für die übrigen Ergebnisse wird `expression` ignoriert.  
  
 Die `Take While`\-Klausel unterscheidet sich von der `Where`\-Klausel insofern, als mit der `Where`\-Klausel alle Elemente einer Abfrage, die eine bestimmte Bedingung erfüllen, eingeschlossen werden können.  Mit der `Take While`\-Klausel werden Elemente nur so lange eingeschlossen, bis die Bedingung zum ersten Mal nicht erfüllt wird.  Die `Take While`\-Klausel ist besonders hilfreich, wenn Sie mit einem sortierten Abfrageergebnis arbeiten.  
  
## Beispiel  
 Im folgenden Codebeispiel werden mit der `Take While`\-Klausel Ergebnisse abgerufen, bis der erste Kunde ohne Bestellungen gefunden wird.  
  
 [!code-vb[VbSimpleQuerySamples#2](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/VbSimpleQuerySamples/QuerySamples1.vb#2)]  
  
## Siehe auch  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Take Clause](../../../visual-basic/language-reference/queries/take-clause.md)   
 [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md)   
 [Where Clause](../../../visual-basic/language-reference/queries/where-clause.md)