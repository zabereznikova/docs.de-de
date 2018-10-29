---
title: Schlüsselwort „protected“ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: cc3c8f81edb68fb26be560c8635e30dfd6e7b372
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50183177"
---
# <a name="protected-c-reference"></a><span data-ttu-id="092c1-102">protected (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="092c1-102">protected (C# Reference)</span></span>

<span data-ttu-id="092c1-103">Das `protected`-Schlüsselwort ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="092c1-103">The `protected` keyword is a member access modifier.</span></span>

 > <span data-ttu-id="092c1-104">Auf dieser Seite wird der Zugriff auf `protected` behandelt.</span><span class="sxs-lookup"><span data-stu-id="092c1-104">This page covers `protected` access.</span></span> <span data-ttu-id="092c1-105">Das Schlüsselwort `protected` ist auch Teil der Zugriffsmodifizierer [`protected internal`](protected-internal.md) und [`private protected`](private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="092c1-105">The `protected` keyword is also part of the [`protected internal`](protected-internal.md) and [`private protected`](private-protected.md) access modifiers.</span></span>

<span data-ttu-id="092c1-106">Auf einen geschützten Member kann innerhalb seiner Klasse und von Instanzen abgeleiteter Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="092c1-106">A protected member is accessible within its class and by derived class instances.</span></span>

<span data-ttu-id="092c1-107">Einen Vergleich von `protected` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="092c1-107">For a comparison of `protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="092c1-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="092c1-108">Example</span></span>

<span data-ttu-id="092c1-109">Auf einen geschützten Member einer Basisklasse kann in einer abgeleiteten Klasse zugegriffen werden, nur wenn der Zugriff über den Typ der abgeleiteten Klasse erfolgt.</span><span class="sxs-lookup"><span data-stu-id="092c1-109">A protected member of a base class is accessible in a derived class only if the access occurs through the derived class type.</span></span> <span data-ttu-id="092c1-110">Sehen Sie sich z.B. folgenden Codeabschnitt an:</span><span class="sxs-lookup"><span data-stu-id="092c1-110">For example, consider the following code segment:</span></span>

[!code-csharp[csrefKeywordsModifiers#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#11)]

<span data-ttu-id="092c1-111">Die Anweisung `a.x = 10` generiert einen Fehler, da sie innerhalb der statischen Main-Methode erstellt wird und keine Instanz der Klasse B ist.</span><span class="sxs-lookup"><span data-stu-id="092c1-111">The statement `a.x = 10` generates an error because it is made within the static method Main, and not an instance of class B.</span></span>

<span data-ttu-id="092c1-112">Strukturmember können nicht geschützt werden, da die Struktur nicht vererbt werden kann.</span><span class="sxs-lookup"><span data-stu-id="092c1-112">Struct members cannot be protected because the struct cannot be inherited.</span></span>

## <a name="example"></a><span data-ttu-id="092c1-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="092c1-113">Example</span></span>

<span data-ttu-id="092c1-114">In diesem Beispiel wird die `DerivedPoint`-Klasse von `Point` abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="092c1-114">In this example, the class `DerivedPoint` is derived from `Point`.</span></span> <span data-ttu-id="092c1-115">Daher können Sie direkt von der abgeleiteten Klasse auf die geschützten Member der Basisklasse zugreifen.</span><span class="sxs-lookup"><span data-stu-id="092c1-115">Therefore, you can access the protected members of the base class directly from the derived class.</span></span>

[!code-csharp[csrefKeywordsModifiers#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#12)]  

<span data-ttu-id="092c1-116">Wenn Sie die Zugriffsebenen von `x` und `y` auf [private](private.md) ändern, wird der Compiler die Fehlermeldungen anzeigen:</span><span class="sxs-lookup"><span data-stu-id="092c1-116">If you change the access levels of `x` and `y` to [private](private.md), the compiler will issue the error messages:</span></span>

`'Point.y' is inaccessible due to its protection level.`

`'Point.x' is inaccessible due to its protection level.`

## <a name="c-language-specification"></a><span data-ttu-id="092c1-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="092c1-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="092c1-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="092c1-118">See also</span></span>

- [<span data-ttu-id="092c1-119">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="092c1-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="092c1-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="092c1-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="092c1-121">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="092c1-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="092c1-122">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="092c1-122">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="092c1-123">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="092c1-123">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="092c1-124">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="092c1-124">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="092c1-125">public</span><span class="sxs-lookup"><span data-stu-id="092c1-125">public</span></span>](public.md)
- [<span data-ttu-id="092c1-126">private</span><span class="sxs-lookup"><span data-stu-id="092c1-126">private</span></span>](private.md)
- [<span data-ttu-id="092c1-127">internal</span><span class="sxs-lookup"><span data-stu-id="092c1-127">internal</span></span>](internal.md)
- <span data-ttu-id="092c1-128">[Sicherheitsaspekte für interne virtuelle Schlüsselwörter](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="092c1-128">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>