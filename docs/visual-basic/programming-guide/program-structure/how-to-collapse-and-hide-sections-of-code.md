---
title: 'Vorgehensweise: Reduzieren und Ausblenden von Codeabschnitten (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: 1282269f06f89645c213f3daaa1bd29e95a44d35
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668716"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>Vorgehensweise: Reduzieren und Ausblenden von Codeabschnitten (Visual Basic)
Die `#Region` Richtlinie ermöglicht es Ihnen, reduzieren und Ausblenden von Codeabschnitten in Visual Basic-Dateien. Die `#Region` -Direktive können Sie einen Block mit Code, den Sie erweitern können, oder reduzieren angeben, wenn Sie Visual Studio Code-Editor verwenden. Die Möglichkeit, um ausgewählten Code auszublenden, kann Ihre Dateien leichter lesbar und besser verwaltbar. Weitere Informationen finden Sie unter [Gliedern](/visualstudio/ide/outlining).  
  
 `#Region` Direktiven unterstützen Code blockieren Semantik, wie z. B. `#If...#End If`. Dies bedeutet, dass sie nicht in einem Block beginnen und enden in einem anderen; die Start- und Endzeit müssen im selben Block sein. `#Region` Anweisungen sind innerhalb von Funktionen nicht unterstützt.  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a>Reduzieren und Ausblenden eines Abschnitts des Codes  
  
-   Platzieren Sie den Abschnitt des Codes zwischen der `#Region` und `#End Region` -Anweisungen, wie im folgenden Beispiel gezeigt:  
  
     [!code-vb[VbVbalrConditionalComp#6](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]  
  
     Die `#Region` Block kann mehrere Male in einer Codedatei verwendet werden; daher können Benutzer ihre eigenen Blöcke von Prozeduren und Klassen, die wiederum reduziert werden können, definieren. `#Region` Blöcke können auch in anderen geschachtelt werden `#Region` Blöcke.  
  
    > [!NOTE]
    >  Ausblenden von Code verhindert nicht, dass er kompiliert wird, und hat keinen Einfluss auf `#If...#End If` Anweisungen.  
  
## <a name="see-also"></a>Siehe auch
- [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [#Region-Anweisung](../../../visual-basic/language-reference/directives/region-directive.md)
- [#If...Then...#Else-Anweisungen](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Gliedern](/visualstudio/ide/outlining)
