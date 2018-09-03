---
title: params (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: 692c2f61ae99f1c1c8e04a5a1bcad08814d286fe
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2018
ms.locfileid: "42752151"
---
# <a name="params-c-reference"></a>params (C#-Referenz)
Mithilfe des Schlüsselworts `params` kann ein [Methodenparameter](../../../csharp/language-reference/keywords/method-parameters.md) angegeben werden, der eine variable Anzahl von Argumenten akzeptiert.  
  
 Sie können eine durch Trennzeichen getrennte Liste der Argumente des in der Parameterdeklaration angegebenen Typs oder ein Array der Argumente des angegebenen Typs senden. Sie können auch auf das Senden von Argumenten verzichten. Wenn Sie keine Argumente senden, ist die Länge der `params`-Liste 0 (null).  
  
 Nach dem `params`-Schlüsselwort sind keine zusätzlichen Parameter in einer Methodendeklaration zugelassen. Gleichzeitig ist nur ein `params`-Schlüsselwort in einer Methodendeklaration zulässig.  
 
 Der deklarierte Typ des `params`-Parameters muss wie im folgenden Beispiel gezeigt ein eindimensionales Array sein. Andernfalls tritt der Compilerfehler [CS0225](../../../csharp/misc/cs0225.md) ein.
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden verschiedene Methoden veranschaulicht, in denen Argumente an einen `params`-Parameter gesendet werden können.  
  
 [!code-csharp[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
 [Methodenparameter](../../../csharp/language-reference/keywords/method-parameters.md)
