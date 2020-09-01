---
description: params-Schlüsselwort für Parameterarrays – C#-Referenz
title: params-Schlüsselwort für Parameterarrays – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
- parameter array
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: a2726c725508cd297001aaabddeff414704d1115
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134470"
---
# <a name="params-c-reference"></a><span data-ttu-id="c1b60-103">params (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c1b60-103">params (C# Reference)</span></span>

<span data-ttu-id="c1b60-104">Mithilfe des Schlüsselworts `params` kann ein [Methodenparameter](method-parameters.md) angegeben werden, der eine variable Anzahl von Argumenten akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="c1b60-104">By using the `params` keyword, you can specify a [method parameter](method-parameters.md) that takes a variable number of arguments.</span></span> <span data-ttu-id="c1b60-105">Der Parametertyp muss ein eindimensionales Array sein.</span><span class="sxs-lookup"><span data-stu-id="c1b60-105">The parameter type must be a single-dimensional array.</span></span>

<span data-ttu-id="c1b60-106">Nach dem `params`-Schlüsselwort sind keine zusätzlichen Parameter in einer Methodendeklaration zugelassen. Gleichzeitig ist nur ein `params`-Schlüsselwort in einer Methodendeklaration zulässig.</span><span class="sxs-lookup"><span data-stu-id="c1b60-106">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>

<span data-ttu-id="c1b60-107">Wenn der deklarierte Typ des `params`-Parameters kein eindimensionales Array ist, tritt der Compilerfehler [CS0225](../../misc/cs0225.md) auf.</span><span class="sxs-lookup"><span data-stu-id="c1b60-107">If the declared type of the `params` parameter is not a single-dimensional array, compiler error [CS0225](../../misc/cs0225.md) occurs.</span></span>

<span data-ttu-id="c1b60-108">Wenn Sie eine Methode mit einem `params`-Parameter aufrufen, können Sie Folgendes übergeben:</span><span class="sxs-lookup"><span data-stu-id="c1b60-108">When you call a method with a `params` parameter, you can pass in:</span></span>

- <span data-ttu-id="c1b60-109">Eine durch Trennzeichen getrennte Liste von Argumenten des Typs der Arrayelemente</span><span class="sxs-lookup"><span data-stu-id="c1b60-109">A comma-separated list of arguments of the type of the array elements.</span></span>
- <span data-ttu-id="c1b60-110">Ein Array aus Argumenten des angegebenen Typs</span><span class="sxs-lookup"><span data-stu-id="c1b60-110">An array of arguments of the specified type.</span></span>
- <span data-ttu-id="c1b60-111">Keine Argumente.</span><span class="sxs-lookup"><span data-stu-id="c1b60-111">No arguments.</span></span> <span data-ttu-id="c1b60-112">Wenn Sie keine Argumente senden, ist die Länge der `params`-Liste 0 (null).</span><span class="sxs-lookup"><span data-stu-id="c1b60-112">If you send no arguments, the length of the `params` list is zero.</span></span>

## <a name="example"></a><span data-ttu-id="c1b60-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c1b60-113">Example</span></span>

<span data-ttu-id="c1b60-114">Im folgenden Beispiel werden verschiedene Methoden veranschaulicht, in denen Argumente an einen `params`-Parameter gesendet werden können.</span><span class="sxs-lookup"><span data-stu-id="c1b60-114">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="c1b60-115">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="c1b60-115">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c1b60-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1b60-116">See also</span></span>

- [<span data-ttu-id="c1b60-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c1b60-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c1b60-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c1b60-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c1b60-119">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="c1b60-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c1b60-120">Methodenparameter</span><span class="sxs-lookup"><span data-stu-id="c1b60-120">Method Parameters</span></span>](method-parameters.md)
