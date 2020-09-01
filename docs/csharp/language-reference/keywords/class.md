---
description: class-Schlüsselwort – C#-Referenz
title: class-Schlüsselwort – C#-Referenz
ms.date: 07/18/2017
f1_keywords:
- class_CSharpKeyword
- class
helpviewer_keywords:
- class keyword [C#]
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
ms.openlocfilehash: 67c9c4be55cce25edf9ecb84b257a8523f193bec
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142114"
---
# <a name="class-c-reference"></a><span data-ttu-id="9aff6-103">class (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="9aff6-103">class (C# Reference)</span></span>

<span data-ttu-id="9aff6-104">Klassen werden mithilfe des Schlüsselworts `class` deklariert, wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="9aff6-104">Classes are declared using the keyword `class`, as shown in the following example:</span></span>

```csharp
class TestClass
{
    // Methods, properties, fields, events, delegates
    // and nested classes go here.
}
```

## <a name="remarks"></a><span data-ttu-id="9aff6-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9aff6-105">Remarks</span></span>

<span data-ttu-id="9aff6-106">In C# ist nur die einfache Vererbung zulässig.</span><span class="sxs-lookup"><span data-stu-id="9aff6-106">Only single inheritance is allowed in C#.</span></span> <span data-ttu-id="9aff6-107">Eine Klasse kann also Implementierungen aus nur einer Basisklasse erben.</span><span class="sxs-lookup"><span data-stu-id="9aff6-107">In other words, a class can inherit implementation from one base class only.</span></span> <span data-ttu-id="9aff6-108">Es kann allerdings mehr als eine Schnittstelle implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="9aff6-108">However, a class can implement more than one interface.</span></span> <span data-ttu-id="9aff6-109">Die folgende Tabelle zeigt Beispiele für Klassenvererbung und Implementierung der Schnittstelle:</span><span class="sxs-lookup"><span data-stu-id="9aff6-109">The following table shows examples of class inheritance and interface implementation:</span></span>

|<span data-ttu-id="9aff6-110">Vererbung</span><span class="sxs-lookup"><span data-stu-id="9aff6-110">Inheritance</span></span>|<span data-ttu-id="9aff6-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9aff6-111">Example</span></span>|
|-----------------|-------------|
|<span data-ttu-id="9aff6-112">Keine</span><span class="sxs-lookup"><span data-stu-id="9aff6-112">None</span></span>|`class ClassA { }`|
|<span data-ttu-id="9aff6-113">Einfach</span><span class="sxs-lookup"><span data-stu-id="9aff6-113">Single</span></span>|`class DerivedClass : BaseClass { }`|
|<span data-ttu-id="9aff6-114">Keine, Implementierung von zwei Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9aff6-114">None, implements two interfaces</span></span>|`class ImplClass : IFace1, IFace2 { }`|
|<span data-ttu-id="9aff6-115">Single, Implementierung einer Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9aff6-115">Single, implements one interface</span></span>|`class ImplDerivedClass : BaseClass, IFace1 { }`|

<span data-ttu-id="9aff6-116">Klassen, die Sie direkt innerhalb eines Namespace und nicht in anderen Klassen geschachtelt deklarieren, können entweder [public](./public.md) oder [internal](./internal.md) sein.</span><span class="sxs-lookup"><span data-stu-id="9aff6-116">Classes that you declare directly within a namespace, not nested within other classes, can be either [public](./public.md) or [internal](./internal.md).</span></span> <span data-ttu-id="9aff6-117">Klassen sind standardmäßig `internal`.</span><span class="sxs-lookup"><span data-stu-id="9aff6-117">Classes are `internal` by default.</span></span>

<span data-ttu-id="9aff6-118">Klassenmember, einschließlich geschachtelter Klassen, können [öffentlich](public.md), [intern geschützt](protected-internal.md), [geschützt](protected.md), [intern](internal.md), [privat geschützt](private.md) oder [privat](private-protected.md) sein.</span><span class="sxs-lookup"><span data-stu-id="9aff6-118">Class members, including nested classes, can be [public](public.md), [protected internal](protected-internal.md), [protected](protected.md), [internal](internal.md), [private](private.md), or [private protected](private-protected.md).</span></span> <span data-ttu-id="9aff6-119">Member sind standardmäßig `private`.</span><span class="sxs-lookup"><span data-stu-id="9aff6-119">Members are `private` by default.</span></span>

<span data-ttu-id="9aff6-120">Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../../programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="9aff6-120">For more information, see [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>

<span data-ttu-id="9aff6-121">Sie können generische Klassen deklarieren, die über Typparameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="9aff6-121">You can declare generic classes that have type parameters.</span></span> <span data-ttu-id="9aff6-122">Weitere Informationen finden Sie unter [Generische Klassen](../../programming-guide/generics/generic-classes.md).</span><span class="sxs-lookup"><span data-stu-id="9aff6-122">For more information, see [Generic Classes](../../programming-guide/generics/generic-classes.md).</span></span>

<span data-ttu-id="9aff6-123">Eine Klasse kann Deklarationen der folgenden Member enthalten:</span><span class="sxs-lookup"><span data-stu-id="9aff6-123">A class can contain declarations of the following members:</span></span>

- [<span data-ttu-id="9aff6-124">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="9aff6-124">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)

- [<span data-ttu-id="9aff6-125">Konstanten</span><span class="sxs-lookup"><span data-stu-id="9aff6-125">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)

- [<span data-ttu-id="9aff6-126">Felder</span><span class="sxs-lookup"><span data-stu-id="9aff6-126">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)

- [<span data-ttu-id="9aff6-127">Finalizer</span><span class="sxs-lookup"><span data-stu-id="9aff6-127">Finalizers</span></span>](../../programming-guide/classes-and-structs/destructors.md)

- [<span data-ttu-id="9aff6-128">Methoden</span><span class="sxs-lookup"><span data-stu-id="9aff6-128">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)

- [<span data-ttu-id="9aff6-129">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9aff6-129">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)

- [<span data-ttu-id="9aff6-130">Indexer</span><span class="sxs-lookup"><span data-stu-id="9aff6-130">Indexers</span></span>](../../programming-guide/indexers/index.md)

- [<span data-ttu-id="9aff6-131">Operatoren</span><span class="sxs-lookup"><span data-stu-id="9aff6-131">Operators</span></span>](../operators/index.md)

- [<span data-ttu-id="9aff6-132">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="9aff6-132">Events</span></span>](../../programming-guide/events/index.md)

- [<span data-ttu-id="9aff6-133">Delegaten</span><span class="sxs-lookup"><span data-stu-id="9aff6-133">Delegates</span></span>](../../programming-guide/delegates/index.md)

- [<span data-ttu-id="9aff6-134">Klassen</span><span class="sxs-lookup"><span data-stu-id="9aff6-134">Classes</span></span>](../../programming-guide/classes-and-structs/classes.md)

- [<span data-ttu-id="9aff6-135">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9aff6-135">Interfaces</span></span>](../../programming-guide/interfaces/index.md)

- [<span data-ttu-id="9aff6-136">Strukturtypen</span><span class="sxs-lookup"><span data-stu-id="9aff6-136">Structure types</span></span>](../builtin-types/struct.md)

- [<span data-ttu-id="9aff6-137">Enumerationstypen</span><span class="sxs-lookup"><span data-stu-id="9aff6-137">Enumeration types</span></span>](../builtin-types/enum.md)

## <a name="example"></a><span data-ttu-id="9aff6-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9aff6-138">Example</span></span>

<span data-ttu-id="9aff6-139">Das folgende Beispiel zeigt das Deklarieren von Klassenfeldern, Konstruktoren und Methoden.</span><span class="sxs-lookup"><span data-stu-id="9aff6-139">The following example demonstrates declaring class fields, constructors, and methods.</span></span> <span data-ttu-id="9aff6-140">Darüber hinaus veranschaulicht es Objektinstanziierung und Ausgabe von Instanzdaten.</span><span class="sxs-lookup"><span data-stu-id="9aff6-140">It also demonstrates object instantiation and printing instance data.</span></span> <span data-ttu-id="9aff6-141">In diesem Beispiel werden zwei Klassen deklariert.</span><span class="sxs-lookup"><span data-stu-id="9aff6-141">In this example, two classes are declared.</span></span> <span data-ttu-id="9aff6-142">Die erste Klasse, `Child`, enthält zwei private Felder (`name` und `age`), zwei öffentliche Konstruktoren und eine öffentliche Methode.</span><span class="sxs-lookup"><span data-stu-id="9aff6-142">The first class, `Child`, contains two private fields (`name` and `age`), two public constructors and one public method.</span></span> <span data-ttu-id="9aff6-143">Die zweite Klasse, `StringTest`, enthält `Main`.</span><span class="sxs-lookup"><span data-stu-id="9aff6-143">The second class, `StringTest`, is used to contain `Main`.</span></span>

[!code-csharp[csrefKeywordsTypes#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#5)]

## <a name="comments"></a><span data-ttu-id="9aff6-144">Kommentare</span><span class="sxs-lookup"><span data-stu-id="9aff6-144">Comments</span></span>

<span data-ttu-id="9aff6-145">Beachten Sie, dass im vorherigen Beispiel nur über die öffentliche Methode der Klasse `Child` auf die privaten Felder (`name` und `age`) zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="9aff6-145">Notice that in the previous example the private fields (`name` and `age`) can only be accessed through the public method of the `Child` class.</span></span> <span data-ttu-id="9aff6-146">Sie können z.B. den Namen des untergeordneten Elements nicht aus der `Main`-Methode mit einer Anweisung wie folgt drucken:</span><span class="sxs-lookup"><span data-stu-id="9aff6-146">For example, you cannot print the child's name, from the `Main` method, using a statement like this:</span></span>

```csharp
Console.Write(child1.name);   // Error
```

<span data-ttu-id="9aff6-147">Zugriff auf private Member der `Child` von `Main` wäre nur möglich, wenn `Main` ein Member der Klasse wäre.</span><span class="sxs-lookup"><span data-stu-id="9aff6-147">Accessing private members of `Child` from `Main` would only be possible if `Main` were a member of the class.</span></span>

<span data-ttu-id="9aff6-148">Typen, die innerhalb einer Klasse ohne Zugriffsmodifizierer deklariert werden, sind standardmäßig `private`, sodass die Datenmember in diesem Beispiel dennoch `private` wären, wenn das Schlüsselwort entfernt worden wäre.</span><span class="sxs-lookup"><span data-stu-id="9aff6-148">Types declared inside a class without an access modifier default to `private`, so the data members in this example would still be `private` if the keyword were removed.</span></span>

<span data-ttu-id="9aff6-149">Beachten Sie schließlich, dass für das Objekt, das mit dem parameterlosen Konstruktor (`child3`) erstellt wurde, das Feld `age` standardmäßig auf 0 (null) initialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="9aff6-149">Finally, notice that for the object created using the parameterless constructor (`child3`), the `age` field was initialized to zero by default.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="9aff6-150">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="9aff6-150">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="9aff6-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9aff6-151">See also</span></span>

- [<span data-ttu-id="9aff6-152">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="9aff6-152">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9aff6-153">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9aff6-153">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9aff6-154">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="9aff6-154">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="9aff6-155">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="9aff6-155">Reference Types</span></span>](./reference-types.md)
