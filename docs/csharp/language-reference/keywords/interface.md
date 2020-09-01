---
description: ':::no-loc text=interface::: (C#-Referenz)'
title: interface – C#-Referenz
ms.date: 01/17/2020
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: 24f95e828522f467c519c0c8a7ba9410aa97af4e
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134587"
---
# <a name="no-loc-textinterface-c-reference"></a><span data-ttu-id="21dee-103">:::no-loc text="interface"::: (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="21dee-103">:::no-loc text="interface"::: (C# Reference)</span></span>

<span data-ttu-id="21dee-104">Eine Schnittstelle definiert einen Vertrag.</span><span class="sxs-lookup"><span data-stu-id="21dee-104">An interface defines a contract.</span></span> <span data-ttu-id="21dee-105">Jede [`class`](class.md) oder [`struct`](../builtin-types/struct.md), die diesen Vertrag implementiert, muss eine Implementierung der in der Schnittstelle definierten Member bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="21dee-105">Any [`class`](class.md) or [`struct`](../builtin-types/struct.md) that implements that contract must provide an implementation of the members defined in the interface.</span></span> <span data-ttu-id="21dee-106">Ab C# 8.0 kann eine Schnittstelle eine Standardimplementierung für Member definieren.</span><span class="sxs-lookup"><span data-stu-id="21dee-106">Beginning with C# 8.0, an interface may define a default implementation for members.</span></span> <span data-ttu-id="21dee-107">Sie kann auch [`static`](static.md)-Member definieren, um eine einzelne Implementierung für allgemeine Funktionen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="21dee-107">It may also define [`static`](static.md) members in order to provide a single implementation for common functionality.</span></span>

<span data-ttu-id="21dee-108">Im folgenden Beispiel muss die Klasse `ImplementationClass` eine Methode mit dem Namen `SampleMethod` implementieren, die keine Parameter hat und `void` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="21dee-108">In the following example, class `ImplementationClass` must implement a method named `SampleMethod` that has no parameters and returns `void`.</span></span>

<span data-ttu-id="21dee-109">Weitere Informationen und Beispiele finden Sie unter [Schnittstellen](../../programming-guide/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="21dee-109">For more information and examples, see [Interfaces](../../programming-guide/interfaces/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="21dee-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21dee-110">Example</span></span>

[!code-csharp[csrefKeywordsTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#14)]

<span data-ttu-id="21dee-111">Eine Schnittstelle kann ein Member eines Namespaces oder einer Klasse sein.</span><span class="sxs-lookup"><span data-stu-id="21dee-111">An interface can be a member of a namespace or a class.</span></span> <span data-ttu-id="21dee-112">Eine Schnittstellendeklaration kann Deklarationen der folgenden Member enthalten (Signaturen ohne Implementierungen):</span><span class="sxs-lookup"><span data-stu-id="21dee-112">An interface declaration can contain declarations (signatures without any implementation) of the following members:</span></span>

- [<span data-ttu-id="21dee-113">Methoden</span><span class="sxs-lookup"><span data-stu-id="21dee-113">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
- [<span data-ttu-id="21dee-114">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="21dee-114">Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)
- [<span data-ttu-id="21dee-115">Indexer</span><span class="sxs-lookup"><span data-stu-id="21dee-115">Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)
- [<span data-ttu-id="21dee-116">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="21dee-116">Events</span></span>](event.md)

<span data-ttu-id="21dee-117">Diese vorangehenden Memberdeklarationen enthalten in der Regel keinen Text.</span><span class="sxs-lookup"><span data-stu-id="21dee-117">These preceding member declarations typically do not contain a body.</span></span> <span data-ttu-id="21dee-118">Ab C# 8.0 kann ein Schnittstellenmember einen Text deklarieren.</span><span class="sxs-lookup"><span data-stu-id="21dee-118">Beginning with C# 8.0, an interface member may declare a body.</span></span> <span data-ttu-id="21dee-119">Dies wird als *Standardimplementierung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="21dee-119">This is called a *default implementation*.</span></span> <span data-ttu-id="21dee-120">Member mit Text ermöglichen der Schnittstelle, eine „Standardimplementierung“ für Klassen und Strukturen bereitzustellen, die keine überschreibende Implementierung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="21dee-120">Members with bodies permit the interface to provide a "default" implementation for classes and structs that don't provide an overriding implementation.</span></span> <span data-ttu-id="21dee-121">Außerdem kann eine Schnittstelle ab C# 8.0 Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="21dee-121">In addition, beginning with C# 8.0, an interface may include:</span></span>

- [<span data-ttu-id="21dee-122">Konstanten</span><span class="sxs-lookup"><span data-stu-id="21dee-122">Constants</span></span>](const.md)
- [<span data-ttu-id="21dee-123">Operatoren</span><span class="sxs-lookup"><span data-stu-id="21dee-123">Operators</span></span>](../operators/operator-overloading.md)
- <span data-ttu-id="21dee-124">[Statischer Konstruktor](../../programming-guide/classes-and-structs/constructors.md#static-constructors)</span><span class="sxs-lookup"><span data-stu-id="21dee-124">[Static constructor](../../programming-guide/classes-and-structs/constructors.md#static-constructors).</span></span>
- [<span data-ttu-id="21dee-125">Geschachtelte Typen</span><span class="sxs-lookup"><span data-stu-id="21dee-125">Nested types</span></span>](../../programming-guide/classes-and-structs/nested-types.md)
- [<span data-ttu-id="21dee-126">Statische Felder, Methoden, Eigenschaften, Indexer und Ereignisse</span><span class="sxs-lookup"><span data-stu-id="21dee-126">Static fields, methods, properties, indexers, and events</span></span>](static.md)
- <span data-ttu-id="21dee-127">Memberdeklarationen, die die Syntax der explizite Schnittstellenimplementierung verwenden</span><span class="sxs-lookup"><span data-stu-id="21dee-127">Member declarations using the explicit interface implementation syntax.</span></span>
- <span data-ttu-id="21dee-128">Explizite Zugriffsmodifizierer (der Standardzugriff ist [`public`](access-modifiers.md))</span><span class="sxs-lookup"><span data-stu-id="21dee-128">Explicit access modifiers (the default access is [`public`](access-modifiers.md)).</span></span>

<span data-ttu-id="21dee-129">Schnittstellen dürfen keinen Instanzstatus enthalten.</span><span class="sxs-lookup"><span data-stu-id="21dee-129">Interfaces may not contain instance state.</span></span> <span data-ttu-id="21dee-130">Obwohl statische Felder jetzt zulässig sind, sind Instanzfelder in Schnittstellen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="21dee-130">While static fields are now permitted, instance fields are not permitted in interfaces.</span></span> <span data-ttu-id="21dee-131">[Automatische Eigenschaften von Instanzen](../../programming-guide/classes-and-structs/auto-implemented-properties.md) werden in Schnittstellen nicht unterstützt, da sie implizit ein ausgeblendetes Feld deklarieren würden.</span><span class="sxs-lookup"><span data-stu-id="21dee-131">[Instance auto-properties](../../programming-guide/classes-and-structs/auto-implemented-properties.md) are not supported in interfaces, as they would implicitly declare a hidden field.</span></span> <span data-ttu-id="21dee-132">Diese Regel hat eine fast unmerkliche Auswirkung auf Eigenschaftsdeklarationen.</span><span class="sxs-lookup"><span data-stu-id="21dee-132">This rule has a subtle effect on property declarations.</span></span> <span data-ttu-id="21dee-133">In einer Schnittstellendeklaration deklariert der folgende Code anders als bei `class` und `struct` keine automatisch implementierte Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="21dee-133">In an interface declaration, the following code does not declare an auto-implemented property as it does in a `class` or `struct`.</span></span> <span data-ttu-id="21dee-134">Stattdessen wird eine Eigenschaft deklariert, die keine Standardimplementierung hat, sondern in jedem Typ implementiert werden muss, der die Schnittstelle implementiert:</span><span class="sxs-lookup"><span data-stu-id="21dee-134">Instead, it declares a property that doesn't have a default implementation but must be implemented in any type that implements the interface:</span></span>

```csharp
public interface INamed
{
  public string Name {get; set;}
}
```

<span data-ttu-id="21dee-135">Eine Schnittstelle kann von einer oder mehreren Basisschnittstellen erben.</span><span class="sxs-lookup"><span data-stu-id="21dee-135">An interface can inherit from one or more base interfaces.</span></span> <span data-ttu-id="21dee-136">Wenn eine Schnittstelle [eine Methode überschreibt](override.md) die in einer Basisschnittstelle implementiert ist, muss sie die Syntax der [expliziten Schnittstellenimplementierung](../../programming-guide/interfaces/explicit-interface-implementation.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="21dee-136">When an interface [overrides a method](override.md) implemented in a base interface, it must use the [explicit interface implementation](../../programming-guide/interfaces/explicit-interface-implementation.md) syntax.</span></span>

<span data-ttu-id="21dee-137">Wenn eine Basistypliste sowohl eine Basisklasse als auch Schnittstellen umfasst, muss die Basisklasse zuerst in der Liste stehen.</span><span class="sxs-lookup"><span data-stu-id="21dee-137">When a base type list contains a base class and interfaces, the base class must come first in the list.</span></span>

<span data-ttu-id="21dee-138">Eine Klasse, die eine Schnittstelle implementiert, kann Member dieser Schnittstelle explizit implementieren.</span><span class="sxs-lookup"><span data-stu-id="21dee-138">A class that implements an interface can explicitly implement members of that interface.</span></span> <span data-ttu-id="21dee-139">Auf einen explizit implementierten Member kann nicht durch eine Klasseninstanz zugegriffen werden, sondern nur durch eine Schnittstelleninstanz.</span><span class="sxs-lookup"><span data-stu-id="21dee-139">An explicitly implemented member cannot be accessed through a class instance, but only through an instance of the interface.</span></span> <span data-ttu-id="21dee-140">Außerdem kann auf Standardschnittstellenmember nur über eine Instanz der Schnittstelle zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="21dee-140">In addition, default interface members can only be accessed through an instance of the interface.</span></span>

<span data-ttu-id="21dee-141">Weitere Informationen zur expliziten Implementierung finden Sie unter [Explizite Schnittstellenimplementierung](../../programming-guide/interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="21dee-141">For more information about explicit interface implementation, see [Explicit Interface Implementation](../../programming-guide/interfaces/explicit-interface-implementation.md).</span></span>

## <a name="example"></a><span data-ttu-id="21dee-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21dee-142">Example</span></span>

<span data-ttu-id="21dee-143">Das folgende Beispiel veranschaulicht die Schnittstellenimplementierung.</span><span class="sxs-lookup"><span data-stu-id="21dee-143">The following example demonstrates interface implementation.</span></span> <span data-ttu-id="21dee-144">In diesem Beispiel enthält die Schnittstelle die Eigenschaftendeklaration, und die Klasse enthält die Implementierung.</span><span class="sxs-lookup"><span data-stu-id="21dee-144">In this example, the interface contains the property declaration and the class contains the implementation.</span></span> <span data-ttu-id="21dee-145">Eine beliebige Instanz einer Klasse, die `IPoint` implementiert, hat die ganzzahligen Eigenschaften `x` und `y`.</span><span class="sxs-lookup"><span data-stu-id="21dee-145">Any instance of a class that implements `IPoint` has integer properties `x` and `y`.</span></span>

[!code-csharp[csrefKeywordsTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#15)]

## <a name="c-language-specification"></a><span data-ttu-id="21dee-146">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="21dee-146">C# language specification</span></span>

<span data-ttu-id="21dee-147">Weitere Informationen finden Sie im Abschnitt [Schnittstellen](~/_csharplang/spec/interfaces.md) der [C# -Sprachspezifikation](~/_csharplang/spec/introduction.md) und in der Featurespezifikation für [Standardschnittstellenmember – C# 8.0](~/_csharplang/proposals/csharp-8.0/default-interface-methods.md).</span><span class="sxs-lookup"><span data-stu-id="21dee-147">For more information, see the [Interfaces](~/_csharplang/spec/interfaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the feature specification for [Default interface members - C# 8.0](~/_csharplang/proposals/csharp-8.0/default-interface-methods.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="21dee-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21dee-148">See also</span></span>

- [<span data-ttu-id="21dee-149">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="21dee-149">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="21dee-150">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="21dee-150">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="21dee-151">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="21dee-151">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="21dee-152">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="21dee-152">Reference Types</span></span>](reference-types.md)
- [<span data-ttu-id="21dee-153">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="21dee-153">Interfaces</span></span>](../../programming-guide/interfaces/index.md)
- [<span data-ttu-id="21dee-154">Verwenden von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="21dee-154">Using Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)
- [<span data-ttu-id="21dee-155">Verwenden von Indexern</span><span class="sxs-lookup"><span data-stu-id="21dee-155">Using Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)
