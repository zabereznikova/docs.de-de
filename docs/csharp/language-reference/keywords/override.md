---
description: override-Modifizierer – C#-Referenz
title: override-Modifizierer – C#-Referenz
ms.date: 10/22/2020
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: 618200183348e68a4600adb9592a635f61f6a875
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434880"
---
# <a name="override-c-reference"></a><span data-ttu-id="3033d-103">override (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="3033d-103">override (C# reference)</span></span>

<span data-ttu-id="3033d-104">Der `override`-Modifizierer wird benötigt, um die abstrakte oder virtuelle Implementierung einer geerbten Methode, Eigenschaft, eines Indexers oder Ereignisses zu erweitern oder ändern.</span><span class="sxs-lookup"><span data-stu-id="3033d-104">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>

<span data-ttu-id="3033d-105">Im folgenden Beispiel muss die `Square`-Klasse eine überschriebene Implementierung von `GetArea` bereitstellen, weil `GetArea` von der abstrakten Klasse `Shape` geerbt wird:</span><span class="sxs-lookup"><span data-stu-id="3033d-105">In the following example, the `Square` class must provide an overridden implementation of `GetArea` because `GetArea` is inherited from the abstract `Shape` class:</span></span>

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

<span data-ttu-id="3033d-106">Eine `override`-Methode stellt eine neue Implementierung der Methode bereit, die von einer Basisklasse geerbt wurde.</span><span class="sxs-lookup"><span data-stu-id="3033d-106">An `override` method provides a new implementation of the method inherited from a base class.</span></span> <span data-ttu-id="3033d-107">Die Methode, die durch eine `override`-Deklaration überschrieben wird, wird als die überschriebene Basismethode bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3033d-107">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="3033d-108">Eine `override`-Methode muss dieselbe Signatur wie die überschriebene Basismethode haben.</span><span class="sxs-lookup"><span data-stu-id="3033d-108">An `override` method must have the same signature as the overridden base method.</span></span> <span data-ttu-id="3033d-109">Ab C# 9.0 unterstützen `override`-Methoden kovariante Rückgabetypen.</span><span class="sxs-lookup"><span data-stu-id="3033d-109">Beginning with C# 9.0, `override` methods support covariant return types.</span></span> <span data-ttu-id="3033d-110">Dies bedeutet, dass der Rückgabetyp einer `override`-Methode vom Rückgabetyp der entsprechenden Basismethode abgeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3033d-110">In particular, the return type of an `override` method can derive from the return type of the corresponding base method.</span></span> <span data-ttu-id="3033d-111">In C# 8.0 und früher müssen die Rückgabetypen einer `override`-Methode und die der überschriebenen Basismethode identisch sein.</span><span class="sxs-lookup"><span data-stu-id="3033d-111">In C# 8.0 and earlier, the return types of an `override` method and the overridden base method must be the same.</span></span>

<span data-ttu-id="3033d-112">Sie können keine nicht virtuelle oder statische Methode überschreiben.</span><span class="sxs-lookup"><span data-stu-id="3033d-112">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="3033d-113">Die überschriebene Basismethode muss `virtual`, `abstract` oder `override` sein.</span><span class="sxs-lookup"><span data-stu-id="3033d-113">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="3033d-114">Ein `override`-Deklaration kann nicht die Erreichbarkeit auf die `virtual` Methode ändern.</span><span class="sxs-lookup"><span data-stu-id="3033d-114">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="3033d-115">Sowohl die Methode `override` als auch `virtual` müssen den gleichen [Zugriffsebenenmodifizierer](access-modifiers.md) besitzen.</span><span class="sxs-lookup"><span data-stu-id="3033d-115">Both the `override` method and the `virtual` method must have the same [access level modifier](access-modifiers.md).</span></span>

<span data-ttu-id="3033d-116">Sie können die Modifizierer `new`, `static` oder `virtual` nicht verwenden, um eine `override`-Methode zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3033d-116">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>

<span data-ttu-id="3033d-117">Eine überschreibende Eigenschaftsdeklaration muss genau denselben Zugriffsmodifizierer, Typ und Namen wie die geerbte Eigenschaft angeben.</span><span class="sxs-lookup"><span data-stu-id="3033d-117">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property.</span></span> <span data-ttu-id="3033d-118">Ab C# 9.0 unterstützen schreibgeschützte überschreibende Eigenschaften kovariante Rückgabetypen.</span><span class="sxs-lookup"><span data-stu-id="3033d-118">Beginning with C# 9.0, read-only overriding properties support covariant return types.</span></span> <span data-ttu-id="3033d-119">Die überschriebene Eigenschaft muss `virtual`, `abstract` oder `override` entsprechen.</span><span class="sxs-lookup"><span data-stu-id="3033d-119">The overridden property must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="3033d-120">Weitere Informationen zur Verwendung des `override`-Schlüsselworts finden Sie unter [Versionsverwaltung mit den Schlüsselwörtern „override“ und „new“](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) und [Wann müssen die Schlüsselwörter „override“ und „new“ verwendet werden?](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="3033d-120">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span> <span data-ttu-id="3033d-121">Weitere Informationen zur Vererbung in C# finden Sie unter [Vererbung](../../programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="3033d-121">For information about inheritance, see [Inheritance](../../programming-guide/classes-and-structs/inheritance.md).</span></span>

## <a name="example"></a><span data-ttu-id="3033d-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3033d-122">Example</span></span>

<span data-ttu-id="3033d-123">In diesem Beispiel wird eine Basisklasse namens `Employee` und eine abgeleitete Klasse namens `SalesEmployee` definiert.</span><span class="sxs-lookup"><span data-stu-id="3033d-123">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="3033d-124">Die `SalesEmployee`-Klasse enthält ein zusätzliches Feld `salesbonus`, und überschreibt die `CalculatePay`-Methode, um dies zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="3033d-124">The `SalesEmployee` class includes an extra field, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="3033d-125">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="3033d-125">C# language specification</span></span>

<span data-ttu-id="3033d-126">Weitere Informationen finden Sie im Abschnitt [override-Methoden](~/_csharplang/spec/classes.md#override-methods) der [Sprachspezifikation für C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="3033d-126">For more information, see the [Override methods](~/_csharplang/spec/classes.md#override-methods) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="3033d-127">Weitere Informationen zu kovarianten Rückgabetypen finden Sie im [Hinweis zum Featurevorschlag](~/_csharplang/proposals/csharp-9.0/covariant-returns.md).</span><span class="sxs-lookup"><span data-stu-id="3033d-127">For more information about covariant return types, see the [feature proposal note](~/_csharplang/proposals/csharp-9.0/covariant-returns.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3033d-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3033d-128">See also</span></span>

- [<span data-ttu-id="3033d-129">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="3033d-129">C# reference</span></span>](../index.md)
- [<span data-ttu-id="3033d-130">Vererbung</span><span class="sxs-lookup"><span data-stu-id="3033d-130">Inheritance</span></span>](../../programming-guide/classes-and-structs/inheritance.md)
- [<span data-ttu-id="3033d-131">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="3033d-131">C# keywords</span></span>](index.md)
- [<span data-ttu-id="3033d-132">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="3033d-132">Modifiers</span></span>](index.md)
- [<span data-ttu-id="3033d-133">abstract</span><span class="sxs-lookup"><span data-stu-id="3033d-133">abstract</span></span>](abstract.md)
- [<span data-ttu-id="3033d-134">virtual</span><span class="sxs-lookup"><span data-stu-id="3033d-134">virtual</span></span>](virtual.md)
- [<span data-ttu-id="3033d-135">new (Modifizierer)</span><span class="sxs-lookup"><span data-stu-id="3033d-135">new (modifier)</span></span>](new-modifier.md)
- [<span data-ttu-id="3033d-136">Polymorphismus</span><span class="sxs-lookup"><span data-stu-id="3033d-136">Polymorphism</span></span>](../../programming-guide/classes-and-structs/polymorphism.md)
