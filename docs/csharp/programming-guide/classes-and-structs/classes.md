---
title: Klassen – C#-Programmierhandbuch
description: Erfahren Sie mehr über die Klassentypen und wie diese erstellt werden
ms.date: 08/21/2018
helpviewer_keywords:
- classes [C#]
- C# language, classes
ms.assetid: e8848524-7273-429f-8aba-c658d5eff5ad
ms.openlocfilehash: 8fa8d33ce9ece20a18c5c1542bc44cf569e9fa2e
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440405"
---
# <a name="classes-c-programming-guide"></a><span data-ttu-id="a5bd2-103">Klassen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="a5bd2-103">Classes (C# Programming Guide)</span></span>

## <a name="reference-types"></a><span data-ttu-id="a5bd2-104">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="a5bd2-104">Reference types</span></span>  

<span data-ttu-id="a5bd2-105">Ein Typ, der als [Klasse](../../language-reference/keywords/class.md) definiert ist, ist ein *Referenztyp*.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-105">A type that is defined as a [class](../../language-reference/keywords/class.md) is a *reference type*.</span></span> <span data-ttu-id="a5bd2-106">Wenn Sie zur Laufzeit eine Variable eines Referenztyps deklarieren, enthält die Variable zunächst den Wert [NULL](../../language-reference/keywords/null.md), bis Sie explizit eine Instanz der Klasse mithilfe des Operators [new](../../language-reference/operators/new-operator.md) erstellen oder ihr ein Objekt eines kompatiblen Typs zuweisen, das wie im folgenden Beispiel möglicherweise an anderer Stelle erstellt wurde:</span><span class="sxs-lookup"><span data-stu-id="a5bd2-106">At run time, when you declare a variable of a reference type, the variable contains the value [null](../../language-reference/keywords/null.md) until you explicitly create an instance of the class by using the [new](../../language-reference/operators/new-operator.md) operator, or assign it an object of a compatible type that may have been created elsewhere, as shown in the following example:</span></span>

```csharp
//Declaring an object of type MyClass.
MyClass mc = new MyClass();

//Declaring another object of the same type, assigning it the value of the first object.
MyClass mc2 = mc;
```

<span data-ttu-id="a5bd2-107">Beim Erstellen des Objekts wird im verwalteten Heap für dieses bestimmte Objekt ausreichend Speicherplatz zugewiesen. Die Variable enthält lediglich einen Verweis auf den Speicherort dieses Objekts.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-107">When the object is created, enough memory is allocated on the managed heap for that specific object, and the variable holds only a reference to the location of said object.</span></span> <span data-ttu-id="a5bd2-108">Für Typen im verwalteten Heap ist Mehraufwand erforderlich, wenn sie zugewiesen werden und wenn sie von der automatischen Speicherverwaltungsfunktion der CLR freigegeben werden, was als *Garbage Collection* bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-108">Types on the managed heap require overhead both when they are allocated and when they are reclaimed by the automatic memory management functionality of the CLR, which is known as *garbage collection*.</span></span> <span data-ttu-id="a5bd2-109">Die Garbage Collection ist jedoch auch stark optimiert. In den meisten Szenarios führt sie nicht zu einem Leistungsproblem.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-109">However, garbage collection is also highly optimized and in most scenarios, it does not create a performance issue.</span></span> <span data-ttu-id="a5bd2-110">Weitere Informationen zur Garbage Collection finden Sie unter [Automatische Speicherverwaltung und Garbage Collection](../../../standard/garbage-collection/fundamentals.md).</span><span class="sxs-lookup"><span data-stu-id="a5bd2-110">For more information about garbage collection, see [Automatic memory management and garbage collection](../../../standard/garbage-collection/fundamentals.md).</span></span>  
  
## <a name="declaring-classes"></a><span data-ttu-id="a5bd2-111">Deklarieren von Klassen</span><span class="sxs-lookup"><span data-stu-id="a5bd2-111">Declaring Classes</span></span>

 <span data-ttu-id="a5bd2-112">Klassen werden mithilfe des Schlüsselworts [class](../../language-reference/keywords/class.md) gefolgt von einem eindeutigen Bezeichner deklariert, wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="a5bd2-112">Classes are declared by using the [class](../../language-reference/keywords/class.md) keyword followed by a unique identifier, as shown in the following example:</span></span>

 ```csharp
//[access modifier] - [class] - [identifier]
 public class Customer
 {
    // Fields, properties, methods and events go here...
 }
```

 <span data-ttu-id="a5bd2-113">Das `class`-Schlüsselwort wird der Zugriffsebene vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-113">The `class` keyword is preceded by the access level.</span></span> <span data-ttu-id="a5bd2-114">Jeder kann Instanzen dieser Klasse erstellen, da in diesem Fall [public](../../language-reference/keywords/public.md) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-114">Because [public](../../language-reference/keywords/public.md) is used in this case, anyone can create instances of this class.</span></span> <span data-ttu-id="a5bd2-115">Der Name der Klasse folgt dem `class`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-115">The name of the class follows the `class` keyword.</span></span> <span data-ttu-id="a5bd2-116">Der Name der Klasse muss ein gültiger C#-[Bezeichnername](../inside-a-program/identifier-names.md) sein.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-116">The name of the class must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span> <span data-ttu-id="a5bd2-117">Der Rest der Definition ist der Text einer Klasse, in dem das Verhalten und die Daten definiert sind.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-117">The remainder of the definition is the class body, where the behavior and data are defined.</span></span> <span data-ttu-id="a5bd2-118">Felder, Eigenschaften, Methoden und Ereignisse für eine Klasse werden zusammen als *Klassenmember* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-118">Fields, properties, methods, and events on a class are collectively referred to as *class members*.</span></span>  
  
## <a name="creating-objects"></a><span data-ttu-id="a5bd2-119">Erstellen von Objekten</span><span class="sxs-lookup"><span data-stu-id="a5bd2-119">Creating objects</span></span>

<span data-ttu-id="a5bd2-120">Obwohl sie manchmal synonym werden, sind eine Klasse und ein Objekt unterschiedliche Dinge.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-120">Although they are sometimes used interchangeably, a class and an object are different things.</span></span> <span data-ttu-id="a5bd2-121">Eine Klasse definiert einen Typ eines Objekts, aber es ist kein Objekt selbst.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-121">A class defines a type of object, but it is not an object itself.</span></span> <span data-ttu-id="a5bd2-122">Ein Objekt ist eine konkrete Entität, basierend auf einer Klasse, und wird manchmal als Instanz einer Klasse bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-122">An object is a concrete entity based on a class, and is sometimes referred to as an instance of a class.</span></span>  
  
 <span data-ttu-id="a5bd2-123">Objekte können mithilfe des Schlüsselworts [new](../../language-reference/operators/new-operator.md) erstellt werden, gefolgt vom Namen der Klasse, auf die das Objekt basiert, z.B.:</span><span class="sxs-lookup"><span data-stu-id="a5bd2-123">Objects can be created by using the [new](../../language-reference/operators/new-operator.md) keyword followed by the name of the class that the object will be based on, like this:</span></span>  

 ```csharp
 Customer object1 = new Customer();
 ```

 <span data-ttu-id="a5bd2-124">Wenn eine Instanz einer Klasse erstellt wird, wird ein Verweis auf das Objekt an den Programmierer übergeben.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-124">When an instance of a class is created, a reference to the object is passed back to the programmer.</span></span> <span data-ttu-id="a5bd2-125">Im vorherigen Beispiel ist `object1` ein Verweis auf ein Objekt, das auf `Customer` basiert.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-125">In the previous example, `object1` is a reference to an object that is based on `Customer`.</span></span> <span data-ttu-id="a5bd2-126">Dieser Verweis bezieht sich auf das neue Objekt, enthält jedoch nicht die Objektdaten selbst.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-126">This reference refers to the new object but does not contain the object data itself.</span></span> <span data-ttu-id="a5bd2-127">In der Tat können Sie einen Objektverweis erstellen, ohne ein Objekt zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="a5bd2-127">In fact, you can create an object reference without creating an object at all:</span></span>  

```csharp
 Customer object2;
```

 <span data-ttu-id="a5bd2-128">Es wird nicht empfohlen, einen Objektverweis wie diesen zu erstellen, der auf kein Objekt verweist. Der Versuch, auf ein Objekt über solch einen Verweis zuzugreifen, schlägt während der Laufzeit fehl.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-128">We don't recommend creating object references such as this one that don't refer to an object because trying to access an object through such a reference will fail at run time.</span></span> <span data-ttu-id="a5bd2-129">Allerdings kann ein solcher Verweis dazu veranlasst werden, auf ein Objekt zu verweisen, indem entweder ein neues Objekt erstellt wird oder indem es einem vorhandenen Objekt zugewiesen wird, z. B.:</span><span class="sxs-lookup"><span data-stu-id="a5bd2-129">However, such a reference can be made to refer to an object, either by creating a new object, or by assigning it an existing object, such as this:</span></span>  

 ```csharp
 Customer object3 = new Customer();
 Customer object4 = object3;
```
  
 <span data-ttu-id="a5bd2-130">Dieser Code erstellt zwei Objektverweise, die beide auf dasselbe Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-130">This code creates two object references that both refer to the same object.</span></span> <span data-ttu-id="a5bd2-131">Aus diesem Grund werden alle Änderungen am Objekt, die über `object3` getätigt worden sind, bei nachfolgenden Verwendungen von `object4` berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-131">Therefore, any changes to the object made through `object3` are reflected in subsequent uses of `object4`.</span></span> <span data-ttu-id="a5bd2-132">Da auf Objekte, die auf Klassen basieren, durch Verweise zurückgegriffen werden, sind Klassen als Verweistypen bekannt.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-132">Because objects that are based on classes are referred to by reference, classes are known as reference types.</span></span>  
  
## <a name="class-inheritance"></a><span data-ttu-id="a5bd2-133">Klassenvererbung</span><span class="sxs-lookup"><span data-stu-id="a5bd2-133">Class inheritance</span></span>  

<span data-ttu-id="a5bd2-134">Klassen unterstützen die *Vererbung* vollständig. Dies ist ein wesentliches Merkmal der objektorientierten Programmierung.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-134">Classes fully support *inheritance*, a fundamental characteristic of object-oriented programming.</span></span> <span data-ttu-id="a5bd2-135">Wenn Sie eine Klasse erstellen, können Sie von einer anderen Klasse erben, die nicht als [versiegelt](../../language-reference/keywords/sealed.md) definiert ist. Andere Klassen können von Ihrer Klasse erben und die virtuellen Methoden überschreiben.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-135">When you create a class, you can inherit from any other class that is not defined as [sealed](../../language-reference/keywords/sealed.md), and other classes can inherit from your class and override class virtual methods.</span></span> <span data-ttu-id="a5bd2-136">Außerdem kann eine Struktur eine oder mehrere Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-136">Furthermore, you can implement one or more interfaces.</span></span>

<span data-ttu-id="a5bd2-137">Die Vererbung erfolgt durch Verwendung einer *Ableitung*, d.h., dass eine Klasse mithilfe einer *Basisklasse* deklariert wird, aus der Sie Daten und das Verhalten erbt.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-137">Inheritance is accomplished by using a *derivation*, which means a class is declared by using a *base class* from which it inherits data and behavior.</span></span> <span data-ttu-id="a5bd2-138">Eine Basisklasse wird durch Anhängen eines Doppelpunkts sowie den Namen der Basisklasse angegeben, die dem abgeleiteten Klassennamen folgt, z.B.:</span><span class="sxs-lookup"><span data-stu-id="a5bd2-138">A base class is specified by appending a colon and the name of the base class following the derived class name, like this:</span></span>  

 ```csharp
 public class Manager : Employee
 {
     // Employee fields, properties, methods and events are inherited
     // New Manager fields, properties, methods and events go here...
 }
 ```

<span data-ttu-id="a5bd2-139">Wenn eine Klasse eine Basisklasse deklariert, erbt sie alle Member der Basisklasse mit Ausnahme der Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-139">When a class declares a base class, it inherits all the members of the base class except the constructors.</span></span> <span data-ttu-id="a5bd2-140">Weitere Informationen finden Sie unter [Vererbung](inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="a5bd2-140">For more information, see [Inheritance](inheritance.md).</span></span>
  
<span data-ttu-id="a5bd2-141">Anders als in C++ kann eine Klasse in C# nur direkt von einer Basisklasse erben.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-141">Unlike C++, a class in C# can only directly inherit from one base class.</span></span> <span data-ttu-id="a5bd2-142">Da jedoch eine Basisklasse von einer anderen Klasse erben kann, kann eine Klasse indirekt von mehreren Basisklassen erben.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-142">However, because a base class may itself inherit from another class, a class may indirectly inherit multiple base classes.</span></span> <span data-ttu-id="a5bd2-143">Darüber hinaus kann eine Klasse mehr als eine Schnittstelle direkt implementieren.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-143">Furthermore, a class can directly implement one or more interfaces.</span></span> <span data-ttu-id="a5bd2-144">Weitere Informationen finden Sie unter [Schnittstellen](../interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="a5bd2-144">For more information, see [Interfaces](../interfaces/index.md).</span></span>  
  
<span data-ttu-id="a5bd2-145">Eine Klasse kann als [abstrakt](../../language-reference/keywords/abstract.md) deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-145">A class can be declared [abstract](../../language-reference/keywords/abstract.md).</span></span> <span data-ttu-id="a5bd2-146">Eine abstrakte Klasse enthält abstrakte Methoden, die über eine Signaturdefinition, aber keine Implementierung verfügen.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-146">An abstract class contains abstract methods that have a signature definition but no implementation.</span></span> <span data-ttu-id="a5bd2-147">Abstrakte Klassen dürfen nicht instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-147">Abstract classes cannot be instantiated.</span></span> <span data-ttu-id="a5bd2-148">Sie können nur mithilfe von abgeleiteten Klassen verwendet werden, die die abstrakten Methoden implementieren.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-148">They can only be used through derived classes that implement the abstract methods.</span></span> <span data-ttu-id="a5bd2-149">Im Gegensatz dazu lässt eine [versiegelte](../../language-reference/keywords/sealed.md) Klasse nicht zu, dass andere Klassen von ihr ableiten.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-149">By contrast, a [sealed](../../language-reference/keywords/sealed.md) class does not allow other classes to derive from it.</span></span> <span data-ttu-id="a5bd2-150">Weitere Informationen finden Sie unter [Abstrakte und versiegelte Klassen und Klassenmember](abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="a5bd2-150">For more information, see [Abstract and Sealed Classes and Class Members](abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
<span data-ttu-id="a5bd2-151">Klassendefinitionen können zwischen verschiedenen Quelldateien aufgeteilt werden.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-151">Class definitions can be split between different source files.</span></span> <span data-ttu-id="a5bd2-152">Weitere Informationen finden Sie unter [Partielle Klassen und Methoden](partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="a5bd2-152">For more information, see [Partial Classes and Methods](partial-classes-and-methods.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5bd2-153">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5bd2-153">Example</span></span>

<span data-ttu-id="a5bd2-154">Im folgenden Beispiel wird eine öffentliche Klasse definiert, die [eine automatisch implementierte Eigenschaft](auto-implemented-properties.md), eine Methode und eine spezielle Methode, einen sogenannten Konstruktor, enthält.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-154">The following example defines a public class that contains an [auto-implemented property](auto-implemented-properties.md), a method, and a special method called a constructor.</span></span> <span data-ttu-id="a5bd2-155">Weitere Informationen finden Sie in den Artikeln zu [Eigenschaften](properties.md), [Methoden](methods.md) und [Konstruktoren](constructors.md).</span><span class="sxs-lookup"><span data-stu-id="a5bd2-155">For more information, see [Properties](properties.md), [Methods](methods.md), and [Constructors](constructors.md) topics.</span></span> <span data-ttu-id="a5bd2-156">Die Instanzen der Klasse werden mit dem Schlüsselwort `new` instanziiert.</span><span class="sxs-lookup"><span data-stu-id="a5bd2-156">The instances of the class are then instantiated with the `new` keyword.</span></span>  
  
[!code-csharp[Class Example](~/samples/snippets/csharp/programming-guide/classes-and-structs/class-example.cs)]
  
## <a name="c-language-specification"></a><span data-ttu-id="a5bd2-157">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="a5bd2-157">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a5bd2-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5bd2-158">See also</span></span>

- [<span data-ttu-id="a5bd2-159">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a5bd2-159">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a5bd2-160">Objektorientierte Programmierung</span><span class="sxs-lookup"><span data-stu-id="a5bd2-160">Object-Oriented Programming</span></span>](../../tutorials/intro-to-csharp/object-oriented-programming.md)
- [<span data-ttu-id="a5bd2-161">Polymorphismus</span><span class="sxs-lookup"><span data-stu-id="a5bd2-161">Polymorphism</span></span>](polymorphism.md)
- [<span data-ttu-id="a5bd2-162">Bezeichnernamen</span><span class="sxs-lookup"><span data-stu-id="a5bd2-162">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="a5bd2-163">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="a5bd2-163">Members</span></span>](members.md)
- [<span data-ttu-id="a5bd2-164">Methoden</span><span class="sxs-lookup"><span data-stu-id="a5bd2-164">Methods</span></span>](methods.md)
- [<span data-ttu-id="a5bd2-165">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="a5bd2-165">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="a5bd2-166">Finalizer</span><span class="sxs-lookup"><span data-stu-id="a5bd2-166">Finalizers</span></span>](destructors.md)
- [<span data-ttu-id="a5bd2-167">Objekte</span><span class="sxs-lookup"><span data-stu-id="a5bd2-167">Objects</span></span>](objects.md)
