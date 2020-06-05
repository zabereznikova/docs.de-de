---
title: '#Const-Anweisung'
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
ms.openlocfilehash: 91152771a4ef5ec74a7408511ccc2afe28dd442e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415465"
---
# <a name="const-directive"></a>#Const-Anweisung

Definiert bedingte Compilerkonstanten für Visual Basic.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
#Const constname = expression  
```  
  
## <a name="parts"></a>Bestandteile  

 `constname`  
 Erforderlich. Der Name der Konstanten, die definiert wird.  
  
 `expression`  
 Erforderlich. Literale, andere Bedingte Compilerkonstante oder eine beliebige Kombination, die beliebige oder alle arithmetischen oder logischen Operatoren mit Ausnahme von enthält `Is` .  
  
## <a name="remarks"></a>Bemerkungen  

 Bedingte Compilerkonstanten sind immer privat für die Datei, in der Sie angezeigt werden. Sie können keine öffentlichen Compilerkonstanten mithilfe der- `#Const` Direktive erstellen. Sie können Sie nur in der Benutzeroberfläche oder mit der- `/define` Compileroption erstellen.  
  
 In können nur bedingte Compilerkonstanten und Literale verwendet werden `expression` . Die Verwendung einer mit definierten Standard Konstante `Const` verursacht einen Fehler. Umgekehrt können Sie mit dem- `#Const` Schlüsselwort definierte Konstanten nur für die bedingte Kompilierung verwenden. Konstanten können ebenfalls nicht definiert werden. in diesem Fall haben Sie den Wert `Nothing` .  
  
## <a name="example"></a>Beispiel  

 Dieses Beispiel verwendet die `#Const`-Anweisung.  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Weitere Informationen

- [-define (Visual Basic)](../../reference/command-line-compiler/define.md)
- [#If...Then...#Else-Anweisungen](if-then-else-directives.md)
- [Const-Anweisung](../statements/const-statement.md)
- [Bedingte Kompilierung](../../programming-guide/program-structure/conditional-compilation.md)
- [If...Then...Else-Anweisung](../statements/if-then-else-statement.md)
