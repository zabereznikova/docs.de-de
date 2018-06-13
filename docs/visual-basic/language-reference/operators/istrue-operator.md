---
title: IsTrue-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: fc01b074d9aba245b1c55b75b841a7f195f7ec04
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605146"
---
# <a name="istrue-operator-visual-basic"></a>IsTrue-Operator (Visual Basic)
Bestimmt, ob ein Ausdruck ist `True`.  
  
 Sie können nicht aufrufen `IsTrue` explizit in Code, jedoch in Visual Basic Compiler können sie zum Generieren von Code aus `OrElse` Klauseln. Wenn Sie eine Klasse oder Struktur definieren und verwenden Sie eine Variable dieses Typs in eine `OrElse` -Klausel, müssen Sie definieren `IsTrue` für diese Klasse oder Struktur.  
  
 Der Compiler betrachtet die `IsTrue` und `IsFalse` Operatoren als eine *zueinander passendes Paar*. Dies bedeutet, dass wenn Sie eine von ihnen definieren, Sie auch die anderen Knoten definieren müssen.  
  
## <a name="compiler-use-of-istrue"></a>Verwendung von IsTrue durch den Compiler  
 Wenn Sie eine Klasse oder Struktur definiert haben, können Sie eine Variable dieses Typs in eine `For`, `If`, `Else``If`, oder `While` -Anweisung oder in einer `When` Klausel. Wenn Sie so vorgehen, erfordert der Compiler einen Operator, der den Typ in konvertiert eine `Boolean` nutzen, damit sie eine Bedingung testen können. Es sucht nach einem geeigneten Operator in der folgenden Reihenfolge:  
  
1.  Eine erweiternde Konvertierungsoperator aus der Klasse oder Struktur, `Boolean`.  
  
2.  Eine erweiternde Konvertierungsoperator aus der Klasse oder Struktur, `Boolean?`.  
  
3.  Die `IsTrue` Operator für die Klasse oder Struktur.  
  
4.  Eine einschränkende Konvertierung in `Boolean?` beinhaltet, die eine Konvertierung von keine `Boolean` auf `Boolean?`.  
  
5.  Eine einschränkende Konvertierungsoperator aus der Klasse oder Struktur, um `Boolean`.  
  
 Wenn Sie keine Konvertierung zu definierten `Boolean` oder ein `IsTrue` -Operator, der Compiler signalisiert einen Fehler.  
  
> [!NOTE]
>  Die `IsTrue` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn Operanden den Typ der betreffenden Klasse oder Struktur hat. Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie dessen neu definierten Verhalten verstehen. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird definiert, den Überblick über eine Struktur, die Definitionen für die `IsFalse` und `IsTrue` Operatoren.  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/istrue-operator_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [IsFalse-Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [Gewusst wie: Definieren eines Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [OrElse-Operator](../../../visual-basic/language-reference/operators/orelse-operator.md)
