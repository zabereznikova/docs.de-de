---
title: override-Modifizierer – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: 6a8e79da3897e867fa3becab5fcfc70afe72e614
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244439"
---
# <a name="override-c-reference"></a><span data-ttu-id="d1463-102">override (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d1463-102">override (C# Reference)</span></span>

<span data-ttu-id="d1463-103">Der `override`-Modifizierer wird benötigt, um die abstrakte oder virtuelle Implementierung einer geerbten Methode, Eigenschaft, eines Indexers oder Ereignisses zu erweitern oder ändern.</span><span class="sxs-lookup"><span data-stu-id="d1463-103">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>

## <a name="example"></a><span data-ttu-id="d1463-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d1463-104">Example</span></span>

<span data-ttu-id="d1463-105">In diesem Beispiel muss die `Square`-Klasse eine überschriebene Implementierung von `Area` bereitstellen, da `Area` von der abstrakten `ShapesClass` geerbt wurde:</span><span class="sxs-lookup"><span data-stu-id="d1463-105">In this example, the `Square` class must provide an overridden implementation of `Area` because `Area` is inherited from the abstract `ShapesClass`:</span></span>

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

<span data-ttu-id="d1463-106">Eine `override`-Methode stellt eine neue Implementierung eines Members bereit, der von einer Basisklasse geerbt wurde.</span><span class="sxs-lookup"><span data-stu-id="d1463-106">An `override` method provides a new implementation of a member that is inherited from a base class.</span></span> <span data-ttu-id="d1463-107">Die Methode, die durch eine `override`-Deklaration überschrieben wird, wird als die überschriebene Basismethode bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d1463-107">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="d1463-108">Die überschriebene Basismethode muss die gleiche Signatur wie die `override`-Methode haben.</span><span class="sxs-lookup"><span data-stu-id="d1463-108">The overridden base method must have the same signature as the `override` method.</span></span> <span data-ttu-id="d1463-109">Weitere Informationen zur Vererbung in C# finden Sie unter [Vererbung](../../programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="d1463-109">For information about inheritance, see [Inheritance](../../programming-guide/classes-and-structs/inheritance.md).</span></span>

<span data-ttu-id="d1463-110">Sie können keine nicht virtuelle oder statische Methode überschreiben.</span><span class="sxs-lookup"><span data-stu-id="d1463-110">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="d1463-111">Die überschriebene Basismethode muss `virtual`, `abstract` oder `override` sein.</span><span class="sxs-lookup"><span data-stu-id="d1463-111">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="d1463-112">Ein `override`-Deklaration kann nicht die Erreichbarkeit auf die `virtual` Methode ändern.</span><span class="sxs-lookup"><span data-stu-id="d1463-112">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="d1463-113">Sowohl die Methode `override` als auch `virtual` müssen den gleichen [Zugriffsebenenmodifizierer](access-modifiers.md) besitzen.</span><span class="sxs-lookup"><span data-stu-id="d1463-113">Both the `override` method and the `virtual` method must have the same [access level modifier](access-modifiers.md).</span></span>

<span data-ttu-id="d1463-114">Sie können die Modifizierer `new`, `static` oder `virtual` nicht verwenden, um eine `override`-Methode zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d1463-114">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>

<span data-ttu-id="d1463-115">Eine überschreibende Eigenschaftsdeklaration muss genau den selben Zugriffsmodifizierertyp und -namen wie die geerbte Eigenschaft angeben, und die überschriebene Eigenschaft muss `virtual`, `abstract` oder `override` sein.</span><span class="sxs-lookup"><span data-stu-id="d1463-115">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property, and the overridden property must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="d1463-116">Weitere Informationen zur Verwendung des `override`-Schlüsselworts finden Sie unter [Versionsverwaltung mit den Schlüsselwörtern „override“ und „new“](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) und [Wann müssen die Schlüsselwörter „override“ und „new“ verwendet werden?](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="d1463-116">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>

## <a name="example"></a><span data-ttu-id="d1463-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d1463-117">Example</span></span>

<span data-ttu-id="d1463-118">In diesem Beispiel wird eine Basisklasse namens `Employee` und eine abgeleitete Klasse namens `SalesEmployee` definiert.</span><span class="sxs-lookup"><span data-stu-id="d1463-118">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="d1463-119">Die `SalesEmployee`-Klasse enthält ein zusätzliches Feld `salesbonus`, und überschreibt die `CalculatePay`-Methode, um dies zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="d1463-119">The `SalesEmployee` class includes an extra field, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="d1463-120">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="d1463-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="d1463-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1463-121">See also</span></span>

- [<span data-ttu-id="d1463-122">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="d1463-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d1463-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d1463-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d1463-124">Vererbung</span><span class="sxs-lookup"><span data-stu-id="d1463-124">Inheritance</span></span>](../../programming-guide/classes-and-structs/inheritance.md)
- [<span data-ttu-id="d1463-125">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d1463-125">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="d1463-126">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="d1463-126">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="d1463-127">abstract</span><span class="sxs-lookup"><span data-stu-id="d1463-127">abstract</span></span>](abstract.md)
- [<span data-ttu-id="d1463-128">virtual</span><span class="sxs-lookup"><span data-stu-id="d1463-128">virtual</span></span>](virtual.md)
- [<span data-ttu-id="d1463-129">new</span><span class="sxs-lookup"><span data-stu-id="d1463-129">new</span></span>](new.md)
- [<span data-ttu-id="d1463-130">Polymorphismus</span><span class="sxs-lookup"><span data-stu-id="d1463-130">Polymorphism</span></span>](../../programming-guide/classes-and-structs/polymorphism.md)
