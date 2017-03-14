---
title: "IsTrue Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.istrue"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "IsTrue operator"
  - "OrElse operator [Visual Basic]"
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# IsTrue Operator (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Bestimmt, ob ein Ausdruck `True` ist.  
  
 Sie können `IsTrue` im Code nicht explizit aufrufen, aber der Visual Basic\-Compiler kann mithilfe dieses Operators aus `OrElse`\-Klauseln Code generieren.  Wenn Sie eine Klasse oder Struktur definieren und dann eine Variable dieses Typs in einer `OrElse`\-Klausel verwenden, müssen Sie `IsTrue` für diese Klasse oder Struktur definieren.  
  
 Der Compiler betrachtet den Operator `IsTrue` und den Operator `IsFalse` als *zueinander passendes Paar*.  Wenn Sie einen dieser beiden Operatoren definieren, müssen Sie daher auch den anderen definieren.  
  
## Compilerverwendung von IsTrue  
 Wenn Sie eine Klasse oder Struktur definiert haben, können Sie eine Variable dieses Typs in einer `For`\-, `If`\-, `Else` `If`\- oder `While`\-Anweisung oder in einer `When`\-Klausel verwenden.  In diesem Fall erwartet der Compiler die Angabe eines Operators, der diesen Typ in einen `Boolean`\-Wert umwandelt, damit die Bedingung überprüft werden kann.  Er sucht in der folgenden Reihenfolge nach einem geeigneten Operator:  
  
1.  Ein Widening\-Konvertierungsoperator für Konvertierungen von der betreffenden Klasse oder Struktur zu `Boolean`.  
  
2.  Ein Widening\-Konvertierungsoperator für Konvertierungen von der betreffenden Klasse oder Struktur zu `Boolean?`.  
  
3.  Der Operator `IsTrue` für die betreffende Klasse oder Struktur.  
  
4.  Eine einschränkende Konvertierung in `Boolean?` ist eine Konvertierung, die keine Konvertierung von `Boolean` in `Boolean?` enthält.  
  
5.  Ein Narrowing\-Konvertierungsoperator für Konvertierungen von der betreffenden Klasse oder Struktur zu `Boolean`.  
  
 Wenn Sie keine Konvertierung zu `Boolean` oder keinen Operator `IsTrue` definiert haben, signalisiert der Compiler einen Fehler.  
  
> [!NOTE]
>  Der Operator `IsTrue` kann *überladen* werden. Das bedeutet, dass eine Klasse oder Struktur sein Verhalten neu definieren kann, wenn sein Operand den Typ dieser Klasse oder Struktur aufweist.  Wenn Sie diesen Operator im Code auf eine solche Klasse oder Struktur anwenden, sollten Sie auf jeden Fall sein neu definiertes Verhalten verstehen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Beispiel  
 Im folgenden Codebeispiel wird das Gerüst für eine Struktur definiert, das Definitionen für den Operator `IsFalse` und den Operator `IsTrue` enthält.  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/istrue-operator_1.vb)]  
  
## Siehe auch  
 [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md)   
 [How to: Define an Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md)