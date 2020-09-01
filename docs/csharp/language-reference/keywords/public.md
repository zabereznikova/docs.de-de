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
ms.openlocfilehash: 26edaf7538d11d082a4b8863228213c3ebc46937
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122341"
---
# <a name="public-c-reference"></a><span data-ttu-id="22cf1-103">public (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="22cf1-103">public (C# Reference)</span></span>

<span data-ttu-id="22cf1-104">Das Schlüsselwort `public` ist ein Zugriffsmodifizierer für Typen und Typmember.</span><span class="sxs-lookup"><span data-stu-id="22cf1-104">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="22cf1-105">Der öffentlicher Zugriff ist die eingeschränkteste Zugriffsebene.</span><span class="sxs-lookup"><span data-stu-id="22cf1-105">Public access is the most permissive access level.</span></span> <span data-ttu-id="22cf1-106">Es gibt keine Einschränkungen für den Zugriff auf öffentliche Member, wie im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="22cf1-106">There are no restrictions on accessing public members, as in this example:</span></span>

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

<span data-ttu-id="22cf1-107">Unter [Access Modifiers (Zugriffsmodifizierer)](../../programming-guide/classes-and-structs/access-modifiers.md) und [Accessibility Levels (Zugriffsebenen)](accessibility-levels.md) finden Sie weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="22cf1-107">See [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](accessibility-levels.md) for more information.</span></span>

## <a name="example"></a><span data-ttu-id="22cf1-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="22cf1-108">Example</span></span>

<span data-ttu-id="22cf1-109">Im folgenden Beispiel werden zwei Klassen deklariert, `PointTest` und `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="22cf1-109">In the following example, two classes are declared, `PointTest` and `MainClass`.</span></span> <span data-ttu-id="22cf1-110">Auf die öffentlichen Member `x` und `y` von `PointTest` wird direkt von `MainClass` zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="22cf1-110">The public members `x` and `y` of `PointTest` are accessed directly from `MainClass`.</span></span>

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

<span data-ttu-id="22cf1-111">Wenn Sie die Zugriffsebene `public` auf [private](private.md) (privat) oder [protected](protected.md) (geschützt) festlegen, wird die folgende Fehlermeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="22cf1-111">If you change the `public` access level to [private](private.md) or [protected](protected.md), you will get the error message:</span></span>

<span data-ttu-id="22cf1-112">'PointTest.y' is inaccessible due to its protection level (Der Zugriff auf ‚PointTest.y‘ ist aufgrund der Sicherheitsebene nicht möglich).</span><span class="sxs-lookup"><span data-stu-id="22cf1-112">'PointTest.y' is inaccessible due to its protection level.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="22cf1-113">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="22cf1-113">C# language specification</span></span>  

<span data-ttu-id="22cf1-114">Weitere Informationen finden Sie unter [Deklarierte Barrierefreiheit](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="22cf1-114">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="22cf1-115">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="22cf1-115">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="22cf1-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22cf1-116">See also</span></span>

- [<span data-ttu-id="22cf1-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="22cf1-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="22cf1-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="22cf1-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="22cf1-119">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="22cf1-119">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="22cf1-120">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="22cf1-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="22cf1-121">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="22cf1-121">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="22cf1-122">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="22cf1-122">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="22cf1-123">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="22cf1-123">Modifiers</span></span>](index.md)
- [<span data-ttu-id="22cf1-124">private</span><span class="sxs-lookup"><span data-stu-id="22cf1-124">private</span></span>](private.md)
- [<span data-ttu-id="22cf1-125">protected</span><span class="sxs-lookup"><span data-stu-id="22cf1-125">protected</span></span>](protected.md)
- [<span data-ttu-id="22cf1-126">internal</span><span class="sxs-lookup"><span data-stu-id="22cf1-126">internal</span></span>](internal.md)
