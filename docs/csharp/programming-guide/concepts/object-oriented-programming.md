---
title: Objektorientiertes Programmieren (C#)
ms.date: 05/13/2020
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: 83140a9dbd16f60f04f50ba18c71099cdd862f15
ms.sourcegitcommit: 67cf756b033c6173a1bbd1cbd5aef1fccac99e34
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2020
ms.locfileid: "86226633"
---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="c0a67-102">Objektorientiertes Programmieren (C#)</span><span class="sxs-lookup"><span data-stu-id="c0a67-102">Object-Oriented programming (C#)</span></span>

<span data-ttu-id="c0a67-103">C# bietet vollständige Unterstützung für objektorientierte Programmierung, einschließlich Abstraktion, Kapselung, Vererbung und Polymorphie.</span><span class="sxs-lookup"><span data-stu-id="c0a67-103">C# provides full support for object-oriented programming including abstraction, encapsulation, inheritance, and polymorphism.</span></span>

- <span data-ttu-id="c0a67-104">*Abstraktion* bedeutet, dass die unnötigen Details von Typconsumern ausgeblendet werden.</span><span class="sxs-lookup"><span data-stu-id="c0a67-104">*Abstraction* means hiding the unnecessary details from type consumers.</span></span>
- <span data-ttu-id="c0a67-105">*Kapselung* bedeutet, dass eine Gruppe verwandter Eigenschaften, Methoden sowie anderer Member als eine Einheit bzw. ein Objekt behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="c0a67-105">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>
- <span data-ttu-id="c0a67-106">*Vererbung* beschreibt die Fähigkeit, neue Klassen basierend auf einer vorhandenen Klasse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c0a67-106">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>
- <span data-ttu-id="c0a67-107">*Polymorphismus* bedeutet, dass Sie mehrere Klassen untereinander austauschen können, obwohl jede Klasse dieselben Eigenschaften oder Methoden auf unterschiedliche Art und Weise implementiert.</span><span class="sxs-lookup"><span data-stu-id="c0a67-107">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

## <a name="classes-and-objects"></a><span data-ttu-id="c0a67-108">Klassen und Objekte</span><span class="sxs-lookup"><span data-stu-id="c0a67-108">Classes and objects</span></span>

<span data-ttu-id="c0a67-109">Die Begriffe *Klasse* und *Objekt* beschreiben jeweils den *Typ* von Objekten und die *Instanzen* von Klassen.</span><span class="sxs-lookup"><span data-stu-id="c0a67-109">The terms *class* and *object* describe the *type* of objects, and the *instances* of classes, respectively.</span></span> <span data-ttu-id="c0a67-110">Das Erstellen eines Objekts wird daher als *Instanziierung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c0a67-110">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="c0a67-111">Um auf den Vergleich mit Bauplänen zurückzukommen: Eine Klasse ist ein Bauplan, und ein Objekt ist ein anhand dieses Bauplans errichtetes Gebäude.</span><span class="sxs-lookup"><span data-stu-id="c0a67-111">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="c0a67-112">So definieren Sie eine Klasse</span><span class="sxs-lookup"><span data-stu-id="c0a67-112">To define a class:</span></span>

```csharp
class SampleClass
{
}
```

<span data-ttu-id="c0a67-113">C# stellt auch Typen namens *Strukturen* bereit, die nützlich sind, wenn Sie keine Unterstützung für Vererbungen oder Polymorphie benötigen.</span><span class="sxs-lookup"><span data-stu-id="c0a67-113">C# also provides types called *structures* that are useful when you don't need support for inheritance or polymorphism.</span></span> <span data-ttu-id="c0a67-114">Weitere Informationen finden Sie unter [Auswählen zwischen Klassen und Strukturen](../../../standard/design-guidelines/choosing-between-class-and-struct.md).</span><span class="sxs-lookup"><span data-stu-id="c0a67-114">For more information, see [Choosing between class and struct](../../../standard/design-guidelines/choosing-between-class-and-struct.md).</span></span>

<span data-ttu-id="c0a67-115">So definieren Sie eine Struktur</span><span class="sxs-lookup"><span data-stu-id="c0a67-115">To define a structure:</span></span>

```csharp
struct SampleStruct
{
}
```

<span data-ttu-id="c0a67-116">Weitere Informationen finden Sie in den Artikeln zu den Schlüsselwörtern [Klasse](../../language-reference/keywords/class.md) und [Struktur](../../language-reference/builtin-types/struct.md).</span><span class="sxs-lookup"><span data-stu-id="c0a67-116">For more information, see the articles on the [class](../../language-reference/keywords/class.md) and [struct](../../language-reference/builtin-types/struct.md) keywords.</span></span>

### <a name="class-members"></a><span data-ttu-id="c0a67-117">Klassenmember</span><span class="sxs-lookup"><span data-stu-id="c0a67-117">Class members</span></span>

<span data-ttu-id="c0a67-118">Jede Klasse kann über andere *Klassenmember* verfügen. Diese enthalten Eigenschaften, die Klassendaten beschreiben, Methoden, die Klassenverhalten definieren sowie Ereignisse, die die Kommunikation zwischen verschiedenen Klassen und Objekten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c0a67-118">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="properties-and-fields"></a><span data-ttu-id="c0a67-119">Eigenschaften und Felder</span><span class="sxs-lookup"><span data-stu-id="c0a67-119">Properties and fields</span></span>

<span data-ttu-id="c0a67-120">Felder und Eigenschaften stellen die in einem Objekt enthaltenen Informationen dar.</span><span class="sxs-lookup"><span data-stu-id="c0a67-120">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="c0a67-121">Felder sind wie Variablen, sie können direkt gelesen oder festgelegt werden und unterliegen anwendbaren Zugriffsmodifizierern.</span><span class="sxs-lookup"><span data-stu-id="c0a67-121">Fields are like variables because they can be read or set directly, subject to applicable access modifiers.</span></span>

<span data-ttu-id="c0a67-122">So definieren Sie ein Feld, auf das innerhalb von Instanzen der Klasse zugegriffen werden kann:</span><span class="sxs-lookup"><span data-stu-id="c0a67-122">To define a field that can be accessed from within instances of the class:</span></span>

```csharp
public class SampleClass
{
    string sampleField;
}
```

<span data-ttu-id="c0a67-123">Eigenschaften verfügen über `get`- und `set`-Zugriffsmethoden, die eine bessere Kontrolle über das Festlegen oder Abrufen von Werten ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c0a67-123">Properties have `get` and `set` accessors, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="c0a67-124">Mit C# können Sie ein privates Feld erstellen, um den Eigenschaftswert zu speichern, oder Sie können automatisch implementierte Eigenschaften verwenden, die dieses Feld automatisch im Hintergrund erstellen und die grundlegende Logik für die Eigenschaftenprozeduren bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c0a67-124">C# allows you either to create a private field for storing the property value or use auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="c0a67-125">So definieren Sie eine automatisch implementierte Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="c0a67-125">To define an auto-implemented property:</span></span>

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

<span data-ttu-id="c0a67-126">Verwenden Sie den folgenden Code, wenn Sie zusätzliche Lese- und Schreibvorgänge für den Eigenschaftswert ausführen müssen, um ein Feld zum Speichern des Eigenschaftswerts zu definieren und die grundlegende Logik zum Speichern und Abrufen bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="c0a67-126">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

```csharp
class SampleClass
{
    private int _sample;
    public int Sample
    {
        // Return the value stored in a field.
        get => _sample;
        // Store the value in the field.
        set =>  _sample = value;
    }
}
```

<span data-ttu-id="c0a67-127">Die meisten Eigenschaften verfügen über Methoden oder Prozeduren zum Festlegen und Abrufen des Eigenschaftswerts.</span><span class="sxs-lookup"><span data-stu-id="c0a67-127">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="c0a67-128">Sie können jedoch schreib- oder lesegeschützte Eigenschaften erstellen, um zu verhindern, dass die Eigenschaften gelesen oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="c0a67-128">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="c0a67-129">In C# muss die `get`-Eigenschaftenmethode oder die `set`-Eigenschaftenmethode nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c0a67-129">In C#, you can omit the `get` or `set` property method.</span></span> <span data-ttu-id="c0a67-130">Automatisch implementierte Eigenschaften können jedoch nicht lesegeschützt sein.</span><span class="sxs-lookup"><span data-stu-id="c0a67-130">However, auto-implemented properties cannot be write-only.</span></span> <span data-ttu-id="c0a67-131">Schreibgeschützte automatisch implementierte Eigenschaften können in Konstruktoren der enthaltenden Klasse festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c0a67-131">Read-only auto-implemented properties can be set in constructors of the containing class.</span></span>

<span data-ttu-id="c0a67-132">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="c0a67-132">For more information, see:</span></span>

- [<span data-ttu-id="c0a67-133">get</span><span class="sxs-lookup"><span data-stu-id="c0a67-133">get</span></span>](../../language-reference/keywords/get.md)
- [<span data-ttu-id="c0a67-134">set</span><span class="sxs-lookup"><span data-stu-id="c0a67-134">set</span></span>](../../language-reference/keywords/set.md)

#### <a name="methods"></a><span data-ttu-id="c0a67-135">Methoden</span><span class="sxs-lookup"><span data-stu-id="c0a67-135">Methods</span></span>

<span data-ttu-id="c0a67-136">Eine *Methode* ist eine Aktion, die von einem Objekt ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c0a67-136">A *method* is an action that an object can perform.</span></span>

<span data-ttu-id="c0a67-137">So definieren Sie eine Methode einer Klasse:</span><span class="sxs-lookup"><span data-stu-id="c0a67-137">To define a method of a class:</span></span>

```csharp
class SampleClass
{
    public int SampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

<span data-ttu-id="c0a67-138">Eine Klasse kann über mehrere Implementierungen oder *Überladungen* der gleichen Methode verfügen, die sich in der Anzahl der Parameter oder Parametertypen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c0a67-138">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="c0a67-139">So überladen Sie eine Methode</span><span class="sxs-lookup"><span data-stu-id="c0a67-139">To overload a method:</span></span>

```csharp
public int SampleMethod(string sampleParam) { }
public int SampleMethod(int sampleParam) { }
```

<span data-ttu-id="c0a67-140">In den meisten Fällen deklarieren Sie eine Methode innerhalb einer Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="c0a67-140">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="c0a67-141">Auch C# unterstützt jedoch *Erweiterungsmethoden*, mit denen Sie einer vorhandenen Klasse außerhalb der eigentlichen Klassendefinition Methoden hinzuzufügen können.</span><span class="sxs-lookup"><span data-stu-id="c0a67-141">However, C# also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="c0a67-142">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="c0a67-142">For more information, see:</span></span>

- [<span data-ttu-id="c0a67-143">Methoden</span><span class="sxs-lookup"><span data-stu-id="c0a67-143">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="c0a67-144">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="c0a67-144">Extension Methods</span></span>](../classes-and-structs/extension-methods.md)

#### <a name="constructors"></a><span data-ttu-id="c0a67-145">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="c0a67-145">Constructors</span></span>

<span data-ttu-id="c0a67-146">Konstruktoren sind Klassenmethoden, die automatisch ausgeführt werden, wenn ein Objekt eines bestimmten Typs erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c0a67-146">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="c0a67-147">Konstruktoren initialisieren normalerweise die Datenmember des neuen Objekts.</span><span class="sxs-lookup"><span data-stu-id="c0a67-147">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="c0a67-148">Konstruktoren können nur einmal während der Erstellung der Klasse ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c0a67-148">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="c0a67-149">Weiterhin wird der Code im Konstruktor immer vor jedem anderen Code in einer Klasse ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c0a67-149">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="c0a67-150">Sie können jedoch mehrere Konstruktorüberladungen auf die gleiche Weise wie für jede andere Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="c0a67-150">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="c0a67-151">So definieren Sie einen Konstruktor für eine Klasse:</span><span class="sxs-lookup"><span data-stu-id="c0a67-151">To define a constructor for a class:</span></span>

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

<span data-ttu-id="c0a67-152">Weitere Informationen finden Sie unter [Konstruktoren](../classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="c0a67-152">For more information, see [Constructors](../classes-and-structs/constructors.md).</span></span>

#### <a name="finalizers"></a><span data-ttu-id="c0a67-153">Finalizer</span><span class="sxs-lookup"><span data-stu-id="c0a67-153">Finalizers</span></span>

<span data-ttu-id="c0a67-154">Ein Finalizer wird zur Zerstörung von Klasseninstanzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0a67-154">A finalizer is used to destruct instances of classes.</span></span> <span data-ttu-id="c0a67-155">In .NET verwaltet der Garbage Collector automatisch die Belegung und Freigabe von Arbeitsspeicher für die verwalteten Objekte in Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c0a67-155">In .NET, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="c0a67-156">Möglicherweise sind jedoch noch Finalizer erforderlich, um alle nicht verwalteten Ressourcen zu bereinigen, die von der Anwendung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c0a67-156">However, you may still need finalizers to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="c0a67-157">Es kann nur einen Finalizer pro Klasse geben.</span><span class="sxs-lookup"><span data-stu-id="c0a67-157">There can be only one finalizer for a class.</span></span>

<span data-ttu-id="c0a67-158">Weitere Informationen zu Finalizern und der Garbage Collection in .NET finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="c0a67-158">For more information about finalizers and garbage collection in .NET, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="events"></a><span data-ttu-id="c0a67-159">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="c0a67-159">Events</span></span>

<span data-ttu-id="c0a67-160">Ereignisse aktivieren eine Klasse oder ein Objekt, um Informationen über Aktionen von Interesse an andere Klassen oder Objekte zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="c0a67-160">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="c0a67-161">Die Klasse, die das Ereignis sendet (oder auslöst), wird als *Herausgeber* bezeichnet, und die Klassen, die das Ereignis empfangen (oder verarbeiten), werden als *Abonnenten* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c0a67-161">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="c0a67-162">Weitere Informationen zu Ereignissen sowie zu ihrer Auslösung und Behandlung finden Sie unter [Ereignisse](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="c0a67-162">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="c0a67-163">Verwenden Sie das Schlüsselwort [event](../../language-reference/keywords/event.md), um ein Ereignis in einer Klasse zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="c0a67-163">To declare an event in a class, use the [event](../../language-reference/keywords/event.md) keyword.</span></span>
- <span data-ttu-id="c0a67-164">Um ein Ereignis auszulösen, rufen Sie den Ereignisdelegaten auf.</span><span class="sxs-lookup"><span data-stu-id="c0a67-164">To raise an event, invoke the event delegate.</span></span>
- <span data-ttu-id="c0a67-165">Verwenden Sie den `+=`-Operator, um ein Ereignis zu abonnieren, und verwenden Sie den `-=`-Operator, um das Abonnement eines Ereignisses zu kündigen.</span><span class="sxs-lookup"><span data-stu-id="c0a67-165">To subscribe to an event, use the `+=` operator; to unsubscribe from an event, use the `-=` operator.</span></span>

#### <a name="nested-classes"></a><span data-ttu-id="c0a67-166">Geschachtelte Klassen</span><span class="sxs-lookup"><span data-stu-id="c0a67-166">Nested classes</span></span>

<span data-ttu-id="c0a67-167">Eine Klasse, die in einer anderen Klasse definiert wird, wird als *geschachtelt* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c0a67-167">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="c0a67-168">Standardmäßig ist die geschachtelte Klasse privat.</span><span class="sxs-lookup"><span data-stu-id="c0a67-168">By default, the nested class is private.</span></span>

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

<span data-ttu-id="c0a67-169">Um eine Instanz der geschachtelten Klasse zu erstellen, verwenden Sie den Namen der Containerklasse und geben einen Punkt sowie anschließend den Namen der geschachtelten Klasse ein:</span><span class="sxs-lookup"><span data-stu-id="c0a67-169">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a><span data-ttu-id="c0a67-170">Zugriffsmodifizierer und Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="c0a67-170">Access modifiers and access levels</span></span>

<span data-ttu-id="c0a67-171">Alle Klassen und Klassenmember können mit *Zugriffsmodifizierern* angeben, welche Zugriffsebene sie für andere Klassen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c0a67-171">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="c0a67-172">Die folgenden Zugriffsmodifizierer sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="c0a67-172">The following access modifiers are available:</span></span>

| <span data-ttu-id="c0a67-173">C#-Modifizierer</span><span class="sxs-lookup"><span data-stu-id="c0a67-173">C# Modifier</span></span> | <span data-ttu-id="c0a67-174">Definition</span><span class="sxs-lookup"><span data-stu-id="c0a67-174">Definition</span></span> |
|--|--|
| [<span data-ttu-id="c0a67-175">public</span><span class="sxs-lookup"><span data-stu-id="c0a67-175">public</span></span>](../../language-reference/keywords/public.md) | <span data-ttu-id="c0a67-176">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder einer anderen Assembly, die darauf verweist, zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="c0a67-176">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span> |
| [<span data-ttu-id="c0a67-177">private</span><span class="sxs-lookup"><span data-stu-id="c0a67-177">private</span></span>](../../language-reference/keywords/private.md) | <span data-ttu-id="c0a67-178">Auf den Typ oder Member kann nur von Code in der gleichen Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="c0a67-178">The type or member can only be accessed by code in the same class.</span></span> |
| [<span data-ttu-id="c0a67-179">protected</span><span class="sxs-lookup"><span data-stu-id="c0a67-179">protected</span></span>](../../language-reference/keywords/protected.md) | <span data-ttu-id="c0a67-180">Auf den Typ oder Member kann nur von Code in der gleichen Klasse oder in einer abgeleiteten Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="c0a67-180">The type or member can only be accessed by code in the same class or in a derived class.</span></span> |
| [<span data-ttu-id="c0a67-181">internal</span><span class="sxs-lookup"><span data-stu-id="c0a67-181">internal</span></span>](../../language-reference/keywords/internal.md) | <span data-ttu-id="c0a67-182">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly zugegriffen werden, jedoch nicht von Code in einer anderen Assembly.</span><span class="sxs-lookup"><span data-stu-id="c0a67-182">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span> |
| [<span data-ttu-id="c0a67-183">protected internal</span><span class="sxs-lookup"><span data-stu-id="c0a67-183">protected internal</span></span>](../../language-reference/keywords/protected-internal.md) | <span data-ttu-id="c0a67-184">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder von jeder abgeleiteten Klasse in einer anderen Assembly zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="c0a67-184">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span> |
| [<span data-ttu-id="c0a67-185">private protected</span><span class="sxs-lookup"><span data-stu-id="c0a67-185">private protected</span></span>](../../language-reference/keywords/private-protected.md) | <span data-ttu-id="c0a67-186">Auf den Typ oder Member kann nur über Code in der gleichen Klasse, in einer abgeleiteten Klasse oder innerhalb der Basisklassenassembly zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="c0a67-186">The type or member can be accessed by code in the same class or in a derived class within the base class assembly.</span></span> |

<span data-ttu-id="c0a67-187">Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="c0a67-187">For more information, see [Access Modifiers](../classes-and-structs/access-modifiers.md).</span></span>

### <a name="instantiating-classes"></a><span data-ttu-id="c0a67-188">Instanziieren von Klassen</span><span class="sxs-lookup"><span data-stu-id="c0a67-188">Instantiating classes</span></span>

<span data-ttu-id="c0a67-189">Um ein Objekt zu erstellen, müssen Sie eine Klasse instanziieren oder eine Klasseninstanz erstellen.</span><span class="sxs-lookup"><span data-stu-id="c0a67-189">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```csharp
SampleClass sampleObject = new SampleClass();
```

<span data-ttu-id="c0a67-190">Nachdem Sie eine Klasse instanziiert haben, können Sie den Eigenschaften und Feldern der Instanz Werte zuweisen und Klassenmethoden aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c0a67-190">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.SampleMethod();
```

<span data-ttu-id="c0a67-191">Verwenden Sie Objektinitialisierer, um Eigenschaften im Rahmen des Klasseninstanziierungsprozesses Werte zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="c0a67-191">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```csharp
// Set a property value.
var sampleObject = new SampleClass
{
    FirstProperty = "A",
    SecondProperty = "B"
};
```

<span data-ttu-id="c0a67-192">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="c0a67-192">For more information, see:</span></span>

- [<span data-ttu-id="c0a67-193">new-Operator</span><span class="sxs-lookup"><span data-stu-id="c0a67-193">new Operator</span></span>](../../language-reference/operators/new-operator.md)
- [<span data-ttu-id="c0a67-194">Objekt- und Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="c0a67-194">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)

### <a name="static-classes-and-members"></a><span data-ttu-id="c0a67-195">Statische Klassen und Member</span><span class="sxs-lookup"><span data-stu-id="c0a67-195">Static Classes and Members</span></span>

<span data-ttu-id="c0a67-196">Ein statischer Member der Klasse ist eine Eigenschaft, eine Prozedur oder ein Feld, die von allen Instanzen einer Klasse gemeinsam verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c0a67-196">A static member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

<span data-ttu-id="c0a67-197">So definieren Sie einen statischen Member:</span><span class="sxs-lookup"><span data-stu-id="c0a67-197">To define a static member:</span></span>

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

<span data-ttu-id="c0a67-198">Verwenden Sie den Namen der Klasse, ohne ein Objekt dieser Klasse zu erstellen, um auf den statischen Member zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="c0a67-198">To access the static member, use the name of the class without creating an object of this class:</span></span>

```csharp
Console.WriteLine(SampleClass.SampleString);
```

<span data-ttu-id="c0a67-199">Statische Klassen in C# haben nur statische Member und können nicht instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="c0a67-199">Static  classes in C# have static members only and cannot be instantiated.</span></span> <span data-ttu-id="c0a67-200">Statische Member können auch nicht auf nicht statische Eigenschaften, Felder oder Methoden zugreifen.</span><span class="sxs-lookup"><span data-stu-id="c0a67-200">Static members also cannot access non-static  properties, fields or methods</span></span>

<span data-ttu-id="c0a67-201">Weitere Informationen finden Sie unter [static](../../language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="c0a67-201">For more information, see: [static](../../language-reference/keywords/static.md).</span></span>

### <a name="anonymous-types"></a><span data-ttu-id="c0a67-202">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="c0a67-202">Anonymous types</span></span>

<span data-ttu-id="c0a67-203">Mit anonymen Typen können Objekte erstellt werden, ohne eine Klassendefinition für den Datentyp zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="c0a67-203">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="c0a67-204">Stattdessen erzeugt der Compiler eine Klasse.</span><span class="sxs-lookup"><span data-stu-id="c0a67-204">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="c0a67-205">Die Klasse hat keinen verwendbaren Namen und enthält die von Ihnen in der Deklaration des Objekts angegebenen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="c0a67-205">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="c0a67-206">So erstellen Sie eine Instanz eines anonymen Typs</span><span class="sxs-lookup"><span data-stu-id="c0a67-206">To create an instance of an anonymous type:</span></span>

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject = new
{
    FirstProperty = "A",
    SecondProperty = "B"
};
```

<span data-ttu-id="c0a67-207">Weitere Informationen finden Sie unter: [Anonyme Typen](../classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="c0a67-207">For more information, see: [Anonymous Types](../classes-and-structs/anonymous-types.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="c0a67-208">Vererbung</span><span class="sxs-lookup"><span data-stu-id="c0a67-208">Inheritance</span></span>

<span data-ttu-id="c0a67-209">Vererbung ermöglicht die Erstellung neuer Klassen, die in anderen Klassen definiertes Verhalten wieder verwenden, erweitern und ändern.</span><span class="sxs-lookup"><span data-stu-id="c0a67-209">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="c0a67-210">Die Klasse, deren Member vererbt werden, wird *Basisklasse* genannt, und die Klasse, die diese Member erbt, wird *abgeleitete Klasse* genannt.</span><span class="sxs-lookup"><span data-stu-id="c0a67-210">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="c0a67-211">Alle Klassen in C# erben jedoch implizit von der Klasse <xref:System.Object>, die die .NET-Klassenhierarchie unterstützt und einfache Dienste für alle Klassen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="c0a67-211">However, all classes in C# implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="c0a67-212">C# unterstützt keine mehrfache Vererbung.</span><span class="sxs-lookup"><span data-stu-id="c0a67-212">C# doesn't support multiple inheritance.</span></span> <span data-ttu-id="c0a67-213">Sie können also nur eine Basisklasse für eine abgeleitete Klasse angeben.</span><span class="sxs-lookup"><span data-stu-id="c0a67-213">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="c0a67-214">So erben Sie von einer Basisklasse</span><span class="sxs-lookup"><span data-stu-id="c0a67-214">To inherit from a base class:</span></span>

```csharp
class DerivedClass:BaseClass { }
```

<span data-ttu-id="c0a67-215">Standardmäßig können alle Klassen geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="c0a67-215">By default all classes can be inherited.</span></span> <span data-ttu-id="c0a67-216">Sie können jedoch angeben, dass eine Klasse nicht als Basisklasse verwendet werden darf, oder eine Klasse erstellen, die nur als Basisklasse verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c0a67-216">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="c0a67-217">So geben Sie an, dass eine Klasse nicht als Basisklasse verwendet werden kann</span><span class="sxs-lookup"><span data-stu-id="c0a67-217">To specify that a class cannot be used as a base class:</span></span>

```csharp
public sealed class A { }
```

<span data-ttu-id="c0a67-218">So geben Sie an, dass eine Klasse nur als Basisklasse verwendet und nicht instanziiert werden kann:</span><span class="sxs-lookup"><span data-stu-id="c0a67-218">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```csharp
public abstract class B { }
```

<span data-ttu-id="c0a67-219">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="c0a67-219">For more information, see:</span></span>

- [<span data-ttu-id="c0a67-220">sealed</span><span class="sxs-lookup"><span data-stu-id="c0a67-220">sealed</span></span>](../../language-reference/keywords/sealed.md)
- [<span data-ttu-id="c0a67-221">abstract</span><span class="sxs-lookup"><span data-stu-id="c0a67-221">abstract</span></span>](../../language-reference/keywords/abstract.md)

### <a name="overriding-members"></a><span data-ttu-id="c0a67-222">Überschreiben von Membern</span><span class="sxs-lookup"><span data-stu-id="c0a67-222">Overriding Members</span></span>

<span data-ttu-id="c0a67-223">Standardmäßig erbt eine abgeleitete Klasse alle Member von ihrer Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="c0a67-223">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="c0a67-224">Wenn Sie das Verhalten des geerbten Members ändern möchten, müssen Sie diesen überschreiben.</span><span class="sxs-lookup"><span data-stu-id="c0a67-224">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="c0a67-225">Das heißt, Sie können eine neue Implementierung der Methode, der Eigenschaft oder des Ereignisses in der abgeleiteten Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="c0a67-225">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="c0a67-226">Mit folgenden Modifizierern steuern Sie das Überschreiben von Eigenschaften und Methoden:</span><span class="sxs-lookup"><span data-stu-id="c0a67-226">The following modifiers are used to control how properties and methods are overridden:</span></span>

| <span data-ttu-id="c0a67-227">C#-Modifizierer</span><span class="sxs-lookup"><span data-stu-id="c0a67-227">C# Modifier</span></span> | <span data-ttu-id="c0a67-228">Definition</span><span class="sxs-lookup"><span data-stu-id="c0a67-228">Definition</span></span> |
|--|--|
| [<span data-ttu-id="c0a67-229">virtual</span><span class="sxs-lookup"><span data-stu-id="c0a67-229">virtual</span></span>](../../language-reference/keywords/virtual.md) | <span data-ttu-id="c0a67-230">Ermöglicht das Überschreiben eines Klassenmembers in einer abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="c0a67-230">Allows a class member to be overridden in a derived class.</span></span> |
| [<span data-ttu-id="c0a67-231">override</span><span class="sxs-lookup"><span data-stu-id="c0a67-231">override</span></span>](../../language-reference/keywords/override.md) | <span data-ttu-id="c0a67-232">Überschreibt einen virtuellen (überschreibbaren) Member, der in der Basisklasse definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c0a67-232">Overrides a virtual (overridable) member defined in the base class.</span></span> |
| [<span data-ttu-id="c0a67-233">abstract</span><span class="sxs-lookup"><span data-stu-id="c0a67-233">abstract</span></span>](../../language-reference/keywords/abstract.md) | <span data-ttu-id="c0a67-234">Erfordert das Überschreiben eines Klassenmembers in der abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="c0a67-234">Requires that a class member to be overridden in the derived class.</span></span> |
| [<span data-ttu-id="c0a67-235">new-Modifizierer</span><span class="sxs-lookup"><span data-stu-id="c0a67-235">new Modifier</span></span>](../../language-reference/keywords/new-modifier.md) | <span data-ttu-id="c0a67-236">Blendet einen von einer Basisklasse geerbten Member aus.</span><span class="sxs-lookup"><span data-stu-id="c0a67-236">Hides a member inherited from a base class</span></span> |

## <a name="interfaces"></a><span data-ttu-id="c0a67-237">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c0a67-237">Interfaces</span></span>

<span data-ttu-id="c0a67-238">Schnittstellen definieren (wie Klassen) einen Satz von Eigenschaften, Methoden und Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="c0a67-238">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="c0a67-239">Im Gegensatz zu Klassen jedoch bieten Schnittstellen keine Implementierung.</span><span class="sxs-lookup"><span data-stu-id="c0a67-239">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="c0a67-240">Sie werden durch Klassen implementiert und als von Klassen unabhängige Entitäten definiert.</span><span class="sxs-lookup"><span data-stu-id="c0a67-240">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="c0a67-241">Eine Schnittstelle stellt insofern einen Vertrag dar, dass eine Klasse, die eine Schnittstelle implementiert, jeden Aspekt dieser Schnittstelle gemäß seiner Definition implementieren muss.</span><span class="sxs-lookup"><span data-stu-id="c0a67-241">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="c0a67-242">So definieren Sie eine Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0a67-242">To define an interface:</span></span>

```csharp
interface ISampleInterface
{
    void DoSomething();
}
```

<span data-ttu-id="c0a67-243">So implementieren Sie eine Schnittstelle in einer Klasse</span><span class="sxs-lookup"><span data-stu-id="c0a67-243">To implement an interface in a class:</span></span>

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.DoSomething()
    {
        // Method implementation.
    }
}
```

<span data-ttu-id="c0a67-244">Weitere Informationen finden Sie im Programmierleitfaden zu [Schnittstellen](../interfaces/index.md) und der Sprachreferenz zum Schlüsselwort [Schnittstelle](../../language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="c0a67-244">For more information, see the programming guide article on [Interfaces](../interfaces/index.md) and the language reference article on the [interface](../../language-reference/keywords/interface.md) keyword.</span></span>

## <a name="generics"></a><span data-ttu-id="c0a67-245">Generics</span><span class="sxs-lookup"><span data-stu-id="c0a67-245">Generics</span></span>

<span data-ttu-id="c0a67-246">Klassen, Strukturen, Schnittstellen und Methoden in .NET können *Typparameter* enthalten, die Objekttypen definieren, die sie speichern oder verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c0a67-246">Classes, structures, interfaces, and methods in .NET can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="c0a67-247">Das einfachste Beispiel für Generics ist eine Auflistung, in der Sie den Typ von Objekten angeben können, die in einer Auflistung gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c0a67-247">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="c0a67-248">So definieren Sie eine generische Klasse</span><span class="sxs-lookup"><span data-stu-id="c0a67-248">To define a generic class:</span></span>

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

<span data-ttu-id="c0a67-249">So erstellen Sie eine Instanz einer generischen Klasse</span><span class="sxs-lookup"><span data-stu-id="c0a67-249">To create an instance of a generic class:</span></span>

```csharp
var sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

<span data-ttu-id="c0a67-250">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="c0a67-250">For more information, see:</span></span>

- [<span data-ttu-id="c0a67-251">Generics in .NET</span><span class="sxs-lookup"><span data-stu-id="c0a67-251">Generics in .NET</span></span>](../../../standard/generics/index.md)
- [<span data-ttu-id="c0a67-252">Generics (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="c0a67-252">Generics - C# Programming Guide</span></span>](../generics/index.md)

## <a name="delegates"></a><span data-ttu-id="c0a67-253">Delegaten</span><span class="sxs-lookup"><span data-stu-id="c0a67-253">Delegates</span></span>

<span data-ttu-id="c0a67-254">Ein *Delegat* ist ein Typ, der eine Methodensignatur definiert. Er kann einen Verweis auf jede Methode bereitstellen, die über eine kompatible Signatur verfügt.</span><span class="sxs-lookup"><span data-stu-id="c0a67-254">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="c0a67-255">Sie können die Methode über den Delegaten aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c0a67-255">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="c0a67-256">Delegaten werden verwendet, um Methoden als Argumente an anderen Methoden zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="c0a67-256">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="c0a67-257">Ereignishandler sind nichts weiter als Methoden, die durch Delegaten aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c0a67-257">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="c0a67-258">Weitere Informationen zur Ereignisbehandlung mit Delegaten finden Sie unter [Ereignisse](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="c0a67-258">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="c0a67-259">So erstellen Sie einen Delegaten</span><span class="sxs-lookup"><span data-stu-id="c0a67-259">To create a delegate:</span></span>

```csharp
public delegate void SampleDelegate(string str);
```

<span data-ttu-id="c0a67-260">So erstellen Sie einen Verweis auf eine Methode, die der vom Delegaten angegebenen Signatur entspricht:</span><span class="sxs-lookup"><span data-stu-id="c0a67-260">To create a reference to a method that matches the signature specified by the delegate:</span></span>

```csharp
class SampleClass
{
    // Method that matches the SampleDelegate signature.
    public static void SampleMethod(string message)
    {
        // Add code here.
    }

    // Method that instantiates the delegate.
    void SampleDelegate()
    {
        SampleDelegate sd = sampleMethod;
        sd("Sample string");
    }
}
```

<span data-ttu-id="c0a67-261">Weitere Informationen finden Sie im Programmierleitfaden zu [Delegaten](../delegates/index.md) und der Sprachreferenz zum Schlüsselwort [Delegat](../../language-reference/builtin-types/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="c0a67-261">For more information, see the programming guide article on [Delegates](../delegates/index.md) and the language reference article on the [delegate](../../language-reference/builtin-types/reference-types.md) keyword.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0a67-262">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0a67-262">See also</span></span>

- [<span data-ttu-id="c0a67-263">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c0a67-263">C# Programming Guide</span></span>](../index.md)
