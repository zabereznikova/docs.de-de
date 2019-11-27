---
title: 'Gewusst wie: Reduzieren und Ausblenden von Codeabschnitten'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: e7aacdc3f41199127b00d276b382ec4a5f258da0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347410"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>Gewusst wie: Reduzieren und Ausblenden von Codeabschnitten (Visual Basic)

Die `#Region`-Direktive ermöglicht das reduzieren und Ausblenden von Code Abschnitten in Visual Basic Dateien. Mit der `#Region`-Direktive können Sie einen Codeblock angeben, den Sie erweitern oder reduzieren können, wenn Sie den Visual Studio-Code-Editor verwenden. Durch die Möglichkeit, Code selektiv auszublenden, werden Ihre Dateien besser verwaltbar und leichter lesbar. Weitere Informationen finden Sie unter [Gliedern](/visualstudio/ide/outlining).

`#Region` Direktiven unterstützen Code Block Semantik wie `#If...#End If`. Dies bedeutet, dass Sie nicht in einem Block beginnen und mit einem anderen enden können. der Start-und der Ende müssen sich im gleichen-Block befinden. `#Region`-Direktiven werden in Functions nicht unterstützt.

## <a name="to-collapse-and-hide-a-section-of-code"></a>So reduzieren Sie einen Code Abschnitt und blenden ihn aus

Platzieren Sie den Code Abschnitt zwischen den Anweisungen `#Region` und `#End Region`, wie im folgenden Beispiel gezeigt:

[!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]

Der `#Region`-Block kann mehrmals in einer Codedatei verwendet werden. Daher können Benutzer eigene Blöcke von Prozeduren und Klassen definieren, die wiederum reduziert werden können. `#Region` Blöcke können auch innerhalb anderer `#Region` Blöcke geschachtelt werden.

> [!NOTE]
> Das Ausblenden von Code verhindert nicht, dass er kompiliert wird, und wirkt sich nicht auf `#If...#End If`-Anweisungen aus.

## <a name="see-also"></a>Siehe auch

- [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [#Region-Anweisung](../../../visual-basic/language-reference/directives/region-directive.md)
- [#If...Then...#Else-Anweisungen](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Gliedern](/visualstudio/ide/outlining)
