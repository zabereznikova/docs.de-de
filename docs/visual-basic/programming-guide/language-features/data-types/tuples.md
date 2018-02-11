---
title: Tupel in Visual Basic
ms.custom: 
ms.date: 04/23/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2653b9dc8a6ecbcb718c20be8bd6275edf4cfb6e
ms.sourcegitcommit: be1fb5d9447ad459bef22b91a91c72e3e0b2d916
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="tuples-visual-basic"></a><span data-ttu-id="527ac-102">Tupel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="527ac-102">Tuples (Visual Basic)</span></span>

<span data-ttu-id="527ac-103">Visual Basic 2017 ab, die Sprache Visual Basic bietet integrierte Unterstützung für Tupel, mit der, Tupel erstellen und den Zugriff auf die Elemente von Tupeln einfacher.</span><span class="sxs-lookup"><span data-stu-id="527ac-103">Starting with Visual Basic 2017, the Visual Basic language offers built-in support for tuples that makes creating tuples and accessing the elements of tuples easier.</span></span> <span data-ttu-id="527ac-104">Ein Tupel ist ein Lightweight-Datenstruktur, die eine bestimmte Anzahl und die Sequenz von Werten aufweist.</span><span class="sxs-lookup"><span data-stu-id="527ac-104">A tuple is a light-weight data structure that has a specific number and sequence of values.</span></span> <span data-ttu-id="527ac-105">Wenn Sie das Tupel instanziieren, definieren Sie die Anzahl und den Datentyp der einzelnen Wert (oder Element).</span><span class="sxs-lookup"><span data-stu-id="527ac-105">When you instantiate the tuple, you define the number and the data type of each value (or element).</span></span> <span data-ttu-id="527ac-106">Ein 2-Tupel (oder ein Paar) hat beispielsweise zwei Elemente auf.</span><span class="sxs-lookup"><span data-stu-id="527ac-106">For example, a 2-tuple (or pair) has two elements.</span></span> <span data-ttu-id="527ac-107">Die erste ist möglicherweise eine `Boolean` Wert, während die zweite ist eine `String`.</span><span class="sxs-lookup"><span data-stu-id="527ac-107">The first might be a `Boolean` value, while the second is a `String`.</span></span> <span data-ttu-id="527ac-108">Da Tupel mehrere Werte in ein einzelnes Objekt speichern erleichtern, werden sie häufig als einfache Möglichkeit, mehrere Werte zurückgegeben werden, von einer Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="527ac-108">Because tuples make it easy to store multiple values in a single object, they are often used as a lightweight way to return multiple values from a method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="527ac-109">Tupel unterstützt wird, muss die <xref:System.ValueTuple> Typ.</span><span class="sxs-lookup"><span data-stu-id="527ac-109">Tuple support requires the <xref:System.ValueTuple> type.</span></span> <span data-ttu-id="527ac-110">Wenn der .NET Framework-4.7 nicht installiert ist, müssen Sie das NuGet-Paket hinzufügen `System.ValueTuple`, die auf der NuGet Gallery verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="527ac-110">If the .NET Framework 4.7 is not installed, you must add the NuGet package `System.ValueTuple`, which is available on the NuGet Gallery.</span></span> <span data-ttu-id="527ac-111">Ohne dieses Paket können Sie erhalten einen Kompilierungsfehler wie "Vordefinierte Typ 'ValueTuple(Of,,,)' nicht definiert oder importiert wird."</span><span class="sxs-lookup"><span data-stu-id="527ac-111">Without this package, you may get a compilation error similar to, "Predefined type 'ValueTuple(Of,,,)' is not defined or imported."</span></span>

## <a name="instantiating-and-using-a-tuple"></a><span data-ttu-id="527ac-112">Instanziieren und verwenden ein Tupel</span><span class="sxs-lookup"><span data-stu-id="527ac-112">Instantiating and using a tuple</span></span>

<span data-ttu-id="527ac-113">Instanziieren Sie ein Tupel durch die Werte durch Kommas getrennte Instant Messaging-Diensten Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="527ac-113">You instantiate a tuple by enclosing its comma-delimited values im parentheses.</span></span> <span data-ttu-id="527ac-114">Jeder dieser Werte wird dann ein Feld des Tupels.</span><span class="sxs-lookup"><span data-stu-id="527ac-114">Each of those values then becomes a field of the tuple.</span></span> <span data-ttu-id="527ac-115">Z. B. der folgende Code definiert eine Triple (oder 3-Tupel) mit einem `Date` als ersten Wert ein `String` als den zweiten und eine `Boolean` als den dritten.</span><span class="sxs-lookup"><span data-stu-id="527ac-115">For example, the following code defines a triple (or 3-tuple) with a `Date` as its first value, a `String` as its second, and a `Boolean` as its third.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

<span data-ttu-id="527ac-116">Wird standardmäßig der Name jedes Felds in einem Tupel besteht aus der Zeichenfolge `Item` zusammen mit dem Feld einsbasierte Positionen im Tupel.</span><span class="sxs-lookup"><span data-stu-id="527ac-116">By default, the name of each field in a tuple consists of the string `Item` along with the field's one-based position in the tuple.</span></span> <span data-ttu-id="527ac-117">Für diese 3-Tupel die `Date` Feld ist `Item1`, `String` Feld ist `Item2`, und die `Boolean` Feld ist `Item3`.</span><span class="sxs-lookup"><span data-stu-id="527ac-117">For this 3-tuple, the `Date` field is `Item1`, the `String` field is `Item2`, and the `Boolean` field is `Item3`.</span></span> <span data-ttu-id="527ac-118">Das folgende Beispiel zeigt die Werte der Felder des Tupels in der vorherigen Codezeile instanziiert</span><span class="sxs-lookup"><span data-stu-id="527ac-118">The following example displays the values of fields of the tuple instantiated in the previous line of code</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

<span data-ttu-id="527ac-119">Die Felder eines Visual Basic-Tupels sind Lese-/ Schreibzugriff. Nachdem Sie ein Tupel instanziiert haben, können Sie dessen Werte ändern.</span><span class="sxs-lookup"><span data-stu-id="527ac-119">The fields of a Visual Basic tuple are read-write; after you've instantiated a tuple, you can modify its values.</span></span> <span data-ttu-id="527ac-120">Im folgende Beispiel ändert zwei der drei Felder des Tupels im vorherigen Beispiel erstellt und das Ergebnis wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="527ac-120">The following example modifies two of the three fields of the tuple created in the previous example and displays the result.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a><span data-ttu-id="527ac-121">Instanziieren und verwenden eine benannte Tupel</span><span class="sxs-lookup"><span data-stu-id="527ac-121">Instantiating and using a named tuple</span></span>

<span data-ttu-id="527ac-122">Statt die Standardnamen für ein Tupel Felder, instanziieren Sie ein *mit dem Namen Tupel* durch das Tupel-Elementen mit Ihren eigenen Namen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="527ac-122">Rather than using default names for a tuple's fields, you can instantiate a *named tuple* by assigning your own names to the tuple's elements.</span></span> <span data-ttu-id="527ac-123">Das Tupel-Felder können dann durch ihre zugewiesenen Namen zugegriffen werden *oder* durch ihre Standardnamen.</span><span class="sxs-lookup"><span data-stu-id="527ac-123">The tuple's fields can then be accessed by their assigned names *or* by their default names.</span></span> <span data-ttu-id="527ac-124">Das folgende Beispiel instanziiert die gleiche 3-Tupel als zuvor mit dem Unterschied, dass es das erste Feld explizit benannt `EventDate`, das zweite `Name`, und der dritte `IsHoliday`.</span><span class="sxs-lookup"><span data-stu-id="527ac-124">The following example instantiates the same 3-tuple as previously, except that it explicitly names the first field `EventDate`, the second `Name`, and the third `IsHoliday`.</span></span> <span data-ttu-id="527ac-125">Es dann zeigt die Feldwerte, ändert sie und die Feldwerte erneut angezeigt.</span><span class="sxs-lookup"><span data-stu-id="527ac-125">It then displays the field values, modifies them, and displays the field values again.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="527ac-126">Abgeleitete Tupel Elementnamen</span><span class="sxs-lookup"><span data-stu-id="527ac-126">Inferred tuple element names</span></span>

<span data-ttu-id="527ac-127">Beginnend mit Visual Basic 15.3, kann Visual Basic die Namen der Tupelelemente ableiten; Sie müssen keinen explizit zuweisen.</span><span class="sxs-lookup"><span data-stu-id="527ac-127">Starting with Visual Basic 15.3, Visual Basic can infer the names of tuple elements; you do not have to assign them explicitly.</span></span> <span data-ttu-id="527ac-128">Abgeleitete Tupel Namen sind hilfreich, wenn Sie ein Tupel aus einem Satz von Variablen initialisieren, und der Elementname Tupel mit dem Variablennamen identisch sein sollen.</span><span class="sxs-lookup"><span data-stu-id="527ac-128">Inferred tuple names are useful when you initialize a tuple from a set of variables, and you want the tuple element name to be the same as the variable name.</span></span> 

<span data-ttu-id="527ac-129">Das folgende Beispiel erstellt eine `stateInfo` Tupel, das drei explizit enthält benannten Elementen, `state`, `stateName`, und `capital`.</span><span class="sxs-lookup"><span data-stu-id="527ac-129">The following example creates a `stateInfo` tuple that contains three explicitly named elements, `state`, `stateName`, and `capital`.</span></span> <span data-ttu-id="527ac-130">Beachten Sie, dass bei der Benennung der Elemente, Tupel Initialisierung die Anweisung einfach benannten Elemente der Werte von gleichnamigen Variablen weist.</span><span class="sxs-lookup"><span data-stu-id="527ac-130">Note that, in naming the elements, the tuple initialization statement simply assigns the named elements the values of the identically named variables.</span></span>

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]
 
<span data-ttu-id="527ac-131">Da Elemente und Variablen, die denselben Namen haben, kann die Visual Basic-Compiler die Namen der Felder, wie im folgenden Beispiel gezeigt ableiten.</span><span class="sxs-lookup"><span data-stu-id="527ac-131">Because elements and variables have the same name, the Visual Basic compiler can infer the names of the fields, as the following example shows.</span></span>

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

<span data-ttu-id="527ac-132">Um interred Tupel Elementnamen zu aktivieren, müssen Sie die Version von Visual Basic-Compiler in Visual Basic-Projekt verwendet definieren (\*.vbproj) Datei:</span><span class="sxs-lookup"><span data-stu-id="527ac-132">To enable interred tuple element names, you must define the version of the Visual Basic compiler to use in your Visual Basic project (\*.vbproj) file:</span></span> 

```xml 
<PropertyGroup> 
  <LangVersion>15.3</LangVersion> 
</PropertyGroup> 

The version number can be any version of the Visual Basic compiler starting with 15.3. Rather than hard-coding a specific compiler version, you can also specify "Latest" as the value of `LangVersion` to compile with the most recent version of the Visual Basic compiler installed on your system.

In some cases, the Visual Basic compiler cannot infer the tuple element name from the candidate name, and the tuple field can only be referenced using its default name, such as `Item1`, `Item2`, etc. These include:

- The candidate name is the same as the name of a tuple member, such as `Item3`, `Rest`, or `ToString`.

- The candidate name is duplicated in the tuple.
 
When field name inference fails, Visual Basic does not generate a compiler error, nor is an exception thrown at runtime. Instead, tuple fields must be referenced by their predefined names, such as `Item1` and `Item2`. 
  
## Tuples versus structures

A Visual Basic tuple is a value type that is an instance of one of the a **System.ValueTuple** generic types. For example, the `holiday` tuple defined in the previous example is an instance of the <xref:System.ValueTuple%603> structure. It is designed to be a lightweight container for data. Since the tuple aims to make it easy to create an object with multiple data items, it lacks some of the features that a custom structure might have. These include:

- Customer members. You cannot define your own properties, methods, or events for a tuple.

- Validation. You cannot validate the data assigned to fields.

- Immutability. Visual Basic tuples are mutable. In contrast, a custom structure allows you to control whether an instance is mutable or immutable.

If custom members, property and field validation, or immutability are important, you should use the Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) statement to define a custom value type.

A Visual Basic tuple does inherit the members of its **ValueTuple** type. In addition to its fields, these include the following methods:

| Member | Description |
| ---|---|
| CompareTo | Compares the current tuple to another tuple with the same number of elements. |
| Equals | Determines whether the current tuple is equal to another tuple or object. |
| GetHashCode | Calculates the hash code for the current instance. |
| ToString | Returns the string representation of this tuple, which takes the form `(Item1, Item2...)`, where `Item1` and `Item2` represent the values of the tuple's fields. |

In addition, the **ValueTuple** types implement <xref:System.Collections.IStructuralComparable> and <xref:System.Collections.IStructuralEquatable> interfaces, which allow you to define customer comparers.

## Assignment and tuples

Visual Basic supports assignment between tuple types that have the same number of fields. The field types can be converted if one of the following is true:

- The source and target field are of the same type.

- A widening (or implicit) conversion of the source type to the target type is defined. 

- `Option Strict` is `On`, and a narrowing (or explicit) conversion of the source type to the target type is defined. This conversion can throw an exception if the source value is outside the range of the target type.

Other conversions are not considered for assignments. Let's look at the kinds of assignments that are allowed between tuple types.

Consider these variables used in the following examples:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

The first two variables, `unnamed` and `anonymous`, do not have semantic names provided for the fields. Their field names are the default `Item1` and `Item2`. The last two variables, `named` and `differentName` have semantic field names. Note that these two tuples have different names for the fields.

All four of these tuples have the same number of fields (referred to as 'arity'), and the types of those fields are identical. Therefore, all of these assignments work:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

Notice that the names of the tuples are not assigned. The values of the fields are assigned following the order of the fields in the tuple.

Finally, notice that we can assign the `named` tuple to the `conversion` tuple, even though the first field of `named` is an `Integer`, and the first field of `conversion` is a `Long`. This assignment succeeds because converting an `Integer` to a `Long` is a widening conversion.

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

Tuples with different numbers of fields are not assignable:

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a><span data-ttu-id="527ac-133">Tupel als Methodenrückgabewert</span><span class="sxs-lookup"><span data-stu-id="527ac-133">Tuples as method return values</span></span>

<span data-ttu-id="527ac-134">Eine Methode kann nur einen einzelnen Wert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="527ac-134">A method can return only a single value.</span></span> <span data-ttu-id="527ac-135">In vielen Fällen jedoch soll einen Methodenaufruf an mehrere Werte zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="527ac-135">Frequently, though, you'd like a method call to return multiple values.</span></span> <span data-ttu-id="527ac-136">Es gibt mehrere Möglichkeiten, diese Einschränkung zu umgehen:</span><span class="sxs-lookup"><span data-stu-id="527ac-136">There are several ways to work around this limitation:</span></span>

- <span data-ttu-id="527ac-137">Sie können eine benutzerdefinierte Klasse oder Struktur erstellen, dessen Eigenschaften oder Felder darstellen, von der Methode zurückgegebenen Werte.</span><span class="sxs-lookup"><span data-stu-id="527ac-137">You can create a custom class or structure whose properties or fields represent values returned by the method.</span></span> <span data-ttu-id="527ac-138">Daher ist eine Heavyweight-Lösung. Es erfordert, dass Sie einen benutzerdefinierten Typ definieren, deren einzige zum Abrufen der Werte aus einem Methodenaufruf dient.</span><span class="sxs-lookup"><span data-stu-id="527ac-138">Thus is a heavyweight solution; it requires that you define a custom type whose only purpose is to retrieve values from a method call.</span></span>

- <span data-ttu-id="527ac-139">Sie können einen einzelnen Wert zurückgeben, von der Methode und die verbleibenden Werte zurück, durch die sie als Verweis an die Methode übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="527ac-139">You can return a single value from the method, and return the remaining values by passing them by reference to the method.</span></span> <span data-ttu-id="527ac-140">Führen Sie dazu den Aufwand für das Instanziieren einer Variablen und Risiken, die den Wert der Variablen, die Sie als Verweis übergeben versehentlich überschrieben.</span><span class="sxs-lookup"><span data-stu-id="527ac-140">This involves the overhead of instantiating a variable and risks inadvertently overwriting the value of the variable that you pass by reference.</span></span>

- <span data-ttu-id="527ac-141">Sie können ein Tupel, eine einfache Lösung bietet für das Abrufen von mehreren Rückgabewerten.</span><span class="sxs-lookup"><span data-stu-id="527ac-141">You can use a tuple, which provides a lightweight solution to retrieving multiple return values.</span></span>

<span data-ttu-id="527ac-142">Z. B. die **TryParse** Methoden in .NET Rückgabe einer `Boolean` Wert, der angibt, ob der Analysevorgang erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="527ac-142">For example, the **TryParse** methods in .NET return a `Boolean` value that indicates whether the parsing operation succeeded.</span></span> <span data-ttu-id="527ac-143">Das Ergebnis des Analysevorgangs wird in einer Variablen als Verweis an die Methode übergebene zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="527ac-143">The result of the parsing operation is returned in a variable passed by reference to the method.</span></span> <span data-ttu-id="527ac-144">In der Regel wird ein Aufruf der einer Analysemethode, z. B. <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> sieht wie folgt:</span><span class="sxs-lookup"><span data-stu-id="527ac-144">Normally, a call to the a parsing method such as <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> looks like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

<span data-ttu-id="527ac-145">Wir können ein Tupel aus der Analysevorgang zurückgeben, wenn es den Aufruf zum Umschließen der <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> Methode in eigenen-Methode.</span><span class="sxs-lookup"><span data-stu-id="527ac-145">We can return a tuple from the parsing operation if we wrap the call to the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method in our own method.</span></span> <span data-ttu-id="527ac-146">Im folgenden Beispiel `NumericLibrary.ParseInteger` Aufrufe der <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> Methode und eine benannte Tupel mit zwei Elementen zurück.</span><span class="sxs-lookup"><span data-stu-id="527ac-146">In the following example, `NumericLibrary.ParseInteger` calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method and returns a named tuple with two elements.</span></span> 

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

<span data-ttu-id="527ac-147">Sie können dann die Methode mit Code wie folgt aufrufen:</span><span class="sxs-lookup"><span data-stu-id="527ac-147">You can then call the method with code like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a><span data-ttu-id="527ac-148">Visual Basic-Tupel und Tupel in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="527ac-148">Visual Basic tuples and tuples in the .NET Framework</span></span>

<span data-ttu-id="527ac-149">Ein Visual Basic-Tupel ist eine Instanz einer von der **System.ValueTuple** generischen Typen, die in der .NET Framework-4.7 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="527ac-149">A Visual Basic tuple is an instance of one of the **System.ValueTuple** generic types, which were introduced in the .NET Framework 4.7.</span></span> <span data-ttu-id="527ac-150">.NET Framework enthält auch eine Reihe von generischen **System.Tuple** Klassen.</span><span class="sxs-lookup"><span data-stu-id="527ac-150">The .NET Framework also includes a set of generic **System.Tuple** classes.</span></span> <span data-ttu-id="527ac-151">Diese Klassen unterscheiden sich jedoch von Visual Basic-Tupeln und **System.ValueTuple** generische Typen, die eine Reihe von Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="527ac-151">These classes, however, differ from Visual Basic tuples and the **System.ValueTuple** generic types in a number of ways:</span></span>

- <span data-ttu-id="527ac-152">Die Elemente der **Tupel** Klassen sind Eigenschaften, die mit dem Namen `Item1`, `Item2`und so weiter.</span><span class="sxs-lookup"><span data-stu-id="527ac-152">The elements of the **Tuple** classes are properties named `Item1`, `Item2`, and so on.</span></span> <span data-ttu-id="527ac-153">In Visual Basic-Tupeln und **ValueTuple** Tupelelementen-Datentypen sind Felder.</span><span class="sxs-lookup"><span data-stu-id="527ac-153">In Visual Basic tuples and the **ValueTuple** types, tuple elements are fields.</span></span>

- <span data-ttu-id="527ac-154">Sie können keine Elemente des aussagekräftige Namen zuweisen eine **Tupel** Instanz oder eine **ValueTuple** Instanz.</span><span class="sxs-lookup"><span data-stu-id="527ac-154">You cannot assign meaningful names to the elements of a **Tuple** instance or of a **ValueTuple** instance.</span></span> <span data-ttu-id="527ac-155">Visual Basic können Sie Namen zuweisen, die die Bedeutung der Felder zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="527ac-155">Visual Basic allows you to assign names that communicate the meaning of the fields.</span></span>

- <span data-ttu-id="527ac-156">Die Eigenschaften einer **Tupel** Instanz schreibgeschützt sind, die Tupel sind unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="527ac-156">The properties of a **Tuple** instance are read-only; the tuples are immutable.</span></span> <span data-ttu-id="527ac-157">In Visual Basic-Tupeln und **ValueTuple** Typen Tupel Felder sind Lese-/ Schreibzugriff; die Tupel sind änderbar.</span><span class="sxs-lookup"><span data-stu-id="527ac-157">In Visual Basic tuples and the **ValueTuple** types, tuple fields are read-write; the tuples are mutable.</span></span>

- <span data-ttu-id="527ac-158">Die generische **Tupel** -Typen sind Referenztypen.</span><span class="sxs-lookup"><span data-stu-id="527ac-158">The generic **Tuple** types are reference types.</span></span> <span data-ttu-id="527ac-159">Mit diesen **Tupel** Typen bedeutet, dass das Zuordnen von Objekten.</span><span class="sxs-lookup"><span data-stu-id="527ac-159">Using these **Tuple** types means allocating objects.</span></span> <span data-ttu-id="527ac-160">Auf dem langsamsten Pfad kann das einen messbaren Einfluss auf die Leistung Ihrer Anwendungen haben.</span><span class="sxs-lookup"><span data-stu-id="527ac-160">On hot paths, this can have a measurable impact on your application's performance.</span></span> <span data-ttu-id="527ac-161">Visual Basic-Tupeln und **ValueTuple** Typen sind Werttypen.</span><span class="sxs-lookup"><span data-stu-id="527ac-161">Visual Basic tuples and the **ValueTuple** types are value types.</span></span>

<span data-ttu-id="527ac-162">Erweiterungsmethoden in den <xref:System.TupleExtensions> Klasse erleichtern das Konvertieren zwischen Tupel Visual Basic und .NET **Tupel** Objekte.</span><span class="sxs-lookup"><span data-stu-id="527ac-162">Extension methods in the <xref:System.TupleExtensions> class make it easy to convert between Visual Basic tuples and .NET **Tuple** objects.</span></span> <span data-ttu-id="527ac-163">Die **ToTuple** Methode konvertiert ein Visual Basic-Tupel in einer .NET **Tupel** -Objekt, und die **ToValueTuple** Methode konvertiert ein .NET **Tupel** Um ein Visual Basic-Tupel-Objekt.</span><span class="sxs-lookup"><span data-stu-id="527ac-163">The **ToTuple** method converts a Visual Basic tuple to a .NET **Tuple** object, and the **ToValueTuple** method converts a .NET **Tuple** object to a Visual Basic tuple.</span></span>

<span data-ttu-id="527ac-164">Das folgende Beispiel erstellt ein Tupel, konvertiert es in einer .NET **Tupel** Objekt und konvertiert sie zurück in ein Visual Basic-Tupel.</span><span class="sxs-lookup"><span data-stu-id="527ac-164">The following example creates a tuple, converts it to a .NET **Tuple** object, and converts it back to a Visual Basic tuple.</span></span> <span data-ttu-id="527ac-165">Im Beispiel vergleicht dieses Tupel mit dem ursprünglichen Stellen Sie sicher, dass sie gleich sind.</span><span class="sxs-lookup"><span data-stu-id="527ac-165">The example then compares this tuple with the original one to ensure that they are equal.</span></span>

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a><span data-ttu-id="527ac-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="527ac-166">See also</span></span>

[<span data-ttu-id="527ac-167">Sprachreferenz zu Visual Basic</span><span class="sxs-lookup"><span data-stu-id="527ac-167">Visual Basic Language Reference</span></span>](index.md)  
