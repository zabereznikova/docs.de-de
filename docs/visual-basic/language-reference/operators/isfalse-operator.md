---
title: IsFalse-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d85fc51a75f82c65cf226b8239a8eee6585bd18a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="isfalse-operator-visual-basic"></a>IsFalse-Operator (Visual Basic)
Bestimmt, ob ein Ausdruck ist `False`.  
  
 Sie können nicht aufrufen `IsFalse` explizit in Code, jedoch in Visual Basic Compiler können sie zum Generieren von Code aus `AndAlso` Klauseln. Wenn Sie eine Klasse oder Struktur definieren und verwenden Sie eine Variable dieses Typs in eine `AndAlso` -Klausel, müssen Sie definieren `IsFalse` für diese Klasse oder Struktur.  
  
 Der Compiler betrachtet die `IsFalse` und `IsTrue` Operatoren als eine *zueinander passendes Paar*. Dies bedeutet, dass wenn Sie eine von ihnen definieren, Sie auch die anderen Knoten definieren müssen.  
  
> [!NOTE]
>  Die `IsFalse` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn Operanden den Typ der betreffenden Klasse oder Struktur hat. Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie dessen neu definierten Verhalten verstehen. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird definiert, den Überblick über eine Struktur, die Definitionen für die `IsFalse` und `IsTrue` Operatoren.  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isfalse-operator_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [IsTrue-Operator](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [Gewusst wie: Definieren eines Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [AndAlso-Operator](../../../visual-basic/language-reference/operators/andalso-operator.md)
