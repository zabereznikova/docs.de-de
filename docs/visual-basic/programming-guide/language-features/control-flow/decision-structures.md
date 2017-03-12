---
title: "Decision Structures (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "statements [Visual Basic], control flow"
  - "If statement, decision structures"
  - "If statement, If...Then...Else"
  - "control flow, decision structures"
  - "decision structures"
  - "conditional statements, decision structures"
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
caps.latest.revision: 29
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 29
---
# Decision Structures (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] gibt Ihnen die Möglichkeit, Bedingungen zu testen und je nach Testergebnis verschiedene Vorgänge durchzuführen.  Sie können für verschiedene Werte eines Ausdrucks oder verschiedene Ausnahmen, die beim Ausführen einer Reihe von Anweisungen generiert werden, testen, ob eine Bedingung "True" oder "False" ist.  
  
 Im folgenden Beispiel wird eine Entscheidungsstruktur veranschaulicht, mit der eine Bedingung auf den Wert True getestet wird und verschiedene Aktionen ausgeführt werden, je nachdem, ob die Bedingung True oder False ist.  
  
 ![Flussdiagramm einer If...Then...Else&#45;Konstruktion](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")  
Ausführen unterschiedlicher Aktionen, je nachdem, ob eine Bedingung True oder False ist  
  
## If...Then...Else\-Konstruktion  
 Anhand von `If...Then...Else`\-Konstruktionen können Sie eine oder mehrere Bedingungen überprüfen und je nach Bedingung eine oder mehrere Anweisungen ausführen.  Sie können Bedingungen testen und folgende, von den Testergebnissen abhängige Maßnahmen ergreifen:  
  
-   Ausführen einer oder mehrerer Anweisungen, wenn eine Bedingung `True` ist  
  
-   Ausführen einer oder mehrerer Anweisungen, wenn eine Bedingung `False` ist  
  
-   Ausführen einer Gruppe von Anweisungen, wenn eine Bedingung `True` ist, und Ausführen anderer Anweisungen, wenn die Bedingung `False` ist  
  
-   Testen einer zusätzlichen Bedingung, wenn eine zuvor angegebene Bedingung `False` ist  
  
 Die Kontrollstruktur, die all diese Maßnahmen ermöglicht, wird als [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md) bezeichnet.  Verwenden Sie eine einzeilige Variante, wenn nur eine Bedingung getestet und eine Anweisung ausgeführt werden soll.  Wenn eine komplexere Gruppe von Bedingungen und Aktionen vorliegt, verwenden Sie die mehrzeilige Variante.  
  
## Select...Case\-Konstruktion  
 Mit der `Select...Case`\-Konstruktion können Sie einen Ausdruck einmal auswerten und für verschiedene mögliche Werte Gruppen von Anweisungen ausführen.  Weitere Informationen finden Sie unter [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## Try...Catch...Finally\-Konstruktion  
 Mit `Try...Catch...Finally`\-Konstruktionen können Sie eine Gruppe von Anweisungen in einer weiterhin steuerbaren Umgebung ausführen, falls eine der Anweisungen eine Ausnahme auslöst.  Unterschiedliche Ausnahmen können unterschiedlich behandelt werden.  Optional können Sie auch einen Codeblock angeben, der in jedem Fall ausgeführt wird, bevor die gesamte `Try...Catch...Finally`\-Konstruktion verlassen wird.  Weitere Informationen finden Sie unter [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
> [!NOTE]
>  Bei vielen Steuerungsstrukturen werden beim Klicken auf ein Schlüsselwort alle Schlüsselwörter der Struktur hervorgehoben.  Wenn Sie in einer `If...Then...Else`\-Konstruktion beispielsweise auf `If` klicken, werden in der Konstruktion alle Instanzen von `If`, `Then`, `ElseIf`, `Else` und `End If` hervorgehoben.  Um zum nächsten oder vorherigen markierten Schlüsselwort zu springen, drücken Sie STRG\+UMSCHALT\+NACH\-UNTEN bzw. STRG\+UMSCHALT\+NACH\-OBEN.  
  
## Siehe auch  
 [Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Other Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)   
 [Nested Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [If Operator](../../../../visual-basic/language-reference/operators/if-operator.md)