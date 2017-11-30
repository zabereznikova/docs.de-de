---
title: '#<a name="ifthenelse-directives"></a>If... ... #Else-Direktiven'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 77757e441ae937aa86122f237e839d1005644409
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ifthenelse-directives"></a>#If...Then...#Else-Anweisung
Bedingt kompiliert ausgewählten Blöcke von Visual Basic-Code.  
  
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
 Erforderlich für `#If` und `#ElseIf` -Anweisungen optional an anderer Stelle. Jeder Ausdruck, bestehend aus ausschließlich eine oder mehrere Konstanten für die bedingte Kompilierung, Literale und Operatoren, der ergibt `True` oder `False`.  
  
 `statements`  
 Erforderlich für `#If` Anweisung zu blockieren, optional an anderer Stelle. Visual Basic-Programm Linien oder Compilerdirektiven, die kompiliert werden, wenn der zugeordnete Ausdruck ergibt `True`.  
  
 `#End If`  
 Beendet die `#If` Anweisungsblock.  
  
## <a name="remarks"></a>Hinweise  
 Auf der Oberfläche, die das Verhalten von der `#If...Then...#Else` Direktiven angezeigt wird die gleiche wie für die `If...Then...Else` Anweisungen. Allerdings die `#If...Then...#Else` Richtlinien auswerten was vom Compiler kompiliert wird, während die `If...Then...Else` Anweisungen Auswerten von Bedingungen zur Laufzeit.  
  
 Bedingter Kompilierung wird normalerweise verwendet, um die gleiche Anwendung für unterschiedliche Plattformen zu kompilieren. Es wird auch verwendet, um zu verhindern, dass Debuggen von Code in eine ausführbare Datei angezeigt werden. Code, der während der bedingten Kompilierung ausgeschlossen wird vollständig über die endgültige ausführbare Datei weggelassen, damit er keine Auswirkungen auf die Größe oder die Leistung hat.  
  
 Unabhängig von dem Ergebnis der Auswertung, werden alle Ausdrücke ausgewertet, mit `Option Compare Binary`. Die `Option Compare` Anweisung wirkt sich nicht auf Ausdrücke in `#If` und `#ElseIf` Anweisungen.  
  
> [!NOTE]
>  Keine einzeilige Form der `#If`, `#Else`, `#ElseIf`, und `#End If` Direktiven vorhanden ist. Kein anderer Code kann auf derselben Zeile wie die Direktiven angezeigt werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `#If...Then...#Else` Konstrukt, um festzustellen, ob bestimmte Anweisungen zu kompilieren.  
  
 [!code-vb[VbVbalrConditionalComp#1](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/if-then-else-directives_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [#Const-Anweisung](../../../visual-basic/language-reference/directives/const-directive.md)  
 [If...Then...Else-Anweisung](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
