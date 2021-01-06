---
description: public-Schlüsselwort – C#-Referenz
title: public-Schlüsselwort – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: 90c1d2a1d9efcdf57f914f4318bf7a743d3f37ec
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938467"
---
# <a name="public-c-reference"></a><span data-ttu-id="0fec6-103">public (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="0fec6-103">public (C# Reference)</span></span>

<span data-ttu-id="0fec6-104">Das Schlüsselwort `public` ist ein Zugriffsmodifizierer für Typen und Typmember.</span><span class="sxs-lookup"><span data-stu-id="0fec6-104">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="0fec6-105">Der öffentlicher Zugriff ist die eingeschränkteste Zugriffsebene.</span><span class="sxs-lookup"><span data-stu-id="0fec6-105">Public access is the most permissive access level.</span></span> <span data-ttu-id="0fec6-106">Es gibt keine Einschränkungen für den Zugriff auf öffentliche Member, wie im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="0fec6-106">There are no restrictions on accessing public members, as in this example:</span></span>

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

<span data-ttu-id="0fec6-107">Unter [Access Modifiers (Zugriffsmodifizierer)](../../programming-guide/classes-and-structs/access-modifiers.md) und [Accessibility Levels (Zugriffsebenen)](accessibility-levels.md) finden Sie weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="0fec6-107">See [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](accessibility-levels.md) for more information.</span></span>

## <a name="example"></a><span data-ttu-id="0fec6-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0fec6-108">Example</span></span>

<span data-ttu-id="0fec6-109">Im folgenden Beispiel werden zwei Klassen deklariert, `PointTest` und `Program`.</span><span class="sxs-lookup"><span data-stu-id="0fec6-109">In the following example, two classes are declared, `PointTest` and `Program`.</span></span> <span data-ttu-id="0fec6-110">Auf die öffentlichen Member `x` und `y` von `PointTest` wird direkt von `Program` zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="0fec6-110">The public members `x` and `y` of `PointTest` are accessed directly from `Program`.</span></span>

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

<span data-ttu-id="0fec6-111">Wenn Sie die Zugriffsebene `public` auf [private](private.md) (privat) oder [protected](protected.md) (geschützt) festlegen, wird die folgende Fehlermeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="0fec6-111">If you change the `public` access level to [private](private.md) or [protected](protected.md), you will get the error message:</span></span>

<span data-ttu-id="0fec6-112">'PointTest.y' is inaccessible due to its protection level (Der Zugriff auf ‚PointTest.y‘ ist aufgrund der Sicherheitsebene nicht möglich).</span><span class="sxs-lookup"><span data-stu-id="0fec6-112">'PointTest.y' is inaccessible due to its protection level.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0fec6-113">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="0fec6-113">C# language specification</span></span>  

<span data-ttu-id="0fec6-114">Weitere Informationen finden Sie unter [Deklarierte Barrierefreiheit](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="0fec6-114">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="0fec6-115">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="0fec6-115">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="0fec6-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0fec6-116">See also</span></span>

- [<span data-ttu-id="0fec6-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="0fec6-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0fec6-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0fec6-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0fec6-119">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="0fec6-119">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="0fec6-120">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="0fec6-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="0fec6-121">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="0fec6-121">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="0fec6-122">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="0fec6-122">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="0fec6-123">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="0fec6-123">Modifiers</span></span>](index.md)
- [<span data-ttu-id="0fec6-124">private</span><span class="sxs-lookup"><span data-stu-id="0fec6-124">private</span></span>](private.md)
- [<span data-ttu-id="0fec6-125">protected</span><span class="sxs-lookup"><span data-stu-id="0fec6-125">protected</span></span>](protected.md)
- [<span data-ttu-id="0fec6-126">internal</span><span class="sxs-lookup"><span data-stu-id="0fec6-126">internal</span></span>](internal.md)
