---
title: "IsFalse Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.isfalse"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "AndAlso operator"
  - "IsFalse operator"
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# IsFalse Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Bestimmt, ob ein Ausdruck `False` ist.  
  
 Sie können `IsFalse` im Code nicht explizit aufrufen, aber der Visual Basic\-Compiler kann mithilfe dieses Operators aus `AndAlso`\-Klauseln Code generieren.  Wenn Sie eine Klasse oder Struktur definieren und dann eine Variable dieses Typs in einer `AndAlso`\-Klausel verwenden, müssen Sie `IsFalse` für diese Klasse oder Struktur definieren.  
  
 Der Compiler betrachtet den Operator `IsFalse` und den Operator `IsTrue` als *zueinander passendes Paar*.  Wenn Sie einen dieser beiden Operatoren definieren, müssen Sie daher auch den anderen definieren.  
  
> [!NOTE]
>  Der Operator `IsFalse` kann *überladen* werden. Das bedeutet, dass eine Klasse oder Struktur sein Verhalten neu definieren kann, wenn sein Operand den Typ dieser Klasse oder Struktur aufweist.  Wenn Sie diesen Operator im Code auf eine solche Klasse oder Struktur anwenden, sollten Sie auf jeden Fall sein neu definiertes Verhalten verstehen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Beispiel  
 Im folgenden Codebeispiel wird das Gerüst für eine Struktur definiert, das Definitionen für den Operator `IsFalse` und den Operator `IsTrue` enthält.  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/isfalse-operator_1.vb)]  
  
## Siehe auch  
 [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md)   
 [How to: Define an Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md)