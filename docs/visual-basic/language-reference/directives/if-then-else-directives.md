---
title: '#If... ... #Else-Anweisungen (Visual Basic)'
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
ms.openlocfilehash: 8c0aece749edf144fdd5c8ede9ec7e2e4c96ad54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746720"
---
# <a name="ifthenelse-directives"></a>#If...Then...#Else-Anweisung
Kompiliert bedingt ausgewählte Codeblöcke Visual Basic-Code ein.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
## <a name="parts"></a>Teile  
 `expression`  
 Erforderlich für `#If` und `#ElseIf` Anweisungen, die optional an anderer Stelle. Ein Ausdruck, bestehend aus ausschließlich eine oder mehrere Konstanten für bedingte Kompilierung, Literale und Operatoren, der ergibt `True` oder `False`.  
  
 `statements`  
 Erforderlich für `#If` Anweisung zu blockieren, optionale an anderer Stelle. Visual Basic-Programm von Linien oder Compiler-Direktiven, die kompiliert werden, wenn der zugeordnete Ausdruck ergibt `True`.  
  
 `#End If`  
 Beendet die `#If` Anweisungsblock.  
  
## <a name="remarks"></a>Hinweise  
 Auf der Oberfläche, die das Verhalten der `#If...Then...#Else` Anweisungen identisch angezeigt, wie mit der `If...Then...Else` Anweisungen. Allerdings die `#If...Then...#Else` Anweisungen auswerten was vom Compiler kompiliert wird, während die `If...Then...Else` Anweisungen Bedingungen auszuwerten, zur Laufzeit.  
  
 Für die bedingte Kompilierung wird normalerweise verwendet, um die gleiche Anwendung für unterschiedliche Plattformen zu kompilieren. Es wird außerdem zu verhindern, dass zum Debuggen von Code in eine ausführbare Datei angezeigt werden. Code während der bedingten Kompilierung ausgeschlossen wird vollständig aus der endgültige ausführbare Datei weggelassen, damit er keine Auswirkungen auf die Größe oder die Leistung hat.  
  
 Unabhängig vom Ergebnis der Auswertung, werden alle Ausdrücke ausgewertet, mit `Option Compare Binary`. Die `Option Compare` Anweisung wirkt sich nicht auf Ausdrücke in `#If` und `#ElseIf` Anweisungen.  
  
> [!NOTE]
>  Keine einzeilige Form der `#If`, `#Else`, `#ElseIf`, und `#End If` Direktiven vorhanden ist. Kein anderer Code kann auf derselben Zeile wie die Direktiven angezeigt werden. 

Die Anweisungen innerhalb eines Blocks für die bedingte Kompilierung müssen vollständigen logischen Anweisungen sein. Z. B. nicht möglich, nur die Attribute einer Funktion, bedingt zu kompilieren, aber Sie können die Funktion zusammen mit seinen Attributen bedingt deklarieren:

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
 Dieses Beispiel verwendet die `#If...Then...#Else` Konstrukt zu bestimmen, ob bestimmte Anweisungen zu kompilieren.  
  
 [!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [#Const-Anweisung](../../../visual-basic/language-reference/directives/const-directive.md)
- [If...Then...Else-Anweisung](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>
