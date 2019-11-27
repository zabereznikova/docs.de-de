---
title: Entscheidungsstrukturen
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
ms.openlocfilehash: d0d4039ff2edc61ee8b4b732c6adcb6e420d73ea
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353967"
---
# <a name="decision-structures-visual-basic"></a>Entscheidungsstrukturen (Visual Basic)
Mit Visual Basic können Sie Bedingungen testen und abhängig von den Ergebnissen dieses Tests verschiedene Vorgänge durchführen. Sie können prüfen, dass eine Bedingung true oder false ist, für verschiedene Werte eines Ausdrucks oder für verschiedene Ausnahmen, die beim Ausführen einer Reihe von Anweisungen generiert werden.  
  
 In der folgenden Abbildung wird eine Entscheidungsstruktur dargestellt, die überprüft, ob eine Bedingung wahr ist, und abhängig davon, ob Sie true oder false ist, verschiedene Aktionen unternimmt.  
  
 ![Ein Flussdiagramm einer If...Then...Else-Konstruktion.](./media/decision-structures/if-then-else-construction.gif)  
  
## <a name="ifthenelse-construction"></a>If...Then...Else-Konstruktion  
 mit `If...Then...Else` Konstruktionen können Sie eine oder mehrere Bedingungen testen und eine oder mehrere-Anweisungen abhängig von den einzelnen Bedingungen ausführen. Es gibt folgende Möglichkeiten, um Bedingungen zu testen und Aktionen auszuführen:  
  
- Führen Sie eine oder mehrere-Anweisungen aus, wenn eine Bedingung `True`  
  
- Führen Sie eine oder mehrere-Anweisungen aus, wenn eine Bedingung `False`  
  
- Führen Sie einige Anweisungen aus, wenn eine Bedingung `True` ist, und andere, wenn Sie `False`  
  
- Testen einer zusätzlichen Bedingung, wenn eine vorherige Bedingung `False`  
  
 Die Steuerelement Struktur, die alle diese Möglichkeiten bietet, ist der [If... Dann... Else-Anweisung](../../../../visual-basic/language-reference/statements/if-then-else-statement.md). Sie können eine einzeilige Version verwenden, wenn Sie nur einen Test und eine Anweisung ausführen müssen. Wenn Sie einen komplexeren Satz von Bedingungen und Aktionen haben, können Sie die mehrzeilige Version verwenden.  
  
## <a name="selectcase-construction"></a>Select...Case Konstruktion  
 Mit der `Select...Case` Konstruktion können Sie einen Ausdruck einmal auswerten und verschiedene Sätze von Anweisungen basierend auf anderen möglichen Werten ausführen. Weitere Informationen finden Sie unter [SELECT... Case-Anweisung](../../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="trycatchfinally-construction"></a>Try...Catch...Finally Konstruktion  
 mit `Try...Catch...Finally` Konstruktionen können Sie eine Reihe von-Anweisungen in einer Umgebung ausführen, die die Steuerung beibehält, wenn eine der Anweisungen eine Ausnahme auslöst. Sie können verschiedene Aktionen für verschiedene Ausnahmen durchführen. Sie können optional einen Codeblock angeben, der ausgeführt wird, bevor Sie die gesamte `Try...Catch...Finally` Konstruktion beenden, unabhängig davon, was passiert. Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
> [!NOTE]
> Wenn Sie für viele Steuerungsstrukturen auf ein Schlüsselwort klicken, werden alle Schlüsselwörter in der Struktur hervorgehoben. Wenn Sie beispielsweise in einer `If...Then...Else` Konstruktion auf `If` klicken, werden alle Instanzen von `If`, `Then`, `ElseIf`, `Else`und `End If` in der Konstruktion hervorgehoben. Um zum nächsten oder vorherigen hervorgehobenen Schlüsselwort zu wechseln, drücken Sie STRG + UMSCHALT + nach-unten oder STRG + UMSCHALT + nach-oben-Taste.  
  
## <a name="see-also"></a>Siehe auch

- [Ablaufsteuerung](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Schleifenstruktur](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Weitere Steuerungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [Geschachtelte Steuerungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [If-Operator](../../../../visual-basic/language-reference/operators/if-operator.md)
