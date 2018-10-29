---
title: Schlüsselwort „params“ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: 089e31f3aad12c2303619e2a1998d0d6a5a0ad86
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48844097"
---
# <a name="params-c-reference"></a><span data-ttu-id="fd6c9-102">params (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="fd6c9-102">params (C# Reference)</span></span>

<span data-ttu-id="fd6c9-103">Mithilfe des Schlüsselworts `params` kann ein [Methodenparameter](method-parameters.md) angegeben werden, der eine variable Anzahl von Argumenten akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="fd6c9-103">By using the `params` keyword, you can specify a [method parameter](method-parameters.md) that takes a variable number of arguments.</span></span>

<span data-ttu-id="fd6c9-104">Sie können eine durch Trennzeichen getrennte Liste der Argumente des in der Parameterdeklaration angegebenen Typs oder ein Array der Argumente des angegebenen Typs senden.</span><span class="sxs-lookup"><span data-stu-id="fd6c9-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="fd6c9-105">Sie können auch auf das Senden von Argumenten verzichten.</span><span class="sxs-lookup"><span data-stu-id="fd6c9-105">You also can send no arguments.</span></span> <span data-ttu-id="fd6c9-106">Wenn Sie keine Argumente senden, ist die Länge der `params`-Liste 0 (null).</span><span class="sxs-lookup"><span data-stu-id="fd6c9-106">If you send no arguments, the length of the `params` list is zero.</span></span>

<span data-ttu-id="fd6c9-107">Nach dem `params`-Schlüsselwort sind keine zusätzlichen Parameter in einer Methodendeklaration zugelassen. Gleichzeitig ist nur ein `params`-Schlüsselwort in einer Methodendeklaration zulässig.</span><span class="sxs-lookup"><span data-stu-id="fd6c9-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>

<span data-ttu-id="fd6c9-108">Der deklarierte Typ des `params`-Parameters muss wie im folgenden Beispiel gezeigt ein eindimensionales Array sein.</span><span class="sxs-lookup"><span data-stu-id="fd6c9-108">The declared type of the `params` parameter must be a single-dimensional array, as the following example shows.</span></span> <span data-ttu-id="fd6c9-109">Andernfalls tritt der Compilerfehler [CS0225](../../misc/cs0225.md) ein.</span><span class="sxs-lookup"><span data-stu-id="fd6c9-109">Otherwise, a compiler error [CS0225](../../misc/cs0225.md) occurs.</span></span>

## <a name="example"></a><span data-ttu-id="fd6c9-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fd6c9-110">Example</span></span>

<span data-ttu-id="fd6c9-111">Im folgenden Beispiel werden verschiedene Methoden veranschaulicht, in denen Argumente an einen `params`-Parameter gesendet werden können.</span><span class="sxs-lookup"><span data-stu-id="fd6c9-111">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)] 

## <a name="c-language-specification"></a><span data-ttu-id="fd6c9-112">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="fd6c9-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="fd6c9-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd6c9-113">See also</span></span>

- [<span data-ttu-id="fd6c9-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="fd6c9-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fd6c9-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="fd6c9-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fd6c9-116">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="fd6c9-116">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="fd6c9-117">Methodenparameter</span><span class="sxs-lookup"><span data-stu-id="fd6c9-117">Method Parameters</span></span>](method-parameters.md)