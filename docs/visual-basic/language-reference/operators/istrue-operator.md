---
title: IsTrue-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 4b863eed8406a10b9a44d7139f8659ac5cb758ad
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349517"
---
# <a name="istrue-operator-visual-basic"></a>IsTrue-Operator (Visual Basic)
Bestimmt, ob ein Ausdruck `True`wird.  
  
 Sie können `IsTrue` nicht explizit in Ihrem Code aufzurufen, aber der Visual Basic Compiler kann ihn verwenden, um Code aus `OrElse` Klauseln zu generieren. Wenn Sie eine Klasse oder Struktur definieren und dann eine Variable dieses Typs in einer `OrElse`-Klausel verwenden, müssen Sie `IsTrue` für diese Klasse oder Struktur definieren.  
  
 Der Compiler betrachtet die Operatoren "`IsTrue`" und "`IsFalse`" als *übereinstimmendes Paar*. Dies bedeutet, dass Sie, wenn Sie einen von Ihnen definieren, auch den anderen definieren müssen.  
  
## <a name="compiler-use-of-istrue"></a>Compilerverwendung von IsTrue  
 Wenn Sie eine Klasse oder Struktur definiert haben, können Sie eine Variable dieses Typs in einer `For`-, `If`-, `Else If`-oder `While`-Anweisung oder in einer `When`-Klausel verwenden. Wenn Sie dies tun, benötigt der Compiler einen Operator, der den Typ in einen `Boolean` Wert konvertiert, damit eine Bedingung getestet werden kann. Er sucht in der folgenden Reihenfolge nach einem passenden Operator:  
  
1. Ein erweiterter Konvertierungs Operator von der Klasse oder Struktur zum `Boolean`.  
  
2. Ein erweiterter Konvertierungs Operator von der Klasse oder Struktur zum `Boolean?`.  
  
3. Der `IsTrue`-Operator für die Klasse oder Struktur.  
  
4. Eine einschränkende Konvertierung in `Boolean?`, die keine Konvertierung von `Boolean` in `Boolean?`einschließt.  
  
5. Ein einschränkende Konvertierungs Operator von der Klasse oder Struktur zum `Boolean`.  
  
 Wenn Sie keine Konvertierung in `Boolean` oder einen `IsTrue` Operator definiert haben, signalisiert der Compiler einen Fehler.  
  
> [!NOTE]
> Der `IsTrue`-Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn der Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die Gliederung einer Struktur definiert, die Definitionen für die `IsFalse`-und `IsTrue`-Operatoren enthält.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Siehe auch

- [IsFalse-Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Gewusst wie: Definieren eines Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [OrElse-Operator](../../../visual-basic/language-reference/operators/orelse-operator.md)
