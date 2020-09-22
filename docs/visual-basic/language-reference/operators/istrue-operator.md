---
title: IsTrue-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 2e67a4adabe58ab12d317ae6318c0a2fac29da7d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866943"
---
# <a name="istrue-operator-visual-basic"></a>IsTrue-Operator (Visual Basic)

Bestimmt, ob ein Ausdruck ist `True` .  
  
 Sie können nicht `IsTrue` explizit in Ihrem Code aufzurufen, der Visual Basic Compiler kann es jedoch zum Generieren von Code aus `OrElse` Klauseln verwenden. Wenn Sie eine Klasse oder Struktur definieren und dann eine Variable dieses Typs in einer- `OrElse` Klausel verwenden, müssen Sie `IsTrue` für diese Klasse oder Struktur definieren.  
  
 Der Compiler betrachtet die `IsTrue` `IsFalse` Operatoren und als ein *übereinstimmendes Paar*. Dies bedeutet, dass Sie, wenn Sie einen von Ihnen definieren, auch den anderen definieren müssen.  
  
## <a name="compiler-use-of-istrue"></a>Compilerverwendung von IsTrue  

 Wenn Sie eine Klasse oder Struktur definiert haben, können Sie eine Variable dieses Typs in einer-,-,- `For` `If` oder- `Else If` `While` Anweisung oder in einer- `When` Klausel verwenden. Wenn Sie dies tun, benötigt der Compiler einen Operator, der den Typ in einen-Wert konvertiert, `Boolean` damit eine Bedingung getestet werden kann. Er sucht in der folgenden Reihenfolge nach einem passenden Operator:  
  
1. Ein erweiterter Konvertierungs Operator von der Klasse oder Struktur zu `Boolean` .  
  
2. Ein erweiterter Konvertierungs Operator von der Klasse oder Struktur zu `Boolean?` .  
  
3. Der `IsTrue` Operator für die Klasse oder Struktur.  
  
4. Eine einschränkende Konvertierung in `Boolean?` , die keine Konvertierung von `Boolean` in einschließt `Boolean?` .  
  
5. Ein einschränkende Konvertierungs Operator von der Klasse oder Struktur zu `Boolean` .  
  
 Wenn Sie keine Konvertierung in `Boolean` oder einen Operator definiert haben `IsTrue` , signalisiert der Compiler einen Fehler.  
  
> [!NOTE]
> Der `IsTrue` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn der Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  

 Im folgenden Codebeispiel wird die Gliederung einer-Struktur definiert, die Definitionen für die `IsFalse` `IsTrue` Operatoren und enthält.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IsFalse-Operator](isfalse-operator.md)
- [Vorgehensweise: Definieren eines Operators](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [OrElse-Operator](orelse-operator.md)
