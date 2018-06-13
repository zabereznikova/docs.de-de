---
title: '##Const-Direktive'
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
ms.openlocfilehash: a3b3318f6b44f7d1798e08195be5aeb920b61c0c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588066"
---
# <a name="const-directive"></a>#Const-Anweisung
Definiert Konstanten für die bedingte Kompilierung für Visual Basic.  
  
## <a name="syntax"></a>Syntax  
  
```  
#Const constname = expression  
```  
  
## <a name="parts"></a>Teile  
 `constname`  
 Erforderlich. Die Namen der Konstanten definiert wird.  
  
 `expression`  
 Erforderlich. Literalzeichen, andere Konstanten für die bedingte Kompilierung oder eine beliebige Kombination, die alle arithmetische oder logische Operatoren außer enthält `Is`.  
  
## <a name="remarks"></a>Hinweise  
 Konstanten für die bedingte Kompilierung sind immer privat für die Datei, in der sie angezeigt werden. Mithilfe von öffentlichen Compilerkonstanten kann nicht erstellt werden die `#Const` Richtlinie; Sie können diese erstellen, nur in der Benutzeroberfläche oder mit der `/define` -Compileroption.  
  
 Können Sie nur Konditionelle Compilerkonstanten und Literale in `expression`. Mithilfe einer standard-konstantes definiert mit `Const` verursacht einen Fehler. Umgekehrt können Sie mit definierte Konstanten verwenden die `#Const` Schlüsselwort nur für die bedingte Kompilierung. Konstanten können auch nicht definiert sein, in diesem Fall haben einen Wert von `Nothing`.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `#Const`-Direktive.  
  
 [!code-vb[VbVbalrConditionalComp#3](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/const-directive_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)  
 [#If...Then...#Else-Anweisungen](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md)  
 [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [If...Then...Else-Anweisung](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
