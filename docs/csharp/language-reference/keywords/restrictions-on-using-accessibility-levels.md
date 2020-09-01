---
description: Einschränkungen bei der Verwendung von Zugriffsebenen – C#-Referenz
title: Einschränkungen bei der Verwendung von Zugriffsebenen – C#-Referenz
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#], accessibility level restrictions
ms.assetid: 987e2f22-46bf-4fea-80ee-270b9cd01045
ms.openlocfilehash: 542e463e41c70f2e8aed5c20dc1294e296a88518
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89136997"
---
# <a name="restrictions-on-using-accessibility-levels-c-reference"></a><span data-ttu-id="5922f-103">Einschränkungen bei der Verwendung von Zugriffsebenen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="5922f-103">Restrictions on using accessibility levels (C# Reference)</span></span>

<span data-ttu-id="5922f-104">Wenn Sie in einer Deklaration einen Typ angeben, überprüfen Sie, ob die Zugriffsebene dieses Typs von der Zugriffsebene eines Members oder eines anderen Typs abhängt.</span><span class="sxs-lookup"><span data-stu-id="5922f-104">When you specify a type in a declaration, check whether the accessibility level of the type is dependent on the accessibility level of a member or of another type.</span></span> <span data-ttu-id="5922f-105">Auf die direkte Basisklasse muss z.B. mindestens genauso zugegriffen werden können wie auf die abgeleitete Klasse.</span><span class="sxs-lookup"><span data-stu-id="5922f-105">For example, the direct base class must be at least as accessible as the derived class.</span></span> <span data-ttu-id="5922f-106">Die folgende Deklaration verursacht einen Compilerfehler, da die Basisklasse `BaseClass` eine stärkere Zugriffsbeschränkung hat als `MyClass`:</span><span class="sxs-lookup"><span data-stu-id="5922f-106">The following declarations cause a compiler error because the base class `BaseClass` is less accessible than `MyClass`:</span></span>

```csharp
class BaseClass {...}
public class MyClass: BaseClass {...} // Error
```

<span data-ttu-id="5922f-107">In der folgenden Tabelle werden die Einschränkungen für deklarierte Zugriffsebenen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="5922f-107">The following table summarizes the restrictions on declared accessibility levels.</span></span>

|<span data-ttu-id="5922f-108">Kontext</span><span class="sxs-lookup"><span data-stu-id="5922f-108">Context</span></span>|<span data-ttu-id="5922f-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5922f-109">Remarks</span></span>|
|-------------|-------------|
|[<span data-ttu-id="5922f-110">Klassen</span><span class="sxs-lookup"><span data-stu-id="5922f-110">Classes</span></span>](../../programming-guide/classes-and-structs/classes.md)|<span data-ttu-id="5922f-111">Die direkte Basisklasse eines Klassentyps muss mindesten dieselben Zugriffsmöglichkeiten wie der Klassentyp selbst bieten.</span><span class="sxs-lookup"><span data-stu-id="5922f-111">The direct base class of a class type must be at least as accessible as the class type itself.</span></span>|
|[<span data-ttu-id="5922f-112">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5922f-112">Interfaces</span></span>](../../programming-guide/interfaces/index.md)|<span data-ttu-id="5922f-113">Die explizite Basisschnittstelle eines Schnittstellentyps muss mindesten dieselben Zugriffsmöglichkeiten bieten wie der Schnittstellentyp selbst.</span><span class="sxs-lookup"><span data-stu-id="5922f-113">The explicit base interfaces of an interface type must be at least as accessible as the interface type itself.</span></span>|
|[<span data-ttu-id="5922f-114">Delegaten</span><span class="sxs-lookup"><span data-stu-id="5922f-114">Delegates</span></span>](../../programming-guide/delegates/index.md)|<span data-ttu-id="5922f-115">Die Rückgabe- und Parametertypen eines Delegattyps müssen mindestens dieselben Zugriffsmöglichkeiten wie der Delegattyp selbst bieten.</span><span class="sxs-lookup"><span data-stu-id="5922f-115">The return type and parameter types of a delegate type must be at least as accessible as the delegate type itself.</span></span>|
|[<span data-ttu-id="5922f-116">Konstanten</span><span class="sxs-lookup"><span data-stu-id="5922f-116">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)|<span data-ttu-id="5922f-117">Der Typ einer Konstante muss mindestens dieselben Zugriffsmöglichkeiten wie die Konstante selbst bieten.</span><span class="sxs-lookup"><span data-stu-id="5922f-117">The type of a constant must be at least as accessible as the constant itself.</span></span>|
|[<span data-ttu-id="5922f-118">Felder</span><span class="sxs-lookup"><span data-stu-id="5922f-118">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)|<span data-ttu-id="5922f-119">Der Typ eines Felds muss mindestens dieselben Zugriffsmöglichkeiten bieten wie das Feld selbst.</span><span class="sxs-lookup"><span data-stu-id="5922f-119">The type of a field must be at least as accessible as the field itself.</span></span>|
|[<span data-ttu-id="5922f-120">Methoden</span><span class="sxs-lookup"><span data-stu-id="5922f-120">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)|<span data-ttu-id="5922f-121">Die Rückgabe- und Parametertypen einer Methode müssen mindestens dieselben Zugriffsmöglichkeiten bieten wie die Methode selbst.</span><span class="sxs-lookup"><span data-stu-id="5922f-121">The return type and parameter types of a method must be at least as accessible as the method itself.</span></span>|
|[<span data-ttu-id="5922f-122">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="5922f-122">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)|<span data-ttu-id="5922f-123">Der Typ einer Eigenschaft muss mindestens dieselben Zugriffsmöglichkeiten bieten wie die Eigenschaft selbst.</span><span class="sxs-lookup"><span data-stu-id="5922f-123">The type of a property must be at least as accessible as the property itself.</span></span>|
|[<span data-ttu-id="5922f-124">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="5922f-124">Events</span></span>](../../programming-guide/events/index.md)|<span data-ttu-id="5922f-125">Der Typ eines Ereignisses muss mindestens dieselben Zugriffsmöglichkeiten bieten wie das Ereignis selbst.</span><span class="sxs-lookup"><span data-stu-id="5922f-125">The type of an event must be at least as accessible as the event itself.</span></span>|
|[<span data-ttu-id="5922f-126">Indexer</span><span class="sxs-lookup"><span data-stu-id="5922f-126">Indexers</span></span>](../../programming-guide/indexers/index.md)|<span data-ttu-id="5922f-127">Der Typ und die Parametertypen eines Indexers müssen mindestens dieselben Zugriffsmöglichkeiten bieten wie der Indexer selbst.</span><span class="sxs-lookup"><span data-stu-id="5922f-127">The type and parameter types of an indexer must be at least as accessible as the indexer itself.</span></span>|
|[<span data-ttu-id="5922f-128">Operatoren</span><span class="sxs-lookup"><span data-stu-id="5922f-128">Operators</span></span>](../operators/index.md)|<span data-ttu-id="5922f-129">Die Rückgabe- und Parametertypen eines Operators müssen mindestens dieselben Zugriffsmöglichkeiten bieten wie der Operator selbst.</span><span class="sxs-lookup"><span data-stu-id="5922f-129">The return type and parameter types of an operator must be at least as accessible as the operator itself.</span></span>|
|[<span data-ttu-id="5922f-130">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="5922f-130">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)|<span data-ttu-id="5922f-131">Die Parametertypen eines Konstruktors müssen mindestens dieselben Zugriffsmöglichkeiten bieten wie der Konstruktor selbst.</span><span class="sxs-lookup"><span data-stu-id="5922f-131">The parameter types of a constructor must be at least as accessible as the constructor itself.</span></span>|

## <a name="example"></a><span data-ttu-id="5922f-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5922f-132">Example</span></span>

<span data-ttu-id="5922f-133">Das folgende Beispiel enthält fehlerhafte Deklarationen verschiedener Typen.</span><span class="sxs-lookup"><span data-stu-id="5922f-133">The following example contains erroneous declarations of different types.</span></span> <span data-ttu-id="5922f-134">Der Kommentar nach jeder Deklaration gibt den erwarteten Compilerfehler an.</span><span class="sxs-lookup"><span data-stu-id="5922f-134">The comment following each declaration indicates the expected compiler error.</span></span>

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

## <a name="c-language-specification"></a><span data-ttu-id="5922f-135">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="5922f-135">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="5922f-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5922f-136">See also</span></span>

- [<span data-ttu-id="5922f-137">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="5922f-137">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5922f-138">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="5922f-138">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5922f-139">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5922f-139">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="5922f-140">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="5922f-140">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="5922f-141">Zugriffsdomäne</span><span class="sxs-lookup"><span data-stu-id="5922f-141">Accessibility Domain</span></span>](accessibility-domain.md)
- [<span data-ttu-id="5922f-142">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="5922f-142">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="5922f-143">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="5922f-143">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="5922f-144">public</span><span class="sxs-lookup"><span data-stu-id="5922f-144">public</span></span>](public.md)
- [<span data-ttu-id="5922f-145">private</span><span class="sxs-lookup"><span data-stu-id="5922f-145">private</span></span>](private.md)
- [<span data-ttu-id="5922f-146">protected</span><span class="sxs-lookup"><span data-stu-id="5922f-146">protected</span></span>](protected.md)
- [<span data-ttu-id="5922f-147">internal</span><span class="sxs-lookup"><span data-stu-id="5922f-147">internal</span></span>](internal.md)
