---
title: IsTrue-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 1152f4b512a85ae183f8fc8d476b69685e2926ef
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966915"
---
# <a name="istrue-operator-visual-basic"></a>IsTrue-Operator (Visual Basic)
Bestimmt, ob ein Ausdruck `True`ist.  
  
 Sie können nicht `IsTrue` explizit in Ihrem Code aufzurufen, der Visual Basic Compiler kann es jedoch zum Generieren von `OrElse` Code aus Klauseln verwenden. Wenn Sie eine Klasse oder Struktur definieren und dann eine Variable dieses Typs in einer `OrElse` -Klausel verwenden, müssen Sie für diese Klasse oder Struktur definieren. `IsTrue`  
  
 Der Compiler betrachtet die `IsTrue` Operatoren und `IsFalse` als ein *übereinstimmendes Paar*. Dies bedeutet, dass Sie, wenn Sie einen von Ihnen definieren, auch den anderen definieren müssen.  
  
## <a name="compiler-use-of-istrue"></a>Compilerverwendung von IsTrue  
 Wenn Sie eine Klasse oder Struktur definiert haben, können Sie eine Variable `For`dieses Typs in einer- `Else If`, `If`-,-oder `While` -Anweisung oder in einer `When` -Klausel verwenden. Wenn Sie dies tun, benötigt der Compiler einen Operator, der den Typ in einen `Boolean` -Wert konvertiert, damit eine Bedingung getestet werden kann. Er sucht in der folgenden Reihenfolge nach einem passenden Operator:  
  
1. Ein erweiterter Konvertierungs Operator von der Klasse oder `Boolean`Struktur zu.  
  
2. Ein erweiterter Konvertierungs Operator von der Klasse oder `Boolean?`Struktur zu.  
  
3. Der `IsTrue` Operator für die Klasse oder Struktur.  
  
4. Eine einschränkende Konvertierung `Boolean?` in, die keine Konvertierung von `Boolean` in `Boolean?`einschließt.  
  
5. Ein einschränkende Konvertierungs Operator von der Klasse oder `Boolean`Struktur zu.  
  
 Wenn Sie keine Konvertierung in `Boolean` oder einen `IsTrue` Operator definiert haben, signalisiert der Compiler einen Fehler.  
  
> [!NOTE]
> Der `IsTrue` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn der Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die Gliederung einer-Struktur definiert, die Definitionen `IsFalse` für `IsTrue` die Operatoren und enthält.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Siehe auch

- [IsFalse-Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Vorgehensweise: Definieren eines Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [OrElse-Operator](../../../visual-basic/language-reference/operators/orelse-operator.md)
