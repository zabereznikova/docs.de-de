---
title: "end of-Anweisung erwartet. | Microsoft Docs"
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
  - "bc30205"
  - "vbc30205"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30205"
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# end of-Anweisung erwartet.
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Die Anweisung ist syntaktisch vollständig. Jedoch folgt auf das Element, das die Anweisung abschließt, ein zusätzliches Programmierelement.  Ein Zeilenabschlusszeichen muss am Ende jeder Anweisung stehen.  
  
 Ein Zeilenabschlusszeichen teilt die Zeichen einer Visual Basic\-Quelldatei in Zeilen unter.  Beispiele für Zeilenabschlusszeichen sind das Unicode\-Wagenrücklaufzeichen \(&HD\), das Unicode\-Zeilenvorschubzeichen \(&HA\) und das Unicode\-Wagenrücklaufzeichen, das vom Unicode\-Zeilenvorschubzeichen folgen.  Weitere Informationen zu Zeilenabschlusszeichen, finden Sie unter [Visual Basic Language Specification](../../../visual-basic/reference/language-specification.md).  
  
 **Fehler\-ID:** BC30205  
  
### So beheben Sie diesen Fehler  
  
1.  Prüfen Sie, ob zwei unterschiedliche Anweisungen versehentlich in derselben Zeile stehen.  
  
2.  Fügen Sie nach dem Element, das die Anweisung abschließt, ein Zeilenabschlusszeichen ein.  
  
## Siehe auch  
 [Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)   
 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)