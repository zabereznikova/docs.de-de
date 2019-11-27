---
title: Objektorientierte Programmierung
ms.date: 07/20/2015
ms.assetid: 49794de4-64c3-473c-b8ed-fe98835df69c
ms.openlocfilehash: 3739919273f4cdd285d519c414c542f1a82a16d2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348162"
---
# <a name="object-oriented-programming-visual-basic"></a><span data-ttu-id="aac98-102">Objektorientierte Programmierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aac98-102">Object-oriented programming (Visual Basic)</span></span>

<span data-ttu-id="aac98-103">Visual Basic bietet vollständige Unterstützung für objektorientierte Programmierung, einschließlich Kapselung, Vererbung und Polymorphie.</span><span class="sxs-lookup"><span data-stu-id="aac98-103">Visual Basic provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>

 <span data-ttu-id="aac98-104">*Kapselung* bedeutet, dass eine Gruppe verwandter Eigenschaften, Methoden sowie anderer Member als eine Einheit bzw. ein Objekt behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="aac98-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>

 <span data-ttu-id="aac98-105">*Vererbung* beschreibt die Fähigkeit, neue Klassen basierend auf einer vorhandenen Klasse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="aac98-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>

 <span data-ttu-id="aac98-106">*Polymorphismus* bedeutet, dass Sie mehrere Klassen untereinander austauschen können, obwohl jede Klasse dieselben Eigenschaften oder Methoden auf unterschiedliche Art und Weise implementiert.</span><span class="sxs-lookup"><span data-stu-id="aac98-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

 <span data-ttu-id="aac98-107">In diesem Abschnitt werden die folgenden Konzepte beschrieben:</span><span class="sxs-lookup"><span data-stu-id="aac98-107">This section describes the following concepts:</span></span>

- [<span data-ttu-id="aac98-108">Klassen und Objekte</span><span class="sxs-lookup"><span data-stu-id="aac98-108">Classes and objects</span></span>](#classes-and-objects)
  - [<span data-ttu-id="aac98-109">Class members (Klassenmember)</span><span class="sxs-lookup"><span data-stu-id="aac98-109">Class members</span></span>](#class-members)
    - [<span data-ttu-id="aac98-110">Eigenschaften und Felder</span><span class="sxs-lookup"><span data-stu-id="aac98-110">Properties and fields</span></span>](#properties-and-fields)
    - [<span data-ttu-id="aac98-111">Methoden</span><span class="sxs-lookup"><span data-stu-id="aac98-111">Methods</span></span>](#methods)
    - [<span data-ttu-id="aac98-112">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="aac98-112">Constructors</span></span>](#constructors)
    - [<span data-ttu-id="aac98-113">Destruktoren</span><span class="sxs-lookup"><span data-stu-id="aac98-113">Destructors</span></span>](#destructors)
    - [<span data-ttu-id="aac98-114">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="aac98-114">Events</span></span>](#events)
    - [<span data-ttu-id="aac98-115">Klassen</span><span class="sxs-lookup"><span data-stu-id="aac98-115">Nested classes</span></span>](#nested-classes)
  - [<span data-ttu-id="aac98-116">Zugriffsmodifizierer und Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="aac98-116">Access modifiers and access levels</span></span>](#access-modifiers-and-access-levels)
    - [<span data-ttu-id="aac98-117">Instanziieren von Klassen</span><span class="sxs-lookup"><span data-stu-id="aac98-117">Instantiating classes</span></span>](#instantiating-classes)
    - [<span data-ttu-id="aac98-118">Freigegebene Klassen und Member</span><span class="sxs-lookup"><span data-stu-id="aac98-118">Shared classes and members</span></span>](#shared-classes-and-members)
    - [<span data-ttu-id="aac98-119">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="aac98-119">Anonymous types</span></span>](#anonymous-types)
- [<span data-ttu-id="aac98-120">Vererbung</span><span class="sxs-lookup"><span data-stu-id="aac98-120">Inheritance</span></span>](#inheritance)
  - [<span data-ttu-id="aac98-121">Überschreiben von Mitgliedern</span><span class="sxs-lookup"><span data-stu-id="aac98-121">Overriding members</span></span>](#overriding-members)
- [<span data-ttu-id="aac98-122">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="aac98-122">Interfaces</span></span>](#interfaces)
- [<span data-ttu-id="aac98-123">Generics</span><span class="sxs-lookup"><span data-stu-id="aac98-123">Generics</span></span>](#generics)
- [<span data-ttu-id="aac98-124">Delegaten</span><span class="sxs-lookup"><span data-stu-id="aac98-124">Delegates</span></span>](#delegates)

## <a name="classes-and-objects"></a><span data-ttu-id="aac98-125">Klassen und Objekte</span><span class="sxs-lookup"><span data-stu-id="aac98-125">Classes and objects</span></span>

<span data-ttu-id="aac98-126">Die Begriffe *Klasse* und *Objekt* werden manchmal synonym verwendet; genau genommen beschreiben Klassen jedoch den *Typ* von Objekten, während Objekte verwendbare *Instanzen* von Klassen sind.</span><span class="sxs-lookup"><span data-stu-id="aac98-126">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="aac98-127">Das Erstellen eines Objekts wird daher als *Instanziierung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="aac98-127">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="aac98-128">Um auf den Vergleich mit Bauplänen zurückzukommen: Eine Klasse ist ein Bauplan, und ein Objekt ist ein anhand dieses Bauplans errichtetes Gebäude.</span><span class="sxs-lookup"><span data-stu-id="aac98-128">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="aac98-129">So definieren Sie eine Klasse</span><span class="sxs-lookup"><span data-stu-id="aac98-129">To define a class:</span></span>

```vb
Class SampleClass
End Class
```

<span data-ttu-id="aac98-130">Visual Basic bietet auch eine einfache Version von Klassen, die als *Strukturen* bezeichnet werden, die nützlich sind, wenn Sie ein großes Array von Objekten erstellen müssen und nicht zu viel Arbeitsspeicher für diese verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="aac98-130">Visual Basic also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>

<span data-ttu-id="aac98-131">So definieren Sie eine Struktur</span><span class="sxs-lookup"><span data-stu-id="aac98-131">To define a structure:</span></span>

```vb
Structure SampleStructure
End Structure
```

<span data-ttu-id="aac98-132">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="aac98-132">For more information, see:</span></span>

- [<span data-ttu-id="aac98-133">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aac98-133">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="aac98-134">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aac98-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)

### <a name="class-members"></a><span data-ttu-id="aac98-135">Klassenmember</span><span class="sxs-lookup"><span data-stu-id="aac98-135">Class members</span></span>

<span data-ttu-id="aac98-136">Jede Klasse kann über andere *Klassenmember* verfügen. Diese enthalten Eigenschaften, die Klassendaten beschreiben, Methoden, die Klassenverhalten definieren sowie Ereignisse, die die Kommunikation zwischen verschiedenen Klassen und Objekten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="aac98-136">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="properties-and-fields"></a><span data-ttu-id="aac98-137">Eigenschaften und Felder</span><span class="sxs-lookup"><span data-stu-id="aac98-137">Properties and fields</span></span>

<span data-ttu-id="aac98-138">Felder und Eigenschaften stellen die in einem Objekt enthaltenen Informationen dar.</span><span class="sxs-lookup"><span data-stu-id="aac98-138">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="aac98-139">Felder sind wie Variablen, sie können direkt gelesen oder festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="aac98-139">Fields are like variables because they can be read or set directly.</span></span>

<span data-ttu-id="aac98-140">So definieren Sie ein Feld</span><span class="sxs-lookup"><span data-stu-id="aac98-140">To define a field:</span></span>

```vb
Class SampleClass
    Public SampleField As String
End Class
```

<span data-ttu-id="aac98-141">Eigenschaften verfügen über Get- und Set-Prozeduren, die eine bessere Kontrolle über das Festlegen oder Abrufen von Werten ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="aac98-141">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="aac98-142">Mit Visual Basic können Sie ein privates Feld zum Speichern des Eigenschafts Werts erstellen oder so genannte automatisch implementierte Eigenschaften verwenden, die dieses Feld automatisch im Hintergrund erstellen und die grundlegende Logik für die Eigenschaften Prozeduren bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="aac98-142">Visual Basic allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="aac98-143">So definieren Sie eine automatisch implementierte Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="aac98-143">To define an auto-implemented property:</span></span>

```vb
Class SampleClass
    Public Property SampleProperty as String
End Class
```

<span data-ttu-id="aac98-144">Verwenden Sie den folgenden Code, wenn Sie zusätzliche Lese- und Schreibvorgänge für den Eigenschaftswert ausführen müssen, um ein Feld zum Speichern des Eigenschaftswerts zu definieren und die grundlegende Logik zum Speichern und Abrufen bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="aac98-144">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

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

<span data-ttu-id="aac98-145">Die meisten Eigenschaften verfügen über Methoden oder Prozeduren zum Festlegen und Abrufen des Eigenschaftswerts.</span><span class="sxs-lookup"><span data-stu-id="aac98-145">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="aac98-146">Sie können jedoch schreib- oder lesegeschützte Eigenschaften erstellen, um zu verhindern, dass die Eigenschaften gelesen oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="aac98-146">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="aac98-147">In Visual Basic können Sie das `ReadOnly`-Schlüsselwort und das `WriteOnly`-Schlüsselwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="aac98-147">In Visual Basic you can use `ReadOnly` and `WriteOnly` keywords.</span></span> <span data-ttu-id="aac98-148">Automatisch implementierte Eigenschaften können jedoch nicht schreib- oder lesegeschützt sein.</span><span class="sxs-lookup"><span data-stu-id="aac98-148">However, auto-implemented properties cannot be read-only or write-only.</span></span>

<span data-ttu-id="aac98-149">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="aac98-149">For more information, see:</span></span>

- [<span data-ttu-id="aac98-150">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aac98-150">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="aac98-151">Get-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aac98-151">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="aac98-152">Set-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aac98-152">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="aac98-153">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="aac98-153">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="aac98-154">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="aac98-154">WriteOnly</span></span>](../../../visual-basic/language-reference/modifiers/writeonly.md)

#### <a name="methods"></a><span data-ttu-id="aac98-155">Methoden</span><span class="sxs-lookup"><span data-stu-id="aac98-155">Methods</span></span>

 <span data-ttu-id="aac98-156">Eine *Methode* ist eine Aktion, die von einem Objekt ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="aac98-156">A *method* is an action that an object can perform.</span></span>

> [!NOTE]
> <span data-ttu-id="aac98-157">In Visual Basic gibt es zwei Möglichkeiten, eine Methode zu erstellen: Wenn die Methode keinen Wert zurückgibt, wird die `Sub`-Anweisung verwendet; andernfalls wird die `Function`-Anweisung verwendet.</span><span class="sxs-lookup"><span data-stu-id="aac98-157">In Visual Basic, there are two ways to create a method: the `Sub` statement is used if the method does not return a value; the `Function` statement is used if a method returns a value.</span></span>

<span data-ttu-id="aac98-158">So definieren Sie eine Methode einer Klasse:</span><span class="sxs-lookup"><span data-stu-id="aac98-158">To define a method of a class:</span></span>

```vb
Class SampleClass
    Public Function SampleFunc(ByVal SampleParam As String)
        ' Add code here
    End Function
End Class
```

<span data-ttu-id="aac98-159">Eine Klasse kann über mehrere Implementierungen oder *Überladungen* der gleichen Methode verfügen, die sich in der Anzahl der Parameter oder Parametertypen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="aac98-159">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="aac98-160">So überladen Sie eine Methode</span><span class="sxs-lookup"><span data-stu-id="aac98-160">To overload a method:</span></span>

```vb
Overloads Sub Display(ByVal theChar As Char)
    ' Add code that displays Char data.
End Sub
Overloads Sub Display(ByVal theInteger As Integer)
    ' Add code that displays Integer data.
End Sub
```

<span data-ttu-id="aac98-161">In den meisten Fällen deklarieren Sie eine Methode innerhalb einer Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="aac98-161">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="aac98-162">Visual Basic unterstützt jedoch auch *Erweiterungs Methoden* , mit denen Sie einer vorhandenen Klasse außerhalb der eigentlichen Definition der Klasse Methoden hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="aac98-162">However, Visual Basic also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="aac98-163">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="aac98-163">For more information, see:</span></span>

- [<span data-ttu-id="aac98-164">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aac98-164">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="aac98-165">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aac98-165">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="aac98-166">Overloads</span><span class="sxs-lookup"><span data-stu-id="aac98-166">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="aac98-167">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="aac98-167">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)

#### <a name="constructors"></a><span data-ttu-id="aac98-168">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="aac98-168">Constructors</span></span>

<span data-ttu-id="aac98-169">Konstruktoren sind Klassenmethoden, die automatisch ausgeführt werden, wenn ein Objekt eines bestimmten Typs erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="aac98-169">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="aac98-170">Konstruktoren initialisieren normalerweise die Datenmember des neuen Objekts.</span><span class="sxs-lookup"><span data-stu-id="aac98-170">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="aac98-171">Konstruktoren können nur einmal während der Erstellung der Klasse ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="aac98-171">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="aac98-172">Weiterhin wird der Code im Konstruktor immer vor jedem anderen Code in einer Klasse ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="aac98-172">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="aac98-173">Sie können jedoch mehrere Konstruktorüberladungen auf die gleiche Weise wie für jede andere Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="aac98-173">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="aac98-174">So definieren Sie einen Konstruktor für eine Klasse:</span><span class="sxs-lookup"><span data-stu-id="aac98-174">To define a constructor for a class:</span></span>

```vb
Class SampleClass
    Sub New(ByVal s As String)
        // Add code here.
    End Sub
End Class
```

<span data-ttu-id="aac98-175">Weitere Informationen finden Sie unter: [Objekt Lebensdauer: Erstellen und zerstören von Objekten](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="aac98-175">For more information, see: [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

#### <a name="destructors"></a><span data-ttu-id="aac98-176">Destruktoren verschoben.</span><span class="sxs-lookup"><span data-stu-id="aac98-176">Destructors</span></span>

<span data-ttu-id="aac98-177">Destruktoren werden zur Zerstörung von Klasseninstanzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="aac98-177">Destructors are used to destruct instances of classes.</span></span> <span data-ttu-id="aac98-178">In .NET Framework verwaltet die Garbage Collection die Speicherbelegung automatisch und gibt Arbeitsspeicher für die verwalteten Objekte in der Anwendung frei.</span><span class="sxs-lookup"><span data-stu-id="aac98-178">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="aac98-179">Möglicherweise sind jedoch noch Destruktoren erforderlich, um alle nicht verwalteten Ressourcen zu bereinigen, die von der Anwendung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="aac98-179">However, you may still need destructors to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="aac98-180">Es kann nur einen Destruktor für eine Klasse geben.</span><span class="sxs-lookup"><span data-stu-id="aac98-180">There can be only one destructor for a class.</span></span>

<span data-ttu-id="aac98-181">Weitere Informationen zu Destruktoren und der Garbage Collection in .NET Framework finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="aac98-181">For more information about destructors and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="events"></a><span data-ttu-id="aac98-182">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="aac98-182">Events</span></span>

<span data-ttu-id="aac98-183">Ereignisse aktivieren eine Klasse oder ein Objekt, um Informationen über Aktionen von Interesse an andere Klassen oder Objekte zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="aac98-183">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="aac98-184">Die Klasse, die das Ereignis sendet (oder auslöst), wird als *Herausgeber* bezeichnet, und die Klassen, die das Ereignis empfangen (oder verarbeiten), werden als *Abonnenten* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="aac98-184">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="aac98-185">Weitere Informationen zu Ereignissen sowie zu ihrer Auslösung und Behandlung finden Sie unter [Ereignisse](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="aac98-185">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="aac98-186">Um Ereignisse zu deklarieren, verwenden Sie die- [Ereignis Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aac98-186">To declare events, use the [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>

- <span data-ttu-id="aac98-187">Um Ereignisse aufzurichten, verwenden Sie die [raigevent-Anweisung](../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aac98-187">To raise events, use the [RaiseEvent Statement](../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span></span>

- <span data-ttu-id="aac98-188">Um Ereignishandler mithilfe einer deklarativen Methode anzugeben, verwenden Sie die [widervents](../../../visual-basic/language-reference/modifiers/withevents.md) -Anweisung und die [Handles](../../../visual-basic/language-reference/statements/handles-clause.md) -Klausel.</span><span class="sxs-lookup"><span data-stu-id="aac98-188">To specify event handlers using a declarative way, use the [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md) statement and the [Handles](../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span>

- <span data-ttu-id="aac98-189">Um den einem Ereignis zugeordneten Ereignishandler dynamisch hinzufügen, entfernen und ändern zu können, verwenden Sie die [AddHandler-Anweisung](../../../visual-basic/language-reference/statements/addhandler-statement.md) und die [RemoveHandler-Anweisung](../../../visual-basic/language-reference/statements/removehandler-statement.md) zusammen mit dem [AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="aac98-189">To be able to dynamically add, remove, and change the event handler associated with an event, use the [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md) and [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) together with the [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md).</span></span>

#### <a name="nested-classes"></a><span data-ttu-id="aac98-190">Klassen</span><span class="sxs-lookup"><span data-stu-id="aac98-190">Nested classes</span></span>

<span data-ttu-id="aac98-191">Eine Klasse, die in einer anderen Klasse definiert wird, wird als *geschachtelt* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="aac98-191">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="aac98-192">Standardmäßig ist die geschachtelte Klasse privat.</span><span class="sxs-lookup"><span data-stu-id="aac98-192">By default, the nested class is private.</span></span>

```vb
Class Container
    Class Nested
    ' Add code here.
    End Class
End Class
```

<span data-ttu-id="aac98-193">Um eine Instanz der geschachtelten Klasse zu erstellen, verwenden Sie den Namen der Containerklasse und geben einen Punkt sowie anschließend den Namen der geschachtelten Klasse ein:</span><span class="sxs-lookup"><span data-stu-id="aac98-193">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```vb
Dim nestedInstance As Container.Nested = New Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a><span data-ttu-id="aac98-194">Zugriffsmodifizierer und Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="aac98-194">Access modifiers and access levels</span></span>

<span data-ttu-id="aac98-195">Alle Klassen und Klassenmember können mit *Zugriffsmodifizierern* angeben, welche Zugriffsebene sie für andere Klassen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="aac98-195">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="aac98-196">Die folgenden Zugriffsmodifizierer sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="aac98-196">The following access modifiers are available:</span></span>

|<span data-ttu-id="aac98-197">Visual Basic-Modifizierer</span><span class="sxs-lookup"><span data-stu-id="aac98-197">Visual Basic Modifier</span></span>|<span data-ttu-id="aac98-198">Definition</span><span class="sxs-lookup"><span data-stu-id="aac98-198">Definition</span></span>|
|---------------------------|----------------|
|[<span data-ttu-id="aac98-199">Public</span><span class="sxs-lookup"><span data-stu-id="aac98-199">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)|<span data-ttu-id="aac98-200">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder einer anderen Assembly, die darauf verweist, zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="aac98-200">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|
|[<span data-ttu-id="aac98-201">Private</span><span class="sxs-lookup"><span data-stu-id="aac98-201">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)|<span data-ttu-id="aac98-202">Auf den Typ oder Member kann nur von Code in der gleichen Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="aac98-202">The type or member can only be accessed by code in the same class.</span></span>|
|[<span data-ttu-id="aac98-203">Protected</span><span class="sxs-lookup"><span data-stu-id="aac98-203">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)|<span data-ttu-id="aac98-204">Auf den Typ oder Member kann nur von Code in der gleichen Klasse oder in einer abgeleiteten Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="aac98-204">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|
|[<span data-ttu-id="aac98-205">Friend</span><span class="sxs-lookup"><span data-stu-id="aac98-205">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)|<span data-ttu-id="aac98-206">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly zugegriffen werden, jedoch nicht von Code in einer anderen Assembly.</span><span class="sxs-lookup"><span data-stu-id="aac98-206">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|
|`Protected Friend`|<span data-ttu-id="aac98-207">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder von jeder abgeleiteten Klasse in einer anderen Assembly zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="aac98-207">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|

<span data-ttu-id="aac98-208">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="aac98-208">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

### <a name="instantiating-classes"></a><span data-ttu-id="aac98-209">Instanziieren von Klassen</span><span class="sxs-lookup"><span data-stu-id="aac98-209">Instantiating classes</span></span>

<span data-ttu-id="aac98-210">Um ein Objekt zu erstellen, müssen Sie eine Klasse instanziieren oder eine Klasseninstanz erstellen.</span><span class="sxs-lookup"><span data-stu-id="aac98-210">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```vb
Dim sampleObject as New SampleClass()
```

<span data-ttu-id="aac98-211">Nachdem Sie eine Klasse instanziiert haben, können Sie den Eigenschaften und Feldern der Instanz Werte zuweisen und Klassenmethoden aufrufen.</span><span class="sxs-lookup"><span data-stu-id="aac98-211">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```vb
' Set a property value.
sampleObject.SampleProperty = "Sample String"
' Call a method.
sampleObject.SampleMethod()
```

<span data-ttu-id="aac98-212">Verwenden Sie Objektinitialisierer, um Eigenschaften im Rahmen des Klasseninstanziierungsprozesses Werte zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="aac98-212">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```vb
Dim sampleObject = New SampleClass With
    {.FirstProperty = "A", .SecondProperty = "B"}
```

<span data-ttu-id="aac98-213">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="aac98-213">For more information, see:</span></span>

- [<span data-ttu-id="aac98-214">New-Operator</span><span class="sxs-lookup"><span data-stu-id="aac98-214">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="aac98-215">Objektinitialisierer: Benannte und anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="aac98-215">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)

### <a name="shared-classes-and-members"></a><span data-ttu-id="aac98-216">Freigegebene Klassen und Member</span><span class="sxs-lookup"><span data-stu-id="aac98-216">Shared classes and members</span></span>

 <span data-ttu-id="aac98-217">Ein gemeinsam genutzter Member der-Klasse ist eine Eigenschaft, Prozedur oder ein Feld, die von allen Instanzen einer Klasse gemeinsam verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="aac98-217">A shared member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

 <span data-ttu-id="aac98-218">So definieren Sie einen freigegebenen Member:</span><span class="sxs-lookup"><span data-stu-id="aac98-218">To define a shared member:</span></span>

```vb
Class SampleClass
    Public Shared SampleString As String = "Sample String"
End Class
```

 <span data-ttu-id="aac98-219">Wenn Sie auf den freigegebenen Member zugreifen möchten, verwenden Sie den Namen der Klasse, ohne ein Objekt dieser Klasse zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="aac98-219">To access the shared member, use the name of the class without creating an object of this class:</span></span>

```vb
MsgBox(SampleClass.SampleString)
```

 <span data-ttu-id="aac98-220">Freigegebene Module in Visual Basic nur gemeinsame Member aufweisen und können nicht instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="aac98-220">Shared modules in Visual Basic have shared members only and cannot be instantiated.</span></span> <span data-ttu-id="aac98-221">Freigegebene Member können auch nicht auf nicht freigegebene Eigenschaften, Felder oder Methoden zugreifen.</span><span class="sxs-lookup"><span data-stu-id="aac98-221">Shared members also cannot access non-shared properties, fields or methods</span></span>

 <span data-ttu-id="aac98-222">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="aac98-222">For more information, see:</span></span>

- [<span data-ttu-id="aac98-223">Shared</span><span class="sxs-lookup"><span data-stu-id="aac98-223">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="aac98-224">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aac98-224">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)

### <a name="anonymous-types"></a><span data-ttu-id="aac98-225">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="aac98-225">Anonymous types</span></span>

<span data-ttu-id="aac98-226">Mit anonymen Typen können Objekte erstellt werden, ohne eine Klassendefinition für den Datentyp zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="aac98-226">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="aac98-227">Stattdessen erzeugt der Compiler eine Klasse.</span><span class="sxs-lookup"><span data-stu-id="aac98-227">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="aac98-228">Die Klasse hat keinen verwendbaren Namen und enthält die von Ihnen in der Deklaration des Objekts angegebenen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="aac98-228">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="aac98-229">So erstellen Sie eine Instanz eines anonymen Typs</span><span class="sxs-lookup"><span data-stu-id="aac98-229">To create an instance of an anonymous type:</span></span>

```vb
' sampleObject is an instance of a simple anonymous type.
Dim sampleObject =
    New With {Key .FirstProperty = "A", .SecondProperty = "B"}
```

<span data-ttu-id="aac98-230">Weitere Informationen finden Sie unter [Anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="aac98-230">For more information, see: [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="aac98-231">Vererbung</span><span class="sxs-lookup"><span data-stu-id="aac98-231">Inheritance</span></span>

<span data-ttu-id="aac98-232">Vererbung ermöglicht die Erstellung neuer Klassen, die in anderen Klassen definiertes Verhalten wieder verwenden, erweitern und ändern.</span><span class="sxs-lookup"><span data-stu-id="aac98-232">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="aac98-233">Die Klasse, deren Member vererbt werden, wird *Basisklasse* genannt, und die Klasse, die diese Member erbt, wird *abgeleitete Klasse* genannt.</span><span class="sxs-lookup"><span data-stu-id="aac98-233">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="aac98-234">Allerdings erben alle Klassen in Visual Basic implizit von der <xref:System.Object> Klasse, die die .NET-Klassenhierarchie unterstützt und Dienste auf niedriger Ebene für alle Klassen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="aac98-234">However, all classes in Visual Basic implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="aac98-235">Visual Basic unterstützt keine mehrfache Vererbung.</span><span class="sxs-lookup"><span data-stu-id="aac98-235">Visual Basic doesn't support multiple inheritance.</span></span> <span data-ttu-id="aac98-236">Sie können also nur eine Basisklasse für eine abgeleitete Klasse angeben.</span><span class="sxs-lookup"><span data-stu-id="aac98-236">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="aac98-237">So erben Sie von einer Basisklasse</span><span class="sxs-lookup"><span data-stu-id="aac98-237">To inherit from a base class:</span></span>

```vb
Class DerivedClass
    Inherits BaseClass
End Class
```

<span data-ttu-id="aac98-238">Standardmäßig können alle Klassen geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="aac98-238">By default all classes can be inherited.</span></span> <span data-ttu-id="aac98-239">Sie können jedoch angeben, dass eine Klasse nicht als Basisklasse verwendet werden darf, oder eine Klasse erstellen, die nur als Basisklasse verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="aac98-239">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="aac98-240">So geben Sie an, dass eine Klasse nicht als Basisklasse verwendet werden kann</span><span class="sxs-lookup"><span data-stu-id="aac98-240">To specify that a class cannot be used as a base class:</span></span>

```vb
NotInheritable Class SampleClass
End Class
```

<span data-ttu-id="aac98-241">So geben Sie an, dass eine Klasse nur als Basisklasse verwendet und nicht instanziiert werden kann:</span><span class="sxs-lookup"><span data-stu-id="aac98-241">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```vb
MustInherit Class BaseClass
End Class
```

<span data-ttu-id="aac98-242">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="aac98-242">For more information, see:</span></span>

- [<span data-ttu-id="aac98-243">Inherits-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aac98-243">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="aac98-244">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="aac98-244">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="aac98-245">MustInherit</span><span class="sxs-lookup"><span data-stu-id="aac98-245">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)

### <a name="overriding-members"></a><span data-ttu-id="aac98-246">Überschreiben von Mitgliedern</span><span class="sxs-lookup"><span data-stu-id="aac98-246">Overriding members</span></span>

<span data-ttu-id="aac98-247">Standardmäßig erbt eine abgeleitete Klasse alle Member von ihrer Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="aac98-247">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="aac98-248">Wenn Sie das Verhalten des geerbten Members ändern möchten, müssen Sie diesen überschreiben.</span><span class="sxs-lookup"><span data-stu-id="aac98-248">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="aac98-249">Das heißt, Sie können eine neue Implementierung der Methode, der Eigenschaft oder des Ereignisses in der abgeleiteten Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="aac98-249">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="aac98-250">Mit folgenden Modifizierern steuern Sie das Überschreiben von Eigenschaften und Methoden:</span><span class="sxs-lookup"><span data-stu-id="aac98-250">The following modifiers are used to control how properties and methods are overridden:</span></span>

|<span data-ttu-id="aac98-251">Visual Basic-Modifizierer</span><span class="sxs-lookup"><span data-stu-id="aac98-251">Visual Basic Modifier</span></span>|<span data-ttu-id="aac98-252">Definition</span><span class="sxs-lookup"><span data-stu-id="aac98-252">Definition</span></span>|
|---------------------------|----------------|
|[<span data-ttu-id="aac98-253">Overrides</span><span class="sxs-lookup"><span data-stu-id="aac98-253">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)|<span data-ttu-id="aac98-254">Ermöglicht das Überschreiben eines Klassenmembers in einer abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="aac98-254">Allows a class member to be overridden in a derived class.</span></span>|
|[<span data-ttu-id="aac98-255">Overrides</span><span class="sxs-lookup"><span data-stu-id="aac98-255">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)|<span data-ttu-id="aac98-256">Überschreibt einen virtuellen (überschreibbaren) Member, der in der Basisklasse definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="aac98-256">Overrides a virtual (overridable) member defined in the base class.</span></span>|
|[<span data-ttu-id="aac98-257">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="aac98-257">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)|<span data-ttu-id="aac98-258">Verhindert das Überschreiben eines Members in einer erbenden Klasse.</span><span class="sxs-lookup"><span data-stu-id="aac98-258">Prevents a member from being overridden in an inheriting class.</span></span>|
|[<span data-ttu-id="aac98-259">MustOverride</span><span class="sxs-lookup"><span data-stu-id="aac98-259">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)|<span data-ttu-id="aac98-260">Erfordert das Überschreiben eines Klassenmembers in der abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="aac98-260">Requires that a class member to be overridden in the derived class.</span></span>|
|[<span data-ttu-id="aac98-261">Shadows</span><span class="sxs-lookup"><span data-stu-id="aac98-261">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)|<span data-ttu-id="aac98-262">Blendet einen von einer Basisklasse geerbten Member aus.</span><span class="sxs-lookup"><span data-stu-id="aac98-262">Hides a member inherited from a base class</span></span>|

## <a name="interfaces"></a><span data-ttu-id="aac98-263">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="aac98-263">Interfaces</span></span>

<span data-ttu-id="aac98-264">Schnittstellen definieren (wie Klassen) einen Satz von Eigenschaften, Methoden und Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="aac98-264">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="aac98-265">Im Gegensatz zu Klassen jedoch bieten Schnittstellen keine Implementierung.</span><span class="sxs-lookup"><span data-stu-id="aac98-265">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="aac98-266">Sie werden durch Klassen implementiert und als von Klassen unabhängige Entitäten definiert.</span><span class="sxs-lookup"><span data-stu-id="aac98-266">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="aac98-267">Eine Schnittstelle stellt insofern einen Vertrag dar, dass eine Klasse, die eine Schnittstelle implementiert, jeden Aspekt dieser Schnittstelle gemäß seiner Definition implementieren muss.</span><span class="sxs-lookup"><span data-stu-id="aac98-267">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="aac98-268">So definieren Sie eine Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aac98-268">To define an interface:</span></span>

```vb
Public Interface ISampleInterface
    Sub DoSomething()
End Interface
```

<span data-ttu-id="aac98-269">So implementieren Sie eine Schnittstelle in einer Klasse</span><span class="sxs-lookup"><span data-stu-id="aac98-269">To implement an interface in a class:</span></span>

```vb
Class SampleClass
    Implements ISampleInterface
    Sub DoSomething
        ' Method implementation.
    End Sub
End Class
```

<span data-ttu-id="aac98-270">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="aac98-270">For more information, see:</span></span>

- [<span data-ttu-id="aac98-271">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="aac98-271">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [<span data-ttu-id="aac98-272">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aac98-272">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="aac98-273">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aac98-273">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)

## <a name="generics"></a><span data-ttu-id="aac98-274">Generika</span><span class="sxs-lookup"><span data-stu-id="aac98-274">Generics</span></span>

<span data-ttu-id="aac98-275">Klassen, Strukturen, Schnittstellen und Methoden in .net können *Typparameter* enthalten, die Typen von Objekten definieren, die Sie speichern oder verwenden können.</span><span class="sxs-lookup"><span data-stu-id="aac98-275">Classes, structures, interfaces and methods in .NET can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="aac98-276">Das einfachste Beispiel für Generics ist eine Auflistung, in der Sie den Typ von Objekten angeben können, die in einer Auflistung gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="aac98-276">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="aac98-277">So definieren Sie eine generische Klasse</span><span class="sxs-lookup"><span data-stu-id="aac98-277">To define a generic class:</span></span>

```vb
Class SampleGeneric(Of T)
    Public Field As T
End Class
```

<span data-ttu-id="aac98-278">So erstellen Sie eine Instanz einer generischen Klasse</span><span class="sxs-lookup"><span data-stu-id="aac98-278">To create an instance of a generic class:</span></span>

```vb
Dim sampleObject As New SampleGeneric(Of String)
sampleObject.Field = "Sample string"
```

<span data-ttu-id="aac98-279">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="aac98-279">For more information, see:</span></span>

- [<span data-ttu-id="aac98-280">Generics</span><span class="sxs-lookup"><span data-stu-id="aac98-280">Generics</span></span>](../../../standard/generics/index.md)
- [<span data-ttu-id="aac98-281">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="aac98-281">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)

## <a name="delegates"></a><span data-ttu-id="aac98-282">Delegaten</span><span class="sxs-lookup"><span data-stu-id="aac98-282">Delegates</span></span>

 <span data-ttu-id="aac98-283">Ein *Delegat* ist ein Typ, der eine Methodensignatur definiert. Er kann einen Verweis auf jede Methode bereitstellen, die über eine kompatible Signatur verfügt.</span><span class="sxs-lookup"><span data-stu-id="aac98-283">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="aac98-284">Sie können die Methode über den Delegaten aufrufen.</span><span class="sxs-lookup"><span data-stu-id="aac98-284">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="aac98-285">Delegaten werden verwendet, um Methoden als Argumente an anderen Methoden zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="aac98-285">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="aac98-286">Ereignishandler sind nichts weiter als Methoden, die durch Delegaten aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="aac98-286">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="aac98-287">Weitere Informationen zur Ereignisbehandlung mit Delegaten finden Sie unter [Ereignisse](../../../standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="aac98-287">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="aac98-288">So erstellen Sie einen Delegaten</span><span class="sxs-lookup"><span data-stu-id="aac98-288">To create a delegate:</span></span>

```vb
Delegate Sub SampleDelegate(ByVal str As String)
```

<span data-ttu-id="aac98-289">So erstellen Sie einen Verweis auf eine Methode, die der vom Delegaten angegebenen Signatur entspricht:</span><span class="sxs-lookup"><span data-stu-id="aac98-289">To create a reference to a method that matches the signature specified by the delegate:</span></span>

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

<span data-ttu-id="aac98-290">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="aac98-290">For more information, see:</span></span>

- [<span data-ttu-id="aac98-291">Delegaten</span><span class="sxs-lookup"><span data-stu-id="aac98-291">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="aac98-292">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aac98-292">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="aac98-293">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="aac98-293">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)

## <a name="see-also"></a><span data-ttu-id="aac98-294">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aac98-294">See also</span></span>

- [<span data-ttu-id="aac98-295">Visual Basic-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="aac98-295">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
