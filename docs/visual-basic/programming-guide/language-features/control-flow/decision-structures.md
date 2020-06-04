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
ms.openlocfilehash: aac9844240defc5a21a3f4e6090fa8f49e6348a1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403515"
---
# <a name="decision-structures-visual-basic"></a>Entscheidungsstrukturen (Visual Basic)
Mit Visual Basic können Sie Bedingungen testen und abhängig von den Ergebnissen dieses Tests verschiedene Vorgänge durchführen. Sie können prüfen, dass eine Bedingung true oder false ist, für verschiedene Werte eines Ausdrucks oder für verschiedene Ausnahmen, die beim Ausführen einer Reihe von Anweisungen generiert werden.  
  
 In der folgenden Abbildung wird eine Entscheidungsstruktur dargestellt, die überprüft, ob eine Bedingung wahr ist, und abhängig davon, ob Sie true oder false ist, verschiedene Aktionen unternimmt.  
  
 ![Ein Flussdiagramm einer if... Dann... Else-Konstruktion.](./media/decision-structures/if-then-else-construction.gif)  
  
## <a name="ifthenelse-construction"></a>Wenn... Dann... Else-Konstruktion  
 `If...Then...Else`mit-Konstruktionen können Sie eine oder mehrere Bedingungen testen und abhängig von den einzelnen Bedingungen eine oder mehrere-Anweisungen ausführen. Es gibt folgende Möglichkeiten, um Bedingungen zu testen und Aktionen auszuführen:  
  
- Führen Sie eine oder mehrere Anweisungen aus, wenn eine Bedingung ist.`True`  
  
- Führen Sie eine oder mehrere Anweisungen aus, wenn eine Bedingung ist.`False`  
  
- Führen Sie einige Anweisungen aus, wenn eine Bedingung ist, `True` und andere, wenn Sie`False`  
  
- Testen einer zusätzlichen Bedingung, wenn eine vorherige Bedingung ist`False`  
  
 Die Steuerelement Struktur, die alle diese Möglichkeiten bietet, ist der [If... Dann... Else-Anweisung](../../../language-reference/statements/if-then-else-statement.md). Sie können eine einzeilige Version verwenden, wenn Sie nur einen Test und eine Anweisung ausführen müssen. Wenn Sie einen komplexeren Satz von Bedingungen und Aktionen haben, können Sie die mehrzeilige Version verwenden.  
  
## <a name="selectcase-construction"></a>Wählen Sie... Fall Konstruktion  
 Die `Select...Case` Konstruktion ermöglicht Ihnen das einmalige Auswerten eines Ausdrucks und das Ausführen verschiedener Sätze von Anweisungen basierend auf anderen möglichen Werten. Weitere Informationen finden Sie unter [SELECT... Case-Anweisung](../../../language-reference/statements/select-case-statement.md).  
  
## <a name="trycatchfinally-construction"></a>Try... Catch... Schließlich erstellen  
 `Try...Catch...Finally`mit-Konstruktionen können Sie eine Reihe von-Anweisungen in einer Umgebung ausführen, die die Steuerung beibehält, wenn eine der Anweisungen eine Ausnahme auslöst. Sie können verschiedene Aktionen für verschiedene Ausnahmen durchführen. Sie können optional einen Codeblock angeben, der ausgeführt wird, bevor Sie die gesamte `Try...Catch...Finally` Konstruktion beenden, unabhängig davon, was passiert. Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../language-reference/statements/try-catch-finally-statement.md).  
  
> [!NOTE]
> Wenn Sie für viele Steuerungsstrukturen auf ein Schlüsselwort klicken, werden alle Schlüsselwörter in der Struktur hervorgehoben. Wenn Sie beispielsweise auf `If` eine Konstruktion klicken `If...Then...Else` , werden alle Instanzen von `If` , `Then` , `ElseIf` , `Else` und `End If` in der Konstruktion hervorgehoben. Um zum nächsten oder vorherigen hervorgehobenen Schlüsselwort zu wechseln, drücken Sie STRG + UMSCHALT + nach-unten oder STRG + UMSCHALT + nach-oben-Taste.  
  
## <a name="see-also"></a>Weitere Informationen

- [Ablauf Steuerung](index.md)
- [Schleifenstrukturen](loop-structures.md)
- [Weitere Steuerungsstrukturen](other-control-structures.md)
- [Geschachtelte Steuerungsstrukturen](nested-control-structures.md)
- [If-Operator](../../../language-reference/operators/if-operator.md)
