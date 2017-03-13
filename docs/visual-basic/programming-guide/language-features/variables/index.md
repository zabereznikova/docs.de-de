---
title: "Variables in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "variables [Visual Basic]"
  - "values [Visual Basic], storing"
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# Variables in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Beim Ausführen von Berechnungen mit [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] müssen häufig Werte gespeichert werden.  Dies ist beispielsweise der Fall, wenn Sie verschiedene Werte berechnen und vergleichen möchten, um dann, in Abhängigkeit von den Ergebnissen des Vergleichs, unterschiedliche Vorgänge mit ihnen auszuführen.  Sie müssen die Werte beibehalten, wenn Sie diese vergleichen möchten.  
  
## Verwendung  
 Wie bei den meisten Programmiersprachen werden in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] Werte mithilfe von Variablen gespeichert.  Eine *Variable* besitzt einen Namen \(die von Ihnen verwendete Bezeichnung für den mithilfe der Variablen gespeicherten Wert\).  Eine Variable weist außerdem einen Datentyp aus \(dieser legt die Daten fest, die in der Variablen gespeichert werden können\).  Eine Variable kann ein Array darstellen, wenn ein indizierter Satz verwandter Datenelemente in ihr gespeichert werden soll.  
  
 Mit lokaler Typableitung können Sie Variablen ohne explizite Angabe eines Datentyps deklarieren.  Stattdessen leitet der Compiler den Typ der Variable vom Typ des Initialisierungsausdrucks ab.  Weitere Informationen finden Sie unter [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) und [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
## Zuweisen von Werten  
 Mit Zuweisungsanweisungen führen Sie Berechnungen durch und weisen das Ergebnis einer Variablen zu, wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbalrVariables#1](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/index_1.vb)]  
  
> [!NOTE]
>  Das Gleichheitszeichen \(`=`\) entspricht in diesem Beispiel einem Zuweisungsoperator, nicht einem Gleichheitsoperator.  Der Wert wird der Variablen `applesSold` zugewiesen.  
  
 Weitere Informationen finden Sie unter [How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md).  
  
## Variablen und Eigenschaften  
 , wenn das Element zur Auflistung gehört, andernfalls .  Sie ist jedoch komplexer als eine Variable.  Eine Eigenschaft verwendet Codeblöcke, die steuern, wie der Wert der Eigenschaft festgelegt und abgerufen wird.  Weitere Informationen finden Sie unter [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).  
  
## Siehe auch  
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Problembehandlung bei Variablen](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)   
 [How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)   
 [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)