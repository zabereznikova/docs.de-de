---
title: Ausführen von Ausdrucksbaumstrukturen (C#)
description: Hier erfahren Sie, wie Sie eine Ausdrucksbaumstruktur ausführen, um einen Wert zurückzugeben oder eine Aktion wie das Aufrufen einer Methode auszuführen.
ms.date: 07/20/2015
ms.assetid: b8c40db5-2464-4bb9-9001-8c2bc7f006c5
ms.openlocfilehash: 9e306da545ba6c6275f36b8f6dd4e98bb91ed54e
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105621"
---
# <a name="how-to-execute-expression-trees-c"></a>Ausführen von Ausdrucksbaumstrukturen (C#)
In diesem Thema erfahren Sie, wie eine Ausdrucksbaumstruktur ausgeführt wird. Die Ausführung einer Ausdrucksbaumstruktur gibt möglicherweise einen Wert zurück. Es kann jedoch auch nur eine Aktion ausgeführt werden, z.B. das Aufrufen einer Methode.  
  
 Nur Ausdrucksbaumstrukturen, die Lambdaausdrücke darstellen, können ausgeführt werden. Ausdrucksbaumstrukturen, die Lambdaausdrücke darstellen, sind vom Typ <xref:System.Linq.Expressions.LambdaExpression> oder <xref:System.Linq.Expressions.Expression%601>. Um diese Ausdrucksbaumstruktur auszuführen, rufen Sie die <xref:System.Linq.Expressions.LambdaExpression.Compile%2A>-Methode auf, um einen ausführbaren Delegaten zu erstellen und diesen anschließend aufzurufen.  
  
> [!NOTE]
> Wenn der Typ des Delegaten nicht bekannt ist, d.h. wenn der Lambdaausdruck vom Typ <xref:System.Linq.Expressions.LambdaExpression> und nicht <xref:System.Linq.Expressions.Expression%601> ist, müssen Sie die <xref:System.Delegate.DynamicInvoke%2A>-Methode auf dem Delegaten aufrufen, anstatt sie direkt aufzurufen.  
  
 Wenn eine Ausdrucksbaumstruktur keinen Lambdaausdruck darstellt,können Sie einen neuen Lambdaausdruck erstellen, der die ursprüngliche Ausdrucksbaumstruktur als Textkörper hat, indem Sie die <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29>-Methode aufrufen. Anschließend können Sie den Lambdaausdruck ausführen, wie weiter oben in diesem Abschnitt beschrieben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine Ausdrucksbaumstruktur ausgeführt wird, die das Potenzieren darstellt, indem ein Lambdaausdruck erstellt und ausgeführt wird. Das Ergebnis, das die potenzierte Zahl darstellt, wird angezeigt.  
  
```csharp  
// The expression tree to execute.  
BinaryExpression be = Expression.Power(Expression.Constant(2D), Expression.Constant(3D));  
  
// Create a lambda expression.  
Expression<Func<double>> le = Expression.Lambda<Func<double>>(be);  
  
// Compile the lambda expression.  
Func<double> compiledExpression = le.Compile();  
  
// Execute the lambda expression.  
double result = compiledExpression();  
  
// Display the result.  
Console.WriteLine(result);  
  
// This code produces the following output:  
// 8  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
- Binden Sie den System.Linq.Expressions-Namespace ein.  
  
## <a name="see-also"></a>Siehe auch

- [Ausdrucksbaumstrukturen (C#)](./index.md)
- [Ändern von Ausdrucksbaumstrukturen (C#)](./how-to-modify-expression-trees.md)
