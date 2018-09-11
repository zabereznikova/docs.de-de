---
title: Schlüsselwort „public“ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: 84a3bc49b6eea047d518edc01dab7f2301854b6a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43518185"
---
# <a name="public-c-reference"></a><span data-ttu-id="3001e-102">public (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="3001e-102">public (C# Reference)</span></span>

<span data-ttu-id="3001e-103">Das Schlüsselwort `public` ist ein Zugriffsmodifizierer für Typen und Typmember.</span><span class="sxs-lookup"><span data-stu-id="3001e-103">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="3001e-104">Der öffentlicher Zugriff ist die eingeschränkteste Zugriffsebene.</span><span class="sxs-lookup"><span data-stu-id="3001e-104">Public access is the most permissive access level.</span></span> <span data-ttu-id="3001e-105">Es gibt keine Einschränkungen für den Zugriff auf öffentliche Member, wie im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="3001e-105">There are no restrictions on accessing public members, as in this example:</span></span>

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

<span data-ttu-id="3001e-106">Unter [Access Modifiers (Zugriffsmodifizierer)](../../programming-guide/classes-and-structs/access-modifiers.md) und [Accessibility Levels (Zugriffsebenen)](accessibility-levels.md) finden Sie weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="3001e-106">See [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](accessibility-levels.md) for more information.</span></span>

## <a name="example"></a><span data-ttu-id="3001e-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3001e-107">Example</span></span>

<span data-ttu-id="3001e-108">Im folgenden Beispiel werden zwei Klassen deklariert, `PointTest` und `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="3001e-108">In the following example, two classes are declared, `PointTest` and `MainClass`.</span></span> <span data-ttu-id="3001e-109">Auf die öffentlichen Member `x` und `y` von `PointTest` wird direkt von `MainClass` zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="3001e-109">The public members `x` and `y` of `PointTest` are accessed directly from `MainClass`.</span></span>

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

<span data-ttu-id="3001e-110">Wenn Sie die Zugriffsebene `public` auf [private](private.md) (privat) oder [protected](protected.md) (geschützt) festlegen, wird die folgende Fehlermeldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="3001e-110">If you change the `public` access level to [private](private.md) or [protected](protected.md), you will get the error message:</span></span>

<span data-ttu-id="3001e-111">'PointTest.y' is inaccessible due to its protection level (Der Zugriff auf ‚PointTest.y‘ ist aufgrund der Sicherheitsebene nicht möglich).</span><span class="sxs-lookup"><span data-stu-id="3001e-111">'PointTest.y' is inaccessible due to its protection level.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3001e-112">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="3001e-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="3001e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3001e-113">See also</span></span>

- [<span data-ttu-id="3001e-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="3001e-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3001e-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3001e-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3001e-116">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="3001e-116">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="3001e-117">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="3001e-117">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="3001e-118">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="3001e-118">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="3001e-119">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="3001e-119">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="3001e-120">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="3001e-120">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="3001e-121">private</span><span class="sxs-lookup"><span data-stu-id="3001e-121">private</span></span>](private.md)
- [<span data-ttu-id="3001e-122">protected</span><span class="sxs-lookup"><span data-stu-id="3001e-122">protected</span></span>](protected.md)
- [<span data-ttu-id="3001e-123">internal</span><span class="sxs-lookup"><span data-stu-id="3001e-123">internal</span></span>](internal.md)