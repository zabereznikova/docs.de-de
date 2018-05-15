---
title: Einschränkungen bei der Verwendung von Zugriffsebenen (C#-Referenz)
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#], accessibility level restrictions
ms.assetid: 987e2f22-46bf-4fea-80ee-270b9cd01045
ms.openlocfilehash: bbe358822e885e5ddaba4cb9d982e89cefe1921e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="restrictions-on-using-accessibility-levels-c-reference"></a><span data-ttu-id="f5dbc-102">Einschränkungen bei der Verwendung von Zugriffsebenen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f5dbc-102">Restrictions on Using Accessibility Levels (C# Reference)</span></span>
<span data-ttu-id="f5dbc-103">Wenn Sie in einer Deklaration einen Typ angeben, überprüfen Sie, ob die Zugriffsebene dieses Typs von der Zugriffsebene eines Members oder eines anderen Typs abhängt.</span><span class="sxs-lookup"><span data-stu-id="f5dbc-103">When you specify a type in a declaration, check whether the accessibility level of the type is dependent on the accessibility level of a member or of another type.</span></span> <span data-ttu-id="f5dbc-104">Auf die direkte Basisklasse muss z.B. mindestens genauso zugegriffen werden können wie auf die abgeleitete Klasse.</span><span class="sxs-lookup"><span data-stu-id="f5dbc-104">For example, the direct base class must be at least as accessible as the derived class.</span></span> <span data-ttu-id="f5dbc-105">Die folgende Deklaration verursacht einen Compilerfehler, da die Basisklasse `BaseClass` eine stärkere Zugriffsbeschränkung hat als `MyClass`:</span><span class="sxs-lookup"><span data-stu-id="f5dbc-105">The following declarations cause a compiler error because the base class `BaseClass` is less accessible than `MyClass`:</span></span>  
  
```  
class BaseClass {...}  
public class MyClass: BaseClass {...} // Error  
```  
  
 <span data-ttu-id="f5dbc-106">In der folgenden Tabelle werden die Einschränkungen für deklarierte Zugriffsebenen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="f5dbc-106">The following table summarizes the restrictions on declared accessibility levels.</span></span>  
  
|<span data-ttu-id="f5dbc-107">Kontext</span><span class="sxs-lookup"><span data-stu-id="f5dbc-107">Context</span></span>|<span data-ttu-id="f5dbc-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f5dbc-108">Remarks</span></span>|  
|-------------|-------------|  
|[<span data-ttu-id="f5dbc-109">Klassen</span><span class="sxs-lookup"><span data-stu-id="f5dbc-109">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)|<span data-ttu-id="f5dbc-110">Die direkte Basisklasse eines Klassentyps muss mindesten dieselben Zugriffsmöglichkeiten wie der Klassentyp selbst bieten.</span><span class="sxs-lookup"><span data-stu-id="f5dbc-110">The direct base class of a class type must be at least as accessible as the class type itself.</span></span>|  
|[<span data-ttu-id="f5dbc-111">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f5dbc-111">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)|<span data-ttu-id="f5dbc-112">Die explizite Basisschnittstelle eines Schnittstellentyps muss mindesten dieselben Zugriffsmöglichkeiten bieten wie der Schnittstellentyp selbst.</span><span class="sxs-lookup"><span data-stu-id="f5dbc-112">The explicit base interfaces of an interface type must be at least as accessible as the interface type itself.</span></span>|  
|[<span data-ttu-id="f5dbc-113">Delegaten</span><span class="sxs-lookup"><span data-stu-id="f5dbc-113">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)|<span data-ttu-id="f5dbc-114">Die Rückgabe- und Parametertypen eines Delegattyps müssen mindestens dieselben Zugriffsmöglichkeiten wie der Delegattyp selbst bieten.</span><span class="sxs-lookup"><span data-stu-id="f5dbc-114">The return type and parameter types of a delegate type must be at least as accessible as the delegate type itself.</span></span>|  
|[<span data-ttu-id="f5dbc-115">Konstanten</span><span class="sxs-lookup"><span data-stu-id="f5dbc-115">Constants</span></span>](../../../csharp/programming-guide/classes-and-structs/constants.md)|<span data-ttu-id="f5dbc-116">Der Typ einer Konstante muss mindestens dieselben Zugriffsmöglichkeiten wie die Konstante selbst bieten.</span><span class="sxs-lookup"><span data-stu-id="f5dbc-116">The type of a constant must be at least as accessible as the constant itself.</span></span>|  
|[<span data-ttu-id="f5dbc-117">Felder</span><span class="sxs-lookup"><span data-stu-id="f5dbc-117">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)|<span data-ttu-id="f5dbc-118">Der Typ eines Felds muss mindestens dieselben Zugriffsmöglichkeiten bieten wie das Feld selbst.</span><span class="sxs-lookup"><span data-stu-id="f5dbc-118">The type of a field must be at least as accessible as the field itself.</span></span>|  
|[<span data-ttu-id="f5dbc-119">Methoden</span><span class="sxs-lookup"><span data-stu-id="f5dbc-119">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)|<span data-ttu-id="f5dbc-120">Die Rückgabe- und Parametertypen einer Methode müssen mindestens dieselben Zugriffsmöglichkeiten bieten wie die Methode selbst.</span><span class="sxs-lookup"><span data-stu-id="f5dbc-120">The return type and parameter types of a method must be at least as accessible as the method itself.</span></span>|  
|[<span data-ttu-id="f5dbc-121">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f5dbc-121">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)|<span data-ttu-id="f5dbc-122">Der Typ einer Eigenschaft muss mindestens dieselben Zugriffsmöglichkeiten bieten wie die Eigenschaft selbst.</span><span class="sxs-lookup"><span data-stu-id="f5dbc-122">The type of a property must be at least as accessible as the property itself.</span></span>|  
|[<span data-ttu-id="f5dbc-123">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="f5dbc-123">Events</span></span>](../../../csharp/programming-guide/events/index.md)|<span data-ttu-id="f5dbc-124">Der Typ eines Ereignisses muss mindestens dieselben Zugriffsmöglichkeiten bieten wie das Ereignis selbst.</span><span class="sxs-lookup"><span data-stu-id="f5dbc-124">The type of an event must be at least as accessible as the event itself.</span></span>|  
|[<span data-ttu-id="f5dbc-125">Indexer</span><span class="sxs-lookup"><span data-stu-id="f5dbc-125">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)|<span data-ttu-id="f5dbc-126">Der Typ und die Parametertypen eines Indexers müssen mindestens dieselben Zugriffsmöglichkeiten bieten wie der Indexer selbst.</span><span class="sxs-lookup"><span data-stu-id="f5dbc-126">The type and parameter types of an indexer must be at least as accessible as the indexer itself.</span></span>|  
|[<span data-ttu-id="f5dbc-127">Operatoren</span><span class="sxs-lookup"><span data-stu-id="f5dbc-127">Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/operators.md)|<span data-ttu-id="f5dbc-128">Die Rückgabe- und Parametertypen eines Operators müssen mindestens dieselben Zugriffsmöglichkeiten bieten wie der Operator selbst.</span><span class="sxs-lookup"><span data-stu-id="f5dbc-128">The return type and parameter types of an operator must be at least as accessible as the operator itself.</span></span>|  
|[<span data-ttu-id="f5dbc-129">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="f5dbc-129">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)|<span data-ttu-id="f5dbc-130">Die Parametertypen eines Konstruktors müssen mindestens dieselben Zugriffsmöglichkeiten bieten wie der Konstruktor selbst.</span><span class="sxs-lookup"><span data-stu-id="f5dbc-130">The parameter types of a constructor must be at least as accessible as the constructor itself.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f5dbc-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f5dbc-131">Example</span></span>  
 <span data-ttu-id="f5dbc-132">Das folgende Beispiel enthält fehlerhafte Deklarationen verschiedener Typen.</span><span class="sxs-lookup"><span data-stu-id="f5dbc-132">The following example contains erroneous declarations of different types.</span></span> <span data-ttu-id="f5dbc-133">Der Kommentar nach jeder Deklaration gibt den erwarteten Compilerfehler an.</span><span class="sxs-lookup"><span data-stu-id="f5dbc-133">The comment following each declaration indicates the expected compiler error.</span></span>  
  
```  
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
  
## <a name="c-language-specification"></a><span data-ttu-id="f5dbc-134">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="f5dbc-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f5dbc-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5dbc-135">See Also</span></span>  
 [<span data-ttu-id="f5dbc-136">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f5dbc-136">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f5dbc-137">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f5dbc-137">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f5dbc-138">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f5dbc-138">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="f5dbc-139">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="f5dbc-139">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="f5dbc-140">Zugriffsdomäne</span><span class="sxs-lookup"><span data-stu-id="f5dbc-140">Accessibility Domain</span></span>](../../../csharp/language-reference/keywords/accessibility-domain.md)  
 [<span data-ttu-id="f5dbc-141">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="f5dbc-141">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="f5dbc-142">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="f5dbc-142">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="f5dbc-143">public</span><span class="sxs-lookup"><span data-stu-id="f5dbc-143">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="f5dbc-144">private</span><span class="sxs-lookup"><span data-stu-id="f5dbc-144">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="f5dbc-145">protected</span><span class="sxs-lookup"><span data-stu-id="f5dbc-145">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="f5dbc-146">internal</span><span class="sxs-lookup"><span data-stu-id="f5dbc-146">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
