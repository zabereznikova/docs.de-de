---
title: IsFalse-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 49b8493575685a220808df1522ce16835b3ce0ed
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917155"
---
# <a name="isfalse-operator-visual-basic"></a>IsFalse-Operator (Visual Basic)
Bestimmt, ob ein Ausdruck `False`ist.  
  
 Sie können nicht `IsFalse` explizit in Ihrem Code aufzurufen, der Visual Basic Compiler kann es jedoch zum Generieren von `AndAlso` Code aus Klauseln verwenden. Wenn Sie eine Klasse oder Struktur definieren und dann eine Variable dieses Typs in einer `AndAlso` -Klausel verwenden, müssen Sie für diese Klasse oder Struktur definieren. `IsFalse`  
  
 Der Compiler betrachtet die `IsFalse` Operatoren und `IsTrue` als ein *übereinstimmendes Paar*. Dies bedeutet, dass Sie, wenn Sie einen von Ihnen definieren, auch den anderen definieren müssen.  
  
> [!NOTE]
> Der `IsFalse` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn der Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die Gliederung einer-Struktur definiert, die Definitionen `IsFalse` für `IsTrue` die Operatoren und enthält.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Siehe auch

- [IsTrue-Operator](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [Vorgehensweise: Definieren eines Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [AndAlso-Operator](../../../visual-basic/language-reference/operators/andalso-operator.md)
