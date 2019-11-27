---
title: '#If...Then...#Else-Anweisungen'
ms.date: 04/11/2018
f1_keywords:
- vb.#EndIf
- '#End If'
- '#Then'
- '#ElseIf'
- vb.#ElseIf
- vb.#Else
- vb.#If
helpviewer_keywords:
- Visual Basic code, compiling
- '#If directive [Visual Basic]'
- conditional compilation [Visual Basic], directives
- '#End if directive [Visual Basic]'
- selective compiling
- else directive (#else)
- '#Else directive [Visual Basic]'
ms.assetid: 10bba104-e3fd-451b-b672-faa472530502
ms.openlocfilehash: 40e93b718241c9819e3c0fd84595e76eb0c86472
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343815"
---
# <a name="ifthenelse-directives"></a>#If...Then...#Else-Anweisung

Kompiliert bedingt ausgewählte Blöcke Visual Basic Codes.

## <a name="syntax"></a>Syntax

```vb
#If expression Then
   statements
[ #ElseIf expression Then
   [ statements ]
...
#ElseIf expression Then
   [ statements ] ]
[ #Else
   [ statements ] ]
#End If
```

## <a name="parts"></a>-Komponenten

`expression`  
Erforderlich für `#If`-und `#ElseIf`-Anweisungen, optional an anderer Stelle. Ein beliebiger Ausdruck, der ausschließlich aus einer oder mehreren bedingten Compilerkonstanten, Literalen und Operatoren besteht, die als `True` oder `False`ausgewertet werden.

`statements`  
Erforderlich für `#If`-Anweisungsblock, optional an anderer Stelle. Visual Basic Programmzeilen oder Compilerdirektiven, die kompiliert werden, wenn der zugehörige Ausdruck zu `True`ausgewertet wird.

`#End If`  
Beendet den `#If`-Anweisungsblock.

## <a name="remarks"></a>Hinweise

Auf der-Oberfläche wird das Verhalten der `#If...Then...#Else` Direktiven genauso wie die der `If...Then...Else`-Anweisungen angezeigt. Die `#If...Then...#Else` Direktiven Werten jedoch aus, was vom Compiler kompiliert wird, während die `If...Then...Else` Anweisungen Bedingungen zur Laufzeit auswerten.

Die bedingte Kompilierung wird normalerweise verwendet, um dasselbe Programm für verschiedene Plattformen zu kompilieren. Außerdem wird es verwendet, um zu verhindern, dass Debugcode in einer ausführbaren Datei angezeigt wird. Code, der während der bedingten Kompilierung ausgeschlossen wird, wird in der endgültigen ausführbaren Datei vollständig ausgelassen und hat daher keine Auswirkung auf die Größe oder Leistung.

Unabhängig vom Ergebnis einer Auswertung werden alle Ausdrücke mithilfe von `Option Compare Binary`ausgewertet. Die `Option Compare`-Anweisung wirkt sich nicht auf Ausdrücke in `#If`-und `#ElseIf`-Anweisungen aus.

> [!NOTE]
> Es sind keine einzeiligen Formen der `#If`-, `#Else`-, `#ElseIf`-und `#End If`-Direktive vorhanden. Es kann kein anderer Code in derselben Zeile wie eine der Direktiven angezeigt werden.

Die Anweisungen in einem Block für die bedingte Kompilierung müssen komplette logische Anweisungen sein. Beispielsweise können Sie die Attribute einer Funktion nicht bedingt kompilieren, Sie können die Funktion aber bedingt zusammen mit ihren Attributen deklarieren:

```vb
#If DEBUG Then
<WebMethod()>
Public Function SomeFunction() As String
#Else
<WebMethod(CacheDuration:=86400)>
Public Function SomeFunction() As String
#End If
```

## <a name="example"></a>Beispiel

In diesem Beispiel wird das `#If...Then...#Else`-Konstrukt verwendet, um zu bestimmen, ob bestimmte Anweisungen kompiliert werden.

[!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]

## <a name="see-also"></a>Siehe auch

- [#Const-Anweisung](../../../visual-basic/language-reference/directives/const-directive.md)
- [If...Then...Else-Anweisung](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>
