---
title: IsFalse-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 51b7bfb2cf5301a39818e6566b408ee0677689f2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349526"
---
# <a name="isfalse-operator-visual-basic"></a>IsFalse-Operator (Visual Basic)
Bestimmt, ob ein Ausdruck `False`wird.  
  
 Sie können `IsFalse` nicht explizit in Ihrem Code aufzurufen, aber der Visual Basic Compiler kann ihn verwenden, um Code aus `AndAlso` Klauseln zu generieren. Wenn Sie eine Klasse oder Struktur definieren und dann eine Variable dieses Typs in einer `AndAlso`-Klausel verwenden, müssen Sie `IsFalse` für diese Klasse oder Struktur definieren.  
  
 Der Compiler betrachtet die Operatoren "`IsFalse`" und "`IsTrue`" als *übereinstimmendes Paar*. Dies bedeutet, dass Sie, wenn Sie einen von Ihnen definieren, auch den anderen definieren müssen.  
  
> [!NOTE]
> Der `IsFalse`-Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn der Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die Gliederung einer Struktur definiert, die Definitionen für die `IsFalse`-und `IsTrue`-Operatoren enthält.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Siehe auch

- [IsTrue-Operator](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [Gewusst wie: Definieren eines Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [AndAlso-Operator](../../../visual-basic/language-reference/operators/andalso-operator.md)
