---
title: Objektorientierte Programmierung
ms.date: 07/20/2015
ms.assetid: 49794de4-64c3-473c-b8ed-fe98835df69c
ms.openlocfilehash: f7e222cde8ce80d4c52cc8b4b111c576eb4041b9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413192"
---
# <a name="object-oriented-programming-visual-basic"></a><span data-ttu-id="f0ed7-102">Objektorientierte Programmierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0ed7-102">Object-oriented programming (Visual Basic)</span></span>

<span data-ttu-id="f0ed7-103">Visual Basic bietet vollständige Unterstützung für objektorientierte Programmierung, einschließlich Kapselung, Vererbung und Polymorphie.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-103">Visual Basic provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>

 <span data-ttu-id="f0ed7-104">*Kapselung* bedeutet, dass eine Gruppe verwandter Eigenschaften, Methoden sowie anderer Member als eine Einheit bzw. ein Objekt behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>

 <span data-ttu-id="f0ed7-105">*Vererbung* beschreibt die Fähigkeit, neue Klassen basierend auf einer vorhandenen Klasse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>

 <span data-ttu-id="f0ed7-106">*Polymorphismus* bedeutet, dass Sie mehrere Klassen untereinander austauschen können, obwohl jede Klasse dieselben Eigenschaften oder Methoden auf unterschiedliche Art und Weise implementiert.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

 <span data-ttu-id="f0ed7-107">In diesem Abschnitt werden die folgenden Konzepte beschrieben:</span><span class="sxs-lookup"><span data-stu-id="f0ed7-107">This section describes the following concepts:</span></span>

- [<span data-ttu-id="f0ed7-108">Klassen und Objekte</span><span class="sxs-lookup"><span data-stu-id="f0ed7-108">Classes and objects</span></span>](#classes-and-objects)
  - [<span data-ttu-id="f0ed7-109">Klassenmember</span><span class="sxs-lookup"><span data-stu-id="f0ed7-109">Class members</span></span>](#class-members)
    - [<span data-ttu-id="f0ed7-110">Eigenschaften und Felder</span><span class="sxs-lookup"><span data-stu-id="f0ed7-110">Properties and fields</span></span>](#properties-and-fields)
    - [<span data-ttu-id="f0ed7-111">Methoden</span><span class="sxs-lookup"><span data-stu-id="f0ed7-111">Methods</span></span>](#methods)
    - [<span data-ttu-id="f0ed7-112">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="f0ed7-112">Constructors</span></span>](#constructors)
    - [<span data-ttu-id="f0ed7-113">Destruktoren</span><span class="sxs-lookup"><span data-stu-id="f0ed7-113">Destructors</span></span>](#destructors)
    - [<span data-ttu-id="f0ed7-114">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="f0ed7-114">Events</span></span>](#events)
    - [<span data-ttu-id="f0ed7-115">Geschachtelte Klassen</span><span class="sxs-lookup"><span data-stu-id="f0ed7-115">Nested classes</span></span>](#nested-classes)
  - [<span data-ttu-id="f0ed7-116">Zugriffsmodifizierer und Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="f0ed7-116">Access modifiers and access levels</span></span>](#access-modifiers-and-access-levels)
    - [<span data-ttu-id="f0ed7-117">Instanziieren von Klassen</span><span class="sxs-lookup"><span data-stu-id="f0ed7-117">Instantiating classes</span></span>](#instantiating-classes)
    - [<span data-ttu-id="f0ed7-118">Freigegebene Klassen und Member</span><span class="sxs-lookup"><span data-stu-id="f0ed7-118">Shared classes and members</span></span>](#shared-classes-and-members)
    - [<span data-ttu-id="f0ed7-119">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="f0ed7-119">Anonymous types</span></span>](#anonymous-types)
- [<span data-ttu-id="f0ed7-120">Vererbung</span><span class="sxs-lookup"><span data-stu-id="f0ed7-120">Inheritance</span></span>](#inheritance)
  - [<span data-ttu-id="f0ed7-121">Überschreiben von Mitgliedern</span><span class="sxs-lookup"><span data-stu-id="f0ed7-121">Overriding members</span></span>](#overriding-members)
- [<span data-ttu-id="f0ed7-122">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f0ed7-122">Interfaces</span></span>](#interfaces)
- [<span data-ttu-id="f0ed7-123">Generics</span><span class="sxs-lookup"><span data-stu-id="f0ed7-123">Generics</span></span>](#generics)
- [<span data-ttu-id="f0ed7-124">Delegaten</span><span class="sxs-lookup"><span data-stu-id="f0ed7-124">Delegates</span></span>](#delegates)

## <a name="classes-and-objects"></a><span data-ttu-id="f0ed7-125">Klassen und Objekte</span><span class="sxs-lookup"><span data-stu-id="f0ed7-125">Classes and objects</span></span>

<span data-ttu-id="f0ed7-126">Die Begriffe *Klasse* und *Objekt* werden manchmal synonym verwendet; genau genommen beschreiben Klassen jedoch den *Typ* von Objekten, während Objekte verwendbare *Instanzen* von Klassen sind.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-126">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="f0ed7-127">Das Erstellen eines Objekts wird daher als *Instanziierung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-127">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="f0ed7-128">Um auf den Vergleich mit Bauplänen zurückzukommen: Eine Klasse ist ein Bauplan, und ein Objekt ist ein anhand dieses Bauplans errichtetes Gebäude.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-128">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="f0ed7-129">So definieren Sie eine Klasse</span><span class="sxs-lookup"><span data-stu-id="f0ed7-129">To define a class:</span></span>

```vb
Class SampleClass
End Class
```

<span data-ttu-id="f0ed7-130">Visual Basic bietet auch eine einfache Version von Klassen, die als *Strukturen* bezeichnet werden, die nützlich sind, wenn Sie ein großes Array von Objekten erstellen müssen und nicht zu viel Arbeitsspeicher für diese verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-130">Visual Basic also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>

<span data-ttu-id="f0ed7-131">So definieren Sie eine Struktur</span><span class="sxs-lookup"><span data-stu-id="f0ed7-131">To define a structure:</span></span>

```vb
Structure SampleStructure
End Structure
```

<span data-ttu-id="f0ed7-132">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="f0ed7-132">For more information, see:</span></span>

- [<span data-ttu-id="f0ed7-133">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f0ed7-133">Class Statement</span></span>](../../language-reference/statements/class-statement.md)
- [<span data-ttu-id="f0ed7-134">Structure Statement</span><span class="sxs-lookup"><span data-stu-id="f0ed7-134">Structure Statement</span></span>](../../language-reference/statements/structure-statement.md)

### <a name="class-members"></a><span data-ttu-id="f0ed7-135">Klassenmember</span><span class="sxs-lookup"><span data-stu-id="f0ed7-135">Class members</span></span>

<span data-ttu-id="f0ed7-136">Jede Klasse kann über andere *Klassenmember* verfügen. Diese enthalten Eigenschaften, die Klassendaten beschreiben, Methoden, die Klassenverhalten definieren sowie Ereignisse, die die Kommunikation zwischen verschiedenen Klassen und Objekten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-136">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="properties-and-fields"></a><span data-ttu-id="f0ed7-137">Eigenschaften und Felder</span><span class="sxs-lookup"><span data-stu-id="f0ed7-137">Properties and fields</span></span>

<span data-ttu-id="f0ed7-138">Felder und Eigenschaften stellen die in einem Objekt enthaltenen Informationen dar.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-138">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="f0ed7-139">Felder sind wie Variablen, sie können direkt gelesen oder festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-139">Fields are like variables because they can be read or set directly.</span></span>

<span data-ttu-id="f0ed7-140">So definieren Sie ein Feld</span><span class="sxs-lookup"><span data-stu-id="f0ed7-140">To define a field:</span></span>

```vb
Class SampleClass
    Public SampleField As String
End Class
```

<span data-ttu-id="f0ed7-141">Eigenschaften verfügen über Get- und Set-Prozeduren, die eine bessere Kontrolle über das Festlegen oder Abrufen von Werten ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-141">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="f0ed7-142">Mit Visual Basic können Sie ein privates Feld zum Speichern des Eigenschafts Werts erstellen oder so genannte automatisch implementierte Eigenschaften verwenden, die dieses Feld automatisch im Hintergrund erstellen und die grundlegende Logik für die Eigenschaften Prozeduren bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-142">Visual Basic allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="f0ed7-143">So definieren Sie eine automatisch implementierte Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="f0ed7-143">To define an auto-implemented property:</span></span>

```vb
Class SampleClass
    Public Property SampleProperty as String
End Class
```

<span data-ttu-id="f0ed7-144">Verwenden Sie den folgenden Code, wenn Sie zusätzliche Lese- und Schreibvorgänge für den Eigenschaftswert ausführen müssen, um ein Feld zum Speichern des Eigenschaftswerts zu definieren und die grundlegende Logik zum Speichern und Abrufen bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="f0ed7-144">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

```vb
Class SampleClass
    Private m_Sample As String
    Public Property Sample() As String
        Get
            ' Return the value stored in the field.
            Return m_Sample
        End Get
        Set(ByVal Value As String)
            ' Store the value in the field.
            m_Sample = Value
        End Set
    End Property
End Class
```

<span data-ttu-id="f0ed7-145">Die meisten Eigenschaften verfügen über Methoden oder Prozeduren zum Festlegen und Abrufen des Eigenschaftswerts.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-145">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="f0ed7-146">Sie können jedoch schreib- oder lesegeschützte Eigenschaften erstellen, um zu verhindern, dass die Eigenschaften gelesen oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-146">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="f0ed7-147">In Visual Basic können Sie das `ReadOnly`-Schlüsselwort und das `WriteOnly`-Schlüsselwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-147">In Visual Basic you can use `ReadOnly` and `WriteOnly` keywords.</span></span> <span data-ttu-id="f0ed7-148">Automatisch implementierte Eigenschaften können jedoch nicht schreib- oder lesegeschützt sein.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-148">However, auto-implemented properties cannot be read-only or write-only.</span></span>

<span data-ttu-id="f0ed7-149">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="f0ed7-149">For more information, see:</span></span>

- [<span data-ttu-id="f0ed7-150">Property Statement</span><span class="sxs-lookup"><span data-stu-id="f0ed7-150">Property Statement</span></span>](../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="f0ed7-151">Get-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f0ed7-151">Get Statement</span></span>](../../language-reference/statements/get-statement.md)
- [<span data-ttu-id="f0ed7-152">Set-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f0ed7-152">Set Statement</span></span>](../../language-reference/statements/set-statement.md)
- [<span data-ttu-id="f0ed7-153">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="f0ed7-153">ReadOnly</span></span>](../../language-reference/modifiers/readonly.md)
- [<span data-ttu-id="f0ed7-154">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="f0ed7-154">WriteOnly</span></span>](../../language-reference/modifiers/writeonly.md)

#### <a name="methods"></a><span data-ttu-id="f0ed7-155">Methoden</span><span class="sxs-lookup"><span data-stu-id="f0ed7-155">Methods</span></span>

 <span data-ttu-id="f0ed7-156">Eine *Methode* ist eine Aktion, die von einem Objekt ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-156">A *method* is an action that an object can perform.</span></span>

> [!NOTE]
> <span data-ttu-id="f0ed7-157">In Visual Basic gibt es zwei Möglichkeiten, eine Methode zu erstellen: Wenn die Methode keinen Wert zurückgibt, wird die `Sub`-Anweisung verwendet; andernfalls wird die `Function`-Anweisung verwendet.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-157">In Visual Basic, there are two ways to create a method: the `Sub` statement is used if the method does not return a value; the `Function` statement is used if a method returns a value.</span></span>

<span data-ttu-id="f0ed7-158">So definieren Sie eine Methode einer Klasse:</span><span class="sxs-lookup"><span data-stu-id="f0ed7-158">To define a method of a class:</span></span>

```vb
Class SampleClass
    Public Function SampleFunc(ByVal SampleParam As String)
        ' Add code here
    End Function
End Class
```

<span data-ttu-id="f0ed7-159">Eine Klasse kann über mehrere Implementierungen oder *Überladungen* der gleichen Methode verfügen, die sich in der Anzahl der Parameter oder Parametertypen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-159">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="f0ed7-160">So überladen Sie eine Methode</span><span class="sxs-lookup"><span data-stu-id="f0ed7-160">To overload a method:</span></span>

```vb
Overloads Sub Display(ByVal theChar As Char)
    ' Add code that displays Char data.
End Sub
Overloads Sub Display(ByVal theInteger As Integer)
    ' Add code that displays Integer data.
End Sub
```

<span data-ttu-id="f0ed7-161">In den meisten Fällen deklarieren Sie eine Methode innerhalb einer Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-161">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="f0ed7-162">Visual Basic unterstützt jedoch auch *Erweiterungs Methoden* , mit denen Sie einer vorhandenen Klasse außerhalb der eigentlichen Definition der Klasse Methoden hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-162">However, Visual Basic also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="f0ed7-163">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="f0ed7-163">For more information, see:</span></span>

- [<span data-ttu-id="f0ed7-164">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f0ed7-164">Function Statement</span></span>](../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="f0ed7-165">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f0ed7-165">Sub Statement</span></span>](../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="f0ed7-166">Overloads</span><span class="sxs-lookup"><span data-stu-id="f0ed7-166">Overloads</span></span>](../../language-reference/modifiers/overloads.md)
- [<span data-ttu-id="f0ed7-167">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="f0ed7-167">Extension Methods</span></span>](../language-features/procedures/extension-methods.md)

#### <a name="constructors"></a><span data-ttu-id="f0ed7-168">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="f0ed7-168">Constructors</span></span>

<span data-ttu-id="f0ed7-169">Konstruktoren sind Klassenmethoden, die automatisch ausgeführt werden, wenn ein Objekt eines bestimmten Typs erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-169">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="f0ed7-170">Konstruktoren initialisieren normalerweise die Datenmember des neuen Objekts.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-170">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="f0ed7-171">Konstruktoren können nur einmal während der Erstellung der Klasse ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-171">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="f0ed7-172">Weiterhin wird der Code im Konstruktor immer vor jedem anderen Code in einer Klasse ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-172">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="f0ed7-173">Sie können jedoch mehrere Konstruktorüberladungen auf die gleiche Weise wie für jede andere Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-173">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="f0ed7-174">So definieren Sie einen Konstruktor für eine Klasse:</span><span class="sxs-lookup"><span data-stu-id="f0ed7-174">To define a constructor for a class:</span></span>

```vb
Class SampleClass
    Sub New(ByVal s As String)
        // Add code here.
    End Sub
End Class
```

<span data-ttu-id="f0ed7-175">Weitere Informationen finden Sie unter: [Objekt Lebensdauer: Erstellen und zerstören von Objekten](../language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="f0ed7-175">For more information, see: [Object Lifetime: How Objects Are Created and Destroyed](../language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

#### <a name="destructors"></a><span data-ttu-id="f0ed7-176">Destruktoren</span><span class="sxs-lookup"><span data-stu-id="f0ed7-176">Destructors</span></span>

<span data-ttu-id="f0ed7-177">Destruktoren werden zur Zerstörung von Klasseninstanzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-177">Destructors are used to destruct instances of classes.</span></span> <span data-ttu-id="f0ed7-178">In .NET Framework verwaltet die Garbage Collection die Speicherbelegung automatisch und gibt Arbeitsspeicher für die verwalteten Objekte in der Anwendung frei.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-178">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="f0ed7-179">Möglicherweise sind jedoch noch Destruktoren erforderlich, um alle nicht verwalteten Ressourcen zu bereinigen, die von der Anwendung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-179">However, you may still need destructors to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="f0ed7-180">Es kann nur einen Destruktor für eine Klasse geben.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-180">There can be only one destructor for a class.</span></span>

<span data-ttu-id="f0ed7-181">Weitere Informationen zu Destruktoren und der Garbage Collection in .NET Framework finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="f0ed7-181">For more information about destructors and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="events"></a><span data-ttu-id="f0ed7-182">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="f0ed7-182">Events</span></span>

<span data-ttu-id="f0ed7-183">Ereignisse aktivieren eine Klasse oder ein Objekt, um Informationen über Aktionen von Interesse an andere Klassen oder Objekte zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-183">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="f0ed7-184">Die Klasse, die das Ereignis sendet (oder auslöst), wird als *Herausgeber* bezeichnet, und die Klassen, die das Ereignis empfangen (oder verarbeiten), werden als *Abonnenten* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-184">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="f0ed7-185">Weitere Informationen zu Ereignissen sowie zu ihrer Auslösung und Behandlung finden Sie unter [Ereignisse](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="f0ed7-185">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="f0ed7-186">Um Ereignisse zu deklarieren, verwenden Sie die- [Ereignis Anweisung](../../language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f0ed7-186">To declare events, use the [Event Statement](../../language-reference/statements/event-statement.md).</span></span>

- <span data-ttu-id="f0ed7-187">Um Ereignisse aufzurichten, verwenden Sie die [raigevent-Anweisung](../../language-reference/statements/raiseevent-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f0ed7-187">To raise events, use the [RaiseEvent Statement](../../language-reference/statements/raiseevent-statement.md).</span></span>

- <span data-ttu-id="f0ed7-188">Um Ereignishandler mithilfe einer deklarativen Methode anzugeben, verwenden Sie die [widervents](../../language-reference/modifiers/withevents.md) -Anweisung und die [Handles](../../language-reference/statements/handles-clause.md) -Klausel.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-188">To specify event handlers using a declarative way, use the [WithEvents](../../language-reference/modifiers/withevents.md) statement and the [Handles](../../language-reference/statements/handles-clause.md) clause.</span></span>

- <span data-ttu-id="f0ed7-189">Um den einem Ereignis zugeordneten Ereignishandler dynamisch hinzufügen, entfernen und ändern zu können, verwenden Sie die [AddHandler-Anweisung](../../language-reference/statements/addhandler-statement.md) und die [RemoveHandler-Anweisung](../../language-reference/statements/removehandler-statement.md) zusammen mit dem [AddressOf-Operator](../../language-reference/operators/addressof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="f0ed7-189">To be able to dynamically add, remove, and change the event handler associated with an event, use the [AddHandler Statement](../../language-reference/statements/addhandler-statement.md) and [RemoveHandler Statement](../../language-reference/statements/removehandler-statement.md) together with the [AddressOf Operator](../../language-reference/operators/addressof-operator.md).</span></span>

#### <a name="nested-classes"></a><span data-ttu-id="f0ed7-190">Geschachtelte Klassen</span><span class="sxs-lookup"><span data-stu-id="f0ed7-190">Nested classes</span></span>

<span data-ttu-id="f0ed7-191">Eine Klasse, die in einer anderen Klasse definiert wird, wird als *geschachtelt* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-191">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="f0ed7-192">Standardmäßig ist die geschachtelte Klasse privat.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-192">By default, the nested class is private.</span></span>

```vb
Class Container
    Class Nested
    ' Add code here.
    End Class
End Class
```

<span data-ttu-id="f0ed7-193">Um eine Instanz der geschachtelten Klasse zu erstellen, verwenden Sie den Namen der Containerklasse und geben einen Punkt sowie anschließend den Namen der geschachtelten Klasse ein:</span><span class="sxs-lookup"><span data-stu-id="f0ed7-193">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```vb
Dim nestedInstance As Container.Nested = New Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a><span data-ttu-id="f0ed7-194">Zugriffsmodifizierer und Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="f0ed7-194">Access modifiers and access levels</span></span>

<span data-ttu-id="f0ed7-195">Alle Klassen und Klassenmember können mit *Zugriffsmodifizierern* angeben, welche Zugriffsebene sie für andere Klassen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-195">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="f0ed7-196">Die folgenden Zugriffsmodifizierer sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="f0ed7-196">The following access modifiers are available:</span></span>

|<span data-ttu-id="f0ed7-197">Visual Basic-Modifizierer</span><span class="sxs-lookup"><span data-stu-id="f0ed7-197">Visual Basic Modifier</span></span>|<span data-ttu-id="f0ed7-198">Definition</span><span class="sxs-lookup"><span data-stu-id="f0ed7-198">Definition</span></span>|
|---------------------------|----------------|
|[<span data-ttu-id="f0ed7-199">Öffentlich</span><span class="sxs-lookup"><span data-stu-id="f0ed7-199">Public</span></span>](../../language-reference/modifiers/public.md)|<span data-ttu-id="f0ed7-200">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder einer anderen Assembly, die darauf verweist, zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-200">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|
|[<span data-ttu-id="f0ed7-201">Privat</span><span class="sxs-lookup"><span data-stu-id="f0ed7-201">Private</span></span>](../../language-reference/modifiers/private.md)|<span data-ttu-id="f0ed7-202">Auf den Typ oder Member kann nur von Code in der gleichen Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-202">The type or member can only be accessed by code in the same class.</span></span>|
|[<span data-ttu-id="f0ed7-203">Gebieten</span><span class="sxs-lookup"><span data-stu-id="f0ed7-203">Protected</span></span>](../../language-reference/modifiers/protected.md)|<span data-ttu-id="f0ed7-204">Auf den Typ oder Member kann nur von Code in der gleichen Klasse oder in einer abgeleiteten Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-204">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|
|[<span data-ttu-id="f0ed7-205">Kollegen</span><span class="sxs-lookup"><span data-stu-id="f0ed7-205">Friend</span></span>](../../language-reference/modifiers/friend.md)|<span data-ttu-id="f0ed7-206">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly zugegriffen werden, jedoch nicht von Code in einer anderen Assembly.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-206">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|
|`Protected Friend`|<span data-ttu-id="f0ed7-207">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder von jeder abgeleiteten Klasse in einer anderen Assembly zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-207">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|

<span data-ttu-id="f0ed7-208">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f0ed7-208">For more information, see [Access levels in Visual Basic](../language-features/declared-elements/access-levels.md).</span></span>

### <a name="instantiating-classes"></a><span data-ttu-id="f0ed7-209">Instanziieren von Klassen</span><span class="sxs-lookup"><span data-stu-id="f0ed7-209">Instantiating classes</span></span>

<span data-ttu-id="f0ed7-210">Um ein Objekt zu erstellen, müssen Sie eine Klasse instanziieren oder eine Klasseninstanz erstellen.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-210">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```vb
Dim sampleObject as New SampleClass()
```

<span data-ttu-id="f0ed7-211">Nachdem Sie eine Klasse instanziiert haben, können Sie den Eigenschaften und Feldern der Instanz Werte zuweisen und Klassenmethoden aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-211">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```vb
' Set a property value.
sampleObject.SampleProperty = "Sample String"
' Call a method.
sampleObject.SampleMethod()
```

<span data-ttu-id="f0ed7-212">Verwenden Sie Objektinitialisierer, um Eigenschaften im Rahmen des Klasseninstanziierungsprozesses Werte zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="f0ed7-212">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```vb
Dim sampleObject = New SampleClass With
    {.FirstProperty = "A", .SecondProperty = "B"}
```

<span data-ttu-id="f0ed7-213">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="f0ed7-213">For more information, see:</span></span>

- [<span data-ttu-id="f0ed7-214">New-Operator</span><span class="sxs-lookup"><span data-stu-id="f0ed7-214">New Operator</span></span>](../../language-reference/operators/new-operator.md)
- [<span data-ttu-id="f0ed7-215">Objektinitialisierer: benannte und anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="f0ed7-215">Object Initializers: Named and Anonymous Types</span></span>](../language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)

### <a name="shared-classes-and-members"></a><span data-ttu-id="f0ed7-216">Freigegebene Klassen und Member</span><span class="sxs-lookup"><span data-stu-id="f0ed7-216">Shared classes and members</span></span>

 <span data-ttu-id="f0ed7-217">Ein gemeinsam genutzter Member der-Klasse ist eine Eigenschaft, Prozedur oder ein Feld, die von allen Instanzen einer Klasse gemeinsam verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-217">A shared member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

 <span data-ttu-id="f0ed7-218">So definieren Sie einen freigegebenen Member:</span><span class="sxs-lookup"><span data-stu-id="f0ed7-218">To define a shared member:</span></span>

```vb
Class SampleClass
    Public Shared SampleString As String = "Sample String"
End Class
```

 <span data-ttu-id="f0ed7-219">Wenn Sie auf den freigegebenen Member zugreifen möchten, verwenden Sie den Namen der Klasse, ohne ein Objekt dieser Klasse zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="f0ed7-219">To access the shared member, use the name of the class without creating an object of this class:</span></span>

```vb
MsgBox(SampleClass.SampleString)
```

 <span data-ttu-id="f0ed7-220">Freigegebene Module in Visual Basic nur gemeinsame Member aufweisen und können nicht instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-220">Shared modules in Visual Basic have shared members only and cannot be instantiated.</span></span> <span data-ttu-id="f0ed7-221">Freigegebene Member können auch nicht auf nicht freigegebene Eigenschaften, Felder oder Methoden zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-221">Shared members also cannot access non-shared properties, fields or methods</span></span>

 <span data-ttu-id="f0ed7-222">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="f0ed7-222">For more information, see:</span></span>

- [<span data-ttu-id="f0ed7-223">Freigegeben</span><span class="sxs-lookup"><span data-stu-id="f0ed7-223">Shared</span></span>](../../language-reference/modifiers/shared.md)
- [<span data-ttu-id="f0ed7-224">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f0ed7-224">Module Statement</span></span>](../../language-reference/statements/module-statement.md)

### <a name="anonymous-types"></a><span data-ttu-id="f0ed7-225">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="f0ed7-225">Anonymous types</span></span>

<span data-ttu-id="f0ed7-226">Mit anonymen Typen können Objekte erstellt werden, ohne eine Klassendefinition für den Datentyp zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-226">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="f0ed7-227">Stattdessen erzeugt der Compiler eine Klasse.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-227">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="f0ed7-228">Die Klasse hat keinen verwendbaren Namen und enthält die von Ihnen in der Deklaration des Objekts angegebenen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-228">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="f0ed7-229">So erstellen Sie eine Instanz eines anonymen Typs</span><span class="sxs-lookup"><span data-stu-id="f0ed7-229">To create an instance of an anonymous type:</span></span>

```vb
' sampleObject is an instance of a simple anonymous type.
Dim sampleObject =
    New With {Key .FirstProperty = "A", .SecondProperty = "B"}
```

<span data-ttu-id="f0ed7-230">Weitere Informationen finden Sie unter: [Anonyme Typen](../language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="f0ed7-230">For more information, see: [Anonymous Types](../language-features/objects-and-classes/anonymous-types.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="f0ed7-231">Vererbung</span><span class="sxs-lookup"><span data-stu-id="f0ed7-231">Inheritance</span></span>

<span data-ttu-id="f0ed7-232">Vererbung ermöglicht die Erstellung neuer Klassen, die in anderen Klassen definiertes Verhalten wieder verwenden, erweitern und ändern.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-232">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="f0ed7-233">Die Klasse, deren Member vererbt werden, wird *Basisklasse* genannt, und die Klasse, die diese Member erbt, wird *abgeleitete Klasse* genannt.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-233">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="f0ed7-234">Allerdings erben alle Klassen in Visual Basic implizit von der <xref:System.Object> -Klasse, die die .NET-Klassenhierarchie unterstützt und Dienste auf niedriger Ebene für alle Klassen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-234">However, all classes in Visual Basic implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="f0ed7-235">Visual Basic unterstützt keine mehrfache Vererbung.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-235">Visual Basic doesn't support multiple inheritance.</span></span> <span data-ttu-id="f0ed7-236">Sie können also nur eine Basisklasse für eine abgeleitete Klasse angeben.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-236">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="f0ed7-237">So erben Sie von einer Basisklasse</span><span class="sxs-lookup"><span data-stu-id="f0ed7-237">To inherit from a base class:</span></span>

```vb
Class DerivedClass
    Inherits BaseClass
End Class
```

<span data-ttu-id="f0ed7-238">Standardmäßig können alle Klassen geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-238">By default all classes can be inherited.</span></span> <span data-ttu-id="f0ed7-239">Sie können jedoch angeben, dass eine Klasse nicht als Basisklasse verwendet werden darf, oder eine Klasse erstellen, die nur als Basisklasse verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-239">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="f0ed7-240">So geben Sie an, dass eine Klasse nicht als Basisklasse verwendet werden kann</span><span class="sxs-lookup"><span data-stu-id="f0ed7-240">To specify that a class cannot be used as a base class:</span></span>

```vb
NotInheritable Class SampleClass
End Class
```

<span data-ttu-id="f0ed7-241">So geben Sie an, dass eine Klasse nur als Basisklasse verwendet und nicht instanziiert werden kann:</span><span class="sxs-lookup"><span data-stu-id="f0ed7-241">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```vb
MustInherit Class BaseClass
End Class
```

<span data-ttu-id="f0ed7-242">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="f0ed7-242">For more information, see:</span></span>

- [<span data-ttu-id="f0ed7-243">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="f0ed7-243">Inherits Statement</span></span>](../../language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="f0ed7-244">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="f0ed7-244">NotInheritable</span></span>](../../language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="f0ed7-245">MustInherit</span><span class="sxs-lookup"><span data-stu-id="f0ed7-245">MustInherit</span></span>](../../language-reference/modifiers/mustinherit.md)

### <a name="overriding-members"></a><span data-ttu-id="f0ed7-246">Überschreiben von Mitgliedern</span><span class="sxs-lookup"><span data-stu-id="f0ed7-246">Overriding members</span></span>

<span data-ttu-id="f0ed7-247">Standardmäßig erbt eine abgeleitete Klasse alle Member von ihrer Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-247">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="f0ed7-248">Wenn Sie das Verhalten des geerbten Members ändern möchten, müssen Sie diesen überschreiben.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-248">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="f0ed7-249">Das heißt, Sie können eine neue Implementierung der Methode, der Eigenschaft oder des Ereignisses in der abgeleiteten Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-249">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="f0ed7-250">Mit folgenden Modifizierern steuern Sie das Überschreiben von Eigenschaften und Methoden:</span><span class="sxs-lookup"><span data-stu-id="f0ed7-250">The following modifiers are used to control how properties and methods are overridden:</span></span>

|<span data-ttu-id="f0ed7-251">Visual Basic-Modifizierer</span><span class="sxs-lookup"><span data-stu-id="f0ed7-251">Visual Basic Modifier</span></span>|<span data-ttu-id="f0ed7-252">Definition</span><span class="sxs-lookup"><span data-stu-id="f0ed7-252">Definition</span></span>|
|---------------------------|----------------|
|[<span data-ttu-id="f0ed7-253">Overrides</span><span class="sxs-lookup"><span data-stu-id="f0ed7-253">Overridable</span></span>](../../language-reference/modifiers/overridable.md)|<span data-ttu-id="f0ed7-254">Ermöglicht das Überschreiben eines Klassenmembers in einer abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-254">Allows a class member to be overridden in a derived class.</span></span>|
|[<span data-ttu-id="f0ed7-255">Überschreibt</span><span class="sxs-lookup"><span data-stu-id="f0ed7-255">Overrides</span></span>](../../language-reference/modifiers/overrides.md)|<span data-ttu-id="f0ed7-256">Überschreibt einen virtuellen (überschreibbaren) Member, der in der Basisklasse definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-256">Overrides a virtual (overridable) member defined in the base class.</span></span>|
|[<span data-ttu-id="f0ed7-257">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="f0ed7-257">NotOverridable</span></span>](../../language-reference/modifiers/notoverridable.md)|<span data-ttu-id="f0ed7-258">Verhindert das Überschreiben eines Members in einer erbenden Klasse.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-258">Prevents a member from being overridden in an inheriting class.</span></span>|
|[<span data-ttu-id="f0ed7-259">MustOverride</span><span class="sxs-lookup"><span data-stu-id="f0ed7-259">MustOverride</span></span>](../../language-reference/modifiers/mustoverride.md)|<span data-ttu-id="f0ed7-260">Erfordert das Überschreiben eines Klassenmembers in der abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-260">Requires that a class member to be overridden in the derived class.</span></span>|
|[<span data-ttu-id="f0ed7-261">Shadows</span><span class="sxs-lookup"><span data-stu-id="f0ed7-261">Shadows</span></span>](../../language-reference/modifiers/shadows.md)|<span data-ttu-id="f0ed7-262">Blendet einen von einer Basisklasse geerbten Member aus.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-262">Hides a member inherited from a base class</span></span>|

## <a name="interfaces"></a><span data-ttu-id="f0ed7-263">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f0ed7-263">Interfaces</span></span>

<span data-ttu-id="f0ed7-264">Schnittstellen definieren (wie Klassen) einen Satz von Eigenschaften, Methoden und Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-264">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="f0ed7-265">Im Gegensatz zu Klassen jedoch bieten Schnittstellen keine Implementierung.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-265">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="f0ed7-266">Sie werden durch Klassen implementiert und als von Klassen unabhängige Entitäten definiert.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-266">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="f0ed7-267">Eine Schnittstelle stellt insofern einen Vertrag dar, dass eine Klasse, die eine Schnittstelle implementiert, jeden Aspekt dieser Schnittstelle gemäß seiner Definition implementieren muss.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-267">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="f0ed7-268">So definieren Sie eine Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0ed7-268">To define an interface:</span></span>

```vb
Public Interface ISampleInterface
    Sub DoSomething()
End Interface
```

<span data-ttu-id="f0ed7-269">So implementieren Sie eine Schnittstelle in einer Klasse</span><span class="sxs-lookup"><span data-stu-id="f0ed7-269">To implement an interface in a class:</span></span>

```vb
Class SampleClass
    Implements ISampleInterface
    Sub DoSomething
        ' Method implementation.
    End Sub
End Class
```

<span data-ttu-id="f0ed7-270">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="f0ed7-270">For more information, see:</span></span>

- [<span data-ttu-id="f0ed7-271">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f0ed7-271">Interfaces</span></span>](../language-features/interfaces/index.md)
- [<span data-ttu-id="f0ed7-272">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f0ed7-272">Interface Statement</span></span>](../../language-reference/statements/interface-statement.md)
- [<span data-ttu-id="f0ed7-273">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f0ed7-273">Implements Statement</span></span>](../../language-reference/statements/implements-statement.md)

## <a name="generics"></a><span data-ttu-id="f0ed7-274">Generics</span><span class="sxs-lookup"><span data-stu-id="f0ed7-274">Generics</span></span>

<span data-ttu-id="f0ed7-275">Klassen, Strukturen, Schnittstellen und Methoden in .net können *Typparameter* enthalten, die Typen von Objekten definieren, die Sie speichern oder verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-275">Classes, structures, interfaces and methods in .NET can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="f0ed7-276">Das einfachste Beispiel für Generics ist eine Auflistung, in der Sie den Typ von Objekten angeben können, die in einer Auflistung gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-276">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="f0ed7-277">So definieren Sie eine generische Klasse</span><span class="sxs-lookup"><span data-stu-id="f0ed7-277">To define a generic class:</span></span>

```vb
Class SampleGeneric(Of T)
    Public Field As T
End Class
```

<span data-ttu-id="f0ed7-278">So erstellen Sie eine Instanz einer generischen Klasse</span><span class="sxs-lookup"><span data-stu-id="f0ed7-278">To create an instance of a generic class:</span></span>

```vb
Dim sampleObject As New SampleGeneric(Of String)
sampleObject.Field = "Sample string"
```

<span data-ttu-id="f0ed7-279">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="f0ed7-279">For more information, see:</span></span>

- [<span data-ttu-id="f0ed7-280">Generics</span><span class="sxs-lookup"><span data-stu-id="f0ed7-280">Generics</span></span>](../../../standard/generics/index.md)
- [<span data-ttu-id="f0ed7-281">Generische Typen in Visual Basic (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0ed7-281">Generic Types in Visual Basic</span></span>](../language-features/data-types/generic-types.md)

## <a name="delegates"></a><span data-ttu-id="f0ed7-282">Delegaten</span><span class="sxs-lookup"><span data-stu-id="f0ed7-282">Delegates</span></span>

 <span data-ttu-id="f0ed7-283">Ein *Delegat* ist ein Typ, der eine Methodensignatur definiert. Er kann einen Verweis auf jede Methode bereitstellen, die über eine kompatible Signatur verfügt.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-283">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="f0ed7-284">Sie können die Methode über den Delegaten aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-284">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="f0ed7-285">Delegaten werden verwendet, um Methoden als Argumente an anderen Methoden zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-285">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="f0ed7-286">Ereignishandler sind nichts weiter als Methoden, die durch Delegaten aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f0ed7-286">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="f0ed7-287">Weitere Informationen zur Ereignisbehandlung mit Delegaten finden Sie unter [Ereignisse](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="f0ed7-287">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="f0ed7-288">So erstellen Sie einen Delegaten</span><span class="sxs-lookup"><span data-stu-id="f0ed7-288">To create a delegate:</span></span>

```vb
Delegate Sub SampleDelegate(ByVal str As String)
```

<span data-ttu-id="f0ed7-289">So erstellen Sie einen Verweis auf eine Methode, die der vom Delegaten angegebenen Signatur entspricht:</span><span class="sxs-lookup"><span data-stu-id="f0ed7-289">To create a reference to a method that matches the signature specified by the delegate:</span></span>

```vb
Class SampleClass
    ' Method that matches the SampleDelegate signature.
    Sub SampleSub(ByVal str As String)
        ' Add code here.
    End Sub
    ' Method that instantiates the delegate.
    Sub SampleDelegateSub()
        Dim sd As SampleDelegate = AddressOf SampleSub
        sd("Sample string")
    End Sub
End Class
```

<span data-ttu-id="f0ed7-290">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="f0ed7-290">For more information, see:</span></span>

- [<span data-ttu-id="f0ed7-291">Delegaten</span><span class="sxs-lookup"><span data-stu-id="f0ed7-291">Delegates</span></span>](../language-features/delegates/index.md)
- [<span data-ttu-id="f0ed7-292">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f0ed7-292">Delegate Statement</span></span>](../../language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="f0ed7-293">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="f0ed7-293">AddressOf Operator</span></span>](../../language-reference/operators/addressof-operator.md)

## <a name="see-also"></a><span data-ttu-id="f0ed7-294">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0ed7-294">See also</span></span>

- [<span data-ttu-id="f0ed7-295">Visual Basic-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f0ed7-295">Visual Basic Programming Guide</span></span>](../index.md)
