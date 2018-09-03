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
# <a name="params-c-reference"></a><span data-ttu-id="eb3b1-102">params (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="eb3b1-102">params (C# Reference)</span></span>
<span data-ttu-id="eb3b1-103">Mithilfe des Schlüsselworts `params` kann ein [Methodenparameter](../../../csharp/language-reference/keywords/method-parameters.md) angegeben werden, der eine variable Anzahl von Argumenten akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="eb3b1-103">By using the `params` keyword, you can specify a [method parameter](../../../csharp/language-reference/keywords/method-parameters.md) that takes a variable number of arguments.</span></span>  
  
 <span data-ttu-id="eb3b1-104">Sie können eine durch Trennzeichen getrennte Liste der Argumente des in der Parameterdeklaration angegebenen Typs oder ein Array der Argumente des angegebenen Typs senden.</span><span class="sxs-lookup"><span data-stu-id="eb3b1-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="eb3b1-105">Sie können auch auf das Senden von Argumenten verzichten.</span><span class="sxs-lookup"><span data-stu-id="eb3b1-105">You also can send no arguments.</span></span> <span data-ttu-id="eb3b1-106">Wenn Sie keine Argumente senden, ist die Länge der `params`-Liste 0 (null).</span><span class="sxs-lookup"><span data-stu-id="eb3b1-106">If you send no arguments, the length of the `params` list is zero.</span></span>  
  
 <span data-ttu-id="eb3b1-107">Nach dem `params`-Schlüsselwort sind keine zusätzlichen Parameter in einer Methodendeklaration zugelassen. Gleichzeitig ist nur ein `params`-Schlüsselwort in einer Methodendeklaration zulässig.</span><span class="sxs-lookup"><span data-stu-id="eb3b1-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>  
 
 <span data-ttu-id="eb3b1-108">Der deklarierte Typ des `params`-Parameters muss wie im folgenden Beispiel gezeigt ein eindimensionales Array sein.</span><span class="sxs-lookup"><span data-stu-id="eb3b1-108">The declared type of the `params` parameter must be a single-dimensional array, as the following example shows.</span></span> <span data-ttu-id="eb3b1-109">Andernfalls tritt der Compilerfehler [CS0225](../../../csharp/misc/cs0225.md) ein.</span><span class="sxs-lookup"><span data-stu-id="eb3b1-109">Otherwise, a compiler error [CS0225](../../../csharp/misc/cs0225.md) occurs.</span></span>
  
## <a name="example"></a><span data-ttu-id="eb3b1-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eb3b1-110">Example</span></span>  
 <span data-ttu-id="eb3b1-111">Im folgenden Beispiel werden verschiedene Methoden veranschaulicht, in denen Argumente an einen `params`-Parameter gesendet werden können.</span><span class="sxs-lookup"><span data-stu-id="eb3b1-111">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>  
  
 [!code-csharp[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="eb3b1-112">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="eb3b1-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="eb3b1-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb3b1-113">See Also</span></span>  
 [<span data-ttu-id="eb3b1-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="eb3b1-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="eb3b1-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="eb3b1-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="eb3b1-116">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="eb3b1-116">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="eb3b1-117">Methodenparameter</span><span class="sxs-lookup"><span data-stu-id="eb3b1-117">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
