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
ms.openlocfilehash: 7054a6ada4583c5d89e020437eb622a59d3eb17a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410009"
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

## <a name="parts"></a>Bestandteile

`expression`  
Erforderlich für `#If` -und- `#ElseIf` Anweisungen, optional an anderer Stelle. Ein beliebiger Ausdruck, der ausschließlich aus einer oder mehreren bedingten Compilerkonstanten, Literalen und Operatoren besteht, die als oder ausgewertet werden `True` `False` .

`statements`  
Erforderlich für einen `#If` Anweisungsblock, optional an anderer Stelle. Visual Basic Programmzeilen oder Compilerdirektiven, die kompiliert werden, wenn der zugehörige Ausdruck zu ausgewertet wird `True` .

`#End If`  
Beendet den `#If` Anweisungsblock.

## <a name="remarks"></a>Bemerkungen

Auf der-Oberfläche wird das Verhalten der- `#If...Then...#Else` Direktiven genauso wie die- `If...Then...Else` Anweisungen angezeigt. Die- `#If...Then...#Else` Direktiven Werten jedoch aus, was vom Compiler kompiliert wird, während die- `If...Then...Else` Anweisungen Bedingungen zur Laufzeit auswerten.

Die bedingte Kompilierung wird normalerweise verwendet, um dasselbe Programm für verschiedene Plattformen zu kompilieren. Außerdem wird es verwendet, um zu verhindern, dass Debugcode in einer ausführbaren Datei angezeigt wird. Code, der während der bedingten Kompilierung ausgeschlossen wird, wird in der endgültigen ausführbaren Datei vollständig ausgelassen und hat daher keine Auswirkung auf die Größe oder Leistung.

Unabhängig vom Ergebnis einer Auswertung werden alle Ausdrücke mithilfe von ausgewertet `Option Compare Binary` . Die `Option Compare` -Anweisung wirkt sich nicht auf Ausdrücke in `#If` -und- `#ElseIf` Anweisungen aus.

> [!NOTE]
> Es sind keine einzeiligen Formen `#If` der `#Else` `#ElseIf` Direktiven,, und `#End If` vorhanden. Es kann kein anderer Code in derselben Zeile wie eine der Direktiven angezeigt werden.

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

In diesem Beispiel wird das- `#If...Then...#Else` Konstrukt verwendet, um zu bestimmen, ob bestimmte Anweisungen kompiliert werden.

[!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]

## <a name="see-also"></a>Weitere Informationen

- [#Const-Anweisung](const-directive.md)
- [If...Then...Else-Anweisung](../statements/if-then-else-statement.md)
- [Bedingte Kompilierung](../../programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>
