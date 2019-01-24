---
title: IsTrue-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 780e67cf54c0bec230d5b052b877cf97a76d3f6d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54641121"
---
# <a name="istrue-operator-visual-basic"></a>IsTrue-Operator (Visual Basic)
Bestimmt, ob ein Ausdruck ist `True`.  
  
 Sie können nicht aufrufen `IsTrue` explizit in Ihrem Code, aber die Visual Basic Compiler können sie zum Generieren von Code aus `OrElse` Klauseln. Wenn Sie eine Klasse oder Struktur definieren und verwenden Sie dann auf eine Variable dieses Typs in eine `OrElse` -Klausel, müssen Sie definieren `IsTrue` für diese Klasse oder Struktur.  
  
 Der Compiler betrachtet die `IsTrue` und `IsFalse` Operatoren als eine *zueinander passendes Paar*. Dies bedeutet, dass wenn Sie einen dieser definieren, Sie auch die anderen Knoten definieren müssen.  
  
## <a name="compiler-use-of-istrue"></a>Verwendung von "IsTrue" durch den Compiler  
 Wenn Sie eine Klasse oder Struktur definiert haben, können Sie eine Variable dieses Typs in eine `For`, `If`, `Else If`, oder `While` -Anweisung oder in eine `When` Klausel. Wenn Sie dies tun, erfordert der Compiler einen Operator, der den Typ in konvertiert eine `Boolean` nutzen, damit sie eine Bedingung testen kann. Es sucht nach einem geeigneten Operator in der folgenden Reihenfolge:  
  
1.  Erweiternde Operator für die Konvertierung aus der Klasse oder Struktur `Boolean`.  
  
2.  Erweiternde Operator für die Konvertierung aus der Klasse oder Struktur `Boolean?`.  
  
3.  Die `IsTrue` Operators für die Klasse oder Struktur.  
  
4.  Eine einschränkende Konvertierung in `Boolean?` , ist eine Konvertierung von nicht beinhalten `Boolean` zu `Boolean?`.  
  
5.  Eine einschränkende Konvertierungsoperator aus der Klasse oder Struktur, `Boolean`.  
  
 Wenn Sie nicht die Konvertierung zu definiert haben `Boolean` oder `IsTrue` -Operator, der Compiler signalisiert einen Fehler.  
  
> [!NOTE]
>  Die `IsTrue` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn der Operand den Typ der Klasse oder Struktur hat. Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Gliederung einer Struktur, die Definitionen für enthält die `IsFalse` und `IsTrue` Operatoren.  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/istrue-operator_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [IsFalse-Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Vorgehensweise: Definieren eines Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [OrElse-Operator](../../../visual-basic/language-reference/operators/orelse-operator.md)
