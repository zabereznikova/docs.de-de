---
title: Entscheidungsstrukturen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
ms.openlocfilehash: 4a76b2565c343e69ac3c11441035a7682a8f08ec
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318935"
---
# <a name="decision-structures-visual-basic"></a>Entscheidungsstrukturen (Visual Basic)
Visual Basic können Sie die Bedingungen zu testen, und führen Sie verschiedene Vorgänge abhängig von den Ergebnissen dieses Tests. Sie können testen, auf eine Bedingung wird "true" oder "false" für verschiedene Werte für einen Ausdruck oder für verschiedene Ausnahmen generiert, wenn Sie eine Reihe von Anweisungen ausführen.  
  
 Die folgende Abbildung zeigt eine Entscheidungsstruktur, die eine Bedingung "true" wird überprüft, und verschiedene Aktionen abhängig davon, ob es "true" oder "false".  
  
 ![Ein Flussdiagramm einer If... Klicken Sie dann... Else-Konstruktion.](./media/decision-structures/if-then-else-construction.gif)  
  
## <a name="ifthenelse-construction"></a>If... Klicken Sie dann... Else-Konstruktion  
 `If...Then...Else` Konstruktionen können Sie für eine oder mehrere Bedingungen zu testen, und führen Sie eine oder mehrere Anweisungen je nach jede Bedingung. Sie können testen Bedingungen und Aktionen auf folgende Weise:  
  
-   Führen Sie eine oder mehrere Anweisungen aus, wenn eine Bedingung `True`  
  
-   Führen Sie eine oder mehrere Anweisungen aus, wenn eine Bedingung `False`  
  
-   Führen Sie einige Anweisungen, wenn eine Bedingung `True` und anderen ist dies `False`  
  
-   Eine weitere Bedingung zu testen, wenn eine vorherige Bedingung `False`  
  
 Die Steuerelement-Struktur, die alle diese Möglichkeiten bietet, ist die [Wenn... Klicken Sie dann... Else-Anweisung](../../../../visual-basic/language-reference/statements/if-then-else-statement.md). Sie können eine einzeilige-Version verwenden, wenn Sie nur einen Test und eine Anweisung ausgeführt haben. Wenn Sie einen komplexen Satz von Bedingungen und Aktionen verfügen, können Sie die Version der Zeile.  
  
## <a name="selectcase-construction"></a>Auswählen... Case-Konstruktion  
 Die `Select...Case` Konstruktion können Sie einen Ausdruck ein Mal ausgewertet, und führen Sie verschiedene Gruppen von Anweisungen basierend auf verschiedenen möglichen Werte. Weitere Informationen finden Sie unter [auswählen... Case-Anweisung](../../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="trycatchfinally-construction"></a>Versuchen Sie es... Catch... Finally-Konstruktion  
 `Try...Catch...Finally` Konstruktionen können Sie eine Reihe von Anweisungen in einer Umgebung ausführen, die die Kontrolle behält, wenn eine der Anweisungen eine Ausnahme auslöst. Sie können verschiedene Aktionen für unterschiedliche Ausnahmen. Optional können Sie angeben, einen Codeblock, der ausgeführt wird, bevor Sie verlassen, dass die gesamte `Try...Catch...Finally` erstellt, unabhängig davon, was geschieht. Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
> [!NOTE]
>  Für viele Steuerungsstrukturen Wenn Sie ein Schlüsselwort, klicken Sie auf werden alle Schlüsselwörter in der Struktur hervorgehoben. Z. B. beim Klicken auf `If` in einer `If...Then...Else` Konstruktion, die alle Instanzen von `If`, `Then`, `ElseIf`, `Else`, und `End If` bei der Erstellung werden hervorgehoben. Um zum nächsten oder vorherigen hervorgehobenen Schlüsselwort zu verschieben, drücken Sie STRG + UMSCHALT + nach-unten oder STRG + UMSCHALT + nach-oben-Taste.  
  
## <a name="see-also"></a>Siehe auch

- [Ablaufsteuerung](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Schleifenstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Weitere Steuerungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [Geschachtelte Steuerungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Operator If](../../../../visual-basic/language-reference/operators/if-operator.md)
