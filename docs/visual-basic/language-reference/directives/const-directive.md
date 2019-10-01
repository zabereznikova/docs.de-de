---
title: '#Konstanten Direktive (Visual Basic)'
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
ms.openlocfilehash: 9b8d2da2158a8244b4533eb6ef49049949417216
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696856"
---
# <a name="const-directive"></a>#Const-Anweisung
Definiert bedingte Compilerkonstanten für Visual Basic.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
#Const constname = expression  
```  
  
## <a name="parts"></a>Teile  
 `constname`  
 Erforderlich. Der Name der Konstanten, die definiert wird.  
  
 `expression`  
 Erforderlich. Literale, andere Bedingte Compilerkonstante oder eine beliebige Kombination, die beliebige oder alle arithmetischen oder logischen Operatoren mit Ausnahme von `Is` einschließt.  
  
## <a name="remarks"></a>Hinweise  
 Bedingte Compilerkonstanten sind immer privat für die Datei, in der Sie angezeigt werden. Sie können keine öffentlichen Compilerkonstanten mithilfe der `#Const`-Direktive erstellen; Sie können nur auf der Benutzeroberfläche oder mit der `/define`-Compileroption erstellt werden.  
  
 In `expression` können nur bedingte Compilerkonstanten und Literale verwendet werden. Die Verwendung einer Standard Konstanten, die mit `Const` definiert ist, verursacht einen Fehler. Umgekehrt können Sie Konstanten verwenden, die mit dem-Schlüsselwort `#Const` definiert sind, nur für die bedingte Kompilierung. Konstanten können ebenfalls nicht definiert werden. in diesem Fall haben Sie den Wert `Nothing`.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `#Const`-Anweisung.  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Siehe auch

- [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [#If...Then...#Else-Anweisungen](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md)
- [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [If...Then...Else-Anweisung](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
