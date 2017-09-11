---
title: params (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- params_CSharpKeyword
- params
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5999911b96d17c710096e74c8f3da65223e778fc
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="params-c-reference"></a><span data-ttu-id="99b2e-102">params (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="99b2e-102">params (C# Reference)</span></span>
<span data-ttu-id="99b2e-103">Mithilfe des Schlüsselworts `params` kann ein [Methodenparameter](../../../csharp/language-reference/keywords/method-parameters.md) angegeben werden, der eine variable Anzahl von Argumenten akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="99b2e-103">By using the `params` keyword, you can specify a [method parameter](../../../csharp/language-reference/keywords/method-parameters.md) that takes a variable number of arguments.</span></span>  
  
 <span data-ttu-id="99b2e-104">Sie können eine durch Trennzeichen getrennte Liste der Argumente des in der Parameterdeklaration angegebenen Typs oder ein Array der Argumente des angegebenen Typs senden.</span><span class="sxs-lookup"><span data-stu-id="99b2e-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="99b2e-105">Sie können auch auf das Senden von Argumenten verzichten.</span><span class="sxs-lookup"><span data-stu-id="99b2e-105">You also can send no arguments.</span></span> <span data-ttu-id="99b2e-106">Wenn Sie keine Argumente senden, ist die Länge der `params`-Liste 0 (null).</span><span class="sxs-lookup"><span data-stu-id="99b2e-106">If you send no arguments, the length of the `params` list is zero.</span></span>  
  
 <span data-ttu-id="99b2e-107">Nach dem `params`-Schlüsselwort sind keine zusätzlichen Parameter in einer Methodendeklaration zugelassen. Gleichzeitig ist nur ein `params`-Schlüsselwort in einer Methodendeklaration zulässig.</span><span class="sxs-lookup"><span data-stu-id="99b2e-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99b2e-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="99b2e-108">Example</span></span>  
 <span data-ttu-id="99b2e-109">Im folgenden Beispiel werden verschiedene Methoden veranschaulicht, in denen Argumente an einen `params`-Parameter gesendet werden können.</span><span class="sxs-lookup"><span data-stu-id="99b2e-109">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>  
  
 <span data-ttu-id="99b2e-110">[!code-cs[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="99b2e-110">[!code-cs[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="99b2e-111">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="99b2e-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="99b2e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99b2e-112">See Also</span></span>  
 <span data-ttu-id="99b2e-113">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="99b2e-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="99b2e-114">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="99b2e-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="99b2e-115">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="99b2e-115">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="99b2e-116">Methodenparameter</span><span class="sxs-lookup"><span data-stu-id="99b2e-116">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)

