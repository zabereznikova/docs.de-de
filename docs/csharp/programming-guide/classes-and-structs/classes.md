---
title: Klassen – C#-Programmierhandbuch
description: Erfahren Sie mehr über die Klassentypen und wie diese erstellt werden
ms.date: 08/21/2018
helpviewer_keywords:
- classes [C#]
- C# language, classes
ms.assetid: e8848524-7273-429f-8aba-c658d5eff5ad
ms.openlocfilehash: aadf555fb47963eab323bbb6105227c5b119e6f4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79170311"
---
# <a name="classes-c-programming-guide"></a><span data-ttu-id="dbf8c-103">Klassen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="dbf8c-103">Classes (C# Programming Guide)</span></span>

## <a name="reference-types"></a><span data-ttu-id="dbf8c-104">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="dbf8c-104">Reference types</span></span>  
<span data-ttu-id="dbf8c-105">Ein Typ, der als [Klasse](../../language-reference/keywords/class.md) definiert ist, ist ein *Referenztyp*.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-105">A type that is defined as a [class](../../language-reference/keywords/class.md) is a *reference type*.</span></span> <span data-ttu-id="dbf8c-106">Wenn Sie zur Laufzeit eine Variable eines Referenztyps deklarieren, enthält die Variable zunächst den Wert [NULL](../../language-reference/keywords/null.md), bis Sie explizit eine Instanz der Klasse mithilfe des Operators [new](../../language-reference/operators/new-operator.md) erstellen oder ihr ein Objekt eines kompatiblen Typs zuweisen, das wie im folgenden Beispiel möglicherweise an anderer Stelle erstellt wurde:</span><span class="sxs-lookup"><span data-stu-id="dbf8c-106">At run time, when you declare a variable of a reference type, the variable contains the value [null](../../language-reference/keywords/null.md) until you explicitly create an instance of the class by using the [new](../../language-reference/operators/new-operator.md) operator, or assign it an object of a compatible type that may have been created elsewhere, as shown in the following example:</span></span>

```csharp
//Declaring an object of type MyClass.
MyClass mc = new MyClass();

//Declaring another object of the same type, assigning it the value of the first object.
MyClass mc2 = mc;
```

<span data-ttu-id="dbf8c-107">Beim Erstellen des Objekts wird im verwalteten Heap für dieses bestimmte Objekt ausreichend Speicherplatz zugewiesen. Die Variable enthält lediglich einen Verweis auf den Speicherort dieses Objekts.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-107">When the object is created, enough memory is allocated on the managed heap for that specific object, and the variable holds only a reference to the location of said object.</span></span> <span data-ttu-id="dbf8c-108">Für Typen im verwalteten Heap ist Mehraufwand erforderlich, wenn sie zugewiesen werden und wenn sie von der automatischen Speicherverwaltungsfunktion der CLR freigegeben werden, was als *Garbage Collection* bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-108">Types on the managed heap require overhead both when they are allocated and when they are reclaimed by the automatic memory management functionality of the CLR, which is known as *garbage collection*.</span></span> <span data-ttu-id="dbf8c-109">Die Garbage Collection ist jedoch auch stark optimiert. In den meisten Szenarios führt sie nicht zu einem Leistungsproblem.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-109">However, garbage collection is also highly optimized and in most scenarios, it does not create a performance issue.</span></span> <span data-ttu-id="dbf8c-110">Weitere Informationen zur Garbage Collection finden Sie unter [Automatische Speicherverwaltung und Garbage Collection](../../../standard/garbage-collection/gc.md).</span><span class="sxs-lookup"><span data-stu-id="dbf8c-110">For more information about garbage collection, see [Automatic memory management and garbage collection](../../../standard/garbage-collection/gc.md).</span></span>  
  
## <a name="declaring-classes"></a><span data-ttu-id="dbf8c-111">Deklarieren von Klassen</span><span class="sxs-lookup"><span data-stu-id="dbf8c-111">Declaring Classes</span></span>

 <span data-ttu-id="dbf8c-112">Klassen werden mithilfe des Schlüsselworts [class](../../language-reference/keywords/class.md) gefolgt von einem eindeutigen Bezeichner deklariert, wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="dbf8c-112">Classes are declared by using the [class](../../language-reference/keywords/class.md) keyword followed by a unique identifier, as shown in the following example:</span></span>

 ```csharp
//[access modifier] - [class] - [identifier]
 public class Customer
 {
    // Fields, properties, methods and events go here...
 }
```

 <span data-ttu-id="dbf8c-113">Das `class`-Schlüsselwort wird der Zugriffsebene vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-113">The `class` keyword is preceded by the access level.</span></span> <span data-ttu-id="dbf8c-114">Jeder kann Instanzen dieser Klasse erstellen, da in diesem Fall [public](../../language-reference/keywords/public.md) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-114">Because [public](../../language-reference/keywords/public.md) is used in this case, anyone can create instances of this class.</span></span> <span data-ttu-id="dbf8c-115">Der Name der Klasse folgt dem `class`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-115">The name of the class follows the `class` keyword.</span></span> <span data-ttu-id="dbf8c-116">Der Name der Klasse muss ein gültiger C#-[Bezeichnername](../inside-a-program/identifier-names.md) sein.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-116">The name of the class must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span> <span data-ttu-id="dbf8c-117">Der Rest der Definition ist der Text einer Klasse, in dem das Verhalten und die Daten definiert sind.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-117">The remainder of the definition is the class body, where the behavior and data are defined.</span></span> <span data-ttu-id="dbf8c-118">Felder, Eigenschaften, Methoden und Ereignisse für eine Klasse werden zusammen als *Klassenmember* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-118">Fields, properties, methods, and events on a class are collectively referred to as *class members*.</span></span>  
  
## <a name="creating-objects"></a><span data-ttu-id="dbf8c-119">Erstellen von Objekten</span><span class="sxs-lookup"><span data-stu-id="dbf8c-119">Creating objects</span></span>

<span data-ttu-id="dbf8c-120">Obwohl sie manchmal synonym werden, sind eine Klasse und ein Objekt unterschiedliche Dinge.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-120">Although they are sometimes used interchangeably, a class and an object are different things.</span></span> <span data-ttu-id="dbf8c-121">Eine Klasse definiert einen Objekttyp, ist aber selbst kein Objekt.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-121">A class defines a type of object, but it is not an object itself.</span></span> <span data-ttu-id="dbf8c-122">Ein Objekt ist eine konkrete Entität, basierend auf einer Klasse, und wird manchmal als Instanz einer Klasse bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-122">An object is a concrete entity based on a class, and is sometimes referred to as an instance of a class.</span></span>  
  
 <span data-ttu-id="dbf8c-123">Objekte können mithilfe des Schlüsselworts [new](../../language-reference/operators/new-operator.md) erstellt werden, gefolgt vom Namen der Klasse, auf der das Objekt basiert, z.B.:</span><span class="sxs-lookup"><span data-stu-id="dbf8c-123">Objects can be created by using the [new](../../language-reference/operators/new-operator.md) keyword followed by the name of the class that the object will be based on, like this:</span></span>  

 ```csharp
 Customer object1 = new Customer();
 ```

 <span data-ttu-id="dbf8c-124">Wenn eine Instanz einer Klasse erstellt wird, wird ein Verweis auf das Objekt zurück an den Programmierer übergeben.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-124">When an instance of a class is created, a reference to the object is passed back to the programmer.</span></span> <span data-ttu-id="dbf8c-125">Im vorherigen Beispiel ist `object1` ein Verweis auf ein Objekt, das auf `Customer` basiert.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-125">In the previous example, `object1` is a reference to an object that is based on `Customer`.</span></span> <span data-ttu-id="dbf8c-126">Dieser Verweis bezieht sich auf das neue Objekt, enthält jedoch nicht die Objektdaten selbst.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-126">This reference refers to the new object but does not contain the object data itself.</span></span> <span data-ttu-id="dbf8c-127">In der Tat können Sie einen Objektverweis erstellen, ohne ein Objekt zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="dbf8c-127">In fact, you can create an object reference without creating an object at all:</span></span>  

```csharp
 Customer object2;
```

 <span data-ttu-id="dbf8c-128">Es wird nicht empfohlen, einen Objektverweis wie diesen zu erstellen, der auf kein Objekt verweist. Der Versuch, auf ein Objekt über solch einen Verweis zuzugreifen, schlägt während der Laufzeit fehl.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-128">We don't recommend creating object references such as this one that don't refer to an object because trying to access an object through such a reference will fail at run time.</span></span> <span data-ttu-id="dbf8c-129">Allerdings kann ein solcher Verweis zum Verweisen auf ein Objekt entweder durch Erstellen eines neues Objekts gemacht werden oder indem Sie ihn einem vorhandenen Objekt zuweisen, z.B.:</span><span class="sxs-lookup"><span data-stu-id="dbf8c-129">However, such a reference can be made to refer to an object, either by creating a new object, or by assigning it to an existing object, such as this:</span></span>  

 ```csharp
 Customer object3 = new Customer();
 Customer object4 = object3;
```
  
 <span data-ttu-id="dbf8c-130">Dieser Code erstellt zwei Objektverweise, die beide auf dasselbe Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-130">This code creates two object references that both refer to the same object.</span></span> <span data-ttu-id="dbf8c-131">Aus diesem Grund werden alle Änderungen am Objekt, die über `object3` getätigt worden sind, bei nachfolgenden Verwendungen von `object4` berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-131">Therefore, any changes to the object made through `object3` are reflected in subsequent uses of `object4`.</span></span> <span data-ttu-id="dbf8c-132">Da auf Objekte, die auf Klassen basieren, durch Verweise zurückgegriffen werden, sind Klassen als Verweistypen bekannt.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-132">Because objects that are based on classes are referred to by reference, classes are known as reference types.</span></span>  
  
## <a name="class-inheritance"></a><span data-ttu-id="dbf8c-133">Klassenvererbung</span><span class="sxs-lookup"><span data-stu-id="dbf8c-133">Class inheritance</span></span>  

<span data-ttu-id="dbf8c-134">Klassen unterstützen die *Vererbung* vollständig. Dies ist ein wesentliches Merkmal der objektorientierten Programmierung.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-134">Classes fully support *inheritance*, a fundamental characteristic of object-oriented programming.</span></span> <span data-ttu-id="dbf8c-135">Wenn Sie eine Klasse erstellen, können Sie von einer anderen Schnittstelle oder Klasse erben, die nicht als [versiegelt](../../language-reference/keywords/sealed.md) definiert ist. Andere Klassen können von Ihrer Klasse erben und die virtuellen Methoden überschreiben.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-135">When you create a class, you can inherit from any other interface or class that is not defined as [sealed](../../language-reference/keywords/sealed.md), and other classes can inherit from your class and override class virtual methods.</span></span>

<span data-ttu-id="dbf8c-136">Die Vererbung erfolgt durch Verwendung einer *Ableitung*, d.h., dass eine Klasse mithilfe einer *Basisklasse* deklariert wird, von der Sie Daten und Verhalten erbt.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-136">Inheritance is accomplished by using a *derivation*, which means a class is declared by using a *base class* from which it inherits data and behavior.</span></span> <span data-ttu-id="dbf8c-137">Eine Basisklasse wird durch Anhängen eines Doppelpunkts sowie des Namens der Basisklasse angegeben, die dem abgeleiteten Klassennamen folgt, z.B.:</span><span class="sxs-lookup"><span data-stu-id="dbf8c-137">A base class is specified by appending a colon and the name of the base class following the derived class name, like this:</span></span>  

 ```csharp
 public class Manager : Employee
 {
     // Employee fields, properties, methods and events are inherited
     // New Manager fields, properties, methods and events go here...
 }
 ```

<span data-ttu-id="dbf8c-138">Wenn eine Klasse eine Basisklasse deklariert, erbt sie alle Member der Basisklasse mit Ausnahme der Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-138">When a class declares a base class, it inherits all the members of the base class except the constructors.</span></span> <span data-ttu-id="dbf8c-139">Weitere Informationen finden Sie unter [Inheritance (Vererbung)](inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="dbf8c-139">For more information, see [Inheritance](inheritance.md).</span></span>
  
<span data-ttu-id="dbf8c-140">Anders als in C++ kann eine Klasse in C# nur direkt von einer Basisklasse erben.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-140">Unlike C++, a class in C# can only directly inherit from one base class.</span></span> <span data-ttu-id="dbf8c-141">Da jedoch eine Basisklasse von einer anderen Klasse erben kann, kann eine Klasse indirekt von mehreren Basisklassen erben.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-141">However, because a base class may itself inherit from another class, a class may indirectly inherit multiple base classes.</span></span> <span data-ttu-id="dbf8c-142">Darüber hinaus kann eine Klasse mehr als eine Schnittstelle direkt implementieren.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-142">Furthermore, a class can directly implement more than one interface.</span></span> <span data-ttu-id="dbf8c-143">Weitere Informationen finden Sie unter [Schnittstellen](../interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="dbf8c-143">For more information, see [Interfaces](../interfaces/index.md).</span></span>  
  
<span data-ttu-id="dbf8c-144">Eine Klasse kann als [abstrakt](../../language-reference/keywords/abstract.md) deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-144">A class can be declared [abstract](../../language-reference/keywords/abstract.md).</span></span> <span data-ttu-id="dbf8c-145">Eine abstrakte Klasse enthält abstrakte Methoden, die über eine Signaturdefinition, aber keine Implementierung verfügen.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-145">An abstract class contains abstract methods that have a signature definition but no implementation.</span></span> <span data-ttu-id="dbf8c-146">Abstrakte Klassen dürfen nicht instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-146">Abstract classes cannot be instantiated.</span></span> <span data-ttu-id="dbf8c-147">Sie können nur mithilfe von abgeleiteten Klassen verwendet werden, die die abstrakten Methoden implementieren.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-147">They can only be used through derived classes that implement the abstract methods.</span></span> <span data-ttu-id="dbf8c-148">Im Gegensatz dazu lässt eine [versiegelte](../../language-reference/keywords/sealed.md) Klasse nicht zu, dass andere Klassen von ihr ableiten.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-148">By contrast, a [sealed](../../language-reference/keywords/sealed.md) class does not allow other classes to derive from it.</span></span> <span data-ttu-id="dbf8c-149">Weitere Informationen finden Sie unter [Abstrakte und versiegelte Klassen und Klassenmember](abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="dbf8c-149">For more information, see [Abstract and Sealed Classes and Class Members](abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
<span data-ttu-id="dbf8c-150">Klassendefinitionen können zwischen verschiedenen Quelldateien aufgeteilt werden.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-150">Class definitions can be split between different source files.</span></span> <span data-ttu-id="dbf8c-151">Weitere Informationen finden Sie unter [Partielle Klassen und Methoden](partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="dbf8c-151">For more information, see [Partial Classes and Methods](partial-classes-and-methods.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbf8c-152">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dbf8c-152">Example</span></span>

<span data-ttu-id="dbf8c-153">Im folgenden Beispiel wird eine öffentliche Klasse definiert, die [eine automatisch implementierte Eigenschaft](auto-implemented-properties.md), eine Methode und eine spezielle Methode, einen sogenannten Konstruktor, enthält.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-153">The following example defines a public class that contains an [auto-implemented property](auto-implemented-properties.md), a method, and a special method called a constructor.</span></span> <span data-ttu-id="dbf8c-154">Weitere Informationen finden Sie in den Artikeln zu [Eigenschaften](properties.md), [Methoden](methods.md) und [Konstruktoren](constructors.md).</span><span class="sxs-lookup"><span data-stu-id="dbf8c-154">For more information, see [Properties](properties.md), [Methods](methods.md), and [Constructors](constructors.md) topics.</span></span> <span data-ttu-id="dbf8c-155">Die Instanzen der Klasse werden mit dem Schlüsselwort `new` instanziiert.</span><span class="sxs-lookup"><span data-stu-id="dbf8c-155">The instances of the class are then instantiated with the `new` keyword.</span></span>  
  
[!code-csharp[Class Example](~/samples/snippets/csharp/programming-guide/classes-and-structs/class-example.cs)]
  
## <a name="c-language-specification"></a><span data-ttu-id="dbf8c-156">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="dbf8c-156">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dbf8c-157">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dbf8c-157">See also</span></span>

- [<span data-ttu-id="dbf8c-158">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="dbf8c-158">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="dbf8c-159">Objektorientierte Programmierung</span><span class="sxs-lookup"><span data-stu-id="dbf8c-159">Object-Oriented Programming</span></span>](../concepts/object-oriented-programming.md)
- [<span data-ttu-id="dbf8c-160">Polymorphismus</span><span class="sxs-lookup"><span data-stu-id="dbf8c-160">Polymorphism</span></span>](polymorphism.md)
- [<span data-ttu-id="dbf8c-161">Bezeichnernamen</span><span class="sxs-lookup"><span data-stu-id="dbf8c-161">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="dbf8c-162">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="dbf8c-162">Members</span></span>](members.md)
- [<span data-ttu-id="dbf8c-163">Methoden</span><span class="sxs-lookup"><span data-stu-id="dbf8c-163">Methods</span></span>](methods.md)
- [<span data-ttu-id="dbf8c-164">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="dbf8c-164">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="dbf8c-165">Finalizer</span><span class="sxs-lookup"><span data-stu-id="dbf8c-165">Finalizers</span></span>](destructors.md)
- [<span data-ttu-id="dbf8c-166">Objekte</span><span class="sxs-lookup"><span data-stu-id="dbf8c-166">Objects</span></span>](objects.md)
