---
description: protected-Schlüsselwort – C#-Referenz
title: protected-Schlüsselwort – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: d8d9a75bb5e07816adaa8d09c96cee8a240130fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688912"
---
# <a name="protected-c-reference"></a><span data-ttu-id="a3d9c-103">protected (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="a3d9c-103">protected (C# Reference)</span></span>

<span data-ttu-id="a3d9c-104">Das `protected`-Schlüsselwort ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="a3d9c-104">The `protected` keyword is a member access modifier.</span></span>

> [!NOTE]
> <span data-ttu-id="a3d9c-105">Auf dieser Seite wird der Zugriff auf `protected` behandelt.</span><span class="sxs-lookup"><span data-stu-id="a3d9c-105">This page covers `protected` access.</span></span> <span data-ttu-id="a3d9c-106">Das Schlüsselwort `protected` ist auch Teil der Zugriffsmodifizierer [`protected internal`](protected-internal.md) und [`private protected`](private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="a3d9c-106">The `protected` keyword is also part of the [`protected internal`](protected-internal.md) and [`private protected`](private-protected.md) access modifiers.</span></span>

<span data-ttu-id="a3d9c-107">Auf einen geschützten Member kann innerhalb seiner Klasse und von Instanzen abgeleiteter Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="a3d9c-107">A protected member is accessible within its class and by derived class instances.</span></span>

<span data-ttu-id="a3d9c-108">Einen Vergleich von `protected` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a3d9c-108">For a comparison of `protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="a3d9c-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a3d9c-109">Example</span></span>

<span data-ttu-id="a3d9c-110">Auf einen geschützten Member einer Basisklasse kann in einer abgeleiteten Klasse zugegriffen werden, nur wenn der Zugriff über den Typ der abgeleiteten Klasse erfolgt.</span><span class="sxs-lookup"><span data-stu-id="a3d9c-110">A protected member of a base class is accessible in a derived class only if the access occurs through the derived class type.</span></span> <span data-ttu-id="a3d9c-111">Sehen Sie sich z.B. folgenden Codeabschnitt an:</span><span class="sxs-lookup"><span data-stu-id="a3d9c-111">For example, consider the following code segment:</span></span>

[!code-csharp[csrefKeywordsModifiers#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#11)]

<span data-ttu-id="a3d9c-112">Die Anweisung `a.x = 10` generiert einen Fehler, da sie innerhalb der statischen Main-Methode erstellt wird und keine Instanz der Klasse B ist.</span><span class="sxs-lookup"><span data-stu-id="a3d9c-112">The statement `a.x = 10` generates an error because it is made within the static method Main, and not an instance of class B.</span></span>

<span data-ttu-id="a3d9c-113">Strukturmember können nicht geschützt werden, da die Struktur nicht vererbt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a3d9c-113">Struct members cannot be protected because the struct cannot be inherited.</span></span>

## <a name="example"></a><span data-ttu-id="a3d9c-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a3d9c-114">Example</span></span>

<span data-ttu-id="a3d9c-115">In diesem Beispiel wird die `DerivedPoint`-Klasse von `Point` abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="a3d9c-115">In this example, the class `DerivedPoint` is derived from `Point`.</span></span> <span data-ttu-id="a3d9c-116">Daher können Sie direkt von der abgeleiteten Klasse auf die geschützten Member der Basisklasse zugreifen.</span><span class="sxs-lookup"><span data-stu-id="a3d9c-116">Therefore, you can access the protected members of the base class directly from the derived class.</span></span>

[!code-csharp[csrefKeywordsModifiers#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#12)]  

<span data-ttu-id="a3d9c-117">Wenn Sie die Zugriffsebenen von `x` und `y` auf [private](private.md) ändern, wird der Compiler die Fehlermeldungen anzeigen:</span><span class="sxs-lookup"><span data-stu-id="a3d9c-117">If you change the access levels of `x` and `y` to [private](private.md), the compiler will issue the error messages:</span></span>

`'Point.y' is inaccessible due to its protection level.`

`'Point.x' is inaccessible due to its protection level.`

## <a name="c-language-specification"></a><span data-ttu-id="a3d9c-118">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="a3d9c-118">C# language specification</span></span>  

<span data-ttu-id="a3d9c-119">Weitere Informationen finden Sie unter [Deklarierte Barrierefreiheit](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="a3d9c-119">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="a3d9c-120">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="a3d9c-120">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3d9c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3d9c-121">See also</span></span>

- [<span data-ttu-id="a3d9c-122">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="a3d9c-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a3d9c-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a3d9c-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a3d9c-124">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="a3d9c-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a3d9c-125">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="a3d9c-125">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="a3d9c-126">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="a3d9c-126">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="a3d9c-127">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="a3d9c-127">Modifiers</span></span>](index.md)
- [<span data-ttu-id="a3d9c-128">public</span><span class="sxs-lookup"><span data-stu-id="a3d9c-128">public</span></span>](public.md)
- [<span data-ttu-id="a3d9c-129">private</span><span class="sxs-lookup"><span data-stu-id="a3d9c-129">private</span></span>](private.md)
- [<span data-ttu-id="a3d9c-130">internal</span><span class="sxs-lookup"><span data-stu-id="a3d9c-130">internal</span></span>](internal.md)
- <span data-ttu-id="a3d9c-131">[Sicherheitsaspekte für interne virtuelle Schlüsselwörter](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a3d9c-131">[Security concerns for internal virtual keywords](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
