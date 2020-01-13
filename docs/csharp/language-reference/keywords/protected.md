---
title: protected-Schlüsselwort – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: bec619d4f49bd26daa742c18c830909c14948adf
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713182"
---
# <a name="protected-c-reference"></a><span data-ttu-id="1a2cd-102">protected (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="1a2cd-102">protected (C# Reference)</span></span>

<span data-ttu-id="1a2cd-103">Das `protected`-Schlüsselwort ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="1a2cd-103">The `protected` keyword is a member access modifier.</span></span>

 > <span data-ttu-id="1a2cd-104">Auf dieser Seite wird der Zugriff auf `protected` behandelt.</span><span class="sxs-lookup"><span data-stu-id="1a2cd-104">This page covers `protected` access.</span></span> <span data-ttu-id="1a2cd-105">Das Schlüsselwort `protected` ist auch Teil der Zugriffsmodifizierer [`protected internal`](protected-internal.md) und [`private protected`](private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="1a2cd-105">The `protected` keyword is also part of the [`protected internal`](protected-internal.md) and [`private protected`](private-protected.md) access modifiers.</span></span>

<span data-ttu-id="1a2cd-106">Auf einen geschützten Member kann innerhalb seiner Klasse und von Instanzen abgeleiteter Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="1a2cd-106">A protected member is accessible within its class and by derived class instances.</span></span>

<span data-ttu-id="1a2cd-107">Einen Vergleich von `protected` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="1a2cd-107">For a comparison of `protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="1a2cd-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1a2cd-108">Example</span></span>

<span data-ttu-id="1a2cd-109">Auf einen geschützten Member einer Basisklasse kann in einer abgeleiteten Klasse zugegriffen werden, nur wenn der Zugriff über den Typ der abgeleiteten Klasse erfolgt.</span><span class="sxs-lookup"><span data-stu-id="1a2cd-109">A protected member of a base class is accessible in a derived class only if the access occurs through the derived class type.</span></span> <span data-ttu-id="1a2cd-110">Sehen Sie sich z.B. folgenden Codeabschnitt an:</span><span class="sxs-lookup"><span data-stu-id="1a2cd-110">For example, consider the following code segment:</span></span>

[!code-csharp[csrefKeywordsModifiers#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#11)]

<span data-ttu-id="1a2cd-111">Die Anweisung `a.x = 10` generiert einen Fehler, da sie innerhalb der statischen Main-Methode erstellt wird und keine Instanz der Klasse B ist.</span><span class="sxs-lookup"><span data-stu-id="1a2cd-111">The statement `a.x = 10` generates an error because it is made within the static method Main, and not an instance of class B.</span></span>

<span data-ttu-id="1a2cd-112">Strukturmember können nicht geschützt werden, da die Struktur nicht vererbt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1a2cd-112">Struct members cannot be protected because the struct cannot be inherited.</span></span>

## <a name="example"></a><span data-ttu-id="1a2cd-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1a2cd-113">Example</span></span>

<span data-ttu-id="1a2cd-114">In diesem Beispiel wird die `DerivedPoint`-Klasse von `Point` abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="1a2cd-114">In this example, the class `DerivedPoint` is derived from `Point`.</span></span> <span data-ttu-id="1a2cd-115">Daher können Sie direkt von der abgeleiteten Klasse auf die geschützten Member der Basisklasse zugreifen.</span><span class="sxs-lookup"><span data-stu-id="1a2cd-115">Therefore, you can access the protected members of the base class directly from the derived class.</span></span>

[!code-csharp[csrefKeywordsModifiers#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#12)]  

<span data-ttu-id="1a2cd-116">Wenn Sie die Zugriffsebenen von `x` und `y` auf [private](private.md) ändern, wird der Compiler die Fehlermeldungen anzeigen:</span><span class="sxs-lookup"><span data-stu-id="1a2cd-116">If you change the access levels of `x` and `y` to [private](private.md), the compiler will issue the error messages:</span></span>

`'Point.y' is inaccessible due to its protection level.`

`'Point.x' is inaccessible due to its protection level.`

## <a name="c-language-specification"></a><span data-ttu-id="1a2cd-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="1a2cd-117">C# language specification</span></span>  

<span data-ttu-id="1a2cd-118">Weitere Informationen finden Sie unter [Deklarierte Barrierefreiheit](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="1a2cd-118">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="1a2cd-119">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="1a2cd-119">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a2cd-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a2cd-120">See also</span></span>

- [<span data-ttu-id="1a2cd-121">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="1a2cd-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1a2cd-122">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="1a2cd-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1a2cd-123">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="1a2cd-123">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="1a2cd-124">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="1a2cd-124">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="1a2cd-125">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="1a2cd-125">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="1a2cd-126">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="1a2cd-126">Modifiers</span></span>](index.md)
- [<span data-ttu-id="1a2cd-127">public</span><span class="sxs-lookup"><span data-stu-id="1a2cd-127">public</span></span>](public.md)
- [<span data-ttu-id="1a2cd-128">private</span><span class="sxs-lookup"><span data-stu-id="1a2cd-128">private</span></span>](private.md)
- [<span data-ttu-id="1a2cd-129">internal</span><span class="sxs-lookup"><span data-stu-id="1a2cd-129">internal</span></span>](internal.md)
- <span data-ttu-id="1a2cd-130">[Sicherheitsaspekte für interne virtuelle Schlüsselwörter](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1a2cd-130">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
