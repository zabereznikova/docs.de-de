---
title: 'Vorgehensweise: Reduzieren und Ausblenden von Codeabschnitten'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: c11affe9c4dd4251ba8ff4b87029d314970b5fcb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404848"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>Gewusst wie: Reduzieren und Ausblenden von Codeabschnitten (Visual Basic)

Die `#Region` -Direktive ermöglicht das reduzieren und Ausblenden von Code Abschnitten in Visual Basic Dateien. Mit der- `#Region` Direktive können Sie einen Codeblock angeben, den Sie erweitern oder reduzieren können, wenn Sie den Visual Studio-Code-Editor verwenden. Durch die Möglichkeit, Code selektiv auszublenden, werden Ihre Dateien besser verwaltbar und leichter lesbar. Weitere Informationen finden Sie unter [Gliedern](/visualstudio/ide/outlining).

`#Region`Direktiven unterstützen Code Block Semantik wie z `#If...#End If` . b.. Dies bedeutet, dass Sie nicht in einem Block beginnen und mit einem anderen enden können. der Start-und der Ende müssen sich im gleichen-Block befinden. `#Region`-Anweisungen werden innerhalb von-Funktionen nicht unterstützt.

## <a name="to-collapse-and-hide-a-section-of-code"></a>So reduzieren Sie einen Code Abschnitt und blenden ihn aus

Platzieren Sie den Code Abschnitt zwischen der `#Region` -Anweisung und der- `#End Region` Anweisung, wie im folgenden Beispiel gezeigt:

[!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]

Der- `#Region` Block kann mehrmals in einer Codedatei verwendet werden. Daher können Benutzer eigene Blöcke von Prozeduren und Klassen definieren, die wiederum reduziert werden können. `#Region`-Blöcke können auch in anderen-Blöcken geschachtelt werden `#Region` .

> [!NOTE]
> Das Ausblenden von Code verhindert nicht, dass er kompiliert wird, und wirkt sich nicht auf- `#If...#End If` Anweisungen aus.

## <a name="see-also"></a>Weitere Informationen

- [Bedingte Kompilierung](conditional-compilation.md)
- [#Region-Direktive](../../language-reference/directives/region-directive.md)
- [#If...Then...#Else-Anweisungen](../../language-reference/directives/if-then-else-directives.md)
- [Gliedern](/visualstudio/ide/outlining)
