---
title: "Continue Statement (Visual Basic) | Microsoft Docs"
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
  - "vb.continue"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Continue statement [Visual Basic]"
  - "loops, transferring to next iteration"
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Continue Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Überträgt die Steuerung direkt an die nächste Iteration einer Schleife  
  
## Syntax  
  
```  
Continue { Do | For | While }  
```  
  
## Hinweise  
 Sie können die Steuerung aus einer `Do`\-Schleife, einer `For`\-Schleife oder einer `While`\-Schleife an die nächste Iteration der jeweiligen Schleife übertragen.  Die Steuerung wird direkt an den Test der Schleifenbedingung übergeben. Dies entspricht dem Übertragen der Steuerung an die `For`\-Anweisung oder die `While`\-Anweisung bzw. die `Do`\-Anweisung oder die `Loop`\-Anweisung, die die `Until`\-Klausel bzw. die `While`\-Klausel enthält.  
  
 Sie können `Continue` an einer beliebigen Position in der Schleife verwenden, die das Übertragen der Steuerung zulässt.  Die Regeln, die das Übertragen der Steuerung zulassen, entsprechen den Regeln für die [GoTo Statement](../../../visual-basic/language-reference/statements/goto-statement.md).  
  
 Wenn sich beispielsweise eine Schleife vollständig in einem `Try`\-Block, einem `Catch`\-Block oder einem `Finally`\-Block befindet, können Sie mit `Continue` die Steuerung aus der Schleife übertragen.  Wenn sich hingegen die `Try`...`End Try`\-Struktur in der Schleife befindet, können Sie nicht mit `Continue` die Steuerung aus dem `Finally`\-Block übertragen, und Sie können mit dieser Anweisung die Steuerung nur aus einem `Try`\-Block oder einem `Catch`\-Block übertragen, wenn die Steuerung vollständig aus der `Try`...`End Try`\-Struktur übertragen wird.  
  
 Bei geschachtelten Schleifen desselben Typs, z. B. einer `Do`\-Schleife in einer weiteren `Do`\-Schleife, springt eine `Continue Do`\-Anweisung zur nächsten Iteration der innersten `Do`\-Schleife, die sie enthält.  Sie können nicht mit `Continue` zur nächsten Iteration einer enthaltenden Schleife desselben Typs springen.  
  
 Bei geschachtelten Schleifen von unterschiedlichem Typ, z. B. einer `Do`\-Schleife in einer `For`\-Schleife, können Sie mit `Continue Do` bzw. `Continue For` zur nächsten Iteration einer der beiden Schleifen springen.  
  
## Beispiel  
 Im folgenden Codebeispiel wird die `Continue While`\-Anweisung verwendet, um zur nächsten Spalte eines Arrays zu springen, wenn ein Divisor 0 \(null\) ist.  `Continue While` befindet sich in einer `For`\-Schleife.  Die Steuerung wird an die `While col < lastcol`\-Anweisung übertragen, bei der es sich um die nächste Iteration der innersten `While`\-Schleife handelt, die die `For`\-Schleife enthält.  
  
 [!code-vb[VbVbalrStatements#14](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/continue-statement_1.vb)]  
  
## Siehe auch  
 [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [For...Next\-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md)   
 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)