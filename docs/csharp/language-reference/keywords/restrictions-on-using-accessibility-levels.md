---
title: Einschränkungen bei der Verwendung von Zugriffsebenen (C#-Referenz)
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#], accessibility level restrictions
ms.assetid: 987e2f22-46bf-4fea-80ee-270b9cd01045
ms.openlocfilehash: 2bcf2b12d1aa1488e6d3e46f5b37ac9535b138dd
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44252699"
---
# <a name="restrictions-on-using-accessibility-levels-c-reference"></a><span data-ttu-id="4e03d-102">Einschränkungen bei der Verwendung von Zugriffsebenen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="4e03d-102">Restrictions on using accessibility levels (C# Reference)</span></span>

<span data-ttu-id="4e03d-103">Wenn Sie in einer Deklaration einen Typ angeben, überprüfen Sie, ob die Zugriffsebene dieses Typs von der Zugriffsebene eines Members oder eines anderen Typs abhängt.</span><span class="sxs-lookup"><span data-stu-id="4e03d-103">When you specify a type in a declaration, check whether the accessibility level of the type is dependent on the accessibility level of a member or of another type.</span></span> <span data-ttu-id="4e03d-104">Auf die direkte Basisklasse muss z.B. mindestens genauso zugegriffen werden können wie auf die abgeleitete Klasse.</span><span class="sxs-lookup"><span data-stu-id="4e03d-104">For example, the direct base class must be at least as accessible as the derived class.</span></span> <span data-ttu-id="4e03d-105">Die folgende Deklaration verursacht einen Compilerfehler, da die Basisklasse `BaseClass` eine stärkere Zugriffsbeschränkung hat als `MyClass`:</span><span class="sxs-lookup"><span data-stu-id="4e03d-105">The following declarations cause a compiler error because the base class `BaseClass` is less accessible than `MyClass`:</span></span>

```csharp
class BaseClass {...}
public class MyClass: BaseClass {...} // Error
```

<span data-ttu-id="4e03d-106">In der folgenden Tabelle werden die Einschränkungen für deklarierte Zugriffsebenen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="4e03d-106">The following table summarizes the restrictions on declared accessibility levels.</span></span>

|<span data-ttu-id="4e03d-107">Kontext</span><span class="sxs-lookup"><span data-stu-id="4e03d-107">Context</span></span>|<span data-ttu-id="4e03d-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4e03d-108">Remarks</span></span>|
|-------------|-------------|
|[<span data-ttu-id="4e03d-109">Klassen</span><span class="sxs-lookup"><span data-stu-id="4e03d-109">Classes</span></span>](../../programming-guide/classes-and-structs/classes.md)|<span data-ttu-id="4e03d-110">Die direkte Basisklasse eines Klassentyps muss mindesten dieselben Zugriffsmöglichkeiten wie der Klassentyp selbst bieten.</span><span class="sxs-lookup"><span data-stu-id="4e03d-110">The direct base class of a class type must be at least as accessible as the class type itself.</span></span>|
|[<span data-ttu-id="4e03d-111">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4e03d-111">Interfaces</span></span>](../../programming-guide/interfaces/index.md)|<span data-ttu-id="4e03d-112">Die explizite Basisschnittstelle eines Schnittstellentyps muss mindesten dieselben Zugriffsmöglichkeiten bieten wie der Schnittstellentyp selbst.</span><span class="sxs-lookup"><span data-stu-id="4e03d-112">The explicit base interfaces of an interface type must be at least as accessible as the interface type itself.</span></span>|
|[<span data-ttu-id="4e03d-113">Delegaten</span><span class="sxs-lookup"><span data-stu-id="4e03d-113">Delegates</span></span>](../../programming-guide/delegates/index.md)|<span data-ttu-id="4e03d-114">Die Rückgabe- und Parametertypen eines Delegattyps müssen mindestens dieselben Zugriffsmöglichkeiten wie der Delegattyp selbst bieten.</span><span class="sxs-lookup"><span data-stu-id="4e03d-114">The return type and parameter types of a delegate type must be at least as accessible as the delegate type itself.</span></span>|
|[<span data-ttu-id="4e03d-115">Konstanten</span><span class="sxs-lookup"><span data-stu-id="4e03d-115">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)|<span data-ttu-id="4e03d-116">Der Typ einer Konstante muss mindestens dieselben Zugriffsmöglichkeiten wie die Konstante selbst bieten.</span><span class="sxs-lookup"><span data-stu-id="4e03d-116">The type of a constant must be at least as accessible as the constant itself.</span></span>|
|[<span data-ttu-id="4e03d-117">Felder</span><span class="sxs-lookup"><span data-stu-id="4e03d-117">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)|<span data-ttu-id="4e03d-118">Der Typ eines Felds muss mindestens dieselben Zugriffsmöglichkeiten bieten wie das Feld selbst.</span><span class="sxs-lookup"><span data-stu-id="4e03d-118">The type of a field must be at least as accessible as the field itself.</span></span>|
|[<span data-ttu-id="4e03d-119">Methoden</span><span class="sxs-lookup"><span data-stu-id="4e03d-119">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)|<span data-ttu-id="4e03d-120">Die Rückgabe- und Parametertypen einer Methode müssen mindestens dieselben Zugriffsmöglichkeiten bieten wie die Methode selbst.</span><span class="sxs-lookup"><span data-stu-id="4e03d-120">The return type and parameter types of a method must be at least as accessible as the method itself.</span></span>|
|[<span data-ttu-id="4e03d-121">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4e03d-121">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)|<span data-ttu-id="4e03d-122">Der Typ einer Eigenschaft muss mindestens dieselben Zugriffsmöglichkeiten bieten wie die Eigenschaft selbst.</span><span class="sxs-lookup"><span data-stu-id="4e03d-122">The type of a property must be at least as accessible as the property itself.</span></span>|
|[<span data-ttu-id="4e03d-123">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="4e03d-123">Events</span></span>](../../programming-guide/events/index.md)|<span data-ttu-id="4e03d-124">Der Typ eines Ereignisses muss mindestens dieselben Zugriffsmöglichkeiten bieten wie das Ereignis selbst.</span><span class="sxs-lookup"><span data-stu-id="4e03d-124">The type of an event must be at least as accessible as the event itself.</span></span>|
|[<span data-ttu-id="4e03d-125">Indexer</span><span class="sxs-lookup"><span data-stu-id="4e03d-125">Indexers</span></span>](../../programming-guide/indexers/index.md)|<span data-ttu-id="4e03d-126">Der Typ und die Parametertypen eines Indexers müssen mindestens dieselben Zugriffsmöglichkeiten bieten wie der Indexer selbst.</span><span class="sxs-lookup"><span data-stu-id="4e03d-126">The type and parameter types of an indexer must be at least as accessible as the indexer itself.</span></span>|
|[<span data-ttu-id="4e03d-127">Operatoren</span><span class="sxs-lookup"><span data-stu-id="4e03d-127">Operators</span></span>](../../programming-guide/statements-expressions-operators/operators.md)|<span data-ttu-id="4e03d-128">Die Rückgabe- und Parametertypen eines Operators müssen mindestens dieselben Zugriffsmöglichkeiten bieten wie der Operator selbst.</span><span class="sxs-lookup"><span data-stu-id="4e03d-128">The return type and parameter types of an operator must be at least as accessible as the operator itself.</span></span>|
|[<span data-ttu-id="4e03d-129">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="4e03d-129">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)|<span data-ttu-id="4e03d-130">Die Parametertypen eines Konstruktors müssen mindestens dieselben Zugriffsmöglichkeiten bieten wie der Konstruktor selbst.</span><span class="sxs-lookup"><span data-stu-id="4e03d-130">The parameter types of a constructor must be at least as accessible as the constructor itself.</span></span>|

## <a name="example"></a><span data-ttu-id="4e03d-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4e03d-131">Example</span></span>

<span data-ttu-id="4e03d-132">Das folgende Beispiel enthält fehlerhafte Deklarationen verschiedener Typen.</span><span class="sxs-lookup"><span data-stu-id="4e03d-132">The following example contains erroneous declarations of different types.</span></span> <span data-ttu-id="4e03d-133">Der Kommentar nach jeder Deklaration gibt den erwarteten Compilerfehler an.</span><span class="sxs-lookup"><span data-stu-id="4e03d-133">The comment following each declaration indicates the expected compiler error.</span></span>

```csharp
// Restrictions on Using Accessibility Levels
// CS0052 expected as well as CS0053, CS0056, and CS0057
// To make the program work, change access level of both class B
// and MyPrivateMethod() to public.

using System;

// A delegate:
delegate int MyDelegate();

class B
{
    // A private method:
    static int MyPrivateMethod()
    {
        return 0;
    }
}

public class A
{
    // Error: The type B is less accessible than the field A.myField.
    public B myField = new B();

    // Error: The type B is less accessible
    // than the constant A.myConst.
    public readonly B myConst = new B();

    public B MyMethod()
    {
        // Error: The type B is less accessible 
        // than the method A.MyMethod.
        return new B();
    }

    // Error: The type B is less accessible than the property A.MyProp
    public B MyProp
    {
        set
        {
        }
    }

    MyDelegate d = new MyDelegate(B.MyPrivateMethod);
    // Even when B is declared public, you still get the error: 
    // "The parameter B.MyPrivateMethod is not accessible due to 
    // protection level."

    public static B operator +(A m1, B m2)
    {
        // Error: The type B is less accessible
        // than the operator A.operator +(A,B)
        return new B();
    }

    static void Main()
    {
        Console.Write("Compiled successfully");
    }
}
```

## <a name="c-language-specification"></a><span data-ttu-id="4e03d-134">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="4e03d-134">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="4e03d-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e03d-135">See also</span></span>

- [<span data-ttu-id="4e03d-136">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="4e03d-136">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="4e03d-137">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="4e03d-137">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4e03d-138">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="4e03d-138">C# Keywords</span></span>](../../language-reference/keywords/index.md)
- [<span data-ttu-id="4e03d-139">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="4e03d-139">Access Modifiers</span></span>](../../language-reference/keywords/access-modifiers.md)
- [<span data-ttu-id="4e03d-140">Zugriffsdomäne</span><span class="sxs-lookup"><span data-stu-id="4e03d-140">Accessibility Domain</span></span>](../../language-reference/keywords/accessibility-domain.md)
- [<span data-ttu-id="4e03d-141">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="4e03d-141">Accessibility Levels</span></span>](../../language-reference/keywords/accessibility-levels.md)
- [<span data-ttu-id="4e03d-142">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="4e03d-142">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="4e03d-143">public</span><span class="sxs-lookup"><span data-stu-id="4e03d-143">public</span></span>](../../language-reference/keywords/public.md)
- [<span data-ttu-id="4e03d-144">private</span><span class="sxs-lookup"><span data-stu-id="4e03d-144">private</span></span>](../../language-reference/keywords/private.md)
- [<span data-ttu-id="4e03d-145">protected</span><span class="sxs-lookup"><span data-stu-id="4e03d-145">protected</span></span>](../../language-reference/keywords/protected.md)
- [<span data-ttu-id="4e03d-146">internal</span><span class="sxs-lookup"><span data-stu-id="4e03d-146">internal</span></span>](../../language-reference/keywords/internal.md)