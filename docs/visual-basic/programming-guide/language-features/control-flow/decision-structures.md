---
title: Decision-Strukturen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement, decision structures
- If statement, If...Then...Else
- control flow, decision structures
- decision structures
- conditional statements, decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
caps.latest.revision: 29
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c69b487322dc75ae8d54f42c1c62f8f5cc35757d
ms.lasthandoff: 03/13/2017

---
# <a name="decision-structures-visual-basic"></a>Entscheidungsstrukturen (Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]können Sie testbedingungen und andere Vorgänge abhängig von den Ergebnissen dieses Tests ausführen. Sie können testen, für eine Bedingung zu true oder false für verschiedene Werte für einen Ausdruck oder für verschiedene Ausnahmen generiert, wenn Sie eine Reihe von Anweisungen ausführen.  
  
 Die folgende Abbildung zeigt eine Entscheidungsstruktur, die testet eine Bedingung erfüllt sein und verschiedene Aktionen abhängig davon, ob er true oder false.  
  
 ![Flussdiagramm einer If... Dann... Else-Konstruktion](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")  
Unterschiedliche Aktionen auszuführen, wenn eine Bedingung True ist, und wenn sie falsch ist.  
  
## <a name="ifthenelse-construction"></a>If... Dann... Else-Konstruktion  
 `If...Then...Else`Konstruktionen können Sie für mindestens eine Bedingung zu testen, und führen Sie eine oder mehrere Anweisungen jede Bedingung. Sie können testbedingungen und Aktionen auf folgende Weise:  
  
-   Führen Sie eine oder mehrere Anweisungen, wenn eine Bedingung`True`  
  
-   Führen Sie eine oder mehrere Anweisungen, wenn eine Bedingung`False`  
  
-   Führen Sie einige Anweisungen, wenn eine Bedingung `True` und anderen ist dies`False`  
  
-   Testen einer zusätzlichen Bedingung, wenn eine zuvor angegebene Bedingung ist`False`  
  
 Die Kontrollstruktur, die all diese Maßnahmen ermöglicht, wird die [Wenn... Dann... Else-Anweisung](../../../../visual-basic/language-reference/statements/if-then-else-statement.md). Sie können eine einzeiligen Version verwenden, haben nur einen Test und eine Anweisung auszuführen. Wenn Sie einen komplexen Satz aus Bedingung und Aktion haben, können Sie die Version für mehrere Zeilen.  
  
## <a name="selectcase-construction"></a>Wählen Sie... Case-Konstruktion  
 Die `Select...Case` Konstruktion können Sie Auswerten eines Ausdrucks einmal, und führen Sie verschiedene Gruppen von Anweisungen basierend auf verschiedenen möglichen Werte. Weitere Informationen finden Sie unter [wählen... Case-Anweisung](../../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="trycatchfinally-construction"></a>Versuchen Sie es... Catch... Finally-Konstruktion  
 `Try...Catch...Finally`Konstruktionen können Sie eine Gruppe von Anweisungen in einer Umgebung ausführen, die Kontrolle behält, wenn eine Anweisung eine Ausnahme auslöst. Sie können verschiedene Aktionen für verschiedene Ausnahmen. Optional können Sie angeben, einen Codeblock, der ausgeführt wird, bevor Sie verlassen, dass die gesamte `Try...Catch...Finally` Konstruktion, unabhängig davon, was auftritt. Weitere Informationen finden Sie unter [versuchen... Catch... Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
> [!NOTE]
>  Für viele Steuerungsstrukturen werden beim Klicken auf ein Schlüsselwort alle Schlüsselwörter in der Struktur hervorgehoben. Z. B. beim Klicken auf `If` in einer `If...Then...Else` Konstruktion, alle Instanzen von `If`, `Then`, `ElseIf`, `Else`, und `End If` bei der Erstellung werden hervorgehoben. Um zum nächsten oder vorherigen hervorgehobenen Schlüsselwort zu wechseln, drücken Sie STRG + UMSCHALT + nach-unten oder STRG + UMSCHALT + nach-oben-Taste.  
  
## <a name="see-also"></a>Siehe auch  
 [Ablaufsteuerung](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Schleifenstruktur](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Weitere Steuerungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)   
 [Geschachtelte Steuerungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [If-Operator](../../../../visual-basic/language-reference/operators/if-operator.md)
