---
title: Schlüsselwort „class“ (C#-Referenz)
ms.date: 07/18/2017
f1_keywords:
- class_CSharpKeyword
- class
helpviewer_keywords:
- class keyword [C#]
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
ms.openlocfilehash: 04e64e825e4297ceb432393c7bd145a6cf4fcb2c
ms.sourcegitcommit: ed7b4b9b77d35e94a35a2634e8c874f46603fb2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36948510"
---
# <a name="class-c-reference"></a><span data-ttu-id="91381-102">class (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="91381-102">class (C# Reference)</span></span>

<span data-ttu-id="91381-103">Klassen werden mithilfe des Schlüsselworts `class` deklariert, wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="91381-103">Classes are declared using the keyword `class`, as shown in the following example:</span></span>

```csharp
class TestClass
{
    // Methods, properties, fields, events, delegates
    // and nested classes go here.
}
```

## <a name="remarks"></a><span data-ttu-id="91381-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="91381-104">Remarks</span></span>

<span data-ttu-id="91381-105">In C# ist nur die einfache Vererbung zulässig.</span><span class="sxs-lookup"><span data-stu-id="91381-105">Only single inheritance is allowed in C#.</span></span> <span data-ttu-id="91381-106">Eine Klasse kann also Implementierungen aus nur einer Basisklasse erben.</span><span class="sxs-lookup"><span data-stu-id="91381-106">In other words, a class can inherit implementation from one base class only.</span></span> <span data-ttu-id="91381-107">Es kann allerdings mehr als eine Schnittstelle implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="91381-107">However, a class can implement more than one interface.</span></span> <span data-ttu-id="91381-108">Die folgende Tabelle zeigt Beispiele für Klassenvererbung und Implementierung der Schnittstelle:</span><span class="sxs-lookup"><span data-stu-id="91381-108">The following table shows examples of class inheritance and interface implementation:</span></span>

|<span data-ttu-id="91381-109">Vererbung</span><span class="sxs-lookup"><span data-stu-id="91381-109">Inheritance</span></span>|<span data-ttu-id="91381-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91381-110">Example</span></span>|
|-----------------|-------------|
|<span data-ttu-id="91381-111">Keiner</span><span class="sxs-lookup"><span data-stu-id="91381-111">None</span></span>|`class ClassA { }`|
|<span data-ttu-id="91381-112">Single</span><span class="sxs-lookup"><span data-stu-id="91381-112">Single</span></span>|`class DerivedClass: BaseClass { }`|
|<span data-ttu-id="91381-113">Keine, Implementierung von zwei Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="91381-113">None, implements two interfaces</span></span>|`class ImplClass: IFace1, IFace2 { }`|
|<span data-ttu-id="91381-114">Single, Implementierung einer Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91381-114">Single, implements one interface</span></span>|`class ImplDerivedClass: BaseClass, IFace1 { }`|

<span data-ttu-id="91381-115">Klassen, die Sie direkt innerhalb eines Namespace und nicht in anderen Klassen geschachtelt deklarieren, können entweder [public](../../../csharp/language-reference/keywords/public.md) oder [internal](../../../csharp/language-reference/keywords/internal.md) sein.</span><span class="sxs-lookup"><span data-stu-id="91381-115">Classes that you declare directly within a namespace, not nested within other classes, can be either [public](../../../csharp/language-reference/keywords/public.md) or [internal](../../../csharp/language-reference/keywords/internal.md).</span></span> <span data-ttu-id="91381-116">Klassen sind standardmäßig `internal`.</span><span class="sxs-lookup"><span data-stu-id="91381-116">Classes are `internal` by default.</span></span>

<span data-ttu-id="91381-117">Klassenmember, einschließlich geschachtelter Klassen, können vom Typ [public](../../../csharp/language-reference/keywords/public.md), `protected internal`, [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [private](../../../csharp/language-reference/keywords/private.md) oder `private protected` sein.</span><span class="sxs-lookup"><span data-stu-id="91381-117">Class members, including nested classes, can be [public](../../../csharp/language-reference/keywords/public.md), `protected internal`, [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [private](../../../csharp/language-reference/keywords/private.md), or `private protected`.</span></span> <span data-ttu-id="91381-118">Member sind standardmäßig [private](../../../csharp/language-reference/keywords/private.md).</span><span class="sxs-lookup"><span data-stu-id="91381-118">Members are [private](../../../csharp/language-reference/keywords/private.md) by default.</span></span>

<span data-ttu-id="91381-119">Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="91381-119">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>

<span data-ttu-id="91381-120">Sie können generische Klassen deklarieren, die über Typparameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="91381-120">You can declare generic classes that have type parameters.</span></span> <span data-ttu-id="91381-121">Weitere Informationen finden Sie unter [Generische Klassen](../../../csharp/programming-guide/generics/generic-classes.md).</span><span class="sxs-lookup"><span data-stu-id="91381-121">For more information, see [Generic Classes](../../../csharp/programming-guide/generics/generic-classes.md).</span></span>

<span data-ttu-id="91381-122">Eine Klasse kann Deklarationen der folgenden Member enthalten:</span><span class="sxs-lookup"><span data-stu-id="91381-122">A class can contain declarations of the following members:</span></span>

- [<span data-ttu-id="91381-123">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="91381-123">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)

- [<span data-ttu-id="91381-124">Konstanten</span><span class="sxs-lookup"><span data-stu-id="91381-124">Constants</span></span>](../../../csharp/programming-guide/classes-and-structs/constants.md)

- [<span data-ttu-id="91381-125">Felder</span><span class="sxs-lookup"><span data-stu-id="91381-125">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)

- [<span data-ttu-id="91381-126">Finalizer</span><span class="sxs-lookup"><span data-stu-id="91381-126">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)

- [<span data-ttu-id="91381-127">Methoden</span><span class="sxs-lookup"><span data-stu-id="91381-127">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)

- [<span data-ttu-id="91381-128">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="91381-128">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)

- [<span data-ttu-id="91381-129">Indexer</span><span class="sxs-lookup"><span data-stu-id="91381-129">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)

- [<span data-ttu-id="91381-130">Operatoren</span><span class="sxs-lookup"><span data-stu-id="91381-130">Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/operators.md)

- [<span data-ttu-id="91381-131">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="91381-131">Events</span></span>](../../../csharp/programming-guide/events/index.md)

- [<span data-ttu-id="91381-132">Delegaten</span><span class="sxs-lookup"><span data-stu-id="91381-132">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)

- [<span data-ttu-id="91381-133">Klassen</span><span class="sxs-lookup"><span data-stu-id="91381-133">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)

- [<span data-ttu-id="91381-134">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="91381-134">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)

- [<span data-ttu-id="91381-135">Strukturen</span><span class="sxs-lookup"><span data-stu-id="91381-135">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)

## <a name="example"></a><span data-ttu-id="91381-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="91381-136">Example</span></span>

<span data-ttu-id="91381-137">Das folgende Beispiel zeigt das Deklarieren von Klassenfeldern, Konstruktoren und Methoden.</span><span class="sxs-lookup"><span data-stu-id="91381-137">The following example demonstrates declaring class fields, constructors, and methods.</span></span> <span data-ttu-id="91381-138">Darüber hinaus veranschaulicht es Objektinstanziierung und Ausgabe von Instanzdaten.</span><span class="sxs-lookup"><span data-stu-id="91381-138">It also demonstrates object instantiation and printing instance data.</span></span> <span data-ttu-id="91381-139">In diesem Beispiel werden zwei Klassen deklariert.</span><span class="sxs-lookup"><span data-stu-id="91381-139">In this example, two classes are declared.</span></span> <span data-ttu-id="91381-140">Die erste Klasse, `Child`, enthält zwei private Felder (`name` und `age`), zwei öffentliche Konstruktoren und eine öffentliche Methode.</span><span class="sxs-lookup"><span data-stu-id="91381-140">The first class, `Child`, contains two private fields (`name` and `age`), two public constructors and one public method.</span></span> <span data-ttu-id="91381-141">Die zweite Klasse, `StringTest`, enthält `Main`.</span><span class="sxs-lookup"><span data-stu-id="91381-141">The second class, `StringTest`, is used to contain `Main`.</span></span>

[!code-csharp[csrefKeywordsTypes#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#5)]

## <a name="comments"></a><span data-ttu-id="91381-142">Kommentare</span><span class="sxs-lookup"><span data-stu-id="91381-142">Comments</span></span>

<span data-ttu-id="91381-143">Beachten Sie, dass im vorherigen Beispiel nur über die öffentliche Methode der Klasse `Child` auf die privaten Felder (`name` und `age`) zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="91381-143">Notice that in the previous example the private fields (`name` and `age`) can only be accessed through the public method of the `Child` class.</span></span> <span data-ttu-id="91381-144">Sie können z.B. den Namen des untergeordneten Elements nicht aus der `Main`-Methode mit einer Anweisung wie folgt drucken:</span><span class="sxs-lookup"><span data-stu-id="91381-144">For example, you cannot print the child's name, from the `Main` method, using a statement like this:</span></span>

```csharp
Console.Write(child1.name);   // Error
```

<span data-ttu-id="91381-145">Zugriff auf private Member der `Child` von `Main` wäre nur möglich, wenn `Main` ein Member der Klasse wäre.</span><span class="sxs-lookup"><span data-stu-id="91381-145">Accessing private members of `Child` from `Main` would only be possible if `Main` were a member of the class.</span></span>

<span data-ttu-id="91381-146">Typen, die innerhalb einer Klasse ohne Zugriffsmodifizierer deklariert werden, sind standardmäßig `private`, sodass die Datenmember in diesem Beispiel dennoch `private` wären, wenn das Schlüsselwort entfernt worden wäre.</span><span class="sxs-lookup"><span data-stu-id="91381-146">Types declared inside a class without an access modifier default to `private`, so the data members in this example would still be `private` if the keyword were removed.</span></span>

<span data-ttu-id="91381-147">Beachten Sie schließlich, dass für das Objekt, das mit dem Standardkonstruktor (`child3`) erstellt wurde, das Altersfeld standardmäßig auf 0 initialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="91381-147">Finally, notice that for the object created using the default constructor (`child3`), the age field was initialized to zero by default.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="91381-148">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="91381-148">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="91381-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91381-149">See also</span></span>

[<span data-ttu-id="91381-150">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="91381-150">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
[<span data-ttu-id="91381-151">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="91381-151">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
[<span data-ttu-id="91381-152">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="91381-152">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
[<span data-ttu-id="91381-153">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="91381-153">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)