---
title: IsFalse-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 7c5ad5fa0b72370eeb19fbaced88807570467552
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370673"
---
# <a name="isfalse-operator-visual-basic"></a>IsFalse-Operator (Visual Basic)
Bestimmt, ob ein Ausdruck ist `False` .  
  
 Sie können nicht `IsFalse` explizit in Ihrem Code aufzurufen, der Visual Basic Compiler kann es jedoch zum Generieren von Code aus `AndAlso` Klauseln verwenden. Wenn Sie eine Klasse oder Struktur definieren und dann eine Variable dieses Typs in einer- `AndAlso` Klausel verwenden, müssen Sie `IsFalse` für diese Klasse oder Struktur definieren.  
  
 Der Compiler betrachtet die `IsFalse` `IsTrue` Operatoren und als ein *übereinstimmendes Paar*. Dies bedeutet, dass Sie, wenn Sie einen von Ihnen definieren, auch den anderen definieren müssen.  
  
> [!NOTE]
> Der `IsFalse` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn der Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die Gliederung einer-Struktur definiert, die Definitionen für die `IsFalse` `IsTrue` Operatoren und enthält.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IsTrue-Operator](istrue-operator.md)
- [Vorgehensweise: Definieren eines Operators](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [AndAlso-Operator](andalso-operator.md)
