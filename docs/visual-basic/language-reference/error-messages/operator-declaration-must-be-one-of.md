---
title: 'Operatordeklaration muss einer der: +,-, *,-, -, ^, &amp;, Like, Mod, und, oder Xor, nicht der Fall, &lt; &lt;, &gt; &gt;, =, &lt; &gt;, &lt;, &lt;= &gt; , &gt;= CType, IsTrue, IsFalse'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords: BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 80c8358dd13105c18e73e94735a51b02d5bd22c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not-ltlt-gtgt"></a>Operatordeklaration muss einer der: +,-, *,\,/, ^, &amp;, Like, Mod, und, oder Xor, nicht der Fall, &lt; &lt;, &gt; &gt;...
Sie können nur einen Operator deklarieren, der für überladen geeignet ist. Die folgende Tabelle enthält die Operatoren, die Sie deklarieren können.  
  
|Typ|Operatoren|  
|----------|---------------|  
|Unär|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binär|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|Konvertierung (unär)|`CType`|  
  
 Beachten Sie, dass die `=` in der Liste binärer Operator wird der Vergleichsoperator, der nicht der Zuweisungsoperator.  
  
 **Fehler-ID:** BC33000  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Wählen Sie einen Operator aus der Gruppe der überladbaren Operatoren aus.  
  
2.  Wenn Sie die Funktionalität des Überladens eines Operators benötigen, der nicht direkt überladen werden kann, erstellen Sie eine `Function` -Prozedur, die die entsprechenden Parameter übernimmt und den entsprechenden Wert zurückgibt.  
  
## <a name="see-also"></a>Siehe auch  
 [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [Gewusst wie: Definieren eines Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [Gewusst wie: Definieren eines Konvertierungsoperators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
