---
title: params-Schlüsselwort – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: f462ccc2421fef3ea111d263ec035a701cf04775
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173548"
---
# <a name="params-c-reference"></a><span data-ttu-id="85084-102">params (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="85084-102">params (C# Reference)</span></span>

<span data-ttu-id="85084-103">Mithilfe des Schlüsselworts `params` kann ein [Methodenparameter](method-parameters.md) angegeben werden, der eine variable Anzahl von Argumenten akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="85084-103">By using the `params` keyword, you can specify a [method parameter](method-parameters.md) that takes a variable number of arguments.</span></span>

<span data-ttu-id="85084-104">Sie können eine durch Trennzeichen getrennte Liste der Argumente des in der Parameterdeklaration angegebenen Typs oder ein Array der Argumente des angegebenen Typs senden.</span><span class="sxs-lookup"><span data-stu-id="85084-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="85084-105">Sie können auch auf das Senden von Argumenten verzichten.</span><span class="sxs-lookup"><span data-stu-id="85084-105">You also can send no arguments.</span></span> <span data-ttu-id="85084-106">Wenn Sie keine Argumente senden, ist die Länge der `params`-Liste 0 (null).</span><span class="sxs-lookup"><span data-stu-id="85084-106">If you send no arguments, the length of the `params` list is zero.</span></span>

<span data-ttu-id="85084-107">Nach dem `params`-Schlüsselwort sind keine zusätzlichen Parameter in einer Methodendeklaration zugelassen. Gleichzeitig ist nur ein `params`-Schlüsselwort in einer Methodendeklaration zulässig.</span><span class="sxs-lookup"><span data-stu-id="85084-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>

<span data-ttu-id="85084-108">Der deklarierte Typ des `params`-Parameters muss wie im folgenden Beispiel gezeigt ein eindimensionales Array sein.</span><span class="sxs-lookup"><span data-stu-id="85084-108">The declared type of the `params` parameter must be a single-dimensional array, as the following example shows.</span></span> <span data-ttu-id="85084-109">Andernfalls tritt der Compilerfehler [CS0225](../../misc/cs0225.md) ein.</span><span class="sxs-lookup"><span data-stu-id="85084-109">Otherwise, a compiler error [CS0225](../../misc/cs0225.md) occurs.</span></span>

## <a name="example"></a><span data-ttu-id="85084-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="85084-110">Example</span></span>

<span data-ttu-id="85084-111">Im folgenden Beispiel werden verschiedene Methoden veranschaulicht, in denen Argumente an einen `params`-Parameter gesendet werden können.</span><span class="sxs-lookup"><span data-stu-id="85084-111">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="85084-112">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="85084-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="85084-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85084-113">See also</span></span>

- [<span data-ttu-id="85084-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="85084-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="85084-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="85084-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="85084-116">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="85084-116">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="85084-117">Methodenparameter</span><span class="sxs-lookup"><span data-stu-id="85084-117">Method Parameters</span></span>](method-parameters.md)
