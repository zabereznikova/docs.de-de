---
title: Objektorientiertes Programmieren (C#)
ms.date: 07/20/2015
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: 1de150f6eb4be893ca1afce6bd16afde5752c986
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711821"
---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="42043-102">Objektorientiertes Programmieren (C#)</span><span class="sxs-lookup"><span data-stu-id="42043-102">Object-Oriented Programming (C#)</span></span>

<span data-ttu-id="42043-103">C# bietet vollständige Unterstützung für objektorientierte Programmierung, einschließlich Kapselung, Vererbung und Polymorphie.</span><span class="sxs-lookup"><span data-stu-id="42043-103">C# provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>

<span data-ttu-id="42043-104">*Kapselung* bedeutet, dass eine Gruppe verwandter Eigenschaften, Methoden sowie anderer Member als eine Einheit bzw. ein Objekt behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="42043-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>

<span data-ttu-id="42043-105">*Vererbung* beschreibt die Fähigkeit, neue Klassen basierend auf einer vorhandenen Klasse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="42043-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>

<span data-ttu-id="42043-106">*Polymorphismus* bedeutet, dass Sie mehrere Klassen untereinander austauschen können, obwohl jede Klasse dieselben Eigenschaften oder Methoden auf unterschiedliche Art und Weise implementiert.</span><span class="sxs-lookup"><span data-stu-id="42043-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

<span data-ttu-id="42043-107">In diesem Abschnitt werden die folgenden Konzepte beschrieben:</span><span class="sxs-lookup"><span data-stu-id="42043-107">This section describes the following concepts:</span></span>

- [<span data-ttu-id="42043-108">Klassen und Objekte</span><span class="sxs-lookup"><span data-stu-id="42043-108">Classes and Objects</span></span>](#Classes)

  - [<span data-ttu-id="42043-109">Klassenmember</span><span class="sxs-lookup"><span data-stu-id="42043-109">Class Members</span></span>](#Members)

    - [<span data-ttu-id="42043-110">Eigenschaften und Felder</span><span class="sxs-lookup"><span data-stu-id="42043-110">Properties and Fields</span></span>](#Properties)

    - [<span data-ttu-id="42043-111">Methoden</span><span class="sxs-lookup"><span data-stu-id="42043-111">Methods</span></span>](#Methods)

    - [<span data-ttu-id="42043-112">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="42043-112">Constructors</span></span>](#Constructors)

    - [<span data-ttu-id="42043-113">Finalizer</span><span class="sxs-lookup"><span data-stu-id="42043-113">Finalizers</span></span>](#Finalizers)

    - [<span data-ttu-id="42043-114">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="42043-114">Events</span></span>](#Events)

    - [<span data-ttu-id="42043-115">Geschachtelte Klassen</span><span class="sxs-lookup"><span data-stu-id="42043-115">Nested Classes</span></span>](#NestedClasses)

  - [<span data-ttu-id="42043-116">Zugriffsmodifizierer und Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="42043-116">Access Modifiers and Access Levels</span></span>](#AccessModifiers)

  - [<span data-ttu-id="42043-117">Instanziieren von Klassen</span><span class="sxs-lookup"><span data-stu-id="42043-117">Instantiating Classes</span></span>](#InstantiatingClasses)

  - [<span data-ttu-id="42043-118">Statische Klassen und statische Klassenmember</span><span class="sxs-lookup"><span data-stu-id="42043-118">Static Classes and Members</span></span>](#Static)

  - [<span data-ttu-id="42043-119">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="42043-119">Anonymous Types</span></span>](#AnonymousTypes)

- [<span data-ttu-id="42043-120">Vererbung</span><span class="sxs-lookup"><span data-stu-id="42043-120">Inheritance</span></span>](#Inheritance)

  - [<span data-ttu-id="42043-121">Überschreiben von Membern</span><span class="sxs-lookup"><span data-stu-id="42043-121">Overriding Members</span></span>](#Overriding)

- [<span data-ttu-id="42043-122">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="42043-122">Interfaces</span></span>](#Interfaces)

- [<span data-ttu-id="42043-123">Generics</span><span class="sxs-lookup"><span data-stu-id="42043-123">Generics</span></span>](#Generics)

- [<span data-ttu-id="42043-124">Delegaten</span><span class="sxs-lookup"><span data-stu-id="42043-124">Delegates</span></span>](#Delegates)

## <a name="Classes"></a> <span data-ttu-id="42043-125">Klassen und Objekte</span><span class="sxs-lookup"><span data-stu-id="42043-125">Classes and Objects</span></span>

<span data-ttu-id="42043-126">Die Begriffe *Klasse* und *Objekt* werden manchmal synonym verwendet; genau genommen beschreiben Klassen jedoch den *Typ* von Objekten, während Objekte verwendbare *Instanzen* von Klassen sind.</span><span class="sxs-lookup"><span data-stu-id="42043-126">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="42043-127">Das Erstellen eines Objekts wird daher als *Instanziierung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="42043-127">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="42043-128">Um auf den Vergleich mit Bauplänen zurückzukommen: Eine Klasse ist ein Bauplan, und ein Objekt ist ein anhand dieses Bauplans errichtetes Gebäude.</span><span class="sxs-lookup"><span data-stu-id="42043-128">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="42043-129">So definieren Sie eine Klasse</span><span class="sxs-lookup"><span data-stu-id="42043-129">To define a class:</span></span>

```csharp
class SampleClass
{
}
```

<span data-ttu-id="42043-130">Auch C# stellt vereinfachte Versionen von Klassen bereit, die als *Strukturen* bezeichnet werden. Strukturen sind hilfreich, wenn Sie ein großes Objektarray erstellen müssen und nicht zu viel Arbeitsspeicher belegen wollen.</span><span class="sxs-lookup"><span data-stu-id="42043-130">C# also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>

<span data-ttu-id="42043-131">So definieren Sie eine Struktur</span><span class="sxs-lookup"><span data-stu-id="42043-131">To define a structure:</span></span>

```csharp
struct SampleStruct
{
}
```

<span data-ttu-id="42043-132">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="42043-132">For more information, see:</span></span>

- [<span data-ttu-id="42043-133">class</span><span class="sxs-lookup"><span data-stu-id="42043-133">class</span></span>](../../language-reference/keywords/class.md)

- [<span data-ttu-id="42043-134">struct</span><span class="sxs-lookup"><span data-stu-id="42043-134">struct</span></span>](../../language-reference/keywords/struct.md)

### <a name="Members"></a> <span data-ttu-id="42043-135">Klassenmember</span><span class="sxs-lookup"><span data-stu-id="42043-135">Class Members</span></span>

<span data-ttu-id="42043-136">Jede Klasse kann über andere *Klassenmember* verfügen. Diese enthalten Eigenschaften, die Klassendaten beschreiben, Methoden, die Klassenverhalten definieren sowie Ereignisse, die die Kommunikation zwischen verschiedenen Klassen und Objekten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="42043-136">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="Properties"></a> <span data-ttu-id="42043-137">Eigenschaften und Felder</span><span class="sxs-lookup"><span data-stu-id="42043-137">Properties and Fields</span></span>

<span data-ttu-id="42043-138">Felder und Eigenschaften stellen die in einem Objekt enthaltenen Informationen dar.</span><span class="sxs-lookup"><span data-stu-id="42043-138">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="42043-139">Felder sind wie Variablen, sie können direkt gelesen oder festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="42043-139">Fields are like variables because they can be read or set directly.</span></span>

<span data-ttu-id="42043-140">So definieren Sie ein Feld</span><span class="sxs-lookup"><span data-stu-id="42043-140">To define a field:</span></span>

```csharp
class SampleClass
{
    public string sampleField;
}
```

<span data-ttu-id="42043-141">Eigenschaften verfügen über Get- und Set-Prozeduren, die eine bessere Kontrolle über das Festlegen oder Abrufen von Werten ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="42043-141">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="42043-142">Mit C# können Sie ein privates Feld erstellen, um den Eigenschaftswert zu speichern, oder Sie können automatisch implementierte Eigenschaften verwenden, die dieses Feld automatisch im Hintergrund erstellen und die grundlegende Logik für die Eigenschaftenprozeduren bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="42043-142">C# allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="42043-143">So definieren Sie eine automatisch implementierte Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="42043-143">To define an auto-implemented property:</span></span>

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

<span data-ttu-id="42043-144">Verwenden Sie den folgenden Code, wenn Sie zusätzliche Lese- und Schreibvorgänge für den Eigenschaftswert ausführen müssen, um ein Feld zum Speichern des Eigenschaftswerts zu definieren und die grundlegende Logik zum Speichern und Abrufen bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="42043-144">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

```csharp
class SampleClass
{
    private int _sample;
    public int Sample
    {
        // Return the value stored in a field.
        get { return _sample; }
        // Store the value in the field.
        set { _sample = value; }
    }
}
```

<span data-ttu-id="42043-145">Die meisten Eigenschaften verfügen über Methoden oder Prozeduren zum Festlegen und Abrufen des Eigenschaftswerts.</span><span class="sxs-lookup"><span data-stu-id="42043-145">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="42043-146">Sie können jedoch schreib- oder lesegeschützte Eigenschaften erstellen, um zu verhindern, dass die Eigenschaften gelesen oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="42043-146">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="42043-147">In C# muss die `get`-Eigenschaftenmethode oder die `set`-Eigenschaftenmethode nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="42043-147">In C#, you can omit the `get` or `set` property method.</span></span> <span data-ttu-id="42043-148">Automatisch implementierte Eigenschaften können jedoch nicht schreib- oder lesegeschützt sein.</span><span class="sxs-lookup"><span data-stu-id="42043-148">However, auto-implemented properties cannot be read-only or write-only.</span></span>

<span data-ttu-id="42043-149">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="42043-149">For more information, see:</span></span>

- [<span data-ttu-id="42043-150">get</span><span class="sxs-lookup"><span data-stu-id="42043-150">get</span></span>](../../language-reference/keywords/get.md)

- [<span data-ttu-id="42043-151">set</span><span class="sxs-lookup"><span data-stu-id="42043-151">set</span></span>](../../language-reference/keywords/set.md)

#### <a name="Methods"></a> <span data-ttu-id="42043-152">Methoden</span><span class="sxs-lookup"><span data-stu-id="42043-152">Methods</span></span>

<span data-ttu-id="42043-153">Eine *Methode* ist eine Aktion, die von einem Objekt ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="42043-153">A *method* is an action that an object can perform.</span></span>

<span data-ttu-id="42043-154">So definieren Sie eine Methode einer Klasse:</span><span class="sxs-lookup"><span data-stu-id="42043-154">To define a method of a class:</span></span>

```csharp
class SampleClass
{
    public int sampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

<span data-ttu-id="42043-155">Eine Klasse kann über mehrere Implementierungen oder *Überladungen* der gleichen Methode verfügen, die sich in der Anzahl der Parameter oder Parametertypen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="42043-155">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="42043-156">So überladen Sie eine Methode</span><span class="sxs-lookup"><span data-stu-id="42043-156">To overload a method:</span></span>

```csharp
public int sampleMethod(string sampleParam) {}
public int sampleMethod(int sampleParam) {}
```

<span data-ttu-id="42043-157">In den meisten Fällen deklarieren Sie eine Methode innerhalb einer Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="42043-157">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="42043-158">Auch C# unterstützt jedoch *Erweiterungsmethoden*, mit denen Sie einer vorhandenen Klasse außerhalb der eigentlichen Klassendefinition Methoden hinzuzufügen können.</span><span class="sxs-lookup"><span data-stu-id="42043-158">However, C# also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="42043-159">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="42043-159">For more information, see:</span></span>

- [<span data-ttu-id="42043-160">Methoden</span><span class="sxs-lookup"><span data-stu-id="42043-160">Methods</span></span>](../classes-and-structs/methods.md)

- [<span data-ttu-id="42043-161">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="42043-161">Extension Methods</span></span>](../classes-and-structs/extension-methods.md)

#### <a name="Constructors"></a> <span data-ttu-id="42043-162">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="42043-162">Constructors</span></span>

<span data-ttu-id="42043-163">Konstruktoren sind Klassenmethoden, die automatisch ausgeführt werden, wenn ein Objekt eines bestimmten Typs erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="42043-163">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="42043-164">Konstruktoren initialisieren normalerweise die Datenmember des neuen Objekts.</span><span class="sxs-lookup"><span data-stu-id="42043-164">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="42043-165">Konstruktoren können nur einmal während der Erstellung der Klasse ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="42043-165">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="42043-166">Weiterhin wird der Code im Konstruktor immer vor jedem anderen Code in einer Klasse ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="42043-166">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="42043-167">Sie können jedoch mehrere Konstruktorüberladungen auf die gleiche Weise wie für jede andere Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="42043-167">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="42043-168">So definieren Sie einen Konstruktor für eine Klasse:</span><span class="sxs-lookup"><span data-stu-id="42043-168">To define a constructor for a class:</span></span>

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

<span data-ttu-id="42043-169">Weitere Informationen finden Sie unter [Konstruktoren](../classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="42043-169">For more information, see [Constructors](../classes-and-structs/constructors.md).</span></span>

#### <a name="Finalizers"></a> <span data-ttu-id="42043-170">Finalizer</span><span class="sxs-lookup"><span data-stu-id="42043-170">Finalizers</span></span>

<span data-ttu-id="42043-171">Finalizer werden zur Zerstörung von Klasseninstanzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="42043-171">Finalizers are used to destruct instances of classes.</span></span> <span data-ttu-id="42043-172">In .NET Framework verwaltet die Garbage Collection die Speicherbelegung automatisch und gibt Arbeitsspeicher für die verwalteten Objekte in der Anwendung frei.</span><span class="sxs-lookup"><span data-stu-id="42043-172">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="42043-173">Möglicherweise sind jedoch noch Finalizer erforderlich, um alle nicht verwalteten Ressourcen zu bereinigen, die von der Anwendung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="42043-173">However, you may still need finalizers to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="42043-174">Es kann nur einen Finalizer für eine Klasse geben.</span><span class="sxs-lookup"><span data-stu-id="42043-174">There can be only one finalizers for a class.</span></span>

<span data-ttu-id="42043-175">Weitere Informationen zu Finalizern und der Garbage Collection in .NET Framework finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="42043-175">For more information about finalizers and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="Events"></a> <span data-ttu-id="42043-176">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="42043-176">Events</span></span>

<span data-ttu-id="42043-177">Ereignisse aktivieren eine Klasse oder ein Objekt, um Informationen über Aktionen von Interesse an andere Klassen oder Objekte zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="42043-177">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="42043-178">Die Klasse, die das Ereignis sendet (oder auslöst), wird als *Herausgeber* bezeichnet, und die Klassen, die das Ereignis empfangen (oder verarbeiten), werden als *Abonnenten* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="42043-178">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="42043-179">Weitere Informationen zu Ereignissen sowie zu ihrer Auslösung und Behandlung finden Sie unter [Ereignisse](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="42043-179">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="42043-180">Verwenden Sie das Schlüsselwort [event](../../language-reference/keywords/event.md), um ein Ereignis in einer Klasse zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="42043-180">To declare an event in a class, use the [event](../../language-reference/keywords/event.md) keyword.</span></span>

- <span data-ttu-id="42043-181">Um ein Ereignis auszulösen, rufen Sie den Ereignisdelegaten auf.</span><span class="sxs-lookup"><span data-stu-id="42043-181">To raise an event, invoke the event delegate.</span></span>

- <span data-ttu-id="42043-182">Verwenden Sie den `+=`-Operator, um ein Ereignis zu abonnieren, und verwenden Sie den `-=`-Operator, um das Abonnement eines Ereignisses zu kündigen.</span><span class="sxs-lookup"><span data-stu-id="42043-182">To subscribe to an event, use the `+=` operator; to unsubscribe from an event, use the `-=` operator.</span></span>

#### <a name="NestedClasses"></a> <span data-ttu-id="42043-183">Geschachtelte Klassen</span><span class="sxs-lookup"><span data-stu-id="42043-183">Nested Classes</span></span>

<span data-ttu-id="42043-184">Eine Klasse, die in einer anderen Klasse definiert wird, wird als *geschachtelt* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="42043-184">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="42043-185">Standardmäßig ist die geschachtelte Klasse privat.</span><span class="sxs-lookup"><span data-stu-id="42043-185">By default, the nested class is private.</span></span>

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

<span data-ttu-id="42043-186">Um eine Instanz der geschachtelten Klasse zu erstellen, verwenden Sie den Namen der Containerklasse und geben einen Punkt sowie anschließend den Namen der geschachtelten Klasse ein:</span><span class="sxs-lookup"><span data-stu-id="42043-186">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="AccessModifiers"></a> <span data-ttu-id="42043-187">Zugriffsmodifizierer und Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="42043-187">Access Modifiers and Access Levels</span></span>

<span data-ttu-id="42043-188">Alle Klassen und Klassenmember können mit *Zugriffsmodifizierern* angeben, welche Zugriffsebene sie für andere Klassen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="42043-188">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="42043-189">Die folgenden Zugriffsmodifizierer sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="42043-189">The following access modifiers are available:</span></span>

|<span data-ttu-id="42043-190">C#-Modifizierer</span><span class="sxs-lookup"><span data-stu-id="42043-190">C# Modifier</span></span>|<span data-ttu-id="42043-191">Definition</span><span class="sxs-lookup"><span data-stu-id="42043-191">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="42043-192">public</span><span class="sxs-lookup"><span data-stu-id="42043-192">public</span></span>](../../language-reference/keywords/public.md)|<span data-ttu-id="42043-193">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder einer anderen Assembly, die darauf verweist, zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="42043-193">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|
|[<span data-ttu-id="42043-194">private</span><span class="sxs-lookup"><span data-stu-id="42043-194">private</span></span>](../../language-reference/keywords/private.md)|<span data-ttu-id="42043-195">Auf den Typ oder Member kann nur von Code in der gleichen Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="42043-195">The type or member can only be accessed by code in the same class.</span></span>|
|[<span data-ttu-id="42043-196">protected</span><span class="sxs-lookup"><span data-stu-id="42043-196">protected</span></span>](../../language-reference/keywords/protected.md)|<span data-ttu-id="42043-197">Auf den Typ oder Member kann nur von Code in der gleichen Klasse oder in einer abgeleiteten Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="42043-197">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|
|[<span data-ttu-id="42043-198">internal</span><span class="sxs-lookup"><span data-stu-id="42043-198">internal</span></span>](../../language-reference/keywords/internal.md)|<span data-ttu-id="42043-199">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly zugegriffen werden, jedoch nicht von Code in einer anderen Assembly.</span><span class="sxs-lookup"><span data-stu-id="42043-199">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|
|[<span data-ttu-id="42043-200">protected internal</span><span class="sxs-lookup"><span data-stu-id="42043-200">protected internal</span></span>](../../language-reference/keywords/protected-internal.md)|<span data-ttu-id="42043-201">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder von jeder abgeleiteten Klasse in einer anderen Assembly zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="42043-201">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|
|[<span data-ttu-id="42043-202">private protected</span><span class="sxs-lookup"><span data-stu-id="42043-202">private protected</span></span>](../../language-reference/keywords/private-protected.md)|<span data-ttu-id="42043-203">Auf den Typ oder Member kann nur über Code in der gleichen Klasse, in einer abgeleiteten Klasse oder innerhalb der Basisklassenassembly zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="42043-203">The type or member can be accessed by code in the same class or in a derived class within the base class assembly.</span></span>|

<span data-ttu-id="42043-204">Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="42043-204">For more information, see [Access Modifiers](../classes-and-structs/access-modifiers.md).</span></span>

### <a name="InstantiatingClasses"></a> <span data-ttu-id="42043-205">Instanziieren von Klassen</span><span class="sxs-lookup"><span data-stu-id="42043-205">Instantiating Classes</span></span>

<span data-ttu-id="42043-206">Um ein Objekt zu erstellen, müssen Sie eine Klasse instanziieren oder eine Klasseninstanz erstellen.</span><span class="sxs-lookup"><span data-stu-id="42043-206">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```csharp
SampleClass sampleObject = new SampleClass();
```

<span data-ttu-id="42043-207">Nachdem Sie eine Klasse instanziiert haben, können Sie den Eigenschaften und Feldern der Instanz Werte zuweisen und Klassenmethoden aufrufen.</span><span class="sxs-lookup"><span data-stu-id="42043-207">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.sampleMethod();
```

<span data-ttu-id="42043-208">Verwenden Sie Objektinitialisierer, um Eigenschaften im Rahmen des Klasseninstanziierungsprozesses Werte zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="42043-208">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```csharp
// Set a property value.
SampleClass sampleObject = new SampleClass
    { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="42043-209">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="42043-209">For more information, see:</span></span>

- [<span data-ttu-id="42043-210">new-Operator</span><span class="sxs-lookup"><span data-stu-id="42043-210">new Operator</span></span>](../../language-reference/operators/new-operator.md)

- [<span data-ttu-id="42043-211">Objekt- und Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="42043-211">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)

### <a name="Static"></a> <span data-ttu-id="42043-212">Statische Klassen und Member</span><span class="sxs-lookup"><span data-stu-id="42043-212">Static Classes and Members</span></span>

<span data-ttu-id="42043-213">Ein statischer Member der Klasse ist eine Eigenschaft, eine Prozedur oder ein Feld, die von allen Instanzen einer Klasse gemeinsam verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="42043-213">A static member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

<span data-ttu-id="42043-214">So definieren Sie einen statischen Member:</span><span class="sxs-lookup"><span data-stu-id="42043-214">To define a static member:</span></span>

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

<span data-ttu-id="42043-215">Verwenden Sie den Namen der Klasse, ohne ein Objekt dieser Klasse zu erstellen, um auf den statischen Member zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="42043-215">To access the static member, use the name of the class without creating an object of this class:</span></span>

```csharp
Console.WriteLine(SampleClass.SampleString);
```

<span data-ttu-id="42043-216">Statische Klassen in C# haben nur statische Member und können nicht instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="42043-216">Static  classes in C# have static members only and cannot be instantiated.</span></span> <span data-ttu-id="42043-217">Statische Member können auch nicht auf nicht statische Eigenschaften, Felder oder Methoden zugreifen.</span><span class="sxs-lookup"><span data-stu-id="42043-217">Static members also cannot access non-static  properties, fields or methods</span></span>

<span data-ttu-id="42043-218">Weitere Informationen finden Sie unter [static](../../language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="42043-218">For more information, see: [static](../../language-reference/keywords/static.md).</span></span>

### <a name="AnonymousTypes"></a> <span data-ttu-id="42043-219">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="42043-219">Anonymous Types</span></span>

<span data-ttu-id="42043-220">Mit anonymen Typen können Objekte erstellt werden, ohne eine Klassendefinition für den Datentyp zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="42043-220">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="42043-221">Stattdessen erzeugt der Compiler eine Klasse.</span><span class="sxs-lookup"><span data-stu-id="42043-221">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="42043-222">Die Klasse hat keinen verwendbaren Namen und enthält die von Ihnen in der Deklaration des Objekts angegebenen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="42043-222">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="42043-223">So erstellen Sie eine Instanz eines anonymen Typs</span><span class="sxs-lookup"><span data-stu-id="42043-223">To create an instance of an anonymous type:</span></span>

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject =
    new { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="42043-224">Weitere Informationen finden Sie unter: [Anonyme Typen](../classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="42043-224">For more information, see: [Anonymous Types](../classes-and-structs/anonymous-types.md).</span></span>

## <a name="Inheritance"></a> <span data-ttu-id="42043-225">Vererbung</span><span class="sxs-lookup"><span data-stu-id="42043-225">Inheritance</span></span>

<span data-ttu-id="42043-226">Vererbung ermöglicht die Erstellung neuer Klassen, die in anderen Klassen definiertes Verhalten wieder verwenden, erweitern und ändern.</span><span class="sxs-lookup"><span data-stu-id="42043-226">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="42043-227">Die Klasse, deren Member vererbt werden, wird *Basisklasse* genannt, und die Klasse, die diese Member erbt, wird *abgeleitete Klasse* genannt.</span><span class="sxs-lookup"><span data-stu-id="42043-227">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="42043-228">Alle Klassen in C# erben jedoch implizit von der Klasse <xref:System.Object>, die die .NET-Klassenhierarchie unterstützt und einfache Dienste für alle Klassen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="42043-228">However, all classes in C# implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="42043-229">C# unterstützt keine mehrfache Vererbung.</span><span class="sxs-lookup"><span data-stu-id="42043-229">C# doesn't support multiple inheritance.</span></span> <span data-ttu-id="42043-230">Sie können also nur eine Basisklasse für eine abgeleitete Klasse angeben.</span><span class="sxs-lookup"><span data-stu-id="42043-230">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="42043-231">So erben Sie von einer Basisklasse</span><span class="sxs-lookup"><span data-stu-id="42043-231">To inherit from a base class:</span></span>

```csharp
class DerivedClass:BaseClass {}
```

<span data-ttu-id="42043-232">Standardmäßig können alle Klassen geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="42043-232">By default all classes can be inherited.</span></span> <span data-ttu-id="42043-233">Sie können jedoch angeben, dass eine Klasse nicht als Basisklasse verwendet werden darf, oder eine Klasse erstellen, die nur als Basisklasse verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="42043-233">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="42043-234">So geben Sie an, dass eine Klasse nicht als Basisklasse verwendet werden kann</span><span class="sxs-lookup"><span data-stu-id="42043-234">To specify that a class cannot be used as a base class:</span></span>

```csharp
public sealed class A { }
```

<span data-ttu-id="42043-235">So geben Sie an, dass eine Klasse nur als Basisklasse verwendet und nicht instanziiert werden kann:</span><span class="sxs-lookup"><span data-stu-id="42043-235">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```csharp
public abstract class B { }
```

<span data-ttu-id="42043-236">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="42043-236">For more information, see:</span></span>

- [<span data-ttu-id="42043-237">sealed</span><span class="sxs-lookup"><span data-stu-id="42043-237">sealed</span></span>](../../language-reference/keywords/sealed.md)

- [<span data-ttu-id="42043-238">abstract</span><span class="sxs-lookup"><span data-stu-id="42043-238">abstract</span></span>](../../language-reference/keywords/abstract.md)

### <a name="Overriding"></a> <span data-ttu-id="42043-239">Überschreiben von Membern</span><span class="sxs-lookup"><span data-stu-id="42043-239">Overriding Members</span></span>

<span data-ttu-id="42043-240">Standardmäßig erbt eine abgeleitete Klasse alle Member von ihrer Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="42043-240">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="42043-241">Wenn Sie das Verhalten des geerbten Members ändern möchten, müssen Sie diesen überschreiben.</span><span class="sxs-lookup"><span data-stu-id="42043-241">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="42043-242">Das heißt, Sie können eine neue Implementierung der Methode, der Eigenschaft oder des Ereignisses in der abgeleiteten Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="42043-242">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="42043-243">Mit folgenden Modifizierern steuern Sie das Überschreiben von Eigenschaften und Methoden:</span><span class="sxs-lookup"><span data-stu-id="42043-243">The following modifiers are used to control how properties and methods are overridden:</span></span>

|<span data-ttu-id="42043-244">C#-Modifizierer</span><span class="sxs-lookup"><span data-stu-id="42043-244">C# Modifier</span></span>|<span data-ttu-id="42043-245">Definition</span><span class="sxs-lookup"><span data-stu-id="42043-245">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="42043-246">virtual</span><span class="sxs-lookup"><span data-stu-id="42043-246">virtual</span></span>](../../language-reference/keywords/virtual.md)|<span data-ttu-id="42043-247">Ermöglicht das Überschreiben eines Klassenmembers in einer abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="42043-247">Allows a class member to be overridden in a derived class.</span></span>|
|[<span data-ttu-id="42043-248">override</span><span class="sxs-lookup"><span data-stu-id="42043-248">override</span></span>](../../language-reference/keywords/override.md)|<span data-ttu-id="42043-249">Überschreibt einen virtuellen (überschreibbaren) Member, der in der Basisklasse definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="42043-249">Overrides a virtual (overridable) member defined in the base class.</span></span>|
|[<span data-ttu-id="42043-250">abstract</span><span class="sxs-lookup"><span data-stu-id="42043-250">abstract</span></span>](../../language-reference/keywords/abstract.md)|<span data-ttu-id="42043-251">Erfordert das Überschreiben eines Klassenmembers in der abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="42043-251">Requires that a class member to be overridden in the derived class.</span></span>|
|[<span data-ttu-id="42043-252">new-Modifizierer</span><span class="sxs-lookup"><span data-stu-id="42043-252">new Modifier</span></span>](../../language-reference/keywords/new-modifier.md)|<span data-ttu-id="42043-253">Blendet einen von einer Basisklasse geerbten Member aus.</span><span class="sxs-lookup"><span data-stu-id="42043-253">Hides a member inherited from a base class</span></span>|

## <a name="Interfaces"></a> <span data-ttu-id="42043-254">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="42043-254">Interfaces</span></span>

<span data-ttu-id="42043-255">Schnittstellen definieren (wie Klassen) einen Satz von Eigenschaften, Methoden und Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="42043-255">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="42043-256">Im Gegensatz zu Klassen jedoch bieten Schnittstellen keine Implementierung.</span><span class="sxs-lookup"><span data-stu-id="42043-256">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="42043-257">Sie werden durch Klassen implementiert und als von Klassen unabhängige Entitäten definiert.</span><span class="sxs-lookup"><span data-stu-id="42043-257">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="42043-258">Eine Schnittstelle stellt insofern einen Vertrag dar, dass eine Klasse, die eine Schnittstelle implementiert, jeden Aspekt dieser Schnittstelle gemäß seiner Definition implementieren muss.</span><span class="sxs-lookup"><span data-stu-id="42043-258">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="42043-259">So definieren Sie eine Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42043-259">To define an interface:</span></span>

```csharp
interface ISampleInterface
{
    void doSomething();
}
```

<span data-ttu-id="42043-260">So implementieren Sie eine Schnittstelle in einer Klasse</span><span class="sxs-lookup"><span data-stu-id="42043-260">To implement an interface in a class:</span></span>

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.doSomething()
    {
        // Method implementation.
    }
}
```

<span data-ttu-id="42043-261">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="42043-261">For more information, see:</span></span>

[<span data-ttu-id="42043-262">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="42043-262">Interfaces</span></span>](../interfaces/index.md)

[<span data-ttu-id="42043-263">interface</span><span class="sxs-lookup"><span data-stu-id="42043-263">interface</span></span>](../../language-reference/keywords/interface.md)

## <a name="Generics"></a> <span data-ttu-id="42043-264">Generics</span><span class="sxs-lookup"><span data-stu-id="42043-264">Generics</span></span>

<span data-ttu-id="42043-265">Klassen, Strukturen, Schnittstellen und Methoden in .NET Framework können *Typparameter* enthalten, die Objekttypen definieren, die sie speichern oder verwenden können.</span><span class="sxs-lookup"><span data-stu-id="42043-265">Classes, structures, interfaces and methods in the .NET Framework can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="42043-266">Das einfachste Beispiel für Generics ist eine Auflistung, in der Sie den Typ von Objekten angeben können, die in einer Auflistung gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="42043-266">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="42043-267">So definieren Sie eine generische Klasse</span><span class="sxs-lookup"><span data-stu-id="42043-267">To define a generic class:</span></span>

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

<span data-ttu-id="42043-268">So erstellen Sie eine Instanz einer generischen Klasse</span><span class="sxs-lookup"><span data-stu-id="42043-268">To create an instance of a generic class:</span></span>

```csharp
SampleGeneric<string> sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

<span data-ttu-id="42043-269">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="42043-269">For more information, see:</span></span>

- [<span data-ttu-id="42043-270">Generics</span><span class="sxs-lookup"><span data-stu-id="42043-270">Generics</span></span>](../../../standard/generics/index.md)

- [<span data-ttu-id="42043-271">Generics</span><span class="sxs-lookup"><span data-stu-id="42043-271">Generics</span></span>](../generics/index.md)

## <a name="Delegates"></a> <span data-ttu-id="42043-272">Delegaten</span><span class="sxs-lookup"><span data-stu-id="42043-272">Delegates</span></span>

<span data-ttu-id="42043-273">Ein *Delegat* ist ein Typ, der eine Methodensignatur definiert. Er kann einen Verweis auf jede Methode bereitstellen, die über eine kompatible Signatur verfügt.</span><span class="sxs-lookup"><span data-stu-id="42043-273">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="42043-274">Sie können die Methode über den Delegaten aufrufen.</span><span class="sxs-lookup"><span data-stu-id="42043-274">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="42043-275">Delegaten werden verwendet, um Methoden als Argumente an anderen Methoden zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="42043-275">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="42043-276">Ereignishandler sind nichts weiter als Methoden, die durch Delegaten aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="42043-276">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="42043-277">Weitere Informationen zur Ereignisbehandlung mit Delegaten finden Sie unter [Ereignisse](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="42043-277">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="42043-278">So erstellen Sie einen Delegaten</span><span class="sxs-lookup"><span data-stu-id="42043-278">To create a delegate:</span></span>

```csharp
public delegate void SampleDelegate(string str);
```

<span data-ttu-id="42043-279">So erstellen Sie einen Verweis auf eine Methode, die der vom Delegaten angegebenen Signatur entspricht:</span><span class="sxs-lookup"><span data-stu-id="42043-279">To create a reference to a method that matches the signature specified by the delegate:</span></span>

```csharp
class SampleClass
{
    // Method that matches the SampleDelegate signature.
    public static void sampleMethod(string message)
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

<span data-ttu-id="42043-280">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="42043-280">For more information, see:</span></span>

- [<span data-ttu-id="42043-281">Delegaten</span><span class="sxs-lookup"><span data-stu-id="42043-281">Delegates</span></span>](../delegates/index.md)

- [<span data-ttu-id="42043-282">delegate</span><span class="sxs-lookup"><span data-stu-id="42043-282">delegate</span></span>](../../language-reference/builtin-types/reference-types.md)

## <a name="see-also"></a><span data-ttu-id="42043-283">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42043-283">See also</span></span>

- [<span data-ttu-id="42043-284">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="42043-284">C# Programming Guide</span></span>](../index.md)
