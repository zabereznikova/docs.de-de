---
title: Operator % (C#-Referenz)
ms.date: 04/04/2018
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
ms.openlocfilehash: b906feb22aaec97e58da562b615baae01f3e0719
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a>Operator % (C#-Referenz)
Der Restoperator `%` berechnet den Rest nach der Division seines ersten Operanden durch den zweiten. Alle numerischen Typen besitzen vordefinierte Restoperatoren. 
  
## <a name="remarks"></a>Hinweise  
 Die Formel `a % b` gibt stets einen Wert im Bereich `(-b, b)` zurück – ausschließlich (es kann nie `b` oder `-b` zurückgegeben werden), wobei das Vorzeichen des Dividenden beibehalten wird. Bei der Ganzzahldivision entspricht der Restoperator der Regel `a % b = a - (a / b) * b`.
  
 Dies ist nicht zu verwechseln mit dem kanonischen Modulo, der bei der ganzzahligen Division eine ähnliche Regel erfüllt und Werte im Bereich `[0, b)` zurückgibt. C# umfasst keinen Operator für den kanonischen Modulo. Das Verhalten für positive Dividenden ist jedoch dasselbe.
  
 Benutzerdefinierte Typen können den Operator `%` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)). Wenn ein binärer Operator überladen ist, wird der zugehörige Zuweisungsoperator, sofern er vorhanden ist, auch implizit überladen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/remainder-operator_1.cs)]  
  
## <a name="comments"></a>Kommentare  
 Beachten Sie die Rundungsfehler im Zusammenhang mit dem double-Typ.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
