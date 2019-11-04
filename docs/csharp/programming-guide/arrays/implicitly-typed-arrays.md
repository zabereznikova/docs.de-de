---
title: Implizit typisierte Arrays – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], implicitly-typed
- implicitly-typed arrays [C#]
- C# language, implicitly typed arrays
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
ms.openlocfilehash: ac47ec6e69b7910f474378eebd91d58c171a802e
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73419551"
---
# <a name="implicitly-typed-arrays-c-programming-guide"></a><span data-ttu-id="25cba-102">Implizit typisierte Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="25cba-102">Implicitly Typed Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="25cba-103">Sie können ein implizit typisiertes Array erstellen, in dem der Typ der Arrayinstanz von den im Arrayinitialisierer angegebenen Elementen abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="25cba-103">You can create an implicitly-typed array in which the type of the array instance is inferred from the elements specified in the array initializer.</span></span> <span data-ttu-id="25cba-104">Die Regeln für implizit typisierte Variablen gelten auch für implizit typisierte Arrays.</span><span class="sxs-lookup"><span data-stu-id="25cba-104">The rules for any implicitly-typed variable also apply to implicitly-typed arrays.</span></span> <span data-ttu-id="25cba-105">Weitere Informationen zu finden Sie unter [Implizit typisierte lokale Variablen](../classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="25cba-105">For more information, see [Implicitly Typed Local Variables](../classes-and-structs/implicitly-typed-local-variables.md).</span></span>

<span data-ttu-id="25cba-106">Implizit typisierte Arrays werden in der Regel in Abfrageausdrücken zusammen mit anonymen Typen sowie Objekt- und Auflistungsinitialisierern verwendet.</span><span class="sxs-lookup"><span data-stu-id="25cba-106">Implicitly-typed arrays are usually used in query expressions together with anonymous types and object and collection initializers.</span></span>

<span data-ttu-id="25cba-107">Die folgenden Beispiele zeigen, wie ein implizit typisiertes Array erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="25cba-107">The following examples show how to create an implicitly-typed array:</span></span>

[!code-csharp[csProgGuideLINQ#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#37)]

<span data-ttu-id="25cba-108">Beachten Sie im vorherigen Beispiel, dass bei implizit typisierten Arrays auf der linken Seite der Initialisierungsanweisung keine eckigen Klammern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="25cba-108">In the previous example, notice that with implicitly-typed arrays, no square brackets are used on the left side of the initialization statement.</span></span> <span data-ttu-id="25cba-109">Beachten Sie auch, dass verzweigte Arrays ebenso wie eindimensionale Arrays mithilfe von `new []` initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="25cba-109">Note also that jagged arrays are initialized by using `new []` just like single-dimension arrays.</span></span>

## <a name="implicitly-typed-arrays-in-object-initializers"></a><span data-ttu-id="25cba-110">Implizit typisierte Arrays in Objektinitialisierern</span><span class="sxs-lookup"><span data-stu-id="25cba-110">Implicitly-typed Arrays in Object Initializers</span></span>

<span data-ttu-id="25cba-111">Beim Erstellen eines anonymen Typs, der ein Array enthält, muss das Array im Objektinitialisierer des Typs implizit typisiert werden.</span><span class="sxs-lookup"><span data-stu-id="25cba-111">When you create an anonymous type that contains an array, the array must be implicitly typed in the type's object initializer.</span></span> <span data-ttu-id="25cba-112">Im folgenden Beispiel ist `contacts` ein implizit typisiertes Array aus anonymen Typen, von denen jeder ein Array mit dem Namen `PhoneNumbers` enthält.</span><span class="sxs-lookup"><span data-stu-id="25cba-112">In the following example, `contacts` is an implicitly-typed array of anonymous types, each of which contains an array named `PhoneNumbers`.</span></span> <span data-ttu-id="25cba-113">Beachten Sie, dass das Schlüsselwort `var` nicht in den Objektinitialisierern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="25cba-113">Note that the `var` keyword is not used inside the object initializers.</span></span>

[!code-csharp[csProgGuideLINQ#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#38)]

## <a name="see-also"></a><span data-ttu-id="25cba-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25cba-114">See also</span></span>

- [<span data-ttu-id="25cba-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="25cba-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="25cba-116">Implizit typisierte lokale Variablen</span><span class="sxs-lookup"><span data-stu-id="25cba-116">Implicitly Typed Local Variables</span></span>](../classes-and-structs/implicitly-typed-local-variables.md)
- [<span data-ttu-id="25cba-117">Arrays</span><span class="sxs-lookup"><span data-stu-id="25cba-117">Arrays</span></span>](./index.md)
- [<span data-ttu-id="25cba-118">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="25cba-118">Anonymous Types</span></span>](../classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="25cba-119">Objekt- und Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="25cba-119">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)
- [<span data-ttu-id="25cba-120">var</span><span class="sxs-lookup"><span data-stu-id="25cba-120">var</span></span>](../../language-reference/keywords/var.md)
- [<span data-ttu-id="25cba-121">LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="25cba-121">LINQ in C#</span></span>](../../linq/index.md)
