---
title: "Ausführliche Informationen zum allgemeinen Typsystem"
description: "Ausführliche Informationen zum allgemeinen Typsystem"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: b5482a1d-7bdc-40fe-aa45-10df930ceb5b
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 6be672acc84a76106e25b82574acad16beb4a8ac
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="common-type-system-in-depth"></a><span data-ttu-id="2a94d-104">Ausführliche Informationen zum allgemeinen Typsystem</span><span class="sxs-lookup"><span data-stu-id="2a94d-104">Common type system in depth</span></span>

<span data-ttu-id="2a94d-105">Dieses Thema enthält die folgenden Abschnitte, die das allgemeine Typsystem ausführlich behandeln:</span><span class="sxs-lookup"><span data-stu-id="2a94d-105">This topic contains the following sections that explore the common type system in depth:</span></span>

* [<span data-ttu-id="2a94d-106">Typen in .NET</span><span class="sxs-lookup"><span data-stu-id="2a94d-106">Types in .NET</span></span>](#types-in-net)

* [<span data-ttu-id="2a94d-107">Typdefinitionen</span><span class="sxs-lookup"><span data-stu-id="2a94d-107">Type definitions</span></span>](#type-definitions)

* [<span data-ttu-id="2a94d-108">Typmember</span><span class="sxs-lookup"><span data-stu-id="2a94d-108">Type members</span></span>](#type-members)

* [<span data-ttu-id="2a94d-109">Eigenschaften von Typmembern</span><span class="sxs-lookup"><span data-stu-id="2a94d-109">Characteristics of type members</span></span>](#characteristics-of-type-members)


## <a name="types-in-net"></a><span data-ttu-id="2a94d-110">Typen in .NET</span><span class="sxs-lookup"><span data-stu-id="2a94d-110">Types in .NET</span></span>

<span data-ttu-id="2a94d-111">Alle Typen in .NET sind entweder Werttypen oder Verweistypen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-111">All types in .NET are either value types or reference types.</span></span> 

<span data-ttu-id="2a94d-112">Werttypen sind Datentypen, deren Objekte durch den tatsächlichen Wert des Objekts dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-112">Value types are data types whose objects are represented by the object's actual value.</span></span> <span data-ttu-id="2a94d-113">Wenn einer Variablen eine Instanz eines Werttyps zugewiesen wird, wird dieser Variablen eine neue Kopie des Werts übergeben.</span><span class="sxs-lookup"><span data-stu-id="2a94d-113">If an instance of a value type is assigned to a variable, that variable is given a fresh copy of the value.</span></span>

<span data-ttu-id="2a94d-114">Referenztypen sind Datentypen, deren Objekte durch einen Verweis (ähnlich einem Zeiger) auf den tatsächlichen Wert des Objekts dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-114">Reference types are data types whose objects are represented by a reference (similar to a pointer) to the object's actual value.</span></span> <span data-ttu-id="2a94d-115">Wenn ein Verweistyp einer Variablen zugeordnet wird, verweist (oder zeigt) diese Variable auf den ursprünglichen Wert.</span><span class="sxs-lookup"><span data-stu-id="2a94d-115">If a reference type is assigned to a variable, that variable references (points to) the original value.</span></span> <span data-ttu-id="2a94d-116">Es wird keine Kopie erstellt.</span><span class="sxs-lookup"><span data-stu-id="2a94d-116">No copy is made.</span></span> 

<span data-ttu-id="2a94d-117">Das allgemeine Typsystem in .NET unterstützt die folgenden fünf Typkategorien:</span><span class="sxs-lookup"><span data-stu-id="2a94d-117">The common type system in .NET supports the following five categories of types:</span></span>

* [<span data-ttu-id="2a94d-118">Klassen</span><span class="sxs-lookup"><span data-stu-id="2a94d-118">Classes</span></span>](#classes)

* [<span data-ttu-id="2a94d-119">Strukturen</span><span class="sxs-lookup"><span data-stu-id="2a94d-119">Structures</span></span>](#structures)

* [<span data-ttu-id="2a94d-120">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="2a94d-120">Enumerations</span></span>](#enumerations)

* [<span data-ttu-id="2a94d-121">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2a94d-121">Interfaces</span></span>](#interfaces)

* [<span data-ttu-id="2a94d-122">Delegaten</span><span class="sxs-lookup"><span data-stu-id="2a94d-122">Delegates</span></span>](#delegates)

### <a name="classes"></a><span data-ttu-id="2a94d-123">Klassen</span><span class="sxs-lookup"><span data-stu-id="2a94d-123">Classes</span></span>

<span data-ttu-id="2a94d-124">Eine Klasse ist ein Referenztyp, der direkt von einer anderen Klasse abgeleitet werden kann und der implizit von [System.Object](xref:System.Object) abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="2a94d-124">A class is a reference type that can be derived directly from another class and that is derived implicitly from [System.Object](xref:System.Object).</span></span> <span data-ttu-id="2a94d-125">Die Klasse definiert die Vorgänge, die ein Objekt (d. h. eine Instanz der Klasse) ausführen kann (Methoden, Ereignisse oder Eigenschaften), sowie die Daten, die das Objekt enthält (Felder).</span><span class="sxs-lookup"><span data-stu-id="2a94d-125">The class defines the operations that an object (which is an instance of the class) can perform (methods, events, or properties) and the data that the object contains (fields).</span></span> <span data-ttu-id="2a94d-126">Obwohl eine Klasse im Allgemeinen sowohl Definition als auch Implementierung enthält (im Gegensatz zu Schnittstellen, die z. B. nur eine Definition ohne Implementierung enthalten), kann sie über einen oder mehrere Member ohne Implementierung verfügen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-126">Although a class generally includes both definition and implementation (unlike interfaces, for example, which contain only definition without implementation), it can have one or more members that have no implementation.</span></span>

<span data-ttu-id="2a94d-127">In der folgenden Tabelle werden einige Eigenschaften beschrieben, über die eine Klasse verfügen kann.</span><span class="sxs-lookup"><span data-stu-id="2a94d-127">The following table describes some of the characteristics that a class may have.</span></span> <span data-ttu-id="2a94d-128">Jede für Laufzeitunterstützung ausgelegte Sprache bietet eine Möglichkeit, eines oder mehrere Merkmale für eine Klasse oder einen Klassenmember festzulegen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-128">Each language that supports the runtime provides a way to indicate that a class or class member has one or more of these characteristics.</span></span> <span data-ttu-id="2a94d-129">In einzelnen Programmiersprachen, die .NET als Ziel haben, sind jedoch möglicherweise nicht alle dieser Eigenschaften verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2a94d-129">However, individual programming languages that target .NET may not make all these characteristics available.</span></span>

<span data-ttu-id="2a94d-130">Merkmal</span><span class="sxs-lookup"><span data-stu-id="2a94d-130">Characteristic</span></span> | <span data-ttu-id="2a94d-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a94d-131">Description</span></span>
-------------- | -----------
<span data-ttu-id="2a94d-132">sealed</span><span class="sxs-lookup"><span data-stu-id="2a94d-132">sealed</span></span> | <span data-ttu-id="2a94d-133">Legt fest, dass von diesem Typ keine andere Klasse abgeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2a94d-133">Specifies that another class cannot be derived from this type.</span></span>
<span data-ttu-id="2a94d-134">implements</span><span class="sxs-lookup"><span data-stu-id="2a94d-134">implements</span></span> | <span data-ttu-id="2a94d-135">Gibt an, dass die Klasse eine oder mehrere Schnittstellen verwendet; es werden Implementierungen von Schnittstellenmembern bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="2a94d-135">Indicates that the class uses one or more interfaces by providing implementations of interface members.</span></span>
<span data-ttu-id="2a94d-136">abstract</span><span class="sxs-lookup"><span data-stu-id="2a94d-136">abstract</span></span> | <span data-ttu-id="2a94d-137">Gibt an, dass die Klasse nicht instanziiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="2a94d-137">Indicates that the class cannot be instantiated.</span></span> <span data-ttu-id="2a94d-138">Um die Klasse verwenden zu können, müssen Sie eine andere Klasse davon ableiten.</span><span class="sxs-lookup"><span data-stu-id="2a94d-138">To use it, you must derive another class from it.</span></span>
<span data-ttu-id="2a94d-139">inherits</span><span class="sxs-lookup"><span data-stu-id="2a94d-139">inherits</span></span> | <span data-ttu-id="2a94d-140">Legt fest, dass an jeder Stelle, an der die Basisklasse angegeben ist, Instanzen der Klasse verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="2a94d-140">Indicates that instances of the class can be used anywhere the base class is specified.</span></span> <span data-ttu-id="2a94d-141">Eine abgeleitete Klasse, die von einer Basisklasse erbt, kann die Implementierung jedes öffentlichen Members verwenden, der von der Basisklasse bereitgestellt wird, oder die abgeleitete Klasse kann die Implementierung der öffentlichen Member mit einer eigenen Implementierung überschreiben.</span><span class="sxs-lookup"><span data-stu-id="2a94d-141">A derived class that inherits from a base class can use the implementation of any public members provided by the base class, or the derived class can override the implementation of the public members with its own implementation.</span></span>
<span data-ttu-id="2a94d-142">exported oder not exported</span><span class="sxs-lookup"><span data-stu-id="2a94d-142">exported or not exported</span></span> | <span data-ttu-id="2a94d-143">Gibt an, ob eine Klasse außerhalb der Assembly, in der sie definiert wurde, sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="2a94d-143">Indicates whether a class is visible outside the assembly in which it is defined.</span></span> <span data-ttu-id="2a94d-144">Dieses Merkmal gilt nur für Klassen der obersten Ebene und nicht für geschachtelte Klassen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-144">This characteristic applies only to top-level classes and not to nested classes.</span></span>

> [!NOTE]
> <span data-ttu-id="2a94d-145">Eine Klasse kann auch in einer übergeordneten Klasse oder Struktur geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-145">A class can also be nested in a parent class or structure.</span></span> <span data-ttu-id="2a94d-146">Auch geschachtelte Klassen verfügen über Membermerkmale.</span><span class="sxs-lookup"><span data-stu-id="2a94d-146">Nested classes also have member characteristics.</span></span> <span data-ttu-id="2a94d-147">Weitere Informationen finden Sie unter [Geschachtelte Typen](#nested-types).</span><span class="sxs-lookup"><span data-stu-id="2a94d-147">For more information, see [Nested types](#nested-types).</span></span>

<span data-ttu-id="2a94d-148">Klassenmember, die keine Implementierung haben, sind abstrakte Member.</span><span class="sxs-lookup"><span data-stu-id="2a94d-148">Class members that have no implementation are abstract members.</span></span> <span data-ttu-id="2a94d-149">Eine Klasse mit einem oder mehreren abstrakten Membern ist selbst abstrakt, und von dieser Klasse können keine Instanzen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-149">A class that has one or more abstract members is itself abstract; new instances of it cannot be created.</span></span> <span data-ttu-id="2a94d-150">Bei einigen Sprachen, die für die Laufzeit konzipiert sind, können Klassen selbst dann als abstrakt gekennzeichnet werden, wenn sie keine abstrakten Member haben.</span><span class="sxs-lookup"><span data-stu-id="2a94d-150">Some languages that target the runtime let you mark a class as abstract even if none of its members are abstract.</span></span> <span data-ttu-id="2a94d-151">Sie können eine abstrakte Klasse verwenden, um eine gewisse Basisfunktionalität einzuschließen, die von abgeleiteten Klassen ggf. geerbt bzw. überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="2a94d-151">You can use an abstract class when you want to encapsulate a basic set of functionality that derived classes can inherit or override when appropriate.</span></span> <span data-ttu-id="2a94d-152">Nicht abstrakte Klassen werden als konkrete Klassen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2a94d-152">Classes that are not abstract are referred to as concrete classes.</span></span>

<span data-ttu-id="2a94d-153">Eine Klasse kann eine beliebige Anzahl von Schnittstellen implementieren, sie kann jedoch nur von einer Basisklasse neben [System.Object](xref:System.Object) erben. Hiervon erben alle Klassen implizit.</span><span class="sxs-lookup"><span data-stu-id="2a94d-153">A class can implement any number of interfaces, but it can inherit from only one base class in addition to [System.Object](xref:System.Object), from which all classes inherit implicitly.</span></span> <span data-ttu-id="2a94d-154">Alle Klassen müssen über mindestens einen Konstruktor verfügen, durch den neue Instanzen der Klasse initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-154">All classes must have at least one constructor, which initializes new instances of the class.</span></span> <span data-ttu-id="2a94d-155">Wenn Sie nicht explizit einen Konstruktor definieren, stellen die meisten Compiler automatisch einen Standardkonstruktor (ohne Parameter) bereit.</span><span class="sxs-lookup"><span data-stu-id="2a94d-155">If you do not explicitly define a constructor, most compilers will automatically provide a default (parameterless) constructor.</span></span>

### <a name="structures"></a><span data-ttu-id="2a94d-156">Strukturen</span><span class="sxs-lookup"><span data-stu-id="2a94d-156">Structures</span></span>

<span data-ttu-id="2a94d-157">Eine Struktur ist ein Werttyp, der implizit von [System.ValueType](xref:System.ValueType) abgeleitet ist. Dies ist wiederum von [System.Object](xref:System.Object) abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="2a94d-157">A structure is a value type that derives implicitly from [System.ValueType](xref:System.ValueType), which in turn is derived from [System.Object](xref:System.Object).</span></span> <span data-ttu-id="2a94d-158">Eine Struktur ist hilfreich beim Darstellen von Werten mit geringen Arbeitsspeicheranforderungen und beim Übergeben von Werten über Parameter als Wert an Methoden mit stark typisierten Parametern.</span><span class="sxs-lookup"><span data-stu-id="2a94d-158">A structure is very useful for representing values whose memory requirements are small, and for passing values as by-value parameters to methods that have strongly typed parameters.</span></span> <span data-ttu-id="2a94d-159">In .NET sind alle primitiven Datentypen ([Boolean](xref:System.Boolean), [Byte](xref:System.Byte), [Char](xref:System.Char), [DateTime](xref:System.DateTime), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32) und [UInt64](xref:System.UInt64)) als Strukturen definiert.</span><span class="sxs-lookup"><span data-stu-id="2a94d-159">In .NET, all primitive data types ([Boolean](xref:System.Boolean), [Byte](xref:System.Byte), [Char](xref:System.Char), [DateTime](xref:System.DateTime), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), and [UInt64](xref:System.UInt64)) are defined as structures.</span></span>

<span data-ttu-id="2a94d-160">Wie Klassen definieren Strukturen sowohl Daten (die Felder der Struktur) als auch die Vorgänge, die für diese Daten (die Methoden der Struktur) ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="2a94d-160">Like classes, structures define both data (the fields of the structure) and the operations that can be performed on that data (the methods of the structure).</span></span> <span data-ttu-id="2a94d-161">Dies bedeutet, dass Sie Methoden für Strukturen aufrufen können, einschließlich der für die [System.Object](xref:System.Object)-Klasse und die [System.ValueType](xref:System.ValueType)-Klasse definierten virtuellen Methoden sowie aller Methoden, die für den Werttyp selbst definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-161">This means that you can call methods on structures, including the virtual methods defined on the [System.Object](xref:System.Object) and [System.ValueType](xref:System.ValueType) classes, and any methods defined on the value type itself.</span></span> <span data-ttu-id="2a94d-162">Anders ausgedrückt können Strukturen Felder, Eigenschaften und Ereignisse sowie statische und nicht statische Methoden aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-162">In other words, structures can have fields, properties, and events, as well as static and nonstatic methods.</span></span> <span data-ttu-id="2a94d-163">Sie können Instanzen von Strukturen erstellen, diese als Parameter übergeben, als lokale Variablen speichern oder im Feld eines anderen Werttyps oder Verweistyps speichern.</span><span class="sxs-lookup"><span data-stu-id="2a94d-163">You can create instances of structures, pass them as parameters, store them as local variables, or store them in a field of another value type or reference type.</span></span> <span data-ttu-id="2a94d-164">Strukturen können auch Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="2a94d-164">Structures can also implement interfaces.</span></span>

<span data-ttu-id="2a94d-165">Werttypen unterscheiden sich in mehreren Punkten auch von Klassen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-165">Value types also differ from classes in several respects.</span></span> <span data-ttu-id="2a94d-166">Zunächst können sie nicht direkt von einem Typ erben, obwohl sie implizit von [System.ValueType](xref:System.ValueType) erben.</span><span class="sxs-lookup"><span data-stu-id="2a94d-166">First, although they implicitly inherit from [System.ValueType](xref:System.ValueType), they cannot directly inherit from any type.</span></span> <span data-ttu-id="2a94d-167">Ebenso sind alle Werttypen versiegelt, was bedeutet, dass kein anderer Typ von ihnen abgeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2a94d-167">Similarly, all value types are sealed, which means that no other type can be derived from them.</span></span> <span data-ttu-id="2a94d-168">Außerdem benötigen sie keine Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="2a94d-168">They also do not require constructors.</span></span>

<span data-ttu-id="2a94d-169">Die Common Language Runtime stellt für jeden Werttyp einen entsprechenden geschachtelten Werttyp bereit, der eine Klasse darstellt, die denselben Zustand und dasselbe Verhalten wie der Werttyp aufweist.</span><span class="sxs-lookup"><span data-stu-id="2a94d-169">For each value type, the common language runtime supplies a corresponding boxed type, which is a class that has the same state and behavior as the value type.</span></span> <span data-ttu-id="2a94d-170">Eine Instanz eines Werttyps wird beim Übergeben an eine Methode geschachtelt, die einen Parameter vom Typ [System.Object](xref:System.Object) annimmt.</span><span class="sxs-lookup"><span data-stu-id="2a94d-170">An instance of a value type is boxed when it is passed to a method that accepts a parameter of type [System.Object](xref:System.Object).</span></span> <span data-ttu-id="2a94d-171">Sie wird mittels Unboxing konvertiert (d. h. aus einer Instanz einer Klasse zurück in die Instanz eines Werttyps konvertiert), wenn ein Steuerelement aus einem Methodenaufruf zurückgegeben wird, in dem ein Werttyp als Parameter als Verweis angenommen wird.</span><span class="sxs-lookup"><span data-stu-id="2a94d-171">It is unboxed (that is, converted from an instance of a class back to an instance of a value type) when control returns from a method call that accepts a value type as a by-reference parameter.</span></span> <span data-ttu-id="2a94d-172">In einigen Sprachen muss eine spezielle Syntax verwendet werden, wenn ein mittels Boxing gepackter Typ erforderlich ist; in anderen Sprachen wird der mittels Boxing gepackte Typ bei Bedarf automatisch verwendet.</span><span class="sxs-lookup"><span data-stu-id="2a94d-172">Some languages require that you use special syntax when the boxed type is required; others automatically use the boxed type when it is needed.</span></span> <span data-ttu-id="2a94d-173">Die Definition eines Werttyps schließt sowohl den mittels Boxing gepackten als auch den mittels Unboxing entpackten Typ ein.</span><span class="sxs-lookup"><span data-stu-id="2a94d-173">When you define a value type, you are defining both the boxed and the unboxed type.</span></span>

### <a name="enumerations"></a><span data-ttu-id="2a94d-174">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="2a94d-174">Enumerations</span></span>

<span data-ttu-id="2a94d-175">Eine Enumeration ist ein Werttyp, der direkt von [System.Enum](xref:System.Enum) erbt und alternative Namen für die Werte eines zugrunde liegenden primitiven Typs bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="2a94d-175">An enumeration (enum) is a value type that inherits directly from [System.Enum](xref:System.Enum) and that supplies alternate names for the values of an underlying primitive type.</span></span> <span data-ttu-id="2a94d-176">Ein Enumerationstyp verfügt über einen Namen, einen zugrunde liegenden Typ, bei dem es sich um einen der integrierten Ganzzahltypen mit oder ohne Vorzeichen handeln muss (z.B. [Byte](xref:System.Byte), [Int32](xref:System.Int32) oder [UInt64](xref:System.UInt64)), und einen Satz von Feldern.</span><span class="sxs-lookup"><span data-stu-id="2a94d-176">An enumeration type has a name, an underlying type that must be one of the built-in signed or unsigned integer types (such as [Byte](xref:System.Byte), [Int32](xref:System.Int32), or [UInt64](xref:System.UInt64)), and a set of fields.</span></span> <span data-ttu-id="2a94d-177">Die Felder sind statische Literalfelder, von denen jedes eine Konstante darstellt.</span><span class="sxs-lookup"><span data-stu-id="2a94d-177">The fields are static literal fields, each of which represents a constant.</span></span> <span data-ttu-id="2a94d-178">Derselbe Wert kann auch mehreren Feldern zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-178">The same value can be assigned to multiple fields.</span></span> <span data-ttu-id="2a94d-179">In dieser Situation muss einer der Werte als primärer Enumerationswert für die Reflektion und Zeichenfolgenkonvertierung gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-179">When this occurs, you must mark one of the values as the primary enumeration value for reflection and string conversion.</span></span>

<span data-ttu-id="2a94d-180">Sie können einer Enumeration einen Wert des zugrunde liegenden Typs zuweisen und umgekehrt (für die Laufzeit ist keine Typumwandlung erforderlich).</span><span class="sxs-lookup"><span data-stu-id="2a94d-180">You can assign a value of the underlying type to an enumeration and vice versa (no cast is required by the runtime).</span></span> <span data-ttu-id="2a94d-181">Sie können eine Instanz einer Enumeration erstellen und die Methoden von [System.Enum](xref:System.Enum) sowie alle für den zugrunde liegenden Enumerationstyp definierten Methoden aufrufen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-181">You can create an instance of an enumeration and call the methods of [System.Enum](xref:System.Enum), as well as any methods defined on the enumeration's underlying type.</span></span> <span data-ttu-id="2a94d-182">In einigen Sprachen ist es jedoch möglicherweise nicht zulässig, dass eine Enumeration als Parameter übergeben wird, wenn eine Instanz des zugrunde liegenden Typs erforderlich ist (oder umgekehrt).</span><span class="sxs-lookup"><span data-stu-id="2a94d-182">However, some languages might not let you pass an enumeration as a parameter when an instance of the underlying type is required (or vice versa).</span></span>

<span data-ttu-id="2a94d-183">Für Enumerationen gelten die folgenden zusätzlichen Beschränkungen:</span><span class="sxs-lookup"><span data-stu-id="2a94d-183">The following additional restrictions apply to enumerations:</span></span> 

* <span data-ttu-id="2a94d-184">Sie können keine eigenen Methoden definieren.</span><span class="sxs-lookup"><span data-stu-id="2a94d-184">They cannot define their own methods.</span></span>

* <span data-ttu-id="2a94d-185">Sie können keine Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="2a94d-185">They cannot implement interfaces.</span></span>

* <span data-ttu-id="2a94d-186">Sie können keine Eigenschaften oder Ereignisse definieren.</span><span class="sxs-lookup"><span data-stu-id="2a94d-186">They cannot define properties or events.</span></span>

* <span data-ttu-id="2a94d-187">Sie können nicht generisch sein, es sei denn, sie sind nur deshalb generisch, weil sie in einem generischen Typ geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="2a94d-187">They cannot be generic, unless they are generic only because they are nested within a generic type.</span></span> <span data-ttu-id="2a94d-188">Das bedeutet, dass eine Enumeration nicht über eigene Typparameter verfügen kann.</span><span class="sxs-lookup"><span data-stu-id="2a94d-188">That is, an enumeration cannot have type parameters of its own.</span></span> 

> [!NOTE]
> <span data-ttu-id="2a94d-189">Geschachtelte Typen (z.B. Enumerationen), die mit C# erstellt wurden, enthalten die Typparameter aller einschließenden generischen Typen und sind daher generisch, auch wenn sie über keine eigenen Typparameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-189">Nested types (including enumerations) created with C# include the type parameters of all enclosing generic types, and are therefore generic even if they do not have type parameters of their own.</span></span> <span data-ttu-id="2a94d-190">Weitere Informationen finden Sie im Referenzthema [Type.MakeGenericType](xref:System.Type.MakeGenericType(System.Type[])).</span><span class="sxs-lookup"><span data-stu-id="2a94d-190">For more information, see the [Type.MakeGenericType](xref:System.Type.MakeGenericType(System.Type[])) reference topic.</span></span> 

<span data-ttu-id="2a94d-191">Durch das [FlagsAttribute](xref:System.FlagsAttribute)-Attribut wird eine spezielle Art von Enumeration, das so genannte Bitfeld, ausgewiesen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-191">The [FlagsAttribute](xref:System.FlagsAttribute) attribute denotes a special kind of enumeration called a bit field.</span></span> <span data-ttu-id="2a94d-192">Von der Laufzeit selbst wird nicht zwischen herkömmlichen Enumerationen und Bitfeldern unterschieden, in Ihrer Programmiersprache könnte dies jedoch der Fall sein.</span><span class="sxs-lookup"><span data-stu-id="2a94d-192">The runtime itself does not distinguish between traditional enumerations and bit fields, but your language might do so.</span></span> <span data-ttu-id="2a94d-193">Wird diese Unterscheidung getroffen, können zum Generieren nicht benannter Werte zwar bitweise Operatoren für Bitfelder, jedoch nicht für Enumerationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-193">When this distinction is made, bitwise operators can be used on bit fields, but not on enumerations, to generate unnamed values.</span></span> <span data-ttu-id="2a94d-194">Enumerationen werden im Allgemeinen für Listen eindeutiger Elemente verwendet, z. B. für Wochentage bzw. Namen für Regionen oder Länder usw.</span><span class="sxs-lookup"><span data-stu-id="2a94d-194">Enumerations are generally used for lists of unique elements, such as days of the week, country or region names, and so on.</span></span> <span data-ttu-id="2a94d-195">Bitfelder werden in der Regel für Listen verwendet, in denen Qualitätsmerkmale oder Mengen definiert sind, die kombiniert auftreten können, z. B. `Red And Big And Fast`.</span><span class="sxs-lookup"><span data-stu-id="2a94d-195">Bit fields are generally used for lists of qualities or quantities that might occur in combination, such as `Red And Big And Fast`.</span></span>

<span data-ttu-id="2a94d-196">Das folgende Beispiel zeigt, wie Bitfelder und herkömmliche Enumerationen in Kombination verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="2a94d-196">The following example shows how to use both bit fields and traditional enumerations.</span></span>

```csharp
using System;
using System.Collections.Generic;

// A traditional enumeration of some root vegetables.
public enum SomeRootVegetables
{
    HorseRadish,
    Radish,
    Turnip
}

// A bit field or flag enumeration of harvesting seasons.
[Flags]
public enum Seasons
{
    None = 0,
    Summer = 1,
    Autumn = 2,
    Winter = 4,
    Spring = 8,
    All = Summer | Autumn | Winter | Spring
}

public class Example
{
   public static void Main()
   {
       // Hash table of when vegetables are available.
       Dictionary<SomeRootVegetables, Seasons> AvailableIn = new Dictionary<SomeRootVegetables, Seasons>();

       AvailableIn[SomeRootVegetables.HorseRadish] = Seasons.All;
       AvailableIn[SomeRootVegetables.Radish] = Seasons.Spring;
       AvailableIn[SomeRootVegetables.Turnip] = Seasons.Spring | 
            Seasons.Autumn;

       // Array of the seasons, using the enumeration.
       Seasons[] theSeasons = new Seasons[] { Seasons.Summer, Seasons.Autumn, 
            Seasons.Winter, Seasons.Spring };

       // Print information of what vegetables are available each season.
       foreach (Seasons season in theSeasons)
       {
          Console.Write(String.Format(
              "The following root vegetables are harvested in {0}:\n", 
              season.ToString("G")));
          foreach (KeyValuePair<SomeRootVegetables, Seasons> item in AvailableIn)
          {
             // A bitwise comparison.
             if (((Seasons)item.Value & season) > 0)
                 Console.Write(String.Format("  {0:G}\n", 
                      (SomeRootVegetables)item.Key));
          }
       }
   }
}
// The example displays the following output:
//    The following root vegetables are harvested in Summer:
//      HorseRadish
//    The following root vegetables are harvested in Autumn:
//      Turnip
//      HorseRadish
//    The following root vegetables are harvested in Winter:
//      HorseRadish
//    The following root vegetables are harvested in Spring:
//      Turnip
//      Radish
//      HorseRadish
```

```vb
Imports System.Collections.Generic

' A traditional enumeration of some root vegetables.
Public Enum SomeRootVegetables
   HorseRadish
   Radish
   Turnip
End Enum 

' A bit field or flag enumeration of harvesting seasons.
<Flags()> Public Enum Seasons
   None = 0
   Summer = 1
   Autumn = 2
   Winter = 4
   Spring = 8
   All = Summer Or Autumn Or Winter Or Spring
End Enum 

' Entry point.
Public Class Example
   Public Shared Sub Main()
      ' Hash table of when vegetables are available.
      Dim AvailableIn As New Dictionary(Of SomeRootVegetables, Seasons)()

      AvailableIn(SomeRootVegetables.HorseRadish) = Seasons.All
      AvailableIn(SomeRootVegetables.Radish) = Seasons.Spring
      AvailableIn(SomeRootVegetables.Turnip) = Seasons.Spring Or _
                                               Seasons.Autumn

      ' Array of the seasons, using the enumeration.
      Dim theSeasons() As Seasons = {Seasons.Summer, Seasons.Autumn, _
                                     Seasons.Winter, Seasons.Spring}

      ' Print information of what vegetables are available each season.
      For Each season As Seasons In theSeasons
         Console.WriteLine(String.Format( _
              "The following root vegetables are harvested in {0}:", _
              season.ToString("G")))
         For Each item As KeyValuePair(Of SomeRootVegetables, Seasons) In AvailableIn
            ' A bitwise comparison.
            If(CType(item.Value, Seasons) And season) > 0 Then
               Console.WriteLine("  " + _
                     CType(item.Key, SomeRootVegetables).ToString("G"))
            End If
         Next
      Next
   End Sub 
End Class 
' The example displays the following output:
'    The following root vegetables are harvested in Summer:
'      HorseRadish
'    The following root vegetables are harvested in Autumn:
'      Turnip
'      HorseRadish
'    The following root vegetables are harvested in Winter:
'      HorseRadish
'    The following root vegetables are harvested in Spring:
'      Turnip
'      Radish
'      HorseRadish
```

### <a name="interfaces"></a><span data-ttu-id="2a94d-197">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2a94d-197">Interfaces</span></span>

<span data-ttu-id="2a94d-198">Eine Schnittstelle definiert einen Vertrag, der eine Kann-Beziehung oder eine Hat-ein-Beziehung angibt.</span><span class="sxs-lookup"><span data-stu-id="2a94d-198">An interface defines a contract that specifies a "can do" relationship or a "has a" relationship.</span></span> <span data-ttu-id="2a94d-199">Schnittstellen werden häufig zur Implementierung einer Funktionalität verwendet, z.B. Vergleichen und Sortieren (die [IComparable](xref:System.IComparable)- und [IComparable&lt;T&gt;](xref:System.IComparable%601)-Schnittstellen), Testen auf Gleichheit (die [IEquatable&lt;T&gt;](xref:System.IEquatable%601)-Schnittstelle) oder Aufzählung von Elementen in einer Sammlung (die [IEnumerable](xref:System.Collections.IEnumerable)- und [IEnumerable&lt;T&gt;](xref:System.Collections.Generic.IEnumerable%601)-Schnittstellen).</span><span class="sxs-lookup"><span data-stu-id="2a94d-199">Interfaces are often used to implement functionality, such as comparing and sorting (the [IComparable](xref:System.IComparable) and [IComparable&lt;T&gt;](xref:System.IComparable%601) interfaces), testing for equality (the [IEquatable&lt;T&gt;](xref:System.IEquatable%601) interface), or enumerating items in a collection (the [IEnumerable](xref:System.Collections.IEnumerable) and [IEnumerable&lt;T&gt;](xref:System.Collections.Generic.IEnumerable%601) interfaces).</span></span> <span data-ttu-id="2a94d-200">Schnittstellen können Eigenschaften, Methoden und Ereignisse aufweisen, die alle abstrakte Member sind. Während die Schnittstelle die Member und deren Signaturen definiert, definiert der die Schnittstelle implementierende Typ die Funktionalität der Schnittstellenmember.</span><span class="sxs-lookup"><span data-stu-id="2a94d-200">Interfaces can have properties, methods, and events, all of which are abstract members; that is, although the interface defines the members and their signatures, it leaves it to the type that implements the interface to define the functionality of each interface member.</span></span> <span data-ttu-id="2a94d-201">Dies bedeutet, dass jede Klasse oder Struktur, die eine Schnittstelle implementiert, Definitionen für die in der Schnittstelle deklarierten abstrakten Member bereitstellen muss.</span><span class="sxs-lookup"><span data-stu-id="2a94d-201">This means that any class or structure that implements an interface must supply definitions for the abstract members declared in the interface.</span></span> <span data-ttu-id="2a94d-202">Für eine Schnittstelle kann es erforderlich sein, dass eine beliebige implementierende Klasse oder Struktur auch mindestens eine andere Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="2a94d-202">An interface can require any implementing class or structure to also implement one or more other interfaces.</span></span>

<span data-ttu-id="2a94d-203">Für Schnittstellen gelten die folgenden Beschränkungen:</span><span class="sxs-lookup"><span data-stu-id="2a94d-203">The following restrictions apply to interfaces:</span></span> 

* <span data-ttu-id="2a94d-204">Eine Schnittstelle kann mit beliebigem Zugriff deklariert werden, die Schnittstellenmember müssen jedoch alle über die Zugriffsart public verfügen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-204">An interface can be declared with any accessibility, but interface members must all have public accessibility.</span></span>

* <span data-ttu-id="2a94d-205">Schnittstellen können keine Konstruktoren definieren.</span><span class="sxs-lookup"><span data-stu-id="2a94d-205">Interfaces cannot define constructors.</span></span>

* <span data-ttu-id="2a94d-206">Schnittstellen können keine Felder definieren.</span><span class="sxs-lookup"><span data-stu-id="2a94d-206">Interfaces cannot define fields.</span></span>

* <span data-ttu-id="2a94d-207">Schnittstellen können nur Instanzmember definieren.</span><span class="sxs-lookup"><span data-stu-id="2a94d-207">Interfaces can define only instance members.</span></span> <span data-ttu-id="2a94d-208">Sie können keine statischen Member definieren.</span><span class="sxs-lookup"><span data-stu-id="2a94d-208">They cannot define static members.</span></span>

<span data-ttu-id="2a94d-209">Jede Sprache muss Regeln zur Verfügung stellen, mit deren Hilfe eine Implementierung der Schnittstelle zugeordnet werden kann, die den Member benötigt. Der Grund ist, dass in mehreren Schnittstellen Member mit identischen Signaturen deklariert werden können, die jedoch möglicherweise über separate Implementierungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-209">Each language must provide rules for mapping an implementation to the interface that requires the member, because more than one interface can declare a member with the same signature, and these members can have separate implementations.</span></span>

### <a name="delegates"></a><span data-ttu-id="2a94d-210">Delegaten</span><span class="sxs-lookup"><span data-stu-id="2a94d-210">Delegates</span></span>

<span data-ttu-id="2a94d-211">Delegaten sind Verweistypen, die einen ähnlichen Zweck erfüllen wie Funktionszeiger in C++.</span><span class="sxs-lookup"><span data-stu-id="2a94d-211">Delegates are reference types that serve a purpose similar to that of function pointers in C++.</span></span> <span data-ttu-id="2a94d-212">Sie werden für Ereignishandler und Rückruffunktionen in .NET verwendet.</span><span class="sxs-lookup"><span data-stu-id="2a94d-212">They are used for event handlers and callback functions in .NET.</span></span> <span data-ttu-id="2a94d-213">Im Gegensatz zu Funktionszeigern sind Delegaten sicher, überprüfbar und typsicher.</span><span class="sxs-lookup"><span data-stu-id="2a94d-213">Unlike function pointers, delegates are secure, verifiable, and type safe.</span></span> <span data-ttu-id="2a94d-214">Ein Delegattyp kann jede Instanzmethode oder statische Methode darstellen, die über eine kompatible Signatur verfügt.</span><span class="sxs-lookup"><span data-stu-id="2a94d-214">A delegate type can represent any instance method or static method that has a compatible signature.</span></span> 

<span data-ttu-id="2a94d-215">Ein Parameter eines Delegaten ist mit dem entsprechenden Parameter einer Methode kompatibel, wenn der Typ des Delegatenparameters restriktiver ist als der Methodenparameter, da so gewährleistet ist, dass ein an den Delegaten übergebenes Argument problemlos an die Methode weitergeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2a94d-215">A parameter of a delegate is compatible with the corresponding parameter of a method if the type of the delegate parameter is more restrictive than the type of the method parameter, because this guarantees that an argument passed to the delegate can be passed safely to the method.</span></span>

<span data-ttu-id="2a94d-216">Ebenso ist der Rückgabetyp eines Delegaten kompatibel mit dem Rückgabetyp einer Methode, wenn der Rückgabetyp der Methode restriktiver ist als der Rückgabetyp des Delegaten, da so gewährleistet ist, dass der Rückgabewert der Methode problemlos in den Rückgabetyp des Delegaten umgewandelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="2a94d-216">Similarly, the return type of a delegate is compatible with the return type of a method if the return type of the method is more restrictive than the return type of the delegate, because this guarantees that the return value of the method can be cast safely to the return type of the delegate.</span></span>

<span data-ttu-id="2a94d-217">Beispielsweise kann ein Delegat mit einem Parameter des Typs [IEnumerable](xref:System.Collections.IEnumerable) und dem Rückgabetyp [Object](xref:System.Object) eine Methode mit einem Parameter des Typs [Object](xref:System.Object) und einem Rückgabewert des Typs [IEnumerable](xref:System.Collections.IEnumerable) darstellen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-217">For example, a delegate that has a parameter of type [IEnumerable](xref:System.Collections.IEnumerable) and a return type of [Object](xref:System.Object) can represent a method that has a parameter of type [Object](xref:System.Object) and a return value of type [IEnumerable](xref:System.Collections.IEnumerable).</span></span> 

 <span data-ttu-id="2a94d-218">Ein Delegat wird als gebunden an die Methode bezeichnet, die er darstellt.</span><span class="sxs-lookup"><span data-stu-id="2a94d-218">A delegate is said to be bound to the method it represents.</span></span> <span data-ttu-id="2a94d-219">Ein Delegat kann nicht nur an die Methode, sondern auch an ein Objekt gebunden sein.</span><span class="sxs-lookup"><span data-stu-id="2a94d-219">In addition to being bound to the method, a delegate can be bound to an object.</span></span> <span data-ttu-id="2a94d-220">Das Objekt stellt den ersten Parameter der Methode dar und wird jedes Mal an die Methode übergeben, wenn der Delegat aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="2a94d-220">The object represents the first parameter of the method, and is passed to the method every time the delegate is invoked.</span></span> <span data-ttu-id="2a94d-221">Wenn es sich bei der Methode um eine Instanzmethode handelt, wird das gebundene Objekt als impliziter `this`-Parameter (`Me` in Visual Basic) übergeben. Wenn die Methode statisch ist, wird das Objekt als erster formaler Parameter der Methode übergeben, und die Delegatsignatur muss den verbleibenden Parametern entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-221">If the method is an instance method, the bound object is passed as the implicit `this` parameter (`Me` in Visual Basic); if the method is static, the object is passed as the first formal parameter of the method, and the delegate signature must match the remaining parameters.</span></span> 
 
 <span data-ttu-id="2a94d-222">Alle Delegaten erben von [System.MulticastDelegate](xref:System.MulticastDelegate), und der erbt wiederum von [System.Delegate](xref:System.Delegate).</span><span class="sxs-lookup"><span data-stu-id="2a94d-222">All delegates inherit from [System.MulticastDelegate](xref:System.MulticastDelegate), which inherits from [System.Delegate](xref:System.Delegate).</span></span> <span data-ttu-id="2a94d-223">In den Programmiersprachen C# und Visual Basic ist die Vererbung von diesen Typen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="2a94d-223">The C# and Visual Basic languages don't allow inheritance from these types.</span></span> <span data-ttu-id="2a94d-224">Stattdessen werden Schlüsselwörter zum Deklarieren von Delegaten bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="2a94d-224">Instead, they provide keywords for declaring delegates.</span></span>
 
 <span data-ttu-id="2a94d-225">Da Delegaten von [MulticastDelegate](xref:System.MulticastDelegate) erben, verfügt ein Delegat über eine Aufrufliste. Dabei handelt es sich um eine Liste der Methoden, die dieser Delegat darstellt und die beim Aufrufen des Delegaten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-225">Because delegates inherit from [MulticastDelegate](xref:System.MulticastDelegate), a delegate has an invocation list, which is a list of methods that the delegate represents and that are executed when the delegate is invoked.</span></span> <span data-ttu-id="2a94d-226">Alle Methoden in der Liste empfangen die beim Aufrufen des Delegaten angegebenen Argumente.</span><span class="sxs-lookup"><span data-stu-id="2a94d-226">All methods in the list receive the arguments supplied when the delegate is invoked.</span></span>

> [!NOTE]
> <span data-ttu-id="2a94d-227">Der Rückgabewert von Delegaten mit mehr als einer Methode in der Aufrufliste ist nicht definiert, selbst wenn diese über einen Rückgabetyp verfügen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-227">The return value is not defined for a delegate that has more than one method in its invocation list, even if the delegate has a return type.</span></span>

<span data-ttu-id="2a94d-228">In vielen Fällen (z. B. bei Rückrufmethoden) stellt ein Delegat nur eine Methode dar. Sie müssen den Delegaten lediglich erstellen und aufrufen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-228">In many cases, such as with callback methods, a delegate represents only one method, and the only actions you have to take are creating the delegate and invoking it.</span></span> 

<span data-ttu-id="2a94d-229">Für Delegaten, die mehrere Methoden darstellen, enthält .NET Methoden der [Delegate](xref:System.Delegate)-Delegatklasse und [MulticastDelegate](xref:System.MulticastDelegate)-Delegatklasse, um verschiedene Vorgänge zu unterstützen. Dazu gehören das Hinzufügen einer Methode zur Aufrufliste eines Delegaten (die [Delegate.Combine](xref:System.Delegate.Combine(System.Delegate,System.Delegate))-Methode), das Entfernen einer Methode (die [Delegate.Remove](xref:System.Delegate.Remove(System.Delegate,System.Delegate))-Methode) und das Abrufen der Aufrufliste (die [Delegate.GetInvocationList](xref:System.Delegate.GetInvocationList)-Methode).</span><span class="sxs-lookup"><span data-stu-id="2a94d-229">For delegates that represent multiple methods, .NET provides methods of the [Delegate](xref:System.Delegate) and [MulticastDelegate](xref:System.MulticastDelegate) delegate classes to support operations such as adding a method to a delegate's invocation list (the [Delegate.Combine](xref:System.Delegate.Combine(System.Delegate,System.Delegate)) method), removing a method (the [Delegate.Remove](xref:System.Delegate.Remove(System.Delegate,System.Delegate)) method), and getting the invocation list (the [Delegate.GetInvocationList](xref:System.Delegate.GetInvocationList) method).</span></span>

> [!NOTE]
> <span data-ttu-id="2a94d-230">Es ist in C# oder Visual Basic nicht erforderlich, diese Methoden für Ereignishandlerdelegaten einzusetzen, da in diesen Programmiersprachen Syntax zum Hinzufügen und Entfernen von Ereignishandlern bereitsteht.</span><span class="sxs-lookup"><span data-stu-id="2a94d-230">It is not necessary to use these methods for event-handler delegates in C# or Visual Basic, because these languages provide syntax for adding and removing event handlers.</span></span>

## <a name="type-definitions"></a><span data-ttu-id="2a94d-231">Typdefinitionen</span><span class="sxs-lookup"><span data-stu-id="2a94d-231">Type definitions</span></span>

<span data-ttu-id="2a94d-232">Eine Typdefinition enthält Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2a94d-232">A type definition includes the following:</span></span> 

* <span data-ttu-id="2a94d-233">Alle für den Typ definierten Attribute.</span><span class="sxs-lookup"><span data-stu-id="2a94d-233">Any attributes defined on the type.</span></span>

* <span data-ttu-id="2a94d-234">Den Zugriff des Typs (Sichtbarkeit).</span><span class="sxs-lookup"><span data-stu-id="2a94d-234">The type's accessibility (visibility).</span></span>

* <span data-ttu-id="2a94d-235">Den Typnamen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-235">The type's name.</span></span>

* <span data-ttu-id="2a94d-236">Den Basistyp des Typs.</span><span class="sxs-lookup"><span data-stu-id="2a94d-236">The type's base type.</span></span>

* <span data-ttu-id="2a94d-237">Alle durch den Typ implementierten Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-237">Any interfaces implemented by the type.</span></span>

* <span data-ttu-id="2a94d-238">Definitionen für jeden Member des Typs.</span><span class="sxs-lookup"><span data-stu-id="2a94d-238">Definitions for each of the type's members.</span></span>

### <a name="attributes"></a><span data-ttu-id="2a94d-239">Attribute</span><span class="sxs-lookup"><span data-stu-id="2a94d-239">Attributes</span></span>

<span data-ttu-id="2a94d-240">Durch Attribute werden zusätzliche benutzerdefinierte Metadaten bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="2a94d-240">Attributes provide additional user-defined metadata.</span></span> <span data-ttu-id="2a94d-241">Sie werden in dem meisten Fällen verwendet, um zusätzliche Informationen zu einem Typ in seiner Assembly zu speichern oder um das Verhalten eines Typmembers zur Entwurfszeit oder in der Laufzeitumgebung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2a94d-241">Most commonly, they are used to store additional information about a type in its assembly, or to modify the behavior of a type member in either the design-time or run-time environment.</span></span> 

<span data-ttu-id="2a94d-242">Attribute sind selbst Klassen, die von [System.Attribute](xref:System.Attribute) erben.</span><span class="sxs-lookup"><span data-stu-id="2a94d-242">Attributes are themselves classes that inherit from [System.Attribute](xref:System.Attribute).</span></span> <span data-ttu-id="2a94d-243">Sprachen, die die Verwendung von Attributen unterstützen, verfügen über eine eigene Syntax zum Anwenden von Attributen auf ein Sprachelement.</span><span class="sxs-lookup"><span data-stu-id="2a94d-243">Languages that support the use of attributes each have their own syntax for applying attributes to a language element.</span></span> <span data-ttu-id="2a94d-244">Attribute können auf fast alle Sprachelemente angewendet werden. Die einzelnen Elemente, auf die ein Attribut angewendet werden kann, werden vom auf die Attributklasse angewendeten [AttributeUsageAttribute](xref:System.AttributeUsageAttribute) definiert.</span><span class="sxs-lookup"><span data-stu-id="2a94d-244">Attributes can be applied to almost any language element; the specific elements to which an attribute can be applied are defined by the [AttributeUsageAttribute](xref:System.AttributeUsageAttribute) that is applied to that attribute class.</span></span>

### <a name="type-accessibility"></a><span data-ttu-id="2a94d-245">Typzugriff</span><span class="sxs-lookup"><span data-stu-id="2a94d-245">Type accessibility</span></span>

<span data-ttu-id="2a94d-246">Alle Typen verfügen über einen Modifizierer, der regelt, welche anderen Typen auf diesen Typ zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="2a94d-246">All types have a modifier that governs their accessibility from other types.</span></span> <span data-ttu-id="2a94d-247">In der folgenden Tabelle werden die von der Laufzeit unterstützten Zugriffsarten auf Typen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2a94d-247">The following table describes the type accessibilities supported by the runtime.</span></span>

<span data-ttu-id="2a94d-248">Barrierefreiheit</span><span class="sxs-lookup"><span data-stu-id="2a94d-248">Accessibility</span></span> | <span data-ttu-id="2a94d-249">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a94d-249">Description</span></span>
------------- | -----------
<span data-ttu-id="2a94d-250">public</span><span class="sxs-lookup"><span data-stu-id="2a94d-250">public</span></span> | <span data-ttu-id="2a94d-251">Auf diesen Typ kann von allen Assemblys zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-251">The type is accessible by all assemblies.</span></span>
<span data-ttu-id="2a94d-252">Assembly</span><span class="sxs-lookup"><span data-stu-id="2a94d-252">assembly</span></span> | <span data-ttu-id="2a94d-253">Auf diesen Typ kann nur innerhalb seiner Assembly zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-253">The type is accessible only from within its assembly.</span></span>

<span data-ttu-id="2a94d-254">Der Zugriff auf einen geschachtelten Typ hängt von seiner Zugriffsdomäne ab, die sowohl durch den deklarierten Zugriffstyp des Members als auch durch die Zugriffsdomäne des direkt enthaltenden Typs bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="2a94d-254">The accessibility of a nested type depends on its accessibility domain, which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="2a94d-255">Die Zugriffsdomäne eines geschachtelten Typs kann jedoch nicht über die des enthaltenden Typs hinausgehen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-255">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>

<span data-ttu-id="2a94d-256">Die Zugriffsdomäne eines geschachtelten Members `M`, der in einem Typ `T` innerhalb eines Programms `P` deklariert ist, wird wie folgt definiert (wobei `M` selbst ein Typ sein kann):</span><span class="sxs-lookup"><span data-stu-id="2a94d-256">The accessibility domain of a nested member `M` declared in a type `T`within a program `P` is defined as follows (noting that `M` might itself be a type):</span></span> 

* <span data-ttu-id="2a94d-257">Wenn die deklarierte Zugriffsart von `M` den Wert `public` hat, entspricht die Zugriffsdomäne von `M` der von `T`.</span><span class="sxs-lookup"><span data-stu-id="2a94d-257">If the declared accessibility of `M` is `public`, the accessibility domain of `M` is the accessibility domain of `T`.</span></span>

* <span data-ttu-id="2a94d-258">Wenn die deklarierte Zugriffsart von `M` den Wert `protected internal` hat, entspricht die Zugriffsdomäne von `M` der Schnittmenge zwischen der Zugriffsdomäne von `T`, dem Programmtext von `P` und dem Programmtext jedes Typs, der von `T` abgeleitet und außerhalb von `P` deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="2a94d-258">If the declared accessibility of `M` is `protected internal`, the accessibility domain of `M` is the intersection of the accessibility domain of `T` with the program text of `P` and the program text of any type derived from `T` declared outside `P`.</span></span>

* <span data-ttu-id="2a94d-259">Wenn die deklarierte Zugriffsart von `M` den Wert `protected` hat, entspricht die Zugriffsdomäne von `M` der Schnittmenge zwischen der Zugriffsdomäne von `T`, dem Programmtext von `T` und jedem von `T` abgeleiteten Typ.</span><span class="sxs-lookup"><span data-stu-id="2a94d-259">If the declared accessibility of `M` is `protected`, the accessibility domain of `M` is the intersection of the accessibility domain of `T` with the program text of `T` and any type derived from `T`.</span></span>

* <span data-ttu-id="2a94d-260">Wenn die deklarierte Zugriffsart von `M` den Wert `internal` hat, entspricht die Zugriffsdomäne von `M` der Schnittmenge zwischen der Zugriffsdomäne von `T` und dem Programmtext von `P`.</span><span class="sxs-lookup"><span data-stu-id="2a94d-260">If the declared accessibility of `M` is `internal`, the accessibility domain of `M` is the intersection of the accessibility domain of `T` with the program text of`P`.</span></span>

* <span data-ttu-id="2a94d-261">Wenn die deklarierte Zugriffsart von `M` den Wert `private` hat, entspricht die Zugriffsdomäne von `M` dem Programmtext von `T`.</span><span class="sxs-lookup"><span data-stu-id="2a94d-261">If the declared accessibility of `M` is `private`, the accessibility domain of `M` is the program text of `T`.</span></span>

### <a name="type-names"></a><span data-ttu-id="2a94d-262">Typnamen</span><span class="sxs-lookup"><span data-stu-id="2a94d-262">Type names</span></span>

<span data-ttu-id="2a94d-263">Das allgemeine Typsystem sieht lediglich zwei Namenseinschränkungen vor:</span><span class="sxs-lookup"><span data-stu-id="2a94d-263">The common type system imposes only two restrictions on names:</span></span> 

* <span data-ttu-id="2a94d-264">Alle Namen werden als Unicode-Zeichenfolgen (16-Bit-Zeichen) codiert.</span><span class="sxs-lookup"><span data-stu-id="2a94d-264">All names are encoded as strings of Unicode (16-bit) characters.</span></span>

* <span data-ttu-id="2a94d-265">Ein eingebetteter Wert von 0x0000 (16 Bits) ist für Namen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="2a94d-265">Names are not permitted to have an embedded (16-bit) value of 0x0000.</span></span>

<span data-ttu-id="2a94d-266">In den meisten Sprachen gelten jedoch möglicherweise zusätzliche Beschränkungen für Typnamen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-266">However, most languages impose additional restrictions on type names.</span></span> <span data-ttu-id="2a94d-267">Alle Vergleiche erfolgen byteweise, sie berücksichtigen daher die Groß-/Kleinschreibung und sind unabhängig vom Gebietsschema.</span><span class="sxs-lookup"><span data-stu-id="2a94d-267">All comparisons are done on a byte-by-byte basis, and are therefore case-sensitive and locale-independent.</span></span>

<span data-ttu-id="2a94d-268">Obwohl ein Typ auf Typen aus anderen Modulen und Assemblys verweisen kann, muss er vollständig innerhalb eines .NET-Moduls definiert werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-268">Although a type might reference types from other modules and assemblies, a type must be fully defined within one .NET module.</span></span> <span data-ttu-id="2a94d-269">(Abhängig von der Compilerunterstützung kann er jedoch auf mehrere Quellcodedateien aufgeteilt werden.) Typnamen müssen nur innerhalb eines Namespace eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="2a94d-269">(Depending on compiler support, however, it can be divided into multiple source code files.) Type names need be unique only within a namespace.</span></span> <span data-ttu-id="2a94d-270">Um einen Typ vollständig zu identifizieren, muss der Typname durch den Namespace gekennzeichnet werden, die die Typimplementierung enthält.</span><span class="sxs-lookup"><span data-stu-id="2a94d-270">To fully identify a type, the type name must be qualified by the namespace that contains the implementation of the type.</span></span>

### <a name="base-types-and-interfaces"></a><span data-ttu-id="2a94d-271">Basistypen und Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2a94d-271">Base types and interfaces</span></span>

<span data-ttu-id="2a94d-272">Ein Typ kann Werte und Verhaltensdefinitionen von anderen Typen erben.</span><span class="sxs-lookup"><span data-stu-id="2a94d-272">A type can inherit values and behaviors from another type.</span></span> <span data-ttu-id="2a94d-273">Gemäß dem allgemeinen Typsystem können Typen nicht von mehr als einem Basistyp erben.</span><span class="sxs-lookup"><span data-stu-id="2a94d-273">The common type system does not allow types to inherit from more than one base type.</span></span>

<span data-ttu-id="2a94d-274">Ein Typ kann eine beliebige Anzahl von Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="2a94d-274">A type can implement any number of interfaces.</span></span> <span data-ttu-id="2a94d-275">Zur Implementierung einer Schnittstelle muss ein Typ alle virtuellen Member der betreffenden Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="2a94d-275">To implement an interface, a type must implement all the virtual members of that interface.</span></span> <span data-ttu-id="2a94d-276">Eine virtuelle Methode kann durch einen abgeleiteten Typ implementiert und entweder statisch oder dynamisch aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-276">A virtual method can be implemented by a derived type and can be invoked either statically or dynamically.</span></span>

## <a name="type-members"></a><span data-ttu-id="2a94d-277">Typmember</span><span class="sxs-lookup"><span data-stu-id="2a94d-277">Type members</span></span>

<span data-ttu-id="2a94d-278">Die Laufzeit ermöglicht es Ihnen, Member des Typs zu definieren. Hierbei werden das Verhalten und der Zustand eines Typs angegeben.</span><span class="sxs-lookup"><span data-stu-id="2a94d-278">The runtime enables you to define members of your type, which specifies the behavior and state of a type.</span></span> <span data-ttu-id="2a94d-279">Typmember umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2a94d-279">Type members include the following:</span></span>

* [<span data-ttu-id="2a94d-280">Felder</span><span class="sxs-lookup"><span data-stu-id="2a94d-280">Fields</span></span>](#fields)

* [<span data-ttu-id="2a94d-281">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2a94d-281">Properties</span></span>](#properties)

* [<span data-ttu-id="2a94d-282">Methoden</span><span class="sxs-lookup"><span data-stu-id="2a94d-282">Methods</span></span>](#methods)

* [<span data-ttu-id="2a94d-283">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="2a94d-283">Constructors</span></span>](#constructors)

* [<span data-ttu-id="2a94d-284">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="2a94d-284">Events</span></span>](#events)

* [<span data-ttu-id="2a94d-285">Geschachtelte Typen</span><span class="sxs-lookup"><span data-stu-id="2a94d-285">Nested types</span></span>](#nested-types)

### <a name="fields"></a><span data-ttu-id="2a94d-286">Felder</span><span class="sxs-lookup"><span data-stu-id="2a94d-286">Fields</span></span>

<span data-ttu-id="2a94d-287">Ein Feld beschreibt und enthält Teile des Typzustands.</span><span class="sxs-lookup"><span data-stu-id="2a94d-287">A field describes and contains part of the type's state.</span></span> <span data-ttu-id="2a94d-288">Felder können jedem von der Laufzeit unterstützten Typ entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-288">Fields can be of any type supported by the runtime.</span></span> <span data-ttu-id="2a94d-289">In den meisten Fällen sind Felder `private` oder `protected`, damit auf sie nur innerhalb der Klasse oder aus einer abgeleiteten Klasse zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="2a94d-289">Most commonly, fields are either `private` or `protected`, so that they are accessible only from within the class or from a derived class.</span></span> <span data-ttu-id="2a94d-290">Wenn der Wert eines Felds außerhalb seines Typs geändert werden kann, wird normalerweise ein Eigenschaftensatzaccessor verwendet.</span><span class="sxs-lookup"><span data-stu-id="2a94d-290">If the value of a field can be modified from outside its type, a property set accessor is typically used.</span></span> <span data-ttu-id="2a94d-291">Öffentlich verfügbar gemachte Felder sind normalerweise schreibgeschützt und können zwei Typen aufweisen:</span><span class="sxs-lookup"><span data-stu-id="2a94d-291">Publicly exposed fields are usually read-only and can be of two types:</span></span> 

* <span data-ttu-id="2a94d-292">Konstanten, deren Wert zur Entwurfszeit zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="2a94d-292">Constants, whose value is assigned at design time.</span></span> <span data-ttu-id="2a94d-293">Diese sind statische Member einer Klasse, obwohl sie nicht mit dem `static`-Schlüsselwort (`Shared` in Visual Basic) definiert werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-293">These are static members of a class, although they are not defined using the `static` (`Shared` in Visual Basic) keyword.</span></span>

* <span data-ttu-id="2a94d-294">Schreibgeschützte Variablen, deren Werte im Klassenkonstruktor zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="2a94d-294">Read-only variables, whose values can be assigned in the class constructor.</span></span>

<span data-ttu-id="2a94d-295">Im folgenden Beispiel werden diese zwei Verwendungen für schreibgeschützte Felder veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2a94d-295">The following example illustrates these two usages of read-only fields.</span></span>

```csharp
using System;

public class Constants
{
   public const double Pi = 3.1416;
   public readonly DateTime BirthDate;

   public Constants(DateTime birthDate)
   {
      this.BirthDate = birthDate;
   }
}

public class Example
{
   public static void Main()
   {
      Constants con = new Constants(new DateTime(1974, 8, 18));
      Console.Write(Constants.Pi + "\n");
      Console.Write(con.BirthDate.ToString("d") + "\n");
   }
}
// The example displays the following output if run on a system whose current
// culture is en-US:
//    3.1417
//    8/18/1974
```

```vb
Public Class Constants
   Public Const Pi As Double = 3.1416
   Public ReadOnly BirthDate As Date

   Public Sub New(birthDate As Date)
      Me.BirthDate = birthDate
   End Sub
End Class

Public Module Example
   Public Sub Main()
      Dim con As New Constants(#8/18/1974#)
      Console.WriteLine(Constants.Pi.ToString())
      Console.WriteLine(con.BirthDate.ToString("d"))
   End Sub
End Module
' The example displays the following output if run on a system whose current
' culture is en-US:
'    3.1417
'    8/18/1974
```

### <a name="properties"></a><span data-ttu-id="2a94d-296">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2a94d-296">Properties</span></span>

<span data-ttu-id="2a94d-297">Eine Eigenschaft benennt einen Wert oder Zustand des Typs und definiert Methoden zum Abrufen oder Festlegen des Eigenschaftswerts.</span><span class="sxs-lookup"><span data-stu-id="2a94d-297">A property names a value or state of the type and defines methods for getting or setting the property's value.</span></span> <span data-ttu-id="2a94d-298">Eigenschaften können primitive Typen, Auflistungen primitiver Typen, benutzerdefinierte Typen oder Auflistungen benutzerdefinierter Typen sein.</span><span class="sxs-lookup"><span data-stu-id="2a94d-298">Properties can be primitive types, collections of primitive types, user-defined types, or collections of user-defined types.</span></span> <span data-ttu-id="2a94d-299">Eigenschaften werden häufig verwendet, um die Unabhängigkeit der öffentlichen Schnittstelle eines Typs von seiner tatsächlichen Darstellung zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="2a94d-299">Properties are often used to keep the public interface of a type independent from the type's actual representation.</span></span> <span data-ttu-id="2a94d-300">So können Eigenschaften Werte reflektieren, die nicht direkt in der Klasse gespeichert sind (z. B., wenn eine Eigenschaft einen berechneten Wert zurückgibt), oder eine Validierung ausführen, bevor privaten Feldern Werte zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-300">This enables properties to reflect values that are not directly stored in the class (for example, when a property returns a computed value) or to perform validation before values are assigned to private fields.</span></span> <span data-ttu-id="2a94d-301">Im folgenden Codebeispiel wird das zweite Schema veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2a94d-301">The following example illustrates the latter pattern.</span></span>

```csharp
using System;

public class Person
{
   private int m_Age;

   public int Age
   { 
      get { return m_Age; }
      set {
         if (value < 0 || value > 125)
         {
            throw new ArgumentOutOfRangeException("The value of the Age property must be between 0 and 125.");
         }
         else
         {
            m_Age = value;
         }         
      }
   }
}
```

```vb
Public Class Person
   Private m_Age As Integer

   Public Property Age As Integer
      Get
         Return m_Age
      End Get
      Set
         If value < 0 Or value > 125 Then
            Throw New ArgumentOutOfRangeException("The value of the Age property must be between 0 and 125.")
         Else
            m_Age = value
         End If
      End Set
   End Property
End Class
```

<span data-ttu-id="2a94d-302">Die Microsoft Intermediate Language (MSIL) schließt nicht nur die Eigenschaft ein, sondern für einen Typ mit einer lesbaren Eigenschaft darüber hinaus eine `get`*_propertyname*-Methode und für einen Typ mit einer beschreibbaren Eigenschaft eine `set`*_propertyname*-Methode.</span><span class="sxs-lookup"><span data-stu-id="2a94d-302">In addition to including the property itself, the Microsoft intermediate language (MSIL) for a type that contains a readable property includes a `get`*_propertyname* method, and the MSIL for a type that contains a writable property includes a `set`*_propertyname* method.</span></span>

### <a name="methods"></a><span data-ttu-id="2a94d-303">Methoden</span><span class="sxs-lookup"><span data-stu-id="2a94d-303">Methods</span></span>

<span data-ttu-id="2a94d-304">Eine Methode beschreibt Vorgänge, die für den Typ verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="2a94d-304">A method describes operations that are available on the type.</span></span> <span data-ttu-id="2a94d-305">Eine Methodensignatur gibt die zulässigen Typen aller Parameter sowie des Rückgabewerts der Methode an.</span><span class="sxs-lookup"><span data-stu-id="2a94d-305">A method's signature specifies the allowable types of all its parameters and of its return value.</span></span>

<span data-ttu-id="2a94d-306">Obwohl die meisten Methoden die erforderliche Anzahl von Parametern für Methodenaufrufe genau definieren, unterstützen einige Methoden eine variable Anzahl von Parametern.</span><span class="sxs-lookup"><span data-stu-id="2a94d-306">Although most methods define the precise number of parameters required for method calls, some methods support a variable number of parameters.</span></span> <span data-ttu-id="2a94d-307">Der letzte deklarierte Parameter dieser Methoden wird mit dem [ParamArrayAttribute](xref:System.ParamArrayAttribute)-Attribut markiert.</span><span class="sxs-lookup"><span data-stu-id="2a94d-307">The final declared parameter of these methods is marked with the [ParamArrayAttribute](xref:System.ParamArrayAttribute) attribute.</span></span> <span data-ttu-id="2a94d-308">Sprachcompiler stellen in der Regel ein Schlüsselwort bereit, z.B. `params` in C# und `ParamArray` in Visual Basic, das die explizite Verwendung von [ParamArrayAttribute](xref:System.ParamArrayAttribute) unnötig macht.</span><span class="sxs-lookup"><span data-stu-id="2a94d-308">Language compilers typically provide a keyword, such as `params` in C# and `ParamArray` in Visual Basic, that makes explicit use of [ParamArrayAttribute](xref:System.ParamArrayAttribute) unnecessary.</span></span>

### <a name="constructors"></a><span data-ttu-id="2a94d-309">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="2a94d-309">Constructors</span></span>

<span data-ttu-id="2a94d-310">Ein Konstruktor ist eine spezielle Methodenform, durch die neue Instanzen einer Klasse oder Struktur erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-310">A constructor is a special kind of method that creates new instances of a class or structure.</span></span> <span data-ttu-id="2a94d-311">Wie jede andere Methode kann ein Konstruktor Parameter einschließen. Konstruktoren verfügen jedoch nicht über einen Rückgabewert (d. h., sie geben `void` zurück).</span><span class="sxs-lookup"><span data-stu-id="2a94d-311">Like any other method, a constructor can include parameters; however, constructors have no return value (that is, they return `void`).</span></span> 

<span data-ttu-id="2a94d-312">Wenn der Quellcode für eine Klasse nicht explizit einen Konstruktor definiert, schließt der Compiler einen Standardkonstruktor (ohne Parameter) ein.</span><span class="sxs-lookup"><span data-stu-id="2a94d-312">If the source code for a class does not explicitly define a constructor, the compiler includes a default (parameterless) constructor.</span></span> <span data-ttu-id="2a94d-313">Wenn der Quellcode für eine Klasse jedoch nur parametrisierte Konstruktoren definiert, generiert der C#-Compiler keinen parameterlosen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="2a94d-313">However, if the source code for a class defines only parameterized constructors, the C# compiler doesn't generate a parameterless constructor.</span></span>

<span data-ttu-id="2a94d-314">Wenn der Quellcode für eine Struktur Konstruktoren definiert, müssen diese parametrisiert werden. Eine Struktur kann keinen Standardkonstruktor (parameterlos) definieren, und Compiler generieren keine parameterlosen Konstruktoren für Strukturen oder andere Werttypen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-314">If the source code for a structure defines constructors, they must be parameterized; a structure cannot define a default (parameterless) constructor, and compilers do not generate parameterless constructors for structures or other value types.</span></span> <span data-ttu-id="2a94d-315">Alle Werttypen verfügen über einen impliziten Standardkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="2a94d-315">All value types do have an implicit default constructor.</span></span> <span data-ttu-id="2a94d-316">Dieser Konstruktor wird von der Common Language Runtime implementiert und initialisiert alle Felder der Struktur mit ihren Standardwerten.</span><span class="sxs-lookup"><span data-stu-id="2a94d-316">This constructor is implemented by the common language runtime and initializes all fields of the structure to their default values.</span></span> 

### <a name="events"></a><span data-ttu-id="2a94d-317">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="2a94d-317">Events</span></span>

<span data-ttu-id="2a94d-318">Ein Ereignis definiert ein Ereignis, auf das reagiert werden kann, und definiert Methoden, mit denen das Ereignis ausgelöst und abonniert bzw. sein Abonnement aufgehoben werden kann.</span><span class="sxs-lookup"><span data-stu-id="2a94d-318">An event defines an incident that can be responded to, and defines methods for subscribing to, unsubscribing from, and raising the event.</span></span> <span data-ttu-id="2a94d-319">Häufig werden mithilfe von Ereignissen andere Typen über Zustandsänderungen informiert.</span><span class="sxs-lookup"><span data-stu-id="2a94d-319">Events are often used to inform other types of state changes.</span></span>

### <a name="nested-types"></a><span data-ttu-id="2a94d-320">Geschachtelte Typen</span><span class="sxs-lookup"><span data-stu-id="2a94d-320">Nested types</span></span>

<span data-ttu-id="2a94d-321">Ein geschachtelter Typ ist ein Typ, der ein Member eines anderen Typs ist.</span><span class="sxs-lookup"><span data-stu-id="2a94d-321">A nested type is a type that is a member of some other type.</span></span> <span data-ttu-id="2a94d-322">Geschachtelte Typen müssen eng mit dem zugehörigen enthaltenden Typ verknüpft sein und dürfen nicht für allgemeine Zwecke verwendbar sein.</span><span class="sxs-lookup"><span data-stu-id="2a94d-322">Nested types should be tightly coupled to their containing type and must not be useful as a general-purpose type.</span></span> <span data-ttu-id="2a94d-323">Geschachtelte Typen sind sinnvoll, wenn der deklarierende Typ Instanzen des geschachtelten Typs verwendet und erstellt und die Verwendung des geschachtelten Typs nicht in öffentlichen Membern verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="2a94d-323">Nested types are useful when the declaring type uses and creates instances of the nested type, and use of the nested type is not exposed in public members.</span></span>

<span data-ttu-id="2a94d-324">Für einige Entwickler sind geschachtelte Typen verwirrend, und sie sollten nur öffentlich sichtbar sein, wenn ein zwingender Grund dafür vorliegt.</span><span class="sxs-lookup"><span data-stu-id="2a94d-324">Nested types are confusing to some developers and should not be publicly visible unless there is a compelling reason for visibility.</span></span> <span data-ttu-id="2a94d-325">In einer gut entworfenen Bibliothek sollten Entwickler nur selten geschachtelte Typen zum Instanziieren von Objekten oder Deklarieren von Variablen verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-325">In a well-designed library, developers should rarely have to use nested types to instantiate objects or declare variables.</span></span>

## <a name="characteristics-of-type-members"></a><span data-ttu-id="2a94d-326">Eigenschaften von Typmembern</span><span class="sxs-lookup"><span data-stu-id="2a94d-326">Characteristics of type members</span></span>

<span data-ttu-id="2a94d-327">Das allgemeine Typsystem unterstützt Typmember, die eine Vielzahl unterschiedlicher Merkmale haben können. Zur Unterstützung all dieser Merkmale sind jedoch keine speziellen Sprachen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2a94d-327">The common type system allows type members to have a variety of characteristics; however, languages are not required to support all these characteristics.</span></span> <span data-ttu-id="2a94d-328">In der folgenden Tabelle sind diese Membermerkmale beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2a94d-328">The following table describes member characteristics.</span></span>

<span data-ttu-id="2a94d-329">Merkmal</span><span class="sxs-lookup"><span data-stu-id="2a94d-329">Characteristic</span></span> | <span data-ttu-id="2a94d-330">Anwendbar auf</span><span class="sxs-lookup"><span data-stu-id="2a94d-330">Can apply to</span></span> | <span data-ttu-id="2a94d-331">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a94d-331">Description</span></span>
-------------- | ------------ | -----------
<span data-ttu-id="2a94d-332">abstract</span><span class="sxs-lookup"><span data-stu-id="2a94d-332">abstract</span></span> | <span data-ttu-id="2a94d-333">Methoden, Eigenschaften und Ereignisse</span><span class="sxs-lookup"><span data-stu-id="2a94d-333">Methods, properties, and events</span></span> | <span data-ttu-id="2a94d-334">Der Typ stellt keine Methodenimplementierung bereit.</span><span class="sxs-lookup"><span data-stu-id="2a94d-334">The type does not supply the method's implementation.</span></span> <span data-ttu-id="2a94d-335">Typen, die abstrakte Methoden erben oder implementieren, müssen eine Implementierung für die Methode bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-335">Types that inherit or implement abstract methods must supply an implementation for the method.</span></span> <span data-ttu-id="2a94d-336">Die einzige Ausnahme liegt vor, wenn der abgeleitete Typ selbst vom Typ abstract ist.</span><span class="sxs-lookup"><span data-stu-id="2a94d-336">The only exception is when the derived type is itself an abstract type.</span></span> <span data-ttu-id="2a94d-337">Alle Methoden vom Typ abstract sind auch virtual.</span><span class="sxs-lookup"><span data-stu-id="2a94d-337">All abstract methods are virtual.</span></span>
<span data-ttu-id="2a94d-338">private</span><span class="sxs-lookup"><span data-stu-id="2a94d-338">private</span></span> | <span data-ttu-id="2a94d-339">Alle</span><span class="sxs-lookup"><span data-stu-id="2a94d-339">All</span></span> | <span data-ttu-id="2a94d-340">Zugriff ist nur innerhalb desselben Typs wie dem des Members oder innerhalb eines geschachtelten Typs möglich.</span><span class="sxs-lookup"><span data-stu-id="2a94d-340">Accessible only from within the same type as the member, or within a nested type.</span></span>
<span data-ttu-id="2a94d-341">family</span><span class="sxs-lookup"><span data-stu-id="2a94d-341">family</span></span> | <span data-ttu-id="2a94d-342">Alle</span><span class="sxs-lookup"><span data-stu-id="2a94d-342">All</span></span> | <span data-ttu-id="2a94d-343">Zugriff innerhalb desselben Typs wie dem des Members und von abgeleiteten Typen möglich, die davon erben.</span><span class="sxs-lookup"><span data-stu-id="2a94d-343">Accessible from within the same type as the member, and from derived types that inherit from it.</span></span>
<span data-ttu-id="2a94d-344">assembly</span><span class="sxs-lookup"><span data-stu-id="2a94d-344">assemby</span></span> | <span data-ttu-id="2a94d-345">Alle</span><span class="sxs-lookup"><span data-stu-id="2a94d-345">All</span></span> | <span data-ttu-id="2a94d-346">Zugriff nur in der Assembly möglich, in der der Typ definiert ist.</span><span class="sxs-lookup"><span data-stu-id="2a94d-346">Accessible only in the assembly in which the type is defined.</span></span>
<span data-ttu-id="2a94d-347">family und assembly</span><span class="sxs-lookup"><span data-stu-id="2a94d-347">family and assembly</span></span> | <span data-ttu-id="2a94d-348">Alle</span><span class="sxs-lookup"><span data-stu-id="2a94d-348">All</span></span> | <span data-ttu-id="2a94d-349">Zugriff nur von Typen möglich, die sowohl über den Zugriffstyp family als auch assembly verfügen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-349">Accessible only from types that qualify for both family and assembly access.</span></span>
<span data-ttu-id="2a94d-350">family oder assembly</span><span class="sxs-lookup"><span data-stu-id="2a94d-350">family or assemby</span></span> | <span data-ttu-id="2a94d-351">Alle</span><span class="sxs-lookup"><span data-stu-id="2a94d-351">All</span></span> | <span data-ttu-id="2a94d-352">Zugriff nur von Typen möglich, die über den Zugriffstyp "family" oder "assembly" verfügen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-352">Accessible only from types that qualify for either family or assembly access.</span></span>
<span data-ttu-id="2a94d-353">public</span><span class="sxs-lookup"><span data-stu-id="2a94d-353">public</span></span> | <span data-ttu-id="2a94d-354">Alle</span><span class="sxs-lookup"><span data-stu-id="2a94d-354">All</span></span> | <span data-ttu-id="2a94d-355">Zugriff von jedem Typ möglich.</span><span class="sxs-lookup"><span data-stu-id="2a94d-355">Accessible from any type.</span></span>
<span data-ttu-id="2a94d-356">final</span><span class="sxs-lookup"><span data-stu-id="2a94d-356">final</span></span> | <span data-ttu-id="2a94d-357">Methoden, Eigenschaften und Ereignisse</span><span class="sxs-lookup"><span data-stu-id="2a94d-357">Methods, properties, and events</span></span> | <span data-ttu-id="2a94d-358">Die virtuelle Methode kann in einem abgeleiteten Typ nicht überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-358">The virtual method cannot be overridden in a derived type.</span></span>
<span data-ttu-id="2a94d-359">initialize-only</span><span class="sxs-lookup"><span data-stu-id="2a94d-359">initialize-only</span></span> | <span data-ttu-id="2a94d-360">Felder</span><span class="sxs-lookup"><span data-stu-id="2a94d-360">Fields</span></span> | <span data-ttu-id="2a94d-361">Der Wert kann lediglich initialisiert werden. Nach der Initialisierung ist kein Schreibzugriff möglich.</span><span class="sxs-lookup"><span data-stu-id="2a94d-361">The value can only be initialized, and cannot be written after initialization.</span></span>
<span data-ttu-id="2a94d-362">instance</span><span class="sxs-lookup"><span data-stu-id="2a94d-362">instance</span></span> | <span data-ttu-id="2a94d-363">Felder, Methoden, Eigenschaften und Ereignisse</span><span class="sxs-lookup"><span data-stu-id="2a94d-363">Fields, methods, properties, and events</span></span> | <span data-ttu-id="2a94d-364">Wenn ein Member nicht als `static` (C#), `Shared` (Visual Basic), `virtual` (C#) oder `Overridable` (Visual Basic) gekennzeichnet ist, handelt es sich um einen Instanzmember (es ist kein instance-Schlüsselwort vorhanden).</span><span class="sxs-lookup"><span data-stu-id="2a94d-364">If a member is not marked as `static` (C#), `Shared` (Visual Basic), `virtual` (C#), or `Overridable` (Visual Basic),  it is an instance member (there is no instance keyword).</span></span> <span data-ttu-id="2a94d-365">Im Arbeitsspeicher befinden sich so viele Kopien dieser Member wie Objekte, von denen sie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-365">There will be as many copies of such members in memory as there are objects that use it.</span></span>
<span data-ttu-id="2a94d-366">literal</span><span class="sxs-lookup"><span data-stu-id="2a94d-366">literal</span></span> | <span data-ttu-id="2a94d-367">Felder</span><span class="sxs-lookup"><span data-stu-id="2a94d-367">Fields</span></span> | <span data-ttu-id="2a94d-368">Der dem Feld zugewiesene Wert ist ein fester, zur Kompilierungszeit bekannter Wert eines integrierten Werttyps.</span><span class="sxs-lookup"><span data-stu-id="2a94d-368">The value assigned to the field is a fixed value, known at compile time, of a built-in value type.</span></span> <span data-ttu-id="2a94d-369">Literalfelder werden zeitweise auch als Konstanten bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2a94d-369">Literal fields are sometimes referred to as constants.</span></span>
<span data-ttu-id="2a94d-370">newslot oder override</span><span class="sxs-lookup"><span data-stu-id="2a94d-370">newslot or override</span></span> | <span data-ttu-id="2a94d-371">Alle</span><span class="sxs-lookup"><span data-stu-id="2a94d-371">All</span></span> | <span data-ttu-id="2a94d-372">Definiert, wie der Member mit geerbten Membern mit identischer Signatur interagiert: `newslot` blendet Member mit identischer Signatur aus; `override` ersetzt die Definition einer geerbten virtuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="2a94d-372">Defines how the member interacts with inherited members that have the same signature: `newslot` hides inherited members that have the same signature; `override` replaces the definition of an inherited virtual method.</span></span> <span data-ttu-id="2a94d-373">Der Standardwert ist newslot.</span><span class="sxs-lookup"><span data-stu-id="2a94d-373">The default is newslot.</span></span>
<span data-ttu-id="2a94d-374">static</span><span class="sxs-lookup"><span data-stu-id="2a94d-374">static</span></span> | <span data-ttu-id="2a94d-375">Felder, Methoden, Eigenschaften und Ereignisse</span><span class="sxs-lookup"><span data-stu-id="2a94d-375">Fields, methods, properties, and events</span></span> | <span data-ttu-id="2a94d-376">Der Member gehört dem Typ an, mit dem er definiert wurde, und keiner bestimmten Instanz des Typs. Der Member existiert selbst dann, wenn keine Instanz des Typs erstellt wird, und wird von allen Instanzen des Typs gemeinsam genutzt.</span><span class="sxs-lookup"><span data-stu-id="2a94d-376">The member belongs to the type it is defined on, not to a particular instance of the type; the member exists even if an instance of the type is not created, and it is shared among all instances of the type.</span></span>
<span data-ttu-id="2a94d-377">virtual</span><span class="sxs-lookup"><span data-stu-id="2a94d-377">virtual</span></span> | <span data-ttu-id="2a94d-378">Methoden, Eigenschaften und Ereignisse</span><span class="sxs-lookup"><span data-stu-id="2a94d-378">Methods, properties, and events</span></span> | <span data-ttu-id="2a94d-379">Die Methode kann durch einen abgeleiteten Typ implementiert und entweder statisch oder dynamisch aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-379">The method can be implemented by a derived type and can be invoked either statically or dynamically.</span></span> <span data-ttu-id="2a94d-380">Beim dynamischen Aufruf bestimmt der Typ der Instanz, durch die der Aufruf zur Laufzeit ausgeführt wird (und nicht der zur Kompilierungszeit bekannte Typ), welche Implementierung der Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="2a94d-380">If dynamic invocation is used, the type of the instance that makes the call at run time (rather than the type known at compile time) determines which implementation of the method is called.</span></span> <span data-ttu-id="2a94d-381">Um eine Methode vom Typ virtual statisch aufzurufen, muss die Variable u. U. in einen Typ umgewandelt werden, der die gewünschte Methodenversion verwendet.</span><span class="sxs-lookup"><span data-stu-id="2a94d-381">To invoke a virtual method statically, the variable might have to be cast to a type that uses the desired version of the method.</span></span>

### <a name="overloading"></a><span data-ttu-id="2a94d-382">Überladen</span><span class="sxs-lookup"><span data-stu-id="2a94d-382">Overloading</span></span>

<span data-ttu-id="2a94d-383">Jeder Typmember verfügt über eine eindeutige Signatur.</span><span class="sxs-lookup"><span data-stu-id="2a94d-383">Each type member has a unique signature.</span></span> <span data-ttu-id="2a94d-384">Methodensignaturen bestehen aus dem Methodennamen und einer Parameterliste (die Reihenfolge und Typen der Argumente der Methode).</span><span class="sxs-lookup"><span data-stu-id="2a94d-384">Method signatures consist of the method name and a parameter list (the order and types of the method's arguments).</span></span> <span data-ttu-id="2a94d-385">Solange die Signaturen unterschiedlich sind, können innerhalb eines Typs mehrere Methoden mit demselben Namen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="2a94d-385">Multiple methods with the same name can be defined within a type as long as their signatures differ.</span></span> <span data-ttu-id="2a94d-386">Wenn zwei oder mehrere Methoden mit demselben Namen definiert sind, wird von einer "überladenen" Methode gesprochen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-386">When two or more methods with the same name are defined, the method is said to be overloaded.</span></span> <span data-ttu-id="2a94d-387">In [System.Char](xref:System.Char) wird z.B. die `IsDigit`-Methode überladen.</span><span class="sxs-lookup"><span data-stu-id="2a94d-387">For example, in [System.Char](xref:System.Char), the `IsDigit` method is overloaded.</span></span> <span data-ttu-id="2a94d-388">Eine Methode nimmt einen [Char](xref:System.Char) an.</span><span class="sxs-lookup"><span data-stu-id="2a94d-388">One method takes a [Char](xref:System.Char).</span></span> <span data-ttu-id="2a94d-389">Die andere Methode nimmt einen [String](xref:System.String) und einen [Int32](xref:System.Int32) an.</span><span class="sxs-lookup"><span data-stu-id="2a94d-389">The other method takes a [String](xref:System.String) and an [Int32](xref:System.Int32).</span></span> 

> [!NOTE]
> <span data-ttu-id="2a94d-390">Der Rückgabetyp wird nicht als Teil der Signatur einer Methode betrachtet.</span><span class="sxs-lookup"><span data-stu-id="2a94d-390">The return type is not considered part of a method's signature.</span></span> <span data-ttu-id="2a94d-391">Dies bedeutet, dass Methoden nicht überladen werden können, wenn sich nur ihr Rückgabetyp unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="2a94d-391">That is, methods cannot be overloaded if they differ only by return type.</span></span>

### <a name="inheriting-overriding-and-hiding-members"></a><span data-ttu-id="2a94d-392">Vererben, Überschreiben und Verdecken von Membern</span><span class="sxs-lookup"><span data-stu-id="2a94d-392">Inheriting, overriding, and hiding members</span></span>

<span data-ttu-id="2a94d-393">Ein abgeleiteter Typ erbt alle Member seines Basistyps. Dies bedeutet, dass diese Member für den abgeleiteten Typ definiert und verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="2a94d-393">A derived type inherits all members of its base type; that is, these members are defined on, and available to, the derived type.</span></span> <span data-ttu-id="2a94d-394">Das Verhalten oder die Merkmale geerbter Member können auf zwei Weisen geändert werden:</span><span class="sxs-lookup"><span data-stu-id="2a94d-394">The behavior or qualities of inherited members can be modified in two ways:</span></span> 

* <span data-ttu-id="2a94d-395">Ein abgeleiteter Typ kann einen geerbten Member verdecken, indem er einen neuen Member mit derselben Signatur definiert.</span><span class="sxs-lookup"><span data-stu-id="2a94d-395">A derived type can hide an inherited member by defining a new member with the same signature.</span></span> <span data-ttu-id="2a94d-396">Dies kann z. B. geschehen, um einen Member, der zuvor als public deklariert war, als private zu definieren, oder um ein neues Verhalten für eine geerbte Methode zu definieren, die mit `final` gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="2a94d-396">This might be done to make a previously public member private or to define new behavior for an inherited method that is marked as `final`.</span></span>

* <span data-ttu-id="2a94d-397">Ein abgeleiteter Typ kann eine geerbte virtuelle Methode überschreiben.</span><span class="sxs-lookup"><span data-stu-id="2a94d-397">A derived type can override an inherited virtual method.</span></span> <span data-ttu-id="2a94d-398">Die überschreibende Methode stellt eine neue Definition für die Methode bereit, die basierend auf dem Werttyp zur Laufzeit aufgerufen wird und nicht basierend auf dem zur Kompilierungszeit bekannten Variablentyp.</span><span class="sxs-lookup"><span data-stu-id="2a94d-398">The overriding method provides a new definition of the method that will be invoked based on the type of the value at run time rather than the type of the variable known at compile time.</span></span> <span data-ttu-id="2a94d-399">Eine virtuelle Methode kann nur von einer Methode überschrieben werden, wenn die virtuelle Methode nicht als `final` gekennzeichnet ist und die neue Methode mindestens dieselben Zugriffstypen unterstützt wie die virtuelle Methode.</span><span class="sxs-lookup"><span data-stu-id="2a94d-399">A method can override a virtual method only if the virtual method is not marked as `final` and the new method is at least as accessible as the virtual method.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a94d-400">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a94d-400">See also</span></span>

[<span data-ttu-id="2a94d-401">Typkonvertierung in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2a94d-401">Type conversion in the .NET Framework</span></span>](type-conversion.md)
