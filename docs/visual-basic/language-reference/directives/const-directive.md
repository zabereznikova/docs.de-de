---
title: '##Const-Anweisung (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.#Const
- '#vb.Const'
- '#Const'
helpviewer_keywords:
- '#Const directive'
- conditional compilation [Visual Basic], directives
- Const directive (#Const)
- Visual Basic compiler, compiler directives
- constants [Visual Basic], Const directive
- constants [Visual Basic], declaring
- Const statement [Visual Basic], directive (#Const)
- 'declaring constants [Visual Basic], #const directive'
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
ms.openlocfilehash: fb937a5a9d4688730085829350cb20172db50e97
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967047"
---
# <a name="const-directive"></a>#Const-Anweisung
Definiert Konstanten für bedingte Kompilierung für Visual Basic.  
  
## <a name="syntax"></a>Syntax  
  
```  
#Const constname = expression  
```  
  
## <a name="parts"></a>Teile  
 `constname`  
 Erforderlich. Die Namen der Konstanten definiert wird.  
  
 `expression`  
 Erforderlich. Literal, andere Konstanten für bedingte Kompilierung oder eine beliebige Kombination, die alle arithmetische oder logische Operatoren außer enthält `Is`.  
  
## <a name="remarks"></a>Hinweise  
 Bedingte Compilerkonstanten sind immer privat für die Datei, die in der sie angezeigt werden. Kann nicht erstellt werden öffentliche Compilerkonstanten mithilfe der `#Const` -Direktive; Sie können diese erstellen, nur in der Benutzeroberfläche oder mit der `/define` -Compileroption.  
  
 Sie können nur Bedingte Compilerkonstanten und Literale in `expression`. Verwenden eine standard-Konstante definiert `Const` verursacht einen Fehler. Im Gegensatz dazu können Sie mit definierte Konstanten der `#Const` Schlüsselwort nur für die bedingte Kompilierung. Konstanten können auch nicht definiert sein, bei dem sie einen Wert von aufweisen `Nothing`.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `#Const`-Anweisung.  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Siehe auch
- [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [#If...Then...#Else-Anweisungen](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md)
- [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [If...Then...Else-Anweisung](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
