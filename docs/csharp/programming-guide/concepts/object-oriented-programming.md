---
title: Objektorientiertes Programmieren (C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: de06921840f06f36d8600b9567986644f58c6ad5
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="72000-102">Objektorientiertes Programmieren (C#)</span><span class="sxs-lookup"><span data-stu-id="72000-102">Object-Oriented Programming (C#)</span></span>
<span data-ttu-id="72000-103">C# bietet vollständige Unterstützung für objektorientierte Programmierung, einschließlich Kapselung, Vererbung und Polymorphie.</span><span class="sxs-lookup"><span data-stu-id="72000-103">C# provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>  
  
 <span data-ttu-id="72000-104">*Kapselung* bedeutet, dass eine Gruppe verwandter Eigenschaften, Methoden sowie anderer Member als eine Einheit bzw. ein Objekt behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="72000-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>  
  
 <span data-ttu-id="72000-105">*Vererbung* beschreibt die Fähigkeit, neue Klassen basierend auf einer vorhandenen Klasse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="72000-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>  
  
 <span data-ttu-id="72000-106">*Polymorphismus* bedeutet, dass Sie mehrere Klassen untereinander austauschen können, obwohl jede Klasse dieselben Eigenschaften oder Methoden auf unterschiedliche Art und Weise implementiert.</span><span class="sxs-lookup"><span data-stu-id="72000-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>  
  
 <span data-ttu-id="72000-107">In diesem Abschnitt werden die folgenden Konzepte beschrieben:</span><span class="sxs-lookup"><span data-stu-id="72000-107">This section describes the following concepts:</span></span>  
  
-   [<span data-ttu-id="72000-108">Klassen und Objekte</span><span class="sxs-lookup"><span data-stu-id="72000-108">Classes and Objects</span></span>](#Classes)  
  
    -   [<span data-ttu-id="72000-109">Klassenmember</span><span class="sxs-lookup"><span data-stu-id="72000-109">Class Members</span></span>](#Members)  
  
         [<span data-ttu-id="72000-110">Eigenschaften und Felder</span><span class="sxs-lookup"><span data-stu-id="72000-110">Properties and Fields</span></span>](#Properties)  
  
         [<span data-ttu-id="72000-111">Methoden</span><span class="sxs-lookup"><span data-stu-id="72000-111">Methods</span></span>](#Methods)  
  
         [<span data-ttu-id="72000-112">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="72000-112">Constructors</span></span>](#Constructors)  
  
         [<span data-ttu-id="72000-113">Finalizer</span><span class="sxs-lookup"><span data-stu-id="72000-113">Finalizers</span></span>](#Finalizers)  
  
         [<span data-ttu-id="72000-114">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="72000-114">Events</span></span>](#Events)  
  
         [<span data-ttu-id="72000-115">Geschachtelte Klassen</span><span class="sxs-lookup"><span data-stu-id="72000-115">Nested Classes</span></span>](#NestedClasses)  
  
    -   [<span data-ttu-id="72000-116">Zugriffsmodifizierer und Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="72000-116">Access Modifiers and Access Levels</span></span>](#AccessModifiers)  
  
    -   [<span data-ttu-id="72000-117">Instanziieren von Klassen</span><span class="sxs-lookup"><span data-stu-id="72000-117">Instantiating Classes</span></span>](#InstantiatingClasses)  
  
    -   [<span data-ttu-id="72000-118">Statische Klassen und statische Klassenmember</span><span class="sxs-lookup"><span data-stu-id="72000-118">Static Classes and Members</span></span>](#Static)  
  
    -   [<span data-ttu-id="72000-119">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="72000-119">Anonymous Types</span></span>](#AnonymousTypes)  
  
-   [<span data-ttu-id="72000-120">Vererbung</span><span class="sxs-lookup"><span data-stu-id="72000-120">Inheritance</span></span>](#Inheritance)  
  
    -   [<span data-ttu-id="72000-121">Überschreiben von Membern</span><span class="sxs-lookup"><span data-stu-id="72000-121">Overriding Members</span></span>](#Overriding)  
  
-   [<span data-ttu-id="72000-122">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="72000-122">Interfaces</span></span>](#Interfaces)  
  
-   [<span data-ttu-id="72000-123">Generika</span><span class="sxs-lookup"><span data-stu-id="72000-123">Generics</span></span>](#Generics)  
  
-   [<span data-ttu-id="72000-124">Delegaten</span><span class="sxs-lookup"><span data-stu-id="72000-124">Delegates</span></span>](#Delegates)  
  
##  <span data-ttu-id="72000-125"><a name="Classes"></a> Klassen und Objekte</span><span class="sxs-lookup"><span data-stu-id="72000-125"><a name="Classes"></a> Classes and Objects</span></span>  
 <span data-ttu-id="72000-126">Die Begriffe *Klasse* und *Objekt* werden manchmal synonym verwendet; genau genommen beschreiben Klassen jedoch den *Typ* von Objekten, während Objekte verwendbare *Instanzen* von Klassen sind.</span><span class="sxs-lookup"><span data-stu-id="72000-126">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="72000-127">Das Erstellen eines Objekts wird daher als *Instanziierung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="72000-127">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="72000-128">Um auf den Vergleich mit Bauplänen zurückzukommen: Eine Klasse ist ein Bauplan, und ein Objekt ist ein anhand dieses Bauplans errichtetes Gebäude.</span><span class="sxs-lookup"><span data-stu-id="72000-128">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>  
  
 <span data-ttu-id="72000-129">So definieren Sie eine Klasse</span><span class="sxs-lookup"><span data-stu-id="72000-129">To define a class:</span></span>  
  
```csharp  
class SampleClass  
{  
}  
```  
  
 <span data-ttu-id="72000-130">Auch C# stellt vereinfachte Versionen von Klassen bereit, die als *Strukturen* bezeichnet werden. Strukturen sind hilfreich, wenn Sie ein großes Objektarray erstellen müssen und nicht zu viel Arbeitsspeicher belegen wollen.</span><span class="sxs-lookup"><span data-stu-id="72000-130">C# also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>  
  
 <span data-ttu-id="72000-131">So definieren Sie eine Struktur</span><span class="sxs-lookup"><span data-stu-id="72000-131">To define a structure:</span></span>  
  
```csharp  
struct SampleStruct  
{  
}  
```  
  
 <span data-ttu-id="72000-132">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="72000-132">For more information, see:</span></span>  
  
-   [<span data-ttu-id="72000-133">class</span><span class="sxs-lookup"><span data-stu-id="72000-133">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="72000-134">struct</span><span class="sxs-lookup"><span data-stu-id="72000-134">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)  
  
###  <span data-ttu-id="72000-135"><a name="Members"></a> Klassenmember</span><span class="sxs-lookup"><span data-stu-id="72000-135"><a name="Members"></a> Class Members</span></span>  
 <span data-ttu-id="72000-136">Jede Klasse kann über andere *Klassenmember* verfügen. Diese enthalten Eigenschaften, die Klassendaten beschreiben, Methoden, die Klassenverhalten definieren sowie Ereignisse, die die Kommunikation zwischen verschiedenen Klassen und Objekten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="72000-136">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>  
  
####  <span data-ttu-id="72000-137"><a name="Properties"></a> Eigenschaften und Felder</span><span class="sxs-lookup"><span data-stu-id="72000-137"><a name="Properties"></a> Properties and Fields</span></span>  
 <span data-ttu-id="72000-138">Felder und Eigenschaften stellen die in einem Objekt enthaltenen Informationen dar.</span><span class="sxs-lookup"><span data-stu-id="72000-138">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="72000-139">Felder sind wie Variablen, sie können direkt gelesen oder festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="72000-139">Fields are like variables because they can be read or set directly.</span></span>  
  
 <span data-ttu-id="72000-140">So definieren Sie ein Feld</span><span class="sxs-lookup"><span data-stu-id="72000-140">To define a field:</span></span>  
  
```csharp  
Class SampleClass  
{  
    public string sampleField;  
}  
```  
  
 <span data-ttu-id="72000-141">Eigenschaften verfügen über Get- und Set-Prozeduren, die eine bessere Kontrolle über das Festlegen oder Abrufen von Werten ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="72000-141">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>  
  
 <span data-ttu-id="72000-142">Mit C# können Sie ein privates Feld erstellen, um den Eigenschaftswert zu speichern, oder Sie können automatisch implementierte Eigenschaften verwenden, die dieses Feld automatisch im Hintergrund erstellen und die grundlegende Logik für die Eigenschaftenprozeduren bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="72000-142">C# allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>  
  
 <span data-ttu-id="72000-143">So definieren Sie eine automatisch implementierte Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="72000-143">To define an auto-implemented property:</span></span>  
  
```csharp  
class SampleClass  
{  
    public int SampleProperty { get; set; }  
}  
```  
  
 <span data-ttu-id="72000-144">Verwenden Sie den folgenden Code, wenn Sie zusätzliche Lese- und Schreibvorgänge für den Eigenschaftswert ausführen müssen, um ein Feld zum Speichern des Eigenschaftswerts zu definieren und die grundlegende Logik zum Speichern und Abrufen bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="72000-144">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>  
  
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
  
 <span data-ttu-id="72000-145">Die meisten Eigenschaften verfügen über Methoden oder Prozeduren zum Festlegen und Abrufen des Eigenschaftswerts.</span><span class="sxs-lookup"><span data-stu-id="72000-145">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="72000-146">Sie können jedoch schreib- oder lesegeschützte Eigenschaften erstellen, um zu verhindern, dass die Eigenschaften gelesen oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="72000-146">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="72000-147">In C# muss die `get`-Eigenschaftenmethode oder die `set`-Eigenschaftenmethode nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="72000-147">In C#, you can omit the `get` or `set` property method.</span></span> <span data-ttu-id="72000-148">Automatisch implementierte Eigenschaften können jedoch nicht schreib- oder lesegeschützt sein.</span><span class="sxs-lookup"><span data-stu-id="72000-148">However, auto-implemented properties cannot be read-only or write-only.</span></span>  
  
 <span data-ttu-id="72000-149">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="72000-149">For more information, see:</span></span>  
  
-   [<span data-ttu-id="72000-150">get</span><span class="sxs-lookup"><span data-stu-id="72000-150">get</span></span>](../../../csharp/language-reference/keywords/get.md)  
  
-   [<span data-ttu-id="72000-151">set</span><span class="sxs-lookup"><span data-stu-id="72000-151">set</span></span>](../../../csharp/language-reference/keywords/set.md)  
  
####  <span data-ttu-id="72000-152"><a name="Methods"></a> Methoden</span><span class="sxs-lookup"><span data-stu-id="72000-152"><a name="Methods"></a> Methods</span></span>  
 <span data-ttu-id="72000-153">Eine *Methode* ist eine Aktion, die von einem Objekt ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="72000-153">A *method* is an action that an object can perform.</span></span>  
  
 <span data-ttu-id="72000-154">So definieren Sie eine Methode einer Klasse:</span><span class="sxs-lookup"><span data-stu-id="72000-154">To define a method of a class:</span></span>  
  
```csharp  
class SampleClass  
{  
    public int sampleMethod(string sampleParam)  
    {  
        // Insert code here  
    }  
}  
```  
  
 <span data-ttu-id="72000-155">Eine Klasse kann über mehrere Implementierungen oder *Überladungen* der gleichen Methode verfügen, die sich in der Anzahl der Parameter oder Parametertypen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="72000-155">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>  
  
 <span data-ttu-id="72000-156">So überladen Sie eine Methode</span><span class="sxs-lookup"><span data-stu-id="72000-156">To overload a method:</span></span>  
  
```csharp  
public int sampleMethod(string sampleParam) {};  
public int sampleMethod(int sampleParam) {}  
```  
  
 <span data-ttu-id="72000-157">In den meisten Fällen deklarieren Sie eine Methode innerhalb einer Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="72000-157">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="72000-158">Auch C# unterstützt jedoch *Erweiterungsmethoden*, mit denen Sie einer vorhandenen Klasse außerhalb der eigentlichen Klassendefinition Methoden hinzuzufügen können.</span><span class="sxs-lookup"><span data-stu-id="72000-158">However, C# also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>  
  
 <span data-ttu-id="72000-159">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="72000-159">For more information, see:</span></span>  
  
-   [<span data-ttu-id="72000-160">Methoden</span><span class="sxs-lookup"><span data-stu-id="72000-160">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [<span data-ttu-id="72000-161">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="72000-161">Extension Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)  
  
####  <span data-ttu-id="72000-162"><a name="Constructors"></a> Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="72000-162"><a name="Constructors"></a> Constructors</span></span>  
 <span data-ttu-id="72000-163">Konstruktoren sind Klassenmethoden, die automatisch ausgeführt werden, wenn ein Objekt eines bestimmten Typs erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="72000-163">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="72000-164">Konstruktoren initialisieren normalerweise die Datenmember des neuen Objekts.</span><span class="sxs-lookup"><span data-stu-id="72000-164">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="72000-165">Konstruktoren können nur einmal während der Erstellung der Klasse ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="72000-165">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="72000-166">Weiterhin wird der Code im Konstruktor immer vor jedem anderen Code in einer Klasse ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="72000-166">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="72000-167">Sie können jedoch mehrere Konstruktorüberladungen auf die gleiche Weise wie für jede andere Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="72000-167">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>  
  
 <span data-ttu-id="72000-168">So definieren Sie einen Konstruktor für eine Klasse:</span><span class="sxs-lookup"><span data-stu-id="72000-168">To define a constructor for a class:</span></span>  
  
```csharp  
public class SampleClass  
{  
    public SampleClass()  
    {  
        // Add code here  
    }  
}  
```  
  
 <span data-ttu-id="72000-169">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="72000-169">For more information, see:</span></span>  
  
 <span data-ttu-id="72000-170">[Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="72000-170">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md).</span></span>  
  
####  <span data-ttu-id="72000-171"><a name="Finalizers"></a> Finalizer</span><span class="sxs-lookup"><span data-stu-id="72000-171"><a name="Finalizers"></a> Finalizers</span></span>  
 <span data-ttu-id="72000-172">Finalizer werden zur Zerstörung von Klasseninstanzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="72000-172">Finalizers are used to destruct instances of classes.</span></span> <span data-ttu-id="72000-173">In .NET Framework verwaltet die Garbage Collection die Speicherbelegung automatisch und gibt Arbeitsspeicher für die verwalteten Objekte in der Anwendung frei.</span><span class="sxs-lookup"><span data-stu-id="72000-173">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="72000-174">Möglicherweise sind jedoch noch Finalizer erforderlich, um alle nicht verwalteten Ressourcen zu bereinigen, die von der Anwendung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="72000-174">However, you may still need finalizers to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="72000-175">Es kann nur einen Finalizer für eine Klasse geben.</span><span class="sxs-lookup"><span data-stu-id="72000-175">There can be only one finalizers for a class.</span></span>  
  
 <span data-ttu-id="72000-176">Weitere Informationen zu Finalizern und der Garbage Collection in .NET Framework finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="72000-176">For more information about finalizers and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
####  <span data-ttu-id="72000-177"><a name="Events"></a> Ereignisse</span><span class="sxs-lookup"><span data-stu-id="72000-177"><a name="Events"></a> Events</span></span>  
 <span data-ttu-id="72000-178">Ereignisse aktivieren eine Klasse oder ein Objekt, um Informationen über Aktionen von Interesse an andere Klassen oder Objekte zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="72000-178">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="72000-179">Die Klasse, die das Ereignis sendet (oder auslöst), wird als *Herausgeber* bezeichnet, und die Klassen, die das Ereignis empfangen (oder verarbeiten), werden als *Abonnenten* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="72000-179">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="72000-180">Weitere Informationen zu Ereignissen sowie zu ihrer Auslösung und Behandlung finden Sie unter [Ereignisse](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="72000-180">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>  
  
-   <span data-ttu-id="72000-181">Verwenden Sie das Schlüsselwort [event](../../../csharp/language-reference/keywords/event.md), um ein Ereignis in einer Klasse zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="72000-181">To declare an event in a class, use the [event](../../../csharp/language-reference/keywords/event.md) keyword.</span></span>  
  
-   <span data-ttu-id="72000-182">Um ein Ereignis auszulösen, rufen Sie den Ereignisdelegaten auf.</span><span class="sxs-lookup"><span data-stu-id="72000-182">To raise an event, invoke the event delegate.</span></span>  
  
-   <span data-ttu-id="72000-183">Verwenden Sie den `+=`-Operator, um ein Ereignis zu abonnieren, und verwenden Sie den `-=`-Operator, um das Abonnement eines Ereignisses zu kündigen.</span><span class="sxs-lookup"><span data-stu-id="72000-183">To subscribe to an event, use the `+=` operator; to unsubscribe from an event, use the `-=` operator.</span></span>  
  
####  <span data-ttu-id="72000-184"><a name="NestedClasses"></a> Geschachtelte Klassen</span><span class="sxs-lookup"><span data-stu-id="72000-184"><a name="NestedClasses"></a> Nested Classes</span></span>  
 <span data-ttu-id="72000-185">Eine Klasse, die in einer anderen Klasse definiert wird, wird als *geschachtelt* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="72000-185">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="72000-186">Standardmäßig ist die geschachtelte Klasse privat.</span><span class="sxs-lookup"><span data-stu-id="72000-186">By default, the nested class is private.</span></span>  
  
```csharp  
class Container  
{  
    class Nested  
    {  
        // Add code here.  
    }  
}  
```  
  
 <span data-ttu-id="72000-187">Um eine Instanz der geschachtelten Klasse zu erstellen, verwenden Sie den Namen der Containerklasse und geben einen Punkt sowie anschließend den Namen der geschachtelten Klasse ein:</span><span class="sxs-lookup"><span data-stu-id="72000-187">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>  
  
```csharp  
Container.Nested nestedInstance = new Container.Nested()  
```  
  
###  <span data-ttu-id="72000-188"><a name="AccessModifiers"></a> Zugriffsmodifizierer und Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="72000-188"><a name="AccessModifiers"></a> Access Modifiers and Access Levels</span></span>  
 <span data-ttu-id="72000-189">Alle Klassen und Klassenmember können mit *Zugriffsmodifizierern* angeben, welche Zugriffsebene sie für andere Klassen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="72000-189">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>  
  
 <span data-ttu-id="72000-190">Die folgenden Zugriffsmodifizierer sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="72000-190">The following access modifiers are available:</span></span>  
  
|<span data-ttu-id="72000-191">C#-Modifizierer</span><span class="sxs-lookup"><span data-stu-id="72000-191">C# Modifier</span></span>|<span data-ttu-id="72000-192">Definition</span><span class="sxs-lookup"><span data-stu-id="72000-192">Definition</span></span>|  
|------------------|----------------|  
|[<span data-ttu-id="72000-193">public</span><span class="sxs-lookup"><span data-stu-id="72000-193">public</span></span>](../../../csharp/language-reference/keywords/public.md)|<span data-ttu-id="72000-194">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder einer anderen Assembly, die darauf verweist, zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="72000-194">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|  
|[<span data-ttu-id="72000-195">private</span><span class="sxs-lookup"><span data-stu-id="72000-195">private</span></span>](../../../csharp/language-reference/keywords/private.md)|<span data-ttu-id="72000-196">Auf den Typ oder Member kann nur von Code in der gleichen Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="72000-196">The type or member can only be accessed by code in the same class.</span></span>|  
|[<span data-ttu-id="72000-197">protected</span><span class="sxs-lookup"><span data-stu-id="72000-197">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)|<span data-ttu-id="72000-198">Auf den Typ oder Member kann nur von Code in der gleichen Klasse oder in einer abgeleiteten Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="72000-198">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|  
|[<span data-ttu-id="72000-199">internal</span><span class="sxs-lookup"><span data-stu-id="72000-199">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)|<span data-ttu-id="72000-200">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly zugegriffen werden, jedoch nicht von Code in einer anderen Assembly.</span><span class="sxs-lookup"><span data-stu-id="72000-200">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|  
|`protected internal`|<span data-ttu-id="72000-201">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder von jeder abgeleiteten Klasse in einer anderen Assembly zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="72000-201">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|  
  
 <span data-ttu-id="72000-202">Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="72000-202">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
###  <span data-ttu-id="72000-203"><a name="InstantiatingClasses"></a> Instanziieren von Klassen</span><span class="sxs-lookup"><span data-stu-id="72000-203"><a name="InstantiatingClasses"></a> Instantiating Classes</span></span>  
 <span data-ttu-id="72000-204">Um ein Objekt zu erstellen, müssen Sie eine Klasse instanziieren oder eine Klasseninstanz erstellen.</span><span class="sxs-lookup"><span data-stu-id="72000-204">To create an object, you need to instantiate a class, or create a class instance.</span></span>  
  
```csharp  
SampleClass sampleObject = new SampleClass();  
```  
  
 <span data-ttu-id="72000-205">Nachdem Sie eine Klasse instanziiert haben, können Sie den Eigenschaften und Feldern der Instanz Werte zuweisen und Klassenmethoden aufrufen.</span><span class="sxs-lookup"><span data-stu-id="72000-205">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>  
  
```csharp  
// Set a property value.  
sampleObject.sampleProperty = "Sample String";  
// Call a method.  
sampleObject.sampleMethod();  
```  
  
 <span data-ttu-id="72000-206">Verwenden Sie Objektinitialisierer, um Eigenschaften im Rahmen des Klasseninstanziierungsprozesses Werte zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="72000-206">To assign values to properties during the class instantiation process, use object initializers:</span></span>  
  
```csharp  
// Set a property value.  
SampleClass sampleObject = new SampleClass   
    { FirstProperty = "A", SecondProperty = "B" };  
```  
  
 <span data-ttu-id="72000-207">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="72000-207">For more information, see:</span></span>  
  
-   [<span data-ttu-id="72000-208">new-Operator</span><span class="sxs-lookup"><span data-stu-id="72000-208">new Operator</span></span>](../../../csharp/language-reference/keywords/new-operator.md)  
  
-   [<span data-ttu-id="72000-209">Objekt- und Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="72000-209">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)  
  
###  <span data-ttu-id="72000-210"><a name="Static"></a> Statische Klassen und Member</span><span class="sxs-lookup"><span data-stu-id="72000-210"><a name="Static"></a> Static Classes and Members</span></span>  
 <span data-ttu-id="72000-211">Ein statischer Member der Klasse ist eine Eigenschaft, eine Prozedur oder ein Feld, die von allen Instanzen einer Klasse gemeinsam verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="72000-211">A static member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>  
  
 <span data-ttu-id="72000-212">So definieren Sie einen statischen Member:</span><span class="sxs-lookup"><span data-stu-id="72000-212">To define a static member:</span></span>  
  
```csharp  
static class SampleClass  
{  
    public static string SampleString = "Sample String";  
}  
```  
  
 <span data-ttu-id="72000-213">Verwenden Sie den Namen der Klasse, ohne ein Objekt dieser Klasse zu erstellen, um auf den statischen Member zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="72000-213">To access the static member, use the name of the class without creating an object of this class:</span></span>  
  
```csharp  
Console.WriteLine(SampleClass.SampleString);  
```  
  
 <span data-ttu-id="72000-214">Statische Klassen in C# haben nur statische Member und können nicht instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="72000-214">Static  classes in C# have static members only and cannot be instantiated.</span></span> <span data-ttu-id="72000-215">Statische Member können auch nicht auf nicht statische Eigenschaften, Felder oder Methoden zugreifen.</span><span class="sxs-lookup"><span data-stu-id="72000-215">Static members also cannot access non-static  properties, fields or methods</span></span>  
  
 <span data-ttu-id="72000-216">Weitere Informationen finden Sie unter [static](../../../csharp/language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="72000-216">For more information, see: [static](../../../csharp/language-reference/keywords/static.md).</span></span>  
  
###  <span data-ttu-id="72000-217"><a name="AnonymousTypes"></a> Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="72000-217"><a name="AnonymousTypes"></a> Anonymous Types</span></span>  
 <span data-ttu-id="72000-218">Mit anonymen Typen können Objekte erstellt werden, ohne eine Klassendefinition für den Datentyp zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="72000-218">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="72000-219">Stattdessen erzeugt der Compiler eine Klasse.</span><span class="sxs-lookup"><span data-stu-id="72000-219">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="72000-220">Die Klasse hat keinen verwendbaren Namen und enthält die von Ihnen in der Deklaration des Objekts angegebenen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="72000-220">The class has no usable name and contains the properties you specify in declaring the object.</span></span>  
  
 <span data-ttu-id="72000-221">So erstellen Sie eine Instanz eines anonymen Typs</span><span class="sxs-lookup"><span data-stu-id="72000-221">To create an instance of an anonymous type:</span></span>  
  
```csharp  
// sampleObject is an instance of a simple anonymous type.  
var sampleObject =   
    new { FirstProperty = "A", SecondProperty = "B" };  
```  
  
 <span data-ttu-id="72000-222">Weitere Informationen finden Sie unter [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="72000-222">For more information, see: [Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>  
  
##  <span data-ttu-id="72000-223"><a name="Inheritance"></a> Vererbung</span><span class="sxs-lookup"><span data-stu-id="72000-223"><a name="Inheritance"></a> Inheritance</span></span>  
 <span data-ttu-id="72000-224">Vererbung ermöglicht die Erstellung neuer Klassen, die in anderen Klassen definiertes Verhalten wieder verwenden, erweitern und ändern.</span><span class="sxs-lookup"><span data-stu-id="72000-224">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="72000-225">Die Klasse, deren Member vererbt werden, wird *Basisklasse* genannt, und die Klasse, die diese Member erbt, wird *abgeleitete Klasse* genannt.</span><span class="sxs-lookup"><span data-stu-id="72000-225">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="72000-226">Alle Klassen in C# erben jedoch implizit von der Klasse <xref:System.Object>, die die .NET-Klassenhierarchie unterstützt und einfache Dienste für alle Klassen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="72000-226">However, all classes in C# implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72000-227">C# unterstützt keine mehrfache Vererbung.</span><span class="sxs-lookup"><span data-stu-id="72000-227">C# doesn't support multiple inheritance.</span></span> <span data-ttu-id="72000-228">Sie können also nur eine Basisklasse für eine abgeleitete Klasse angeben.</span><span class="sxs-lookup"><span data-stu-id="72000-228">That is, you can specify only one base class for a derived class.</span></span>  
  
 <span data-ttu-id="72000-229">So erben Sie von einer Basisklasse</span><span class="sxs-lookup"><span data-stu-id="72000-229">To inherit from a base class:</span></span>  
  
```csharp  
class DerivedClass:BaseClass{}  
```  
  
 <span data-ttu-id="72000-230">Standardmäßig können alle Klassen geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="72000-230">By default all classes can be inherited.</span></span> <span data-ttu-id="72000-231">Sie können jedoch angeben, dass eine Klasse nicht als Basisklasse verwendet werden darf, oder eine Klasse erstellen, die nur als Basisklasse verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="72000-231">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>  
  
 <span data-ttu-id="72000-232">So geben Sie an, dass eine Klasse nicht als Basisklasse verwendet werden kann</span><span class="sxs-lookup"><span data-stu-id="72000-232">To specify that a class cannot be used as a base class:</span></span>  
  
```csharp  
public sealed class A { }  
```  
  
 <span data-ttu-id="72000-233">So geben Sie an, dass eine Klasse nur als Basisklasse verwendet und nicht instanziiert werden kann:</span><span class="sxs-lookup"><span data-stu-id="72000-233">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>  
  
```csharp  
public abstract class B { }  
```  
  
 <span data-ttu-id="72000-234">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="72000-234">For more information, see:</span></span>  
  
-   [<span data-ttu-id="72000-235">sealed</span><span class="sxs-lookup"><span data-stu-id="72000-235">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)  
  
-   [<span data-ttu-id="72000-236">abstract</span><span class="sxs-lookup"><span data-stu-id="72000-236">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)  
  
###  <span data-ttu-id="72000-237"><a name="Overriding"></a> Überschreiben von Membern</span><span class="sxs-lookup"><span data-stu-id="72000-237"><a name="Overriding"></a> Overriding Members</span></span>  
 <span data-ttu-id="72000-238">Standardmäßig erbt eine abgeleitete Klasse alle Member von ihrer Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="72000-238">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="72000-239">Wenn Sie das Verhalten des geerbten Members ändern möchten, müssen Sie diesen überschreiben.</span><span class="sxs-lookup"><span data-stu-id="72000-239">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="72000-240">Das heißt, Sie können eine neue Implementierung der Methode, der Eigenschaft oder des Ereignisses in der abgeleiteten Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="72000-240">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>  
  
 <span data-ttu-id="72000-241">Mit folgenden Modifizierern steuern Sie das Überschreiben von Eigenschaften und Methoden:</span><span class="sxs-lookup"><span data-stu-id="72000-241">The following modifiers are used to control how properties and methods are overridden:</span></span>  
  
|<span data-ttu-id="72000-242">C#-Modifizierer</span><span class="sxs-lookup"><span data-stu-id="72000-242">C# Modifier</span></span>|<span data-ttu-id="72000-243">Definition</span><span class="sxs-lookup"><span data-stu-id="72000-243">Definition</span></span>|  
|------------------|----------------|  
|[<span data-ttu-id="72000-244">virtual</span><span class="sxs-lookup"><span data-stu-id="72000-244">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)|<span data-ttu-id="72000-245">Ermöglicht das Überschreiben eines Klassenmembers in einer abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="72000-245">Allows a class member to be overridden in a derived class.</span></span>|  
|[<span data-ttu-id="72000-246">override</span><span class="sxs-lookup"><span data-stu-id="72000-246">override</span></span>](../../../csharp/language-reference/keywords/override.md)|<span data-ttu-id="72000-247">Überschreibt einen virtuellen (überschreibbaren) Member, der in der Basisklasse definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="72000-247">Overrides a virtual (overridable) member defined in the base class.</span></span>|  
|[<span data-ttu-id="72000-248">abstract</span><span class="sxs-lookup"><span data-stu-id="72000-248">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)|<span data-ttu-id="72000-249">Erfordert das Überschreiben eines Klassenmembers in der abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="72000-249">Requires that a class member to be overridden in the derived class.</span></span>|  
|[<span data-ttu-id="72000-250">new-Modifizierer</span><span class="sxs-lookup"><span data-stu-id="72000-250">new Modifier</span></span>](../../../csharp/language-reference/keywords/new-modifier.md)|<span data-ttu-id="72000-251">Blendet einen von einer Basisklasse geerbten Member aus.</span><span class="sxs-lookup"><span data-stu-id="72000-251">Hides a member inherited from a base class</span></span>|  
  
##  <span data-ttu-id="72000-252"><a name="Interfaces"></a> Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="72000-252"><a name="Interfaces"></a> Interfaces</span></span>  
 <span data-ttu-id="72000-253">Schnittstellen definieren (wie Klassen) einen Satz von Eigenschaften, Methoden und Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="72000-253">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="72000-254">Im Gegensatz zu Klassen jedoch bieten Schnittstellen keine Implementierung.</span><span class="sxs-lookup"><span data-stu-id="72000-254">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="72000-255">Sie werden durch Klassen implementiert und als von Klassen unabhängige Entitäten definiert.</span><span class="sxs-lookup"><span data-stu-id="72000-255">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="72000-256">Eine Schnittstelle stellt insofern einen Vertrag dar, dass eine Klasse, die eine Schnittstelle implementiert, jeden Aspekt dieser Schnittstelle gemäß seiner Definition implementieren muss.</span><span class="sxs-lookup"><span data-stu-id="72000-256">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>  
  
 <span data-ttu-id="72000-257">So definieren Sie eine Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="72000-257">To define an interface:</span></span>  
  
```csharp  
interface ISampleInterface  
{  
    void doSomething();  
}  
```  
  
 <span data-ttu-id="72000-258">So implementieren Sie eine Schnittstelle in einer Klasse</span><span class="sxs-lookup"><span data-stu-id="72000-258">To implement an interface in a class:</span></span>  
  
```csharp  
class SampleClass : ISampleInterface  
{  
    void ISampleInterface.doSomething()  
    {  
        // Method implementation.  
    }  
}  
```  
  
 <span data-ttu-id="72000-259">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="72000-259">For more information, see:</span></span>  
  
 [<span data-ttu-id="72000-260">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="72000-260">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
  
 [<span data-ttu-id="72000-261">interface</span><span class="sxs-lookup"><span data-stu-id="72000-261">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
##  <span data-ttu-id="72000-262"><a name="Generics"></a> Generika</span><span class="sxs-lookup"><span data-stu-id="72000-262"><a name="Generics"></a> Generics</span></span>  
 <span data-ttu-id="72000-263">Klassen, Strukturen, Schnittstellen und Methoden in .NET Framework können *Typparameter* enthalten, die Objekttypen definieren, die sie speichern oder verwenden können.</span><span class="sxs-lookup"><span data-stu-id="72000-263">Classes, structures, interfaces and methods in the .NET Framework can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="72000-264">Das einfachste Beispiel für Generika ist eine Auflistung, in der Sie den Typ von Objekten angeben können, die in einer Auflistung gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="72000-264">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>  
  
 <span data-ttu-id="72000-265">So definieren Sie eine generische Klasse</span><span class="sxs-lookup"><span data-stu-id="72000-265">To define a generic class:</span></span>  
  
```csharp  
Public class SampleGeneric<T>   
{  
    public T Field;  
}  
```  
  
 <span data-ttu-id="72000-266">So erstellen Sie eine Instanz einer generischen Klasse</span><span class="sxs-lookup"><span data-stu-id="72000-266">To create an instance of a generic class:</span></span>  
  
```csharp  
SampleGeneric<string> sampleObject = new SampleGeneric<string>();  
sampleObject.Field = "Sample string";  
```  
  
 <span data-ttu-id="72000-267">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="72000-267">For more information, see:</span></span>  
  
-   [<span data-ttu-id="72000-268">Generika</span><span class="sxs-lookup"><span data-stu-id="72000-268">Generics</span></span>](~/docs/standard/generics/index.md)  
  
-   [<span data-ttu-id="72000-269">Generika</span><span class="sxs-lookup"><span data-stu-id="72000-269">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)  
  
##  <span data-ttu-id="72000-270"><a name="Delegates"></a> Delegaten</span><span class="sxs-lookup"><span data-stu-id="72000-270"><a name="Delegates"></a> Delegates</span></span>  
 <span data-ttu-id="72000-271">Ein *Delegat* ist ein Typ, der eine Methodensignatur definiert. Er kann einen Verweis auf jede Methode bereitstellen, die über eine kompatible Signatur verfügt.</span><span class="sxs-lookup"><span data-stu-id="72000-271">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="72000-272">Sie können die Methode über den Delegaten aufrufen.</span><span class="sxs-lookup"><span data-stu-id="72000-272">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="72000-273">Delegaten werden verwendet, um Methoden als Argumente an anderen Methoden zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="72000-273">Delegates are used to pass methods as arguments to other methods.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72000-274">Ereignishandler sind nichts weiter als Methoden, die durch Delegaten aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="72000-274">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="72000-275">Weitere Informationen zur Ereignisbehandlung mit Delegaten finden Sie unter [Ereignisse](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="72000-275">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>  
  
 <span data-ttu-id="72000-276">So erstellen Sie einen Delegaten</span><span class="sxs-lookup"><span data-stu-id="72000-276">To create a delegate:</span></span>  
  
```csharp  
public delegate void SampleDelegate(string str);  
```  
  
 <span data-ttu-id="72000-277">So erstellen Sie einen Verweis auf eine Methode, die der vom Delegaten angegebenen Signatur entspricht:</span><span class="sxs-lookup"><span data-stu-id="72000-277">To create a reference to a method that matches the signature specified by the delegate:</span></span>  
  
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
  
 <span data-ttu-id="72000-278">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="72000-278">For more information, see:</span></span>  
  
-   [<span data-ttu-id="72000-279">Delegaten</span><span class="sxs-lookup"><span data-stu-id="72000-279">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
  
-   [<span data-ttu-id="72000-280">delegate</span><span class="sxs-lookup"><span data-stu-id="72000-280">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
## <a name="see-also"></a><span data-ttu-id="72000-281">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72000-281">See Also</span></span>  
 [<span data-ttu-id="72000-282">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="72000-282">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

