---
title: 'Vorgehensweise: Reduzieren und Ausblenden von Code Abschnitten (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: db396adf24c12542f720d3b235068aea2329288d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949731"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>Vorgehensweise: Reduzieren und Ausblenden von Code Abschnitten (Visual Basic)
Die `#Region` -Direktive ermöglicht das reduzieren und Ausblenden von Code Abschnitten in Visual Basic Dateien. Mit `#Region` der-Direktive können Sie einen Codeblock angeben, den Sie erweitern oder reduzieren können, wenn Sie den Visual Studio-Code-Editor verwenden. Durch die Möglichkeit, Code selektiv auszublenden, werden Ihre Dateien besser verwaltbar und leichter lesbar. Weitere Informationen finden Sie unter [Gliedern](/visualstudio/ide/outlining).  
  
 `#Region`Direktiven unterstützen Code Block Semantik `#If...#End If`wie z. b. Dies bedeutet, dass Sie nicht in einem Block beginnen und mit einem anderen enden können. der Start-und der Ende müssen sich im gleichen-Block befinden. `#Region`-Anweisungen werden innerhalb von-Funktionen nicht unterstützt.  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a>So reduzieren Sie einen Code Abschnitt und blenden ihn aus  
  
- Platzieren Sie den Code Abschnitt zwischen der `#Region` - `#End Region` Anweisung und der-Anweisung, wie im folgenden Beispiel gezeigt:  
  
     [!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]  
  
     Der `#Region` -Block kann mehrmals in einer Codedatei verwendet werden. Daher können Benutzer eigene Blöcke von Prozeduren und Klassen definieren, die wiederum reduziert werden können. `#Region`-Blöcke können auch in anderen `#Region` -Blöcken geschachtelt werden.  
  
    > [!NOTE]
    > Das Ausblenden von Code verhindert nicht, dass er kompiliert wird, und `#If...#End If` wirkt sich nicht auf-Anweisungen aus.  
  
## <a name="see-also"></a>Siehe auch

- [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [#Region-Anweisung](../../../visual-basic/language-reference/directives/region-directive.md)
- [#If...Then...#Else-Anweisungen](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Gliedern](/visualstudio/ide/outlining)
