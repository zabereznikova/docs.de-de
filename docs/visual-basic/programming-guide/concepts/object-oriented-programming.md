---
title: Objektorientierte Programmierung (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
ms.assetid: 49794de4-64c3-473c-b8ed-fe98835df69c
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d5491b3bd5a25908194d02063f688a319509bb77
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="object-oriented-programming-visual-basic"></a><span data-ttu-id="995fc-102">Objektorientierte Programmierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="995fc-102">Object-Oriented Programming (Visual Basic)</span></span>
<span data-ttu-id="995fc-103">Visual Basic bietet vollständige Unterstützung für objektorientierte Programmierung einschließlich Kapselung, Vererbung und Polymorphie.</span><span class="sxs-lookup"><span data-stu-id="995fc-103">Visual Basic provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>  
  
 <span data-ttu-id="995fc-104">*Kapselung* bedeutet, dass eine Gruppe verwandter Eigenschaften, Methoden und anderen Member als eine Einheit bzw. ein Objekt behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="995fc-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>  
  
 <span data-ttu-id="995fc-105">*Vererbung* beschreibt die Fähigkeit, neue Klassen basierend auf einer vorhandenen Klasse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="995fc-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>  
  
 <span data-ttu-id="995fc-106">*Polymorphismus* bedeutet, dass Sie mehrere Klassen untereinander austauschen können, obwohl jede Klasse dieselben Eigenschaften oder Methoden auf unterschiedliche Weise implementiert.</span><span class="sxs-lookup"><span data-stu-id="995fc-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>  
  
 <span data-ttu-id="995fc-107">In diesem Abschnitt werden die folgenden Konzepte beschrieben:</span><span class="sxs-lookup"><span data-stu-id="995fc-107">This section describes the following concepts:</span></span>  
  
-   [<span data-ttu-id="995fc-108">Klassen und Objekten</span><span class="sxs-lookup"><span data-stu-id="995fc-108">Classes and Objects</span></span>](#Classes)  
  
    -   [<span data-ttu-id="995fc-109">Klassenmember</span><span class="sxs-lookup"><span data-stu-id="995fc-109">Class Members</span></span>](#Members)  
  
         [<span data-ttu-id="995fc-110">Eigenschaften und Felder</span><span class="sxs-lookup"><span data-stu-id="995fc-110">Properties and Fields</span></span>](#Properties)  
  
         [<span data-ttu-id="995fc-111">Methoden</span><span class="sxs-lookup"><span data-stu-id="995fc-111">Methods</span></span>](#Methods)  
  
         [<span data-ttu-id="995fc-112">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="995fc-112">Constructors</span></span>](#Constructors)  
  
         [<span data-ttu-id="995fc-113">Destruktoren</span><span class="sxs-lookup"><span data-stu-id="995fc-113">Destructors</span></span>](#Destructors)  
  
         [<span data-ttu-id="995fc-114">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="995fc-114">Events</span></span>](#Events)  
  
         [<span data-ttu-id="995fc-115">Geschachtelte Klassen</span><span class="sxs-lookup"><span data-stu-id="995fc-115">Nested Classes</span></span>](#NestedClasses)  
  
    -   [<span data-ttu-id="995fc-116">Zugriffsmodifizierer und Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="995fc-116">Access Modifiers and Access Levels</span></span>](#AccessModifiers)  
  
    -   [<span data-ttu-id="995fc-117">Instanziieren von Klassen</span><span class="sxs-lookup"><span data-stu-id="995fc-117">Instantiating Classes</span></span>](#InstantiatingClasses)  
  
    -   [<span data-ttu-id="995fc-118">Freigegebene Klassen und Member</span><span class="sxs-lookup"><span data-stu-id="995fc-118">Shared Classes and Members</span></span>](#Static)  
  
    -   [<span data-ttu-id="995fc-119">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="995fc-119">Anonymous Types</span></span>](#AnonymousTypes)  
  
-   [<span data-ttu-id="995fc-120">Vererbung</span><span class="sxs-lookup"><span data-stu-id="995fc-120">Inheritance</span></span>](#Inheritance)  
  
    -   [<span data-ttu-id="995fc-121">Überschreiben von Membern</span><span class="sxs-lookup"><span data-stu-id="995fc-121">Overriding Members</span></span>](#Overriding)  
  
-   [<span data-ttu-id="995fc-122">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="995fc-122">Interfaces</span></span>](#Interfaces)  
  
-   [<span data-ttu-id="995fc-123">Generika</span><span class="sxs-lookup"><span data-stu-id="995fc-123">Generics</span></span>](#Generics)  
  
-   [<span data-ttu-id="995fc-124">Delegaten</span><span class="sxs-lookup"><span data-stu-id="995fc-124">Delegates</span></span>](#Delegates)  
  
##  <span data-ttu-id="995fc-125"><a name="Classes"></a>Klassen und Objekten</span><span class="sxs-lookup"><span data-stu-id="995fc-125"><a name="Classes"></a> Classes and Objects</span></span>  
 <span data-ttu-id="995fc-126">Die Begriffe *Klasse* und *Objekt* werden manchmal synonym verwendet, jedoch in der Tat Klassen beschreiben die *Typ* von Objekten, während Objekte verwendbare *Instanzen* Klassen.</span><span class="sxs-lookup"><span data-stu-id="995fc-126">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="995fc-127">Daher wird der Vorgang der Erstellung eines Objekts aufgerufen *Instanziierung*.</span><span class="sxs-lookup"><span data-stu-id="995fc-127">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="995fc-128">Um auf den Vergleich mit Bauplänen zurückzukommen: Eine Klasse ist ein Bauplan, und ein Objekt ist ein anhand dieses Bauplans errichtetes Gebäude.</span><span class="sxs-lookup"><span data-stu-id="995fc-128">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>  
  
 <span data-ttu-id="995fc-129">So definieren Sie eine Klasse</span><span class="sxs-lookup"><span data-stu-id="995fc-129">To define a class:</span></span>  
  
```vb  
Class SampleClass  
End Class  
```  
  
 <span data-ttu-id="995fc-130">Visual Basic bietet auch eine light-Version von Klassen mit den Namen *Strukturen* , die sind nützlich, wenn müssen Sie ein großes Array von Objekten erstellen und führen nicht zu viel Arbeitsspeicher belegen soll.</span><span class="sxs-lookup"><span data-stu-id="995fc-130">Visual Basic also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>  
  
 <span data-ttu-id="995fc-131">So definieren Sie eine Struktur</span><span class="sxs-lookup"><span data-stu-id="995fc-131">To define a structure:</span></span>  
  
```vb  
Structure SampleStructure  
End Structure  
```  
  
 <span data-ttu-id="995fc-132">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="995fc-132">For more information, see:</span></span>  
  
-   [<span data-ttu-id="995fc-133">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="995fc-133">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
-   [<span data-ttu-id="995fc-134">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="995fc-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
###  <span data-ttu-id="995fc-135"><a name="Members"></a>Klassenmember</span><span class="sxs-lookup"><span data-stu-id="995fc-135"><a name="Members"></a> Class Members</span></span>  
 <span data-ttu-id="995fc-136">Jede Klasse können unterschiedliche *-Klassenmember* diese enthalten Eigenschaften, die Klassendaten beschreiben, Methoden, die Klassenverhalten definieren, sowie Ereignisse, die Kommunikation zwischen verschiedenen Klassen und Objekten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="995fc-136">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>  
  
####  <span data-ttu-id="995fc-137"><a name="Properties"></a>Eigenschaften und Felder</span><span class="sxs-lookup"><span data-stu-id="995fc-137"><a name="Properties"></a> Properties and Fields</span></span>  
 <span data-ttu-id="995fc-138">Felder und Eigenschaften stellen die in einem Objekt enthaltenen Informationen dar.</span><span class="sxs-lookup"><span data-stu-id="995fc-138">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="995fc-139">Felder sind wie Variablen, sie können direkt gelesen oder festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="995fc-139">Fields are like variables because they can be read or set directly.</span></span>  
  
 <span data-ttu-id="995fc-140">So definieren Sie ein Feld</span><span class="sxs-lookup"><span data-stu-id="995fc-140">To define a field:</span></span>  
  
```vb  
Class SampleClass  
    Public SampleField As String  
End Class  
```  
  
 <span data-ttu-id="995fc-141">Eigenschaften verfügen über Get- und Set-Prozeduren, die eine bessere Kontrolle über das Festlegen oder Abrufen von Werten ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="995fc-141">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>  
  
 <span data-ttu-id="995fc-142">Visual Basic können Sie erstellen, um ein privates Feld für das Speichern des Eigenschaftswerts oder so genannte automatisch implementierte Eigenschaften verwenden, die dieses Feld automatisch im Hintergrund erstellen und die grundlegende Logik für die Eigenschaftenprozeduren bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="995fc-142">Visual Basic allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>  
  
 <span data-ttu-id="995fc-143">So definieren Sie eine automatisch implementierte Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="995fc-143">To define an auto-implemented property:</span></span>  
  
```vb  
Class SampleClass  
    Public Property SampleProperty as String  
End Class  
```  
  
 <span data-ttu-id="995fc-144">Verwenden Sie den folgenden Code, wenn Sie zusätzliche Lese- und Schreibvorgänge für den Eigenschaftswert ausführen müssen, um ein Feld zum Speichern des Eigenschaftswerts zu definieren und die grundlegende Logik zum Speichern und Abrufen bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="995fc-144">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>  
  
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
  
 <span data-ttu-id="995fc-145">Die meisten Eigenschaften verfügen über Methoden oder Prozeduren zum Festlegen und Abrufen des Eigenschaftswerts.</span><span class="sxs-lookup"><span data-stu-id="995fc-145">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="995fc-146">Sie können jedoch schreib- oder lesegeschützte Eigenschaften erstellen, um zu verhindern, dass die Eigenschaften gelesen oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="995fc-146">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="995fc-147">In Visual Basic können Sie das `ReadOnly`-Schlüsselwort und das `WriteOnly`-Schlüsselwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="995fc-147">In Visual Basic you can use `ReadOnly` and `WriteOnly` keywords.</span></span> <span data-ttu-id="995fc-148">Allerdings können nicht automatisch implementierte Eigenschaften schreibgeschützt oder lesegeschützt sein.</span><span class="sxs-lookup"><span data-stu-id="995fc-148">However, auto-implemented properties cannot be read-only or write-only.</span></span>  
  
 <span data-ttu-id="995fc-149">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="995fc-149">For more information, see:</span></span>  
  
-   [<span data-ttu-id="995fc-150">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="995fc-150">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [<span data-ttu-id="995fc-151">Get-Anweisung</span><span class="sxs-lookup"><span data-stu-id="995fc-151">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
  
-   [<span data-ttu-id="995fc-152">Set-Anweisung</span><span class="sxs-lookup"><span data-stu-id="995fc-152">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)  
  
-   [<span data-ttu-id="995fc-153">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="995fc-153">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)  
  
-   [<span data-ttu-id="995fc-154">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="995fc-154">WriteOnly</span></span>](../../../visual-basic/language-reference/modifiers/writeonly.md)  
  
####  <span data-ttu-id="995fc-155"><a name="Methods"></a>Methoden</span><span class="sxs-lookup"><span data-stu-id="995fc-155"><a name="Methods"></a> Methods</span></span>  
 <span data-ttu-id="995fc-156">Ein *Methode* ist eine Aktion, die ein Objekt ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="995fc-156">A *method* is an action that an object can perform.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="995fc-157">In Visual Basic gibt es zwei Möglichkeiten, eine Methode zu erstellen: Wenn die Methode keinen Wert zurückgibt, wird die `Sub`-Anweisung verwendet; andernfalls wird die `Function`-Anweisung verwendet.</span><span class="sxs-lookup"><span data-stu-id="995fc-157">In Visual Basic, there are two ways to create a method: the `Sub` statement is used if the method does not return a value; the `Function` statement is used if a method returns a value.</span></span>  
  
 <span data-ttu-id="995fc-158">So definieren Sie eine Methode einer Klasse:</span><span class="sxs-lookup"><span data-stu-id="995fc-158">To define a method of a class:</span></span>  
  
```vb  
Class SampleClass  
    Public Function SampleFunc(ByVal SampleParam As String)  
        ' Add code here  
    End Function  
End Class  
```  
  
 <span data-ttu-id="995fc-159">Eine Klasse kann mehrere Implementierungen aufweisen oder *Überladungen*, der die gleiche Methode, die die Anzahl der Parameter oder Parametertypen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="995fc-159">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>  
  
 <span data-ttu-id="995fc-160">So überladen Sie eine Methode</span><span class="sxs-lookup"><span data-stu-id="995fc-160">To overload a method:</span></span>  
  
```vb  
Overloads Sub Display(ByVal theChar As Char)  
    ' Add code that displays Char data.  
End Sub  
Overloads Sub Display(ByVal theInteger As Integer)  
    ' Add code that displays Integer data.  
End Sub  
```  
  
 <span data-ttu-id="995fc-161">In den meisten Fällen deklarieren Sie eine Methode innerhalb einer Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="995fc-161">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="995fc-162">Visual Basic unterstützt jedoch auch *Erweiterungsmethoden* , mit denen Sie einer vorhandenen Klasse außerhalb der eigentlichen Klassendefinition der Klasse Methoden hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="995fc-162">However, Visual Basic also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>  
  
 <span data-ttu-id="995fc-163">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="995fc-163">For more information, see:</span></span>  
  
-   [<span data-ttu-id="995fc-164">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="995fc-164">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="995fc-165">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="995fc-165">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
-   [<span data-ttu-id="995fc-166">Overloads</span><span class="sxs-lookup"><span data-stu-id="995fc-166">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
-   [<span data-ttu-id="995fc-167">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="995fc-167">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
  
####  <span data-ttu-id="995fc-168"><a name="Constructors"></a>Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="995fc-168"><a name="Constructors"></a> Constructors</span></span>  
 <span data-ttu-id="995fc-169">Konstruktoren sind Klassenmethoden, die automatisch ausgeführt werden, wenn ein Objekt eines bestimmten Typs erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="995fc-169">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="995fc-170">Konstruktoren initialisieren normalerweise die Datenmember des neuen Objekts.</span><span class="sxs-lookup"><span data-stu-id="995fc-170">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="995fc-171">Konstruktoren können nur einmal während der Erstellung der Klasse ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="995fc-171">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="995fc-172">Weiterhin wird der Code im Konstruktor immer vor jedem anderen Code in einer Klasse ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="995fc-172">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="995fc-173">Sie können jedoch mehrere Konstruktorüberladungen auf die gleiche Weise wie für jede andere Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="995fc-173">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>  
  
 <span data-ttu-id="995fc-174">So definieren Sie einen Konstruktor für eine Klasse:</span><span class="sxs-lookup"><span data-stu-id="995fc-174">To define a constructor for a class:</span></span>  
  
```vb  
Class SampleClass  
    Sub New(ByVal s As String)  
        // Add code here.  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="995fc-175">Weitere Informationen finden Sie unter: [Objektlebensdauer: wie Objekte erstellen und zerstören sind](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="995fc-175">For more information, see: [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
####  <span data-ttu-id="995fc-176"><a name="Destructors"></a>Destruktoren</span><span class="sxs-lookup"><span data-stu-id="995fc-176"><a name="Destructors"></a> Destructors</span></span>  
 <span data-ttu-id="995fc-177">Destruktoren werden zur Zerstörung von Klasseninstanzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="995fc-177">Destructors are used to destruct instances of classes.</span></span> <span data-ttu-id="995fc-178">In .NET Framework verwaltet die Garbage Collection die Speicherbelegung automatisch und gibt Arbeitsspeicher für die verwalteten Objekte in der Anwendung frei.</span><span class="sxs-lookup"><span data-stu-id="995fc-178">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="995fc-179">Möglicherweise sind jedoch noch Destruktoren erforderlich, um alle nicht verwalteten Ressourcen zu bereinigen, die von der Anwendung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="995fc-179">However, you may still need destructors to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="995fc-180">Es kann nur einen Destruktor für eine Klasse geben.</span><span class="sxs-lookup"><span data-stu-id="995fc-180">There can be only one destructor for a class.</span></span>  
  
 <span data-ttu-id="995fc-181">Weitere Informationen zu Destruktoren und der Garbagecollection in .NET Framework finden Sie unter [Garbage Collection](../../../standard/garbagecollection/index.md).</span><span class="sxs-lookup"><span data-stu-id="995fc-181">For more information about destructors and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbagecollection/index.md).</span></span>  
  
####  <span data-ttu-id="995fc-182"><a name="Events"></a>Ereignisse</span><span class="sxs-lookup"><span data-stu-id="995fc-182"><a name="Events"></a> Events</span></span>  
 <span data-ttu-id="995fc-183">Ereignisse aktivieren eine Klasse oder ein Objekt, um Informationen über Aktionen von Interesse an andere Klassen oder Objekte zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="995fc-183">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="995fc-184">Die Klasse, die das Ereignis sendet (oder auslöst) wird aufgerufen, die *Publisher* und die Klassen, die das Ereignis empfangen (oder behandeln) aufgerufen werden *Abonnenten*.</span><span class="sxs-lookup"><span data-stu-id="995fc-184">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="995fc-185">Weitere Informationen zu Ereignissen, wie Sie ihrer Auslösung und Behandlung finden Sie unter [Ereignisse](http://msdn.microsoft.com/library/b6f65241-e0ad-4590-a99f-200ce741bb1f).</span><span class="sxs-lookup"><span data-stu-id="995fc-185">For more information about events, how they are raised and handled, see [Events](http://msdn.microsoft.com/library/b6f65241-e0ad-4590-a99f-200ce741bb1f).</span></span>  
  
-   <span data-ttu-id="995fc-186">Um Ereignisse zu deklarieren, verwenden Sie die [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="995fc-186">To declare events, use the [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
-   <span data-ttu-id="995fc-187">Um Ereignisse auszulösen, verwenden Sie die [RaiseEvent-Anweisung](../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span><span class="sxs-lookup"><span data-stu-id="995fc-187">To raise events, use the [RaiseEvent Statement](../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span></span>  
  
-   <span data-ttu-id="995fc-188">Um Ereignishandler per Deklaration festzulegen, verwenden Sie die [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md) Anweisung und die [behandelt](../../../visual-basic/language-reference/statements/handles-clause.md) Klausel.</span><span class="sxs-lookup"><span data-stu-id="995fc-188">To specify event handlers using a declarative way, use the [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md) statement and the [Handles](../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span>  
  
-   <span data-ttu-id="995fc-189">Um können dynamisch hinzufügen, entfernen und ändern den Ereignishandler mit einem Ereignis verknüpft ist, verwenden Sie die [AddHandler-Anweisung](../../../visual-basic/language-reference/statements/addhandler-statement.md) und [RemoveHandler-Anweisung](../../../visual-basic/language-reference/statements/removehandler-statement.md) zusammen mit den [AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="995fc-189">To be able to dynamically add, remove, and change the event handler associated with an event, use the [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md) and [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) together with the [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md).</span></span>  
  
####  <span data-ttu-id="995fc-190"><a name="NestedClasses"></a>Geschachtelte Klassen</span><span class="sxs-lookup"><span data-stu-id="995fc-190"><a name="NestedClasses"></a> Nested Classes</span></span>  
 <span data-ttu-id="995fc-191">Eine Klasse, die in einer anderen Klasse definiert heißt *geschachtelten*.</span><span class="sxs-lookup"><span data-stu-id="995fc-191">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="995fc-192">Standardmäßig ist die geschachtelte Klasse privat.</span><span class="sxs-lookup"><span data-stu-id="995fc-192">By default, the nested class is private.</span></span>  
  
```vb  
Class Container  
    Class Nested  
    ' Add code here.  
    End Class  
End Class  
```  
  
 <span data-ttu-id="995fc-193">Um eine Instanz der geschachtelten Klasse zu erstellen, verwenden Sie den Namen der Containerklasse und geben einen Punkt sowie anschließend den Namen der geschachtelten Klasse ein:</span><span class="sxs-lookup"><span data-stu-id="995fc-193">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>  
  
```vb  
Dim nestedInstance As Container.Nested = New Container.Nested()  
```  
  
###  <span data-ttu-id="995fc-194"><a name="AccessModifiers"></a>Zugriffsmodifizierer und Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="995fc-194"><a name="AccessModifiers"></a> Access Modifiers and Access Levels</span></span>  
 <span data-ttu-id="995fc-195">Alle Klassen und Klassenmember können angeben, welche Zugriffsebene sie für andere Klassen bereitstellen, mit *Zugriffsmodifizierer*.</span><span class="sxs-lookup"><span data-stu-id="995fc-195">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>  
  
 <span data-ttu-id="995fc-196">Die folgenden Zugriffsmodifizierer sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="995fc-196">The following access modifiers are available:</span></span>  
  
|<span data-ttu-id="995fc-197">Visual Basic-Modifizierer</span><span class="sxs-lookup"><span data-stu-id="995fc-197">Visual Basic Modifier</span></span>|<span data-ttu-id="995fc-198">Definition</span><span class="sxs-lookup"><span data-stu-id="995fc-198">Definition</span></span>|  
|---------------------------|----------------|  
|[<span data-ttu-id="995fc-199">Public</span><span class="sxs-lookup"><span data-stu-id="995fc-199">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)|<span data-ttu-id="995fc-200">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder einer anderen Assembly, die darauf verweist, zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="995fc-200">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|  
|[<span data-ttu-id="995fc-201">Private</span><span class="sxs-lookup"><span data-stu-id="995fc-201">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)|<span data-ttu-id="995fc-202">Auf den Typ oder Member kann nur von Code in der gleichen Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="995fc-202">The type or member can only be accessed by code in the same class.</span></span>|  
|[<span data-ttu-id="995fc-203">Protected</span><span class="sxs-lookup"><span data-stu-id="995fc-203">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)|<span data-ttu-id="995fc-204">Auf den Typ oder Member kann nur von Code in der gleichen Klasse oder in einer abgeleiteten Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="995fc-204">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|  
|[<span data-ttu-id="995fc-205">Friend</span><span class="sxs-lookup"><span data-stu-id="995fc-205">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)|<span data-ttu-id="995fc-206">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly zugegriffen werden, jedoch nicht von Code in einer anderen Assembly.</span><span class="sxs-lookup"><span data-stu-id="995fc-206">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|  
|`Protected Friend`|<span data-ttu-id="995fc-207">Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder von jeder abgeleiteten Klasse in einer anderen Assembly zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="995fc-207">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|  
  
 <span data-ttu-id="995fc-208">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="995fc-208">For more information, see [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
###  <span data-ttu-id="995fc-209"><a name="InstantiatingClasses"></a>Instanziieren von Klassen</span><span class="sxs-lookup"><span data-stu-id="995fc-209"><a name="InstantiatingClasses"></a> Instantiating Classes</span></span>  
 <span data-ttu-id="995fc-210">Um ein Objekt zu erstellen, müssen Sie eine Klasse instanziieren oder eine Klasseninstanz erstellen.</span><span class="sxs-lookup"><span data-stu-id="995fc-210">To create an object, you need to instantiate a class, or create a class instance.</span></span>  
  
```vb  
Dim sampleObject as New SampleClass()  
```  
  
 <span data-ttu-id="995fc-211">Nachdem Sie eine Klasse instanziiert haben, können Sie den Eigenschaften und Feldern der Instanz Werte zuweisen und Klassenmethoden aufrufen.</span><span class="sxs-lookup"><span data-stu-id="995fc-211">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>  
  
```vb  
' Set a property value.  
sampleObject.SampleProperty = "Sample String"  
' Call a method.  
sampleObject.SampleMethod()  
```  
  
 <span data-ttu-id="995fc-212">Verwenden Sie Objektinitialisierer, um Eigenschaften im Rahmen des Klasseninstanziierungsprozesses Werte zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="995fc-212">To assign values to properties during the class instantiation process, use object initializers:</span></span>  
  
```vb  
Dim sampleObject = New SampleClass With   
    {.FirstProperty = "A", .SecondProperty = "B"}  
```  
  
 <span data-ttu-id="995fc-213">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="995fc-213">For more information, see:</span></span>  
  
-   [<span data-ttu-id="995fc-214">New-Operator</span><span class="sxs-lookup"><span data-stu-id="995fc-214">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)  
  
-   [<span data-ttu-id="995fc-215">Objektinitialisierer: Benannte und anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="995fc-215">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
  
###  <span data-ttu-id="995fc-216"><a name="Static"></a>Freigegebene Klassen und Member</span><span class="sxs-lookup"><span data-stu-id="995fc-216"><a name="Static"></a> Shared Classes and Members</span></span>  
 <span data-ttu-id="995fc-217">Ein freigegebener Member der Klasse ist eine Eigenschaft, eine Prozedur oder ein Feld, das von allen Instanzen einer Klasse gemeinsam verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="995fc-217">A shared member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>  
  
 <span data-ttu-id="995fc-218">So definieren Sie einen freigegebenen Member:</span><span class="sxs-lookup"><span data-stu-id="995fc-218">To define a shared member:</span></span>  
  
```vb  
Class SampleClass  
    Public Shared SampleString As String = "Sample String"  
End Class  
```  
  
 <span data-ttu-id="995fc-219">Verwenden Sie den Namen der Klasse für den Zugriff auf die freigegebenen Member ohne ein Objekt dieser Klasse zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="995fc-219">To access the shared member, use the name of the class without creating an object of this class:</span></span>  
  
```vb  
MsgBox(SampleClass.SampleString)  
```  
  
 <span data-ttu-id="995fc-220">Freigegebene Module in Visual Basic nur Member freigegeben und können nicht instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="995fc-220">Shared modules in Visual Basic have shared members only and cannot be instantiated.</span></span> <span data-ttu-id="995fc-221">Freigegebene Member können nicht auch nicht freigegebene Eigenschaften, Felder oder Methoden zugreifen.</span><span class="sxs-lookup"><span data-stu-id="995fc-221">Shared members also cannot access non-shared properties, fields or methods</span></span>  
  
 <span data-ttu-id="995fc-222">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="995fc-222">For more information, see:</span></span>  
  
-   [<span data-ttu-id="995fc-223">Shared</span><span class="sxs-lookup"><span data-stu-id="995fc-223">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)  
  
-   [<span data-ttu-id="995fc-224">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="995fc-224">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
###  <span data-ttu-id="995fc-225"><a name="AnonymousTypes"></a>Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="995fc-225"><a name="AnonymousTypes"></a> Anonymous Types</span></span>  
 <span data-ttu-id="995fc-226">Mit anonymen Typen können Objekte erstellt werden, ohne eine Klassendefinition für den Datentyp zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="995fc-226">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="995fc-227">Stattdessen erzeugt der Compiler eine Klasse.</span><span class="sxs-lookup"><span data-stu-id="995fc-227">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="995fc-228">Die Klasse hat keinen verwendbaren Namen und enthält die von Ihnen in der Deklaration des Objekts angegebenen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="995fc-228">The class has no usable name and contains the properties you specify in declaring the object.</span></span>  
  
 <span data-ttu-id="995fc-229">So erstellen Sie eine Instanz eines anonymen Typs</span><span class="sxs-lookup"><span data-stu-id="995fc-229">To create an instance of an anonymous type:</span></span>  
  
```vb  
' sampleObject is an instance of a simple anonymous type.  
Dim sampleObject =   
    New With {Key .FirstProperty = "A", .SecondProperty = "B"}  
```  
  
 <span data-ttu-id="995fc-230">Weitere Informationen finden Sie unter: [anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="995fc-230">For more information, see: [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
##  <span data-ttu-id="995fc-231"><a name="Inheritance"></a>Vererbung</span><span class="sxs-lookup"><span data-stu-id="995fc-231"><a name="Inheritance"></a> Inheritance</span></span>  
 <span data-ttu-id="995fc-232">Vererbung ermöglicht die Erstellung neuer Klassen, die in anderen Klassen definiertes Verhalten wieder verwenden, erweitern und ändern.</span><span class="sxs-lookup"><span data-stu-id="995fc-232">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="995fc-233">Wird aufgerufen, die Klasse, deren Member vererbt werden, der *Basisklasse*, und die Klasse, die diese Member erbt heißt der *abgeleitete Klasse*.</span><span class="sxs-lookup"><span data-stu-id="995fc-233">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="995fc-234">Alle Klassen in Visual Basic erben jedoch implizit von der <xref:System.Object>-Klasse, die Klassenhierarchie .NET unterstützt und Low-Level-Dienste für alle Klassen bereitstellt.</xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="995fc-234">However, all classes in Visual Basic implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="995fc-235">Visual Basic unterstützt keine mehrfache Vererbung.</span><span class="sxs-lookup"><span data-stu-id="995fc-235">Visual Basic doesn't support multiple inheritance.</span></span> <span data-ttu-id="995fc-236">Sie können also nur eine Basisklasse für eine abgeleitete Klasse angeben.</span><span class="sxs-lookup"><span data-stu-id="995fc-236">That is, you can specify only one base class for a derived class.</span></span>  
  
 <span data-ttu-id="995fc-237">So erben Sie von einer Basisklasse</span><span class="sxs-lookup"><span data-stu-id="995fc-237">To inherit from a base class:</span></span>  
  
```vb  
Class DerivedClass  
    Inherits BaseClass  
End Class  
```  
  
 <span data-ttu-id="995fc-238">Standardmäßig können alle Klassen geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="995fc-238">By default all classes can be inherited.</span></span> <span data-ttu-id="995fc-239">Sie können jedoch angeben, dass eine Klasse nicht als Basisklasse verwendet werden darf, oder eine Klasse erstellen, die nur als Basisklasse verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="995fc-239">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>  
  
 <span data-ttu-id="995fc-240">So geben Sie an, dass eine Klasse nicht als Basisklasse verwendet werden kann</span><span class="sxs-lookup"><span data-stu-id="995fc-240">To specify that a class cannot be used as a base class:</span></span>  
  
```vb  
NotInheritable Class SampleClass  
End Class  
```  
  
 <span data-ttu-id="995fc-241">So geben Sie an, dass eine Klasse nur als Basisklasse verwendet und nicht instanziiert werden kann:</span><span class="sxs-lookup"><span data-stu-id="995fc-241">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>  
  
```vb  
MustInherit Class BaseClass  
End Class  
```  
  
 <span data-ttu-id="995fc-242">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="995fc-242">For more information, see:</span></span>  
  
-   [<span data-ttu-id="995fc-243">Inherits-Anweisung</span><span class="sxs-lookup"><span data-stu-id="995fc-243">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)  
  
-   [<span data-ttu-id="995fc-244">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="995fc-244">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)  
  
-   [<span data-ttu-id="995fc-245">MustInherit</span><span class="sxs-lookup"><span data-stu-id="995fc-245">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)  
  
###  <span data-ttu-id="995fc-246"><a name="Overriding"></a>Überschreiben von Membern</span><span class="sxs-lookup"><span data-stu-id="995fc-246"><a name="Overriding"></a> Overriding Members</span></span>  
 <span data-ttu-id="995fc-247">Standardmäßig erbt eine abgeleitete Klasse alle Member von ihrer Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="995fc-247">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="995fc-248">Wenn Sie das Verhalten des geerbten Members ändern möchten, müssen Sie diesen überschreiben.</span><span class="sxs-lookup"><span data-stu-id="995fc-248">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="995fc-249">Das heißt, Sie können eine neue Implementierung der Methode, der Eigenschaft oder des Ereignisses in der abgeleiteten Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="995fc-249">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>  
  
 <span data-ttu-id="995fc-250">Mit folgenden Modifizierern steuern Sie das Überschreiben von Eigenschaften und Methoden:</span><span class="sxs-lookup"><span data-stu-id="995fc-250">The following modifiers are used to control how properties and methods are overridden:</span></span>  
  
|<span data-ttu-id="995fc-251">Visual Basic-Modifizierer</span><span class="sxs-lookup"><span data-stu-id="995fc-251">Visual Basic Modifier</span></span>|<span data-ttu-id="995fc-252">Definition</span><span class="sxs-lookup"><span data-stu-id="995fc-252">Definition</span></span>|  
|---------------------------|----------------|  
|[<span data-ttu-id="995fc-253">Overridable</span><span class="sxs-lookup"><span data-stu-id="995fc-253">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)|<span data-ttu-id="995fc-254">Ermöglicht das Überschreiben eines Klassenmembers in einer abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="995fc-254">Allows a class member to be overridden in a derived class.</span></span>|  
|[<span data-ttu-id="995fc-255">Overrides</span><span class="sxs-lookup"><span data-stu-id="995fc-255">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)|<span data-ttu-id="995fc-256">Überschreibt einen virtuellen (überschreibbaren) Member, der in der Basisklasse definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="995fc-256">Overrides a virtual (overridable) member defined in the base class.</span></span>|  
|[<span data-ttu-id="995fc-257">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="995fc-257">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)|<span data-ttu-id="995fc-258">Verhindert das Überschreiben eines Members in einer erbenden Klasse.</span><span class="sxs-lookup"><span data-stu-id="995fc-258">Prevents a member from being overridden in an inheriting class.</span></span>|  
|[<span data-ttu-id="995fc-259">MustOverride</span><span class="sxs-lookup"><span data-stu-id="995fc-259">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)|<span data-ttu-id="995fc-260">Erfordert das Überschreiben eines Klassenmembers in der abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="995fc-260">Requires that a class member to be overridden in the derived class.</span></span>|  
|[<span data-ttu-id="995fc-261">Shadows</span><span class="sxs-lookup"><span data-stu-id="995fc-261">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)|<span data-ttu-id="995fc-262">Blendet einen von einer Basisklasse geerbten Member aus.</span><span class="sxs-lookup"><span data-stu-id="995fc-262">Hides a member inherited from a base class</span></span>|  
  
##  <span data-ttu-id="995fc-263"><a name="Interfaces"></a>Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="995fc-263"><a name="Interfaces"></a> Interfaces</span></span>  
 <span data-ttu-id="995fc-264">Schnittstellen definieren (wie Klassen) einen Satz von Eigenschaften, Methoden und Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="995fc-264">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="995fc-265">Im Gegensatz zu Klassen jedoch bieten Schnittstellen keine Implementierung.</span><span class="sxs-lookup"><span data-stu-id="995fc-265">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="995fc-266">Sie werden durch Klassen implementiert und als von Klassen unabhängige Entitäten definiert.</span><span class="sxs-lookup"><span data-stu-id="995fc-266">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="995fc-267">Eine Schnittstelle stellt insofern einen Vertrag dar, dass eine Klasse, die eine Schnittstelle implementiert, jeden Aspekt dieser Schnittstelle gemäß seiner Definition implementieren muss.</span><span class="sxs-lookup"><span data-stu-id="995fc-267">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>  
  
 <span data-ttu-id="995fc-268">So definieren Sie eine Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="995fc-268">To define an interface:</span></span>  
  
```vb  
Public Interface ISampleInterface  
    Sub DoSomething()  
End Interface  
```  
  
 <span data-ttu-id="995fc-269">So implementieren Sie eine Schnittstelle in einer Klasse</span><span class="sxs-lookup"><span data-stu-id="995fc-269">To implement an interface in a class:</span></span>  
  
```vb  
Class SampleClass  
    Implements ISampleInterface  
    Sub DoSomething  
        ' Method implementation.  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="995fc-270">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="995fc-270">For more information, see:</span></span>  
  
-   [<span data-ttu-id="995fc-271">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="995fc-271">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
  
-   [<span data-ttu-id="995fc-272">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="995fc-272">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
-   [<span data-ttu-id="995fc-273">Implements-Anweisung</span><span class="sxs-lookup"><span data-stu-id="995fc-273">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)  
  
##  <span data-ttu-id="995fc-274"><a name="Generics"></a>Generika</span><span class="sxs-lookup"><span data-stu-id="995fc-274"><a name="Generics"></a> Generics</span></span>  
 <span data-ttu-id="995fc-275">Klassen, Strukturen, Schnittstellen und Methoden in .NET Framework gehören *Typparameter* , definieren die Typen von Objekten, die sie speichern oder verwenden können.</span><span class="sxs-lookup"><span data-stu-id="995fc-275">Classes, structures, interfaces and methods in the .NET Framework can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="995fc-276">Das einfachste Beispiel für Generika ist eine Auflistung, in der Sie den Typ von Objekten angeben können, die in einer Auflistung gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="995fc-276">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>  
  
 <span data-ttu-id="995fc-277">So definieren Sie eine generische Klasse</span><span class="sxs-lookup"><span data-stu-id="995fc-277">To define a generic class:</span></span>  
  
```vb  
Class SampleGeneric(Of T)  
    Public Field As T  
End Class  
```  
  
 <span data-ttu-id="995fc-278">So erstellen Sie eine Instanz einer generischen Klasse</span><span class="sxs-lookup"><span data-stu-id="995fc-278">To create an instance of a generic class:</span></span>  
  
```vb  
Dim sampleObject As New SampleGeneric(Of String)  
sampleObject.Field = "Sample string"  
```  
  
 <span data-ttu-id="995fc-279">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="995fc-279">For more information, see:</span></span>  
  
-   [<span data-ttu-id="995fc-280">Generika</span><span class="sxs-lookup"><span data-stu-id="995fc-280">Generics</span></span>](https://msdn.microsoft.com/library/ms172192)  
  
-   [<span data-ttu-id="995fc-281">Generische Typen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="995fc-281">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
  
##  <span data-ttu-id="995fc-282"><a name="Delegates"></a>Delegaten</span><span class="sxs-lookup"><span data-stu-id="995fc-282"><a name="Delegates"></a> Delegates</span></span>  
 <span data-ttu-id="995fc-283">Ein *Delegieren* ist ein Typ, der eine Methodensignatur definiert und kann einen Verweis auf jede Methode mit einer kompatiblen Signatur bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="995fc-283">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="995fc-284">Sie können die Methode über den Delegaten aufrufen.</span><span class="sxs-lookup"><span data-stu-id="995fc-284">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="995fc-285">Delegaten werden verwendet, um Methoden als Argumente an anderen Methoden zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="995fc-285">Delegates are used to pass methods as arguments to other methods.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="995fc-286">Ereignishandler sind nichts weiter als Methoden, die durch Delegaten aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="995fc-286">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="995fc-287">Weitere Informationen zur Ereignisbehandlung mit Delegaten finden Sie unter [Ereignisse](http://msdn.microsoft.com/library/b6f65241-e0ad-4590-a99f-200ce741bb1f).</span><span class="sxs-lookup"><span data-stu-id="995fc-287">For more information about using delegates in event handling, see [Events](http://msdn.microsoft.com/library/b6f65241-e0ad-4590-a99f-200ce741bb1f).</span></span>  
  
 <span data-ttu-id="995fc-288">So erstellen Sie einen Delegaten</span><span class="sxs-lookup"><span data-stu-id="995fc-288">To create a delegate:</span></span>  
  
```vb  
Delegate Sub SampleDelegate(ByVal str As String)  
```  
  
 <span data-ttu-id="995fc-289">So erstellen Sie einen Verweis auf eine Methode, die der vom Delegaten angegebenen Signatur entspricht:</span><span class="sxs-lookup"><span data-stu-id="995fc-289">To create a reference to a method that matches the signature specified by the delegate:</span></span>  
  
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
  
 <span data-ttu-id="995fc-290">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="995fc-290">For more information, see:</span></span>  
  
-   [<span data-ttu-id="995fc-291">Delegaten</span><span class="sxs-lookup"><span data-stu-id="995fc-291">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
  
-   [<span data-ttu-id="995fc-292">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="995fc-292">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
-   [<span data-ttu-id="995fc-293">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="995fc-293">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
  
## <a name="see-also"></a><span data-ttu-id="995fc-294">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="995fc-294">See Also</span></span>  
 [<span data-ttu-id="995fc-295">Visual Basic-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="995fc-295">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
