---
title: 'Gewusst wie: Reduzieren und Ausblenden von Codeabschnitten (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: f6c272b7ac016258d99873512cb789bba6739727
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>Gewusst wie: Reduzieren und Ausblenden von Codeabschnitten (Visual Basic)
Die `#Region` Richtlinie ermöglicht es Ihnen, reduzieren und blenden Sie Codeabschnitte im Visual Basic-Dateien. Die `#Region` Richtlinie ermöglicht die Angabe einen Block mit Code, den Sie erweitern können oder reduzieren bei Verwendung von Visual Studio Code-Editor. Die Möglichkeit, um ausgewählten Code auszublenden, sind die Dateien, besser verwaltbare und einfacher zu lesen. Weitere Informationen finden Sie unter [Gliedern](/visualstudio/ide/outlining).  
  
 `#Region` Direktiven unterstützen Codesemantik-Block, wie z. B. `#If...#End If`. Dies bedeutet, dass sie nicht in einem Block beginnen und enden in einer anderen; Anfang und Ende müssen im selben Block sein. `#Region` Richtlinien werden nicht innerhalb von Funktionen unterstützt.  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a>Reduzieren und Ausblenden von einem Abschnitt des Codes  
  
-   Platzieren Sie den Codeabschnitt zwischen den `#Region` und `#End Region` -Anweisungen, wie im folgenden Beispiel gezeigt:  
  
     [!code-vb[VbVbalrConditionalComp#6](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]  
  
     Die `#Region` Block kann mehrmals verwendet werden, in einer Codedatei; Folglich können Benutzer ihre eigenen Blöcke von Prozeduren und Klassen, die wiederum reduziert werden können, definieren. `#Region` Blöcke können auch geschachtelt werden, in anderen `#Region` blockiert.  
  
    > [!NOTE]
    >  Ausblenden von Code verhindert nicht, dass sie kompiliert wird, und hat keinen Einfluss auf `#If...#End If` Anweisungen.  
  
## <a name="see-also"></a>Siehe auch  
 [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [#Region-Anweisung](../../../visual-basic/language-reference/directives/region-directive.md)  
 [#If...Then...#Else-Anweisungen](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [Gliedern](/visualstudio/ide/outlining)
