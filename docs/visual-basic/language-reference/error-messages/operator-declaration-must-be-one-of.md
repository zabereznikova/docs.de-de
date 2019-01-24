---
title: 'Operatordeklaration muss eine der: +,-, *, /, ^, &amp;, Like, Mod, und, Or, Xor, nicht der Fall, &lt; &lt;, &gt; &gt;, =, &lt; &gt;, &lt;, &lt;= &gt; , &gt;=, CType, IsTrue, IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: f32935dd4aaccd3040655b418badc13c1988c1b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622272"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not-ltlt-gtgt"></a>Operatordeklaration muss eine der: +,-, *,\,/, ^, &amp;, Like, Mod, und, Or, Xor, nicht der Fall, &lt; &lt;, &gt; &gt;...
Sie können nur einen Operator deklarieren, der für überladen geeignet ist. Die folgende Tabelle enthält die Operatoren, die Sie deklarieren können.  
  
|Typ|Operatoren|  
|----------|---------------|  
|Unär|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binär|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|Konvertierung (unär)|`CType`|  
  
 Beachten Sie, dass die `=` Operator in der binären Liste wird der Vergleichsoperator, der nicht der Zuweisungsoperator.  
  
 **Fehler-ID:** BC33000  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Wählen Sie einen Operator aus der Gruppe der überladbaren Operatoren aus.  
  
2.  Wenn Sie die Funktionalität des Überladens eines Operators benötigen, der nicht direkt überladen werden kann, erstellen Sie eine `Function` -Prozedur, die die entsprechenden Parameter übernimmt und den entsprechenden Wert zurückgibt.  
  
## <a name="see-also"></a>Siehe auch
- [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [Vorgehensweise: Definieren eines Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Vorgehensweise: Definieren eines Konvertierungsoperators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
