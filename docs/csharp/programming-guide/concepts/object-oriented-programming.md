---
title: Objektorientiertes Programmieren (C#)
ms.date: 07/20/2015
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: a7a3ce1b33d040b337087dfede90b58906c95cbd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59481170"
---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="cd5ab-102">Objektorientiertes Programmieren (C#)</span><span class="sxs-lookup"><span data-stu-id="cd5ab-102">Object-Oriented Programming (C#)</span></span>

<span data-ttu-id="cd5ab-103">C# bietet vollständige Unterstützung für objektorientierte Programmierung, einschließlich Kapselung, Vererbung und Polymorphie.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-103">C# provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>

<span data-ttu-id="cd5ab-104">*Kapselung* bedeutet, dass eine Gruppe verwandter Eigenschaften, Methoden sowie anderer Member als eine Einheit bzw. ein Objekt behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>

<span data-ttu-id="cd5ab-105">*Vererbung* beschreibt die Fähigkeit, neue Klassen basierend auf einer vorhandenen Klasse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>

<span data-ttu-id="cd5ab-106">*Polymorphismus* bedeutet, dass Sie mehrere Klassen untereinander austauschen können, obwohl jede Klasse dieselben Eigenschaften oder Methoden auf unterschiedliche Art und Weise implementiert.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

<span data-ttu-id="cd5ab-107">In diesem Abschnitt werden die folgenden Konzepte beschrieben:</span><span class="sxs-lookup"><span data-stu-id="cd5ab-107">This section describes the following concepts:</span></span>

- [<span data-ttu-id="cd5ab-108">Klassen und Objekte</span><span class="sxs-lookup"><span data-stu-id="cd5ab-108">Classes and Objects</span></span>](#Classes)

  - [<span data-ttu-id="cd5ab-109">Klassenmember</span><span class="sxs-lookup"><span data-stu-id="cd5ab-109">Class Members</span></span>](#Members)

        [Properties and Fields](#Properties)

        [Methods](#Methods)

        [Constructors](#Constructors)

        [Finalizers](#Finalizers)

        [Events](#Events)

        [Nested Classes](#NestedClasses)

  - [<span data-ttu-id="cd5ab-110">Zugriffsmodifizierer und Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="cd5ab-110">Access Modifiers and Access Levels</span></span>](#AccessModifiers)

  - [<span data-ttu-id="cd5ab-111">Instanziieren von Klassen</span><span class="sxs-lookup"><span data-stu-id="cd5ab-111">Instantiating Classes</span></span>](#InstantiatingClasses)

  - [<span data-ttu-id="cd5ab-112">Statische Klassen und statische Klassenmember</span><span class="sxs-lookup"><span data-stu-id="cd5ab-112">Static Classes and Members</span></span>](#Static)

  - [<span data-ttu-id="cd5ab-113">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="cd5ab-113">Anonymous Types</span></span>](#AnonymousTypes)

- [<span data-ttu-id="cd5ab-114">Vererbung</span><span class="sxs-lookup"><span data-stu-id="cd5ab-114">Inheritance</span></span>](#Inheritance)

  - [<span data-ttu-id="cd5ab-115">Überschreiben von Membern</span><span class="sxs-lookup"><span data-stu-id="cd5ab-115">Overriding Members</span></span>](#Overriding)

- [<span data-ttu-id="cd5ab-116">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="cd5ab-116">Interfaces</span></span>](#Interfaces)

- [<span data-ttu-id="cd5ab-117">Generics</span><span class="sxs-lookup"><span data-stu-id="cd5ab-117">Generics</span></span>](#Generics)

- [<span data-ttu-id="cd5ab-118">Delegaten</span><span class="sxs-lookup"><span data-stu-id="cd5ab-118">Delegates</span></span>](#Delegates)

## <a name="Classes"></a> <span data-ttu-id="cd5ab-119">Klassen und Objekte</span><span class="sxs-lookup"><span data-stu-id="cd5ab-119">Classes and Objects</span></span>

<span data-ttu-id="cd5ab-120">Die Begriffe *Klasse* und *Objekt* werden manchmal synonym verwendet; genau genommen beschreiben Klassen jedoch den *Typ* von Objekten, während Objekte verwendbare *Instanzen* von Klassen sind.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-120">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="cd5ab-121">Das Erstellen eines Objekts wird daher als *Instanziierung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-121">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="cd5ab-122">Um auf den Vergleich mit Bauplänen zurückzukommen: Eine Klasse ist ein Bauplan, und ein Objekt ist ein anhand dieses Bauplans errichtetes Gebäude.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-122">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="cd5ab-123">So definieren Sie eine Klasse</span><span class="sxs-lookup"><span data-stu-id="cd5ab-123">To define a class:</span></span>

```csharp
class SampleClass
{
}
```

<span data-ttu-id="cd5ab-124">Auch C# stellt vereinfachte Versionen von Klassen bereit, die als *Strukturen* bezeichnet werden. Strukturen sind hilfreich, wenn Sie ein großes Objektarray erstellen müssen und nicht zu viel Arbeitsspeicher belegen wollen.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-124">C# also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>

<span data-ttu-id="cd5ab-125">So definieren Sie eine Struktur</span><span class="sxs-lookup"><span data-stu-id="cd5ab-125">To define a structure:</span></span>

```csharp
struct SampleStruct
{
}
```

<span data-ttu-id="cd5ab-126">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="cd5ab-126">For more information, see:</span></span>

- [<span data-ttu-id="cd5ab-127">class</span><span class="sxs-lookup"><span data-stu-id="cd5ab-127">class</span></span>](../../../csharp/language-reference/keywords/class.md)

- [<span data-ttu-id="cd5ab-128">struct</span><span class="sxs-lookup"><span data-stu-id="cd5ab-128">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)

### <a name="Members"></a> <span data-ttu-id="cd5ab-129">Klassenmember</span><span class="sxs-lookup"><span data-stu-id="cd5ab-129">Class Members</span></span>

<span data-ttu-id="cd5ab-130">Jede Klasse kann über andere *Klassenmember* verfügen. Diese enthalten Eigenschaften, die Klassendaten beschreiben, Methoden, die Klassenverhalten definieren sowie Ereignisse, die die Kommunikation zwischen verschiedenen Klassen und Objekten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-130">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="Properties"></a> <span data-ttu-id="cd5ab-131">Eigenschaften und Felder</span><span class="sxs-lookup"><span data-stu-id="cd5ab-131">Properties and Fields</span></span>

<span data-ttu-id="cd5ab-132">Felder und Eigenschaften stellen die in einem Objekt enthaltenen Informationen dar.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-132">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="cd5ab-133">Felder sind wie Variablen, sie können direkt gelesen oder festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-133">Fields are like variables because they can be read or set directly.</span></span>

<span data-ttu-id="cd5ab-134">So definieren Sie ein Feld</span><span class="sxs-lookup"><span data-stu-id="cd5ab-134">To define a field:</span></span>

```csharp
class SampleClass
{
    public string sampleField;
}
```

<span data-ttu-id="cd5ab-135">Eigenschaften verfügen über Get- und Set-Prozeduren, die eine bessere Kontrolle über das Festlegen oder Abrufen von Werten ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-135">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="cd5ab-136">Mit C# können Sie ein privates Feld erstellen, um den Eigenschaftswert zu speichern, oder Sie können automatisch implementierte Eigenschaften verwenden, die dieses Feld automatisch im Hintergrund erstellen und die grundlegende Logik für die Eigenschaftenprozeduren bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-136">C# allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="cd5ab-137">So definieren Sie eine automatisch implementierte Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="cd5ab-137">To define an auto-implemented property:</span></span>

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

<span data-ttu-id="cd5ab-138">Verwenden Sie den folgenden Code, wenn Sie zusätzliche Lese- und Schreibvorgänge für den Eigenschaftswert ausführen müssen, um ein Feld zum Speichern des Eigenschaftswerts zu definieren und die grundlegende Logik zum Speichern und Abrufen bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="cd5ab-138">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

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

<span data-ttu-id="cd5ab-139">Die meisten Eigenschaften verfügen über Methoden oder Prozeduren zum Festlegen und Abrufen des Eigenschaftswerts.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-139">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="cd5ab-140">Sie können jedoch schreib- oder lesegeschützte Eigenschaften erstellen, um zu verhindern, dass die Eigenschaften gelesen oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-140">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="cd5ab-141">In C# muss die `get`-Eigenschaftenmethode oder die `set`-Eigenschaftenmethode nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-141">In C#, you can omit the `get` or `set` property method.</span></span> <span data-ttu-id="cd5ab-142">Automatisch implementierte Eigenschaften können jedoch nicht schreib- oder lesegeschützt sein.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-142">However, auto-implemented properties cannot be read-only or write-only.</span></span>

<span data-ttu-id="cd5ab-143">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="cd5ab-143">For more information, see:</span></span>

- [<span data-ttu-id="cd5ab-144">get</span><span class="sxs-lookup"><span data-stu-id="cd5ab-144">get</span></span>](../../../csharp/language-reference/keywords/get.md)

- [<span data-ttu-id="cd5ab-145">set</span><span class="sxs-lookup"><span data-stu-id="cd5ab-145">set</span></span>](../../../csharp/language-reference/keywords/set.md)

#### <a name="Methods"></a> <span data-ttu-id="cd5ab-146">Methoden</span><span class="sxs-lookup"><span data-stu-id="cd5ab-146">Methods</span></span>

<span data-ttu-id="cd5ab-147">Eine *Methode* ist eine Aktion, die von einem Objekt ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-147">A *method* is an action that an object can perform.</span></span>

<span data-ttu-id="cd5ab-148">So definieren Sie eine Methode einer Klasse:</span><span class="sxs-lookup"><span data-stu-id="cd5ab-148">To define a method of a class:</span></span>

```csharp
class SampleClass
{
    public int sampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

<span data-ttu-id="cd5ab-149">Eine Klasse kann über mehrere Implementierungen oder *Überladungen* der gleichen Methode verfügen, die sich in der Anzahl der Parameter oder Parametertypen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-149">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="cd5ab-150">So überladen Sie eine Methode</span><span class="sxs-lookup"><span data-stu-id="cd5ab-150">To overload a method:</span></span>

```csharp
public int sampleMethod(string sampleParam) {};
public int sampleMethod(int sampleParam) {}
```

<span data-ttu-id="cd5ab-151">In den meisten Fällen deklarieren Sie eine Methode innerhalb einer Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-151">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="cd5ab-152">Auch C# unterstützt jedoch *Erweiterungsmethoden*, mit denen Sie einer vorhandenen Klasse außerhalb der eigentlichen Klassendefinition Methoden hinzuzufügen können.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-152">However, C# also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="cd5ab-153">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="cd5ab-153">For more information, see:</span></span>

- [<span data-ttu-id="cd5ab-154">Methoden</span><span class="sxs-lookup"><span data-stu-id="cd5ab-154">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)

- [<span data-ttu-id="cd5ab-155">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="cd5ab-155">Extension Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)

#### <a name="Constructors"></a> <span data-ttu-id="cd5ab-156">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="cd5ab-156">Constructors</span></span>

<span data-ttu-id="cd5ab-157">Konstruktoren sind Klassenmethoden, die automatisch ausgeführt werden, wenn ein Objekt eines bestimmten Typs erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-157">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="cd5ab-158">Konstruktoren initialisieren normalerweise die Datenmember des neuen Objekts.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-158">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="cd5ab-159">Konstruktoren können nur einmal während der Erstellung der Klasse ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-159">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="cd5ab-160">Weiterhin wird der Code im Konstruktor immer vor jedem anderen Code in einer Klasse ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-160">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="cd5ab-161">Sie können jedoch mehrere Konstruktorüberladungen auf die gleiche Weise wie für jede andere Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-161">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="cd5ab-162">So definieren Sie einen Konstruktor für eine Klasse:</span><span class="sxs-lookup"><span data-stu-id="cd5ab-162">To define a constructor for a class:</span></span>

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

<span data-ttu-id="cd5ab-163">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="cd5ab-163">For more information, see:</span></span>

<span data-ttu-id="cd5ab-164">[Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="cd5ab-164">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md).</span></span>

#### <a name="Finalizers"></a> <span data-ttu-id="cd5ab-165">Finalizer</span><span class="sxs-lookup"><span data-stu-id="cd5ab-165">Finalizers</span></span>

<span data-ttu-id="cd5ab-166">Finalizer werden zur Zerstörung von Klasseninstanzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-166">Finalizers are used to destruct instances of classes.</span></span> <span data-ttu-id="cd5ab-167">In .NET Framework verwaltet die Garbage Collection die Speicherbelegung automatisch und gibt Arbeitsspeicher für die verwalteten Objekte in der Anwendung frei.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-167">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="cd5ab-168">Möglicherweise sind jedoch noch Finalizer erforderlich, um alle nicht verwalteten Ressourcen zu bereinigen, die von der Anwendung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-168">However, you may still need finalizers to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="cd5ab-169">Es kann nur einen Finalizer für eine Klasse geben.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-169">There can be only one finalizers for a class.</span></span>

<span data-ttu-id="cd5ab-170">Weitere Informationen zu Finalizern und der Garbage Collection in .NET Framework finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="cd5ab-170">For more information about finalizers and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="Events"></a> <span data-ttu-id="cd5ab-171">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="cd5ab-171">Events</span></span>

<span data-ttu-id="cd5ab-172">Ereignisse aktivieren eine Klasse oder ein Objekt, um Informationen über Aktionen von Interesse an andere Klassen oder Objekte zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-172">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="cd5ab-173">Die Klasse, die das Ereignis sendet (oder auslöst), wird als *Herausgeber* bezeichnet, und die Klassen, die das Ereignis empfangen (oder verarbeiten), werden als *Abonnenten* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-173">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="cd5ab-174">Weitere Informationen zu Ereignissen sowie zu ihrer Auslösung und Behandlung finden Sie unter [Ereignisse](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="cd5ab-174">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="cd5ab-175">Verwenden Sie das Schlüsselwort [event](../../../csharp/language-reference/keywords/event.md), um ein Ereignis in einer Klasse zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-175">To declare an event in a class, use the [event](../../../csharp/language-reference/keywords/event.md) keyword.</span></span>

- <span data-ttu-id="cd5ab-176">Um ein Ereignis auszulösen, rufen Sie den Ereignisdelegaten auf.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-176">To raise an event, invoke the event delegate.</span></span>

- <span data-ttu-id="cd5ab-177">Verwenden Sie den `+=`-Operator, um ein Ereignis zu abonnieren, und verwenden Sie den `-=`-Operator, um das Abonnement eines Ereignisses zu kündigen.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-177">To subscribe to an event, use the `+=` operator; to unsubscribe from an event, use the `-=` operator.</span></span>

#### <a name="NestedClasses"></a> <span data-ttu-id="cd5ab-178">Geschachtelte Klassen</span><span class="sxs-lookup"><span data-stu-id="cd5ab-178">Nested Classes</span></span>

<span data-ttu-id="cd5ab-179">Eine Klasse, die in einer anderen Klasse definiert wird, wird als *geschachtelt* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-179">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="cd5ab-180">Standardmäßig ist die geschachtelte Klasse privat.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-180">By default, the nested class is private.</span></span>

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

<span data-ttu-id="cd5ab-181">Um eine Instanz der geschachtelten Klasse zu erstellen, verwenden Sie den Namen der Containerklasse und geben einen Punkt sowie anschließend den Namen der geschachtelten Klasse ein:</span><span class="sxs-lookup"><span data-stu-id="cd5ab-181">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="AccessModifiers"></a> <span data-ttu-id="cd5ab-182">Zugriffsmodifizierer und Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="cd5ab-182">Access Modifiers and Access Levels</span></span>

<span data-ttu-id="cd5ab-183">Alle Klassen und Klassenmember können mit *Zugriffsmodifizierern* angeben, welche Zugriffsebene sie für andere Klassen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-183">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="cd5ab-184">Die folgenden Zugriffsmodifizierer sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="cd5ab-184">The following access modifiers are available:</span></span>

|<span data-ttu-id="cd5ab-185">C#-Modifizierer</span><span class="sxs-lookup"><span data-stu-id="cd5ab-185">C# Modifier</span></span>|<span data-ttu-id="cd5ab-186">Definition</span><span class="sxs-lookup"><span data-stu-id="cd5ab-186">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="cd5ab-187">public</span><span class="sxs-lookup"><span data-stu-id="cd5ab-187">public</span></span>](../../../csharp/language-reference/keywords/public.md)|<span data-ttu-id="cd5ab-188">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder einer anderen Assembly, die darauf verweist, zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-188">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|
|[<span data-ttu-id="cd5ab-189">private</span><span class="sxs-lookup"><span data-stu-id="cd5ab-189">private</span></span>](../../../csharp/language-reference/keywords/private.md)|<span data-ttu-id="cd5ab-190">Auf den Typ oder Member kann nur von Code in der gleichen Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-190">The type or member can only be accessed by code in the same class.</span></span>|
|[<span data-ttu-id="cd5ab-191">protected</span><span class="sxs-lookup"><span data-stu-id="cd5ab-191">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)|<span data-ttu-id="cd5ab-192">Auf den Typ oder Member kann nur von Code in der gleichen Klasse oder in einer abgeleiteten Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-192">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|
|[<span data-ttu-id="cd5ab-193">internal</span><span class="sxs-lookup"><span data-stu-id="cd5ab-193">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)|<span data-ttu-id="cd5ab-194">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly zugegriffen werden, jedoch nicht von Code in einer anderen Assembly.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-194">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|
|[<span data-ttu-id="cd5ab-195">protected internal</span><span class="sxs-lookup"><span data-stu-id="cd5ab-195">protected internal</span></span>](../../../csharp/language-reference/keywords/protected-internal.md)|<span data-ttu-id="cd5ab-196">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder von jeder abgeleiteten Klasse in einer anderen Assembly zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-196">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|
|[<span data-ttu-id="cd5ab-197">private protected</span><span class="sxs-lookup"><span data-stu-id="cd5ab-197">private protected</span></span>](../../../csharp/language-reference/keywords/private-protected.md)|<span data-ttu-id="cd5ab-198">Auf den Typ oder Member kann nur über Code in der gleichen Klasse, in einer abgeleiteten Klasse oder innerhalb der Basisklassenassembly zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-198">The type or member can be accessed by code in the same class or in a derived class within the base class assembly.</span></span>|

<span data-ttu-id="cd5ab-199">Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="cd5ab-199">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>

### <a name="InstantiatingClasses"></a> <span data-ttu-id="cd5ab-200">Instanziieren von Klassen</span><span class="sxs-lookup"><span data-stu-id="cd5ab-200">Instantiating Classes</span></span>

<span data-ttu-id="cd5ab-201">Um ein Objekt zu erstellen, müssen Sie eine Klasse instanziieren oder eine Klasseninstanz erstellen.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-201">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```csharp
SampleClass sampleObject = new SampleClass();
```

<span data-ttu-id="cd5ab-202">Nachdem Sie eine Klasse instanziiert haben, können Sie den Eigenschaften und Feldern der Instanz Werte zuweisen und Klassenmethoden aufrufen.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-202">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.sampleMethod();
```

<span data-ttu-id="cd5ab-203">Verwenden Sie Objektinitialisierer, um Eigenschaften im Rahmen des Klasseninstanziierungsprozesses Werte zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="cd5ab-203">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```csharp
// Set a property value.
SampleClass sampleObject = new SampleClass
    { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="cd5ab-204">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="cd5ab-204">For more information, see:</span></span>

- [<span data-ttu-id="cd5ab-205">new-Operator</span><span class="sxs-lookup"><span data-stu-id="cd5ab-205">new Operator</span></span>](../../../csharp/language-reference/keywords/new-operator.md)

- [<span data-ttu-id="cd5ab-206">Objekt- und Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="cd5ab-206">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)

### <a name="Static"></a> <span data-ttu-id="cd5ab-207">Statische Klassen und Member</span><span class="sxs-lookup"><span data-stu-id="cd5ab-207">Static Classes and Members</span></span>

<span data-ttu-id="cd5ab-208">Ein statischer Member der Klasse ist eine Eigenschaft, eine Prozedur oder ein Feld, die von allen Instanzen einer Klasse gemeinsam verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-208">A static member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

<span data-ttu-id="cd5ab-209">So definieren Sie einen statischen Member:</span><span class="sxs-lookup"><span data-stu-id="cd5ab-209">To define a static member:</span></span>

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

<span data-ttu-id="cd5ab-210">Verwenden Sie den Namen der Klasse, ohne ein Objekt dieser Klasse zu erstellen, um auf den statischen Member zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="cd5ab-210">To access the static member, use the name of the class without creating an object of this class:</span></span>

```csharp
Console.WriteLine(SampleClass.SampleString);
```

<span data-ttu-id="cd5ab-211">Statische Klassen in C# haben nur statische Member und können nicht instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-211">Static  classes in C# have static members only and cannot be instantiated.</span></span> <span data-ttu-id="cd5ab-212">Statische Member können auch nicht auf nicht statische Eigenschaften, Felder oder Methoden zugreifen.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-212">Static members also cannot access non-static  properties, fields or methods</span></span>

<span data-ttu-id="cd5ab-213">Weitere Informationen finden Sie unter [static](../../../csharp/language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="cd5ab-213">For more information, see: [static](../../../csharp/language-reference/keywords/static.md).</span></span>

### <a name="AnonymousTypes"></a> <span data-ttu-id="cd5ab-214">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="cd5ab-214">Anonymous Types</span></span>

<span data-ttu-id="cd5ab-215">Mit anonymen Typen können Objekte erstellt werden, ohne eine Klassendefinition für den Datentyp zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-215">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="cd5ab-216">Stattdessen erzeugt der Compiler eine Klasse.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-216">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="cd5ab-217">Die Klasse hat keinen verwendbaren Namen und enthält die von Ihnen in der Deklaration des Objekts angegebenen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-217">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="cd5ab-218">So erstellen Sie eine Instanz eines anonymen Typs</span><span class="sxs-lookup"><span data-stu-id="cd5ab-218">To create an instance of an anonymous type:</span></span>

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject =
    new { FirstProperty = "A", SecondProperty = "B" };
```

<span data-ttu-id="cd5ab-219">Weitere Informationen finden Sie unter: [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="cd5ab-219">For more information, see: [Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>

## <a name="Inheritance"></a> <span data-ttu-id="cd5ab-220">Vererbung</span><span class="sxs-lookup"><span data-stu-id="cd5ab-220">Inheritance</span></span>

<span data-ttu-id="cd5ab-221">Vererbung ermöglicht die Erstellung neuer Klassen, die in anderen Klassen definiertes Verhalten wieder verwenden, erweitern und ändern.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-221">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="cd5ab-222">Die Klasse, deren Member vererbt werden, wird *Basisklasse* genannt, und die Klasse, die diese Member erbt, wird *abgeleitete Klasse* genannt.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-222">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="cd5ab-223">Alle Klassen in C# erben jedoch implizit von der Klasse <xref:System.Object>, die die .NET-Klassenhierarchie unterstützt und einfache Dienste für alle Klassen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-223">However, all classes in C# implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="cd5ab-224">C# unterstützt keine mehrfache Vererbung.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-224">C# doesn't support multiple inheritance.</span></span> <span data-ttu-id="cd5ab-225">Sie können also nur eine Basisklasse für eine abgeleitete Klasse angeben.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-225">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="cd5ab-226">So erben Sie von einer Basisklasse</span><span class="sxs-lookup"><span data-stu-id="cd5ab-226">To inherit from a base class:</span></span>

```csharp
class DerivedClass:BaseClass {}
```

<span data-ttu-id="cd5ab-227">Standardmäßig können alle Klassen geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-227">By default all classes can be inherited.</span></span> <span data-ttu-id="cd5ab-228">Sie können jedoch angeben, dass eine Klasse nicht als Basisklasse verwendet werden darf, oder eine Klasse erstellen, die nur als Basisklasse verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-228">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="cd5ab-229">So geben Sie an, dass eine Klasse nicht als Basisklasse verwendet werden kann</span><span class="sxs-lookup"><span data-stu-id="cd5ab-229">To specify that a class cannot be used as a base class:</span></span>

```csharp
public sealed class A { }
```

<span data-ttu-id="cd5ab-230">So geben Sie an, dass eine Klasse nur als Basisklasse verwendet und nicht instanziiert werden kann:</span><span class="sxs-lookup"><span data-stu-id="cd5ab-230">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```csharp
public abstract class B { }
```

<span data-ttu-id="cd5ab-231">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="cd5ab-231">For more information, see:</span></span>

- [<span data-ttu-id="cd5ab-232">sealed</span><span class="sxs-lookup"><span data-stu-id="cd5ab-232">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)

- [<span data-ttu-id="cd5ab-233">abstract</span><span class="sxs-lookup"><span data-stu-id="cd5ab-233">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)

### <a name="Overriding"></a> <span data-ttu-id="cd5ab-234">Überschreiben von Membern</span><span class="sxs-lookup"><span data-stu-id="cd5ab-234">Overriding Members</span></span>

<span data-ttu-id="cd5ab-235">Standardmäßig erbt eine abgeleitete Klasse alle Member von ihrer Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-235">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="cd5ab-236">Wenn Sie das Verhalten des geerbten Members ändern möchten, müssen Sie diesen überschreiben.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-236">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="cd5ab-237">Das heißt, Sie können eine neue Implementierung der Methode, der Eigenschaft oder des Ereignisses in der abgeleiteten Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-237">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="cd5ab-238">Mit folgenden Modifizierern steuern Sie das Überschreiben von Eigenschaften und Methoden:</span><span class="sxs-lookup"><span data-stu-id="cd5ab-238">The following modifiers are used to control how properties and methods are overridden:</span></span>

|<span data-ttu-id="cd5ab-239">C#-Modifizierer</span><span class="sxs-lookup"><span data-stu-id="cd5ab-239">C# Modifier</span></span>|<span data-ttu-id="cd5ab-240">Definition</span><span class="sxs-lookup"><span data-stu-id="cd5ab-240">Definition</span></span>|
|------------------|----------------|
|[<span data-ttu-id="cd5ab-241">virtual</span><span class="sxs-lookup"><span data-stu-id="cd5ab-241">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)|<span data-ttu-id="cd5ab-242">Ermöglicht das Überschreiben eines Klassenmembers in einer abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-242">Allows a class member to be overridden in a derived class.</span></span>|
|[<span data-ttu-id="cd5ab-243">override</span><span class="sxs-lookup"><span data-stu-id="cd5ab-243">override</span></span>](../../../csharp/language-reference/keywords/override.md)|<span data-ttu-id="cd5ab-244">Überschreibt einen virtuellen (überschreibbaren) Member, der in der Basisklasse definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-244">Overrides a virtual (overridable) member defined in the base class.</span></span>|
|[<span data-ttu-id="cd5ab-245">abstract</span><span class="sxs-lookup"><span data-stu-id="cd5ab-245">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)|<span data-ttu-id="cd5ab-246">Erfordert das Überschreiben eines Klassenmembers in der abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-246">Requires that a class member to be overridden in the derived class.</span></span>|
|[<span data-ttu-id="cd5ab-247">new-Modifizierer</span><span class="sxs-lookup"><span data-stu-id="cd5ab-247">new Modifier</span></span>](../../../csharp/language-reference/keywords/new-modifier.md)|<span data-ttu-id="cd5ab-248">Blendet einen von einer Basisklasse geerbten Member aus.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-248">Hides a member inherited from a base class</span></span>|

## <a name="Interfaces"></a> <span data-ttu-id="cd5ab-249">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="cd5ab-249">Interfaces</span></span>

<span data-ttu-id="cd5ab-250">Schnittstellen definieren (wie Klassen) einen Satz von Eigenschaften, Methoden und Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-250">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="cd5ab-251">Im Gegensatz zu Klassen jedoch bieten Schnittstellen keine Implementierung.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-251">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="cd5ab-252">Sie werden durch Klassen implementiert und als von Klassen unabhängige Entitäten definiert.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-252">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="cd5ab-253">Eine Schnittstelle stellt insofern einen Vertrag dar, dass eine Klasse, die eine Schnittstelle implementiert, jeden Aspekt dieser Schnittstelle gemäß seiner Definition implementieren muss.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-253">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="cd5ab-254">So definieren Sie eine Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cd5ab-254">To define an interface:</span></span>

```csharp
interface ISampleInterface
{
    void doSomething();
}
```

<span data-ttu-id="cd5ab-255">So implementieren Sie eine Schnittstelle in einer Klasse</span><span class="sxs-lookup"><span data-stu-id="cd5ab-255">To implement an interface in a class:</span></span>

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.doSomething()
    {
        // Method implementation.
    }
}
```

<span data-ttu-id="cd5ab-256">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="cd5ab-256">For more information, see:</span></span>

[<span data-ttu-id="cd5ab-257">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="cd5ab-257">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)

[<span data-ttu-id="cd5ab-258">interface</span><span class="sxs-lookup"><span data-stu-id="cd5ab-258">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)

## <a name="Generics"></a> <span data-ttu-id="cd5ab-259">Generics</span><span class="sxs-lookup"><span data-stu-id="cd5ab-259">Generics</span></span>

<span data-ttu-id="cd5ab-260">Klassen, Strukturen, Schnittstellen und Methoden in .NET Framework können *Typparameter* enthalten, die Objekttypen definieren, die sie speichern oder verwenden können.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-260">Classes, structures, interfaces and methods in the .NET Framework can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="cd5ab-261">Das einfachste Beispiel für Generics ist eine Auflistung, in der Sie den Typ von Objekten angeben können, die in einer Auflistung gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-261">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="cd5ab-262">So definieren Sie eine generische Klasse</span><span class="sxs-lookup"><span data-stu-id="cd5ab-262">To define a generic class:</span></span>

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

<span data-ttu-id="cd5ab-263">So erstellen Sie eine Instanz einer generischen Klasse</span><span class="sxs-lookup"><span data-stu-id="cd5ab-263">To create an instance of a generic class:</span></span>

```csharp
SampleGeneric<string> sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

<span data-ttu-id="cd5ab-264">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="cd5ab-264">For more information, see:</span></span>

- [<span data-ttu-id="cd5ab-265">Generics</span><span class="sxs-lookup"><span data-stu-id="cd5ab-265">Generics</span></span>](~/docs/standard/generics/index.md)

- [<span data-ttu-id="cd5ab-266">Generics</span><span class="sxs-lookup"><span data-stu-id="cd5ab-266">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)

## <a name="Delegates"></a> <span data-ttu-id="cd5ab-267">Delegaten</span><span class="sxs-lookup"><span data-stu-id="cd5ab-267">Delegates</span></span>

<span data-ttu-id="cd5ab-268">Ein *Delegat* ist ein Typ, der eine Methodensignatur definiert. Er kann einen Verweis auf jede Methode bereitstellen, die über eine kompatible Signatur verfügt.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-268">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="cd5ab-269">Sie können die Methode über den Delegaten aufrufen.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-269">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="cd5ab-270">Delegaten werden verwendet, um Methoden als Argumente an anderen Methoden zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-270">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="cd5ab-271">Ereignishandler sind nichts weiter als Methoden, die durch Delegaten aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cd5ab-271">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="cd5ab-272">Weitere Informationen zur Ereignisbehandlung mit Delegaten finden Sie unter [Ereignisse](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="cd5ab-272">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="cd5ab-273">So erstellen Sie einen Delegaten</span><span class="sxs-lookup"><span data-stu-id="cd5ab-273">To create a delegate:</span></span>

```csharp
public delegate void SampleDelegate(string str);
```

<span data-ttu-id="cd5ab-274">So erstellen Sie einen Verweis auf eine Methode, die der vom Delegaten angegebenen Signatur entspricht:</span><span class="sxs-lookup"><span data-stu-id="cd5ab-274">To create a reference to a method that matches the signature specified by the delegate:</span></span>

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

<span data-ttu-id="cd5ab-275">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="cd5ab-275">For more information, see:</span></span>

- [<span data-ttu-id="cd5ab-276">Delegaten</span><span class="sxs-lookup"><span data-stu-id="cd5ab-276">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)

- [<span data-ttu-id="cd5ab-277">delegate</span><span class="sxs-lookup"><span data-stu-id="cd5ab-277">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)

## <a name="see-also"></a><span data-ttu-id="cd5ab-278">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd5ab-278">See also</span></span>

- [<span data-ttu-id="cd5ab-279">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="cd5ab-279">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
