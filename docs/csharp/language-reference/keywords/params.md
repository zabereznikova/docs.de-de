---
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
ms.openlocfilehash: 77d7fd19ff57f80f401191027e2fae95026e1966
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738845"
---
# <a name="params-c-reference"></a><span data-ttu-id="d9e9e-102">params (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d9e9e-102">params (C# Reference)</span></span>

<span data-ttu-id="d9e9e-103">Mithilfe des Schlüsselworts `params` kann ein [Methodenparameter](method-parameters.md) angegeben werden, der eine variable Anzahl von Argumenten akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="d9e9e-103">By using the `params` keyword, you can specify a [method parameter](method-parameters.md) that takes a variable number of arguments.</span></span> <span data-ttu-id="d9e9e-104">Der Parametertyp muss ein eindimensionales Array sein.</span><span class="sxs-lookup"><span data-stu-id="d9e9e-104">The parameter type must be a single-dimensional array.</span></span>

<span data-ttu-id="d9e9e-105">Nach dem `params`-Schlüsselwort sind keine zusätzlichen Parameter in einer Methodendeklaration zugelassen. Gleichzeitig ist nur ein `params`-Schlüsselwort in einer Methodendeklaration zulässig.</span><span class="sxs-lookup"><span data-stu-id="d9e9e-105">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>

<span data-ttu-id="d9e9e-106">Wenn der deklarierte Typ des `params`-Parameters kein eindimensionales Array ist, tritt der Compilerfehler [CS0225](../../misc/cs0225.md) auf.</span><span class="sxs-lookup"><span data-stu-id="d9e9e-106">If the declared type of the `params` parameter is not a single-dimensional array, compiler error [CS0225](../../misc/cs0225.md) occurs.</span></span>

<span data-ttu-id="d9e9e-107">Wenn Sie eine Methode mit einem `params`-Parameter aufrufen, können Sie Folgendes übergeben:</span><span class="sxs-lookup"><span data-stu-id="d9e9e-107">When you call a method with a `params` parameter, you can pass in:</span></span>

- <span data-ttu-id="d9e9e-108">Eine durch Trennzeichen getrennte Liste von Argumenten des Typs der Arrayelemente</span><span class="sxs-lookup"><span data-stu-id="d9e9e-108">A comma-separated list of arguments of the type of the array elements.</span></span>
- <span data-ttu-id="d9e9e-109">Ein Array aus Argumenten des angegebenen Typs</span><span class="sxs-lookup"><span data-stu-id="d9e9e-109">An array of arguments of the specified type.</span></span>
- <span data-ttu-id="d9e9e-110">Keine Argumente.</span><span class="sxs-lookup"><span data-stu-id="d9e9e-110">No arguments.</span></span> <span data-ttu-id="d9e9e-111">Wenn Sie keine Argumente senden, ist die Länge der `params`-Liste 0 (null).</span><span class="sxs-lookup"><span data-stu-id="d9e9e-111">If you send no arguments, the length of the `params` list is zero.</span></span>

## <a name="example"></a><span data-ttu-id="d9e9e-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d9e9e-112">Example</span></span>

<span data-ttu-id="d9e9e-113">Im folgenden Beispiel werden verschiedene Methoden veranschaulicht, in denen Argumente an einen `params`-Parameter gesendet werden können.</span><span class="sxs-lookup"><span data-stu-id="d9e9e-113">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="d9e9e-114">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="d9e9e-114">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="d9e9e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9e9e-115">See also</span></span>

- [<span data-ttu-id="d9e9e-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="d9e9e-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d9e9e-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d9e9e-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d9e9e-118">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d9e9e-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="d9e9e-119">Methodenparameter</span><span class="sxs-lookup"><span data-stu-id="d9e9e-119">Method Parameters</span></span>](method-parameters.md)
