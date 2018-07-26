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
ms.openlocfilehash: d7e0094d0f60aa201ae7229983f3e4b9764d2cbc
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37960194"
---
# <a name="params-c-reference"></a><span data-ttu-id="e2d5f-102">params (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e2d5f-102">params (C# Reference)</span></span>
<span data-ttu-id="e2d5f-103">Mithilfe des Schlüsselworts `params` kann ein [Methodenparameter](../../../csharp/language-reference/keywords/method-parameters.md) angegeben werden, der eine variable Anzahl von Argumenten akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="e2d5f-103">By using the `params` keyword, you can specify a [method parameter](../../../csharp/language-reference/keywords/method-parameters.md) that takes a variable number of arguments.</span></span>  
  
 <span data-ttu-id="e2d5f-104">Sie können eine durch Trennzeichen getrennte Liste der Argumente des in der Parameterdeklaration angegebenen Typs oder ein Array der Argumente des angegebenen Typs senden.</span><span class="sxs-lookup"><span data-stu-id="e2d5f-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="e2d5f-105">Sie können auch auf das Senden von Argumenten verzichten.</span><span class="sxs-lookup"><span data-stu-id="e2d5f-105">You also can send no arguments.</span></span> <span data-ttu-id="e2d5f-106">Wenn Sie keine Argumente senden, ist die Länge der `params`-Liste 0 (null).</span><span class="sxs-lookup"><span data-stu-id="e2d5f-106">If you send no arguments, the length of the `params` list is zero.</span></span>  
  
 <span data-ttu-id="e2d5f-107">Nach dem `params`-Schlüsselwort sind keine zusätzlichen Parameter in einer Methodendeklaration zugelassen. Gleichzeitig ist nur ein `params`-Schlüsselwort in einer Methodendeklaration zulässig.</span><span class="sxs-lookup"><span data-stu-id="e2d5f-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2d5f-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e2d5f-108">Example</span></span>  
 <span data-ttu-id="e2d5f-109">Im folgenden Beispiel werden verschiedene Methoden veranschaulicht, in denen Argumente an einen `params`-Parameter gesendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e2d5f-109">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>  
  
 [!code-csharp[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="e2d5f-110">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="e2d5f-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e2d5f-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2d5f-111">See Also</span></span>  
 [<span data-ttu-id="e2d5f-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="e2d5f-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e2d5f-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e2d5f-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e2d5f-114">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="e2d5f-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="e2d5f-115">Methodenparameter</span><span class="sxs-lookup"><span data-stu-id="e2d5f-115">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
