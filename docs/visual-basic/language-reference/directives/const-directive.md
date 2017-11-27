---
title: '#<a name="const-directive"></a>#Const-Direktive'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a6e162b01dc5c99fb7708337d259f9e66ddd6b64
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
