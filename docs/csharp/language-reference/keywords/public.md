---
title: Schlüsselwort „public“ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: b2e09bdb16d6128d69a3eb33cf2cffd4cba60376
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2018
ms.locfileid: "43518185"
---
# <a name="public-c-reference"></a><span data-ttu-id="67475-102">public (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="67475-102">public (C# Reference)</span></span>

<span data-ttu-id="67475-103">Das Schlüsselwort `public` ist ein Zugriffsmodifizierer für Typen und Typmember.</span><span class="sxs-lookup"><span data-stu-id="67475-103">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="67475-104">Der öffentlicher Zugriff ist die eingeschränkteste Zugriffsebene.</span><span class="sxs-lookup"><span data-stu-id="67475-104">Public access is the most permissive access level.</span></span> <span data-ttu-id="67475-105">Es gibt keine Einschränkungen für den Zugriff auf öffentliche Member, wie im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="67475-105">There are no restrictions on accessing public members, as in this example:</span></span>

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

<span data-ttu-id="67475-106">Unter [Access Modifiers (Zugriffsmodifizierer)](../../programming-guide/classes-and-structs/access-modifiers.md) und [Accessibility Levels (Zugriffsebenen)](accessibility-levels.md) finden Sie weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="67475-106">See [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](accessibility-levels.md) for more information.</span></span>

## <a name="example"></a><span data-ttu-id="67475-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="67475-107">Example</span></span>

<span data-ttu-id="67475-108">Im folgenden Beispiel werden zwei Klassen deklariert, `PointTest` und `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="67475-108">In the following example, two classes are declared, `PointTest` and `MainClass`.</span></span> <span data-ttu-id="67475-109">Auf die öffentlichen Member `x` und `y` von `PointTest` wird direkt von `MainClass` zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="67475-109">The public members `x` and `y` of `PointTest` are accessed directly from `MainClass`.</span></span>

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

<span data-ttu-id="67475-110">Wenn Sie die Zugriffsebene `public` auf [private](private.md) (privat) oder [protected](protected.md) (geschützt) festlegen, wird die folgende Fehlermeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="67475-110">If you change the `public` access level to [private](private.md) or [protected](protected.md), you will get the error message:</span></span>

<span data-ttu-id="67475-111">'PointTest.y' is inaccessible due to its protection level (Der Zugriff auf ‚PointTest.y‘ ist aufgrund der Sicherheitsebene nicht möglich).</span><span class="sxs-lookup"><span data-stu-id="67475-111">'PointTest.y' is inaccessible due to its protection level.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="67475-112">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="67475-112">C# language specification</span></span>  

<span data-ttu-id="67475-113">Weitere Informationen finden Sie unter [Deklarierte Barrierefreiheit](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="67475-113">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="67475-114">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="67475-114">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="67475-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67475-115">See also</span></span>

- [<span data-ttu-id="67475-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="67475-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="67475-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="67475-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="67475-118">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="67475-118">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="67475-119">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="67475-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="67475-120">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="67475-120">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="67475-121">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="67475-121">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="67475-122">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="67475-122">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="67475-123">private</span><span class="sxs-lookup"><span data-stu-id="67475-123">private</span></span>](private.md)
- [<span data-ttu-id="67475-124">protected</span><span class="sxs-lookup"><span data-stu-id="67475-124">protected</span></span>](protected.md)
- [<span data-ttu-id="67475-125">internal</span><span class="sxs-lookup"><span data-stu-id="67475-125">internal</span></span>](internal.md)