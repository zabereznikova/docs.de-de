---
title: 'Gewusst wie: Reduzieren und Ausblenden von Codeabschnitten (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4497c9586182cca9e2be97dc39e5ccb242725d25
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
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
