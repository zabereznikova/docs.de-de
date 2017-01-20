---
title: "#If...Then...#Else Directives | Microsoft Docs"
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
  - "vb.#EndIf"
  - "#End If"
  - "#Then"
  - "#ElseIf"
  - "vb.#ElseIf"
  - "vb.#Else"
  - "vb.#If"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic code, compiling"
  - "#If directive [Visual Basic]"
  - "conditional compilation, directives"
  - "#End if directive [Visual Basic]"
  - "selective compiling"
  - "else directive (#else)"
  - "#Else directive [Visual Basic]"
ms.assetid: 10bba104-e3fd-451b-b672-faa472530502
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# #If...Then...#Else Directives
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Kompiliert ausgewählte Blöcke von Visual Basic\-Code, wenn bestimmte Bedingungen erfüllt sind.  
  
## Syntax  
  
```  
#If expression Then  
   statements  
[ #ElseIf expression Then  
   [ statements ]  
...  
#ElseIf expression Then  
   [ statements ] ]  
[ #Else  
   [ statements ] ]  
#End If  
```  
  
## Teile  
 `expression`  
 Erforderlich für die `#If`\-Anweisung und die `#ElseIf`\-Anweisung, andernfalls optional.  Ein beliebiger Ausdruck, der ausschließlich aus einer oder mehreren Konstanten für die bedingte Kompilierung, Literalzeichen oder Operatoren besteht und der `True` oder `False` ergibt.  
  
 `statements`  
 Erforderlich für `#If`\-Anweisungsblöcke, andernfalls optional.  Visual Basic\-Programmzeilen oder Compilerdirektiven, die kompiliert werden, wenn der zugehörige Ausdruck `True` ergibt.  
  
 `#End If`  
 Beendet den `#If`\-Anweisungsblock.  
  
## Hinweise  
 Auf den ersten Blick unterscheiden sich die `#If...Then...#Else`\-Direktiven kaum von den `If...Then...Else`\-Anweisungen.  Die `#If...Then...#Else`\-Direktiven werten jedoch aus, was vom Compiler kompiliert wird. Die `If...Then...Else`\-Anweisungen werten dagegen Bedingungen zur Laufzeit aus.  
  
 Bedingte Kompilierung wird normalerweise zum Kompilieren desselben Programms für verschiedene Plattformen verwendet.  Sie verhindert auch, dass Code zu Debugzwecken in einer ausführbaren Datei erscheint.  Während der bedingten Kompilierung ausgeschlossener Code wird beim Erstellen der ausführbaren Datei nicht in die Datei aufgenommen und hat daher keinerlei Auswirkung auf die Größe oder das Leistungsverhalten.  
  
 Unabhängig vom Ergebnis der einzelnen Auswertungen werden alle Ausdrücke mit `Option Compare Binary` ausgewertet.  Die `Option Compare`\-Anweisung hat keine Auswirkungen auf Ausdrücke in den Anweisungen `#If` und `#ElseIf`.  
  
> [!NOTE]
>  Es gibt keine einzeilige Form der Direktiven `#If`, `#Else`, `#ElseIf` und `#End If`.  In der gleichen Zeile können nur die Direktiven stehen, kein anderer Code.  
  
## Beispiel  
 In diesem Beispiel wird mithilfe des `#If...Then...#Else`\-Konstrukts ermittelt, ob bestimmte Anweisungen kompiliert werden.  
  
 [!code-vb[VbVbalrConditionalComp#1](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/if-then-else-directives_1.vb)]  
  
## Siehe auch  
 [\#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md)   
 [If...Then...Else Statement](../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)