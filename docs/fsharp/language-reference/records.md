---
title: Datensätze
description: 'Erfahren Sie, wie F #-Datensätze einfache Aggregate benannter Werte darstellen, optional mit Membern.'
ms.date: 08/15/2020
ms.openlocfilehash: 03de96b9c53bc21e7a7723a15d2a8451d100ba76
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682028"
---
# <a name="records"></a><span data-ttu-id="0e2f4-103">Datensätze</span><span class="sxs-lookup"><span data-stu-id="0e2f4-103">Records</span></span>

<span data-ttu-id="0e2f4-104">Datensätze stellen einfache Aggregate benannter Werte dar, optional mit Membern.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-104">Records represent simple aggregates of named values, optionally with members.</span></span> <span data-ttu-id="0e2f4-105">Sie können entweder Strukturen oder Verweis Typen sein.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-105">They can either be structs or reference types.</span></span>  <span data-ttu-id="0e2f4-106">Standardmäßig handelt es sich dabei um Verweis Typen.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-106">They are reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="0e2f4-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e2f4-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] typename =
    { [ mutable ] label1 : type1;
      [ mutable ] label2 : type2;
      ... }
    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="0e2f4-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0e2f4-108">Remarks</span></span>

<span data-ttu-id="0e2f4-109">In der vorherigen Syntax ist *tykame* der Name des Daten Satz Typs, *Label1* und *Label2* sind Namen von Werten, die als *Bezeichnungen* bezeichnet werden, und *Typ1* und *Typ2* sind die Typen dieser Werte.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-109">In the previous syntax, *typename* is the name of the record type, *label1* and *label2* are names of values, referred to as *labels*, and *type1* and *type2* are the types of these values.</span></span> <span data-ttu-id="0e2f4-110">"Element *-List* " ist die optionale Liste der Member für den Typ.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-110">*member-list* is the optional list of members for the type.</span></span>  <span data-ttu-id="0e2f4-111">Mit dem-Attribut können Sie `[<Struct>]` einen Strukturdaten Satz anstelle eines Datensatzes erstellen, bei dem es sich um einen Verweistyp handelt.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-111">You can use the `[<Struct>]` attribute to create a struct record rather than a record which is a reference type.</span></span>

<span data-ttu-id="0e2f4-112">Hier einige Beispiele.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-112">Following are some examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

<span data-ttu-id="0e2f4-113">Wenn sich jede Bezeichnung in einer separaten Zeile befindet, ist das Semikolon optional.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-113">When each label is on a separate line, the semicolon is optional.</span></span>

<span data-ttu-id="0e2f4-114">Sie können Werte in Ausdrücken festlegen, die als *Daten Satz Ausdrücke* bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-114">You can set values in expressions known as *record expressions*.</span></span> <span data-ttu-id="0e2f4-115">Der Compiler leitet den Typ von den verwendeten Bezeichnungen ab (wenn sich die Bezeichnungen ausreichend von denen anderer Daten Satz Typen unterscheiden).</span><span class="sxs-lookup"><span data-stu-id="0e2f4-115">The compiler infers the type from the labels used (if the labels are sufficiently distinct from those of other record types).</span></span> <span data-ttu-id="0e2f4-116">Geschweifte Klammern ({}) schließen den Daten Satz Ausdruck ein.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-116">Braces ({ }) enclose the record expression.</span></span> <span data-ttu-id="0e2f4-117">Der folgende Code zeigt einen Datensatz-Ausdruck, der einen Datensatz mit drei float-Elementen mit den Bezeichnungen `x` , und initialisiert `y` `z` .</span><span class="sxs-lookup"><span data-stu-id="0e2f4-117">The following code shows a record expression that initializes a record with three float elements with labels `x`, `y` and `z`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

<span data-ttu-id="0e2f4-118">Verwenden Sie das gekürzte Formular nicht, wenn ein anderer Typ vorhanden sein könnte, der auch über dieselben Bezeichnungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-118">Do not use the shortened form if there could be another type that also has the same labels.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

<span data-ttu-id="0e2f4-119">Die Bezeichnungen des zuletzt deklarierten Typs haben Vorrang vor denen des zuvor deklarierten Typs. im vorherigen Beispiel wird daher als `mypoint3D` abgeleitet `Point3D` .</span><span class="sxs-lookup"><span data-stu-id="0e2f4-119">The labels of the most recently declared type take precedence over those of the previously declared type, so in the preceding example, `mypoint3D` is inferred to be `Point3D`.</span></span> <span data-ttu-id="0e2f4-120">Sie können den Daten Satz Typen explizit angeben, wie im folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-120">You can explicitly specify the record type, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

<span data-ttu-id="0e2f4-121">Methoden können für Daten Satz Typen genau wie für Klassentypen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-121">Methods can be defined for record types just as for class types.</span></span>

## <a name="creating-records-by-using-record-expressions"></a><span data-ttu-id="0e2f4-122">Erstellen von Datensätzen mithilfe von Daten Satz Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="0e2f4-122">Creating Records by Using Record Expressions</span></span>

<span data-ttu-id="0e2f4-123">Sie können Datensätze mit den Bezeichnungen initialisieren, die im Datensatz definiert sind.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-123">You can initialize records by using the labels that are defined in the record.</span></span> <span data-ttu-id="0e2f4-124">Ein Ausdruck, der dies bewirkt, wird als *Daten Satz Ausdruck* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-124">An expression that does this is referred to as a *record expression*.</span></span> <span data-ttu-id="0e2f4-125">Verwenden Sie geschweifte Klammern, um den Daten Satz Ausdruck einzuschließen und das Semikolon als Trennzeichen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-125">Use braces to enclose the record expression and use the semicolon as a delimiter.</span></span>

<span data-ttu-id="0e2f4-126">Im folgenden Beispiel wird gezeigt, wie ein Datensatz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-126">The following example shows how to create a record.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

<span data-ttu-id="0e2f4-127">Die Semikolons nach dem letzten Feld im Daten Satz Ausdruck und in der Typdefinition sind optional, unabhängig davon, ob sich die Felder in einer Zeile befinden.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-127">The semicolons after the last field in the record expression and in the type definition are optional, regardless of whether the fields are all in one line.</span></span>

<span data-ttu-id="0e2f4-128">Wenn Sie einen Datensatz erstellen, müssen Sie Werte für jedes Feld angeben.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-128">When you create a record, you must supply values for each field.</span></span> <span data-ttu-id="0e2f4-129">Sie können nicht auf die Werte anderer Felder im Initialisierungs Ausdruck für ein beliebiges Feld verweisen.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-129">You cannot refer to the values of other fields in the initialization expression for any field.</span></span>

<span data-ttu-id="0e2f4-130">Im folgenden Code wird der Typ von `myRecord2` aus den Namen der Felder abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-130">In the following code, the type of `myRecord2` is inferred from the names of the fields.</span></span> <span data-ttu-id="0e2f4-131">Optional können Sie den Typnamen explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-131">Optionally, you can specify the type name explicitly.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="0e2f4-132">Eine andere Form der Daten Satz Erstellung kann nützlich sein, wenn Sie einen vorhandenen Datensatz kopieren und möglicherweise einige der Feldwerte ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-132">Another form of record construction can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span> <span data-ttu-id="0e2f4-133">Dies wird in der folgenden Codezeile veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-133">The following line of code illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

<span data-ttu-id="0e2f4-134">Diese Form des Daten Satz Ausdrucks wird als *Kopier-und Update Daten Satz Ausdruck* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-134">This form of the record expression is called the *copy and update record expression*.</span></span>

<span data-ttu-id="0e2f4-135">Datensätze sind standardmäßig unveränderlich. mithilfe eines Kopier-und Update Ausdrucks können Sie jedoch problemlos geänderte Datensätze erstellen.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-135">Records are immutable by default; however, you can easily create modified records by using a copy and update expression.</span></span> <span data-ttu-id="0e2f4-136">Sie können auch explizit ein änderbares Feld angeben.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-136">You can also explicitly specify a mutable field.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

<span data-ttu-id="0e2f4-137">Verwenden Sie das DefaultValue-Attribut nicht mit Datensatz-Feldern.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-137">Don't use the DefaultValue attribute with record fields.</span></span> <span data-ttu-id="0e2f4-138">Ein besserer Ansatz besteht darin, Standard Instanzen von Datensätzen mit Feldern zu definieren, die mit Standardwerten initialisiert werden. Anschließend können Sie mithilfe eines Ausdrucks zum Kopieren und Aktualisieren von Datensätzen alle Felder festlegen, die von den Standardwerten abweichen.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-138">A better approach is to define default instances of records with fields that are initialized to default values and then use a copy and update record expression to set any fields that differ from the default values.</span></span>

```fsharp
// Rather than use [<DefaultValue>], define a default record.
type MyRecord =
    { Field1 : int
      Field2 : int }

let defaultRecord1 = { Field1 = 0; Field2 = 0 }
let defaultRecord2 = { Field1 = 1; Field2 = 25 }

// Use the with keyword to populate only a few chosen fields
// and leave the rest with default values.
let rr3 = { defaultRecord1 with Field2 = 42 }
```

## <a name="creating-mutually-recursive-records"></a><span data-ttu-id="0e2f4-139">Erstellen von rekursiven Datensätzen</span><span class="sxs-lookup"><span data-stu-id="0e2f4-139">Creating Mutually Recursive Records</span></span>

<span data-ttu-id="0e2f4-140">Wenn Sie einen Datensatz erstellen, ist es möglicherweise von einem anderen Typ abhängig, den Sie später definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-140">Sometime when creating a record, you may want to have it depend on another type that you would like to define afterwards.</span></span> <span data-ttu-id="0e2f4-141">Dies ist ein Kompilierungsfehler, es sei denn, Sie definieren die Daten Satz Typen, die gegenseitig rekursiv</span><span class="sxs-lookup"><span data-stu-id="0e2f4-141">This is a compile error unless you define the record types to be mutually recursive.</span></span>

<span data-ttu-id="0e2f4-142">Das Definieren von gegenseitig rekursiven Datensätzen erfolgt mit dem `and` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-142">Defining mutually recursive records is done with the `and` keyword.</span></span> <span data-ttu-id="0e2f4-143">Auf diese Weise können Sie zwei oder mehr Daten Satz Typen miteinander verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-143">This lets you link 2 or more record types together.</span></span>

<span data-ttu-id="0e2f4-144">Der folgende Code definiert z. b. einen `Person` -Typ und den- `Address` Typ als gegenseitig rekursiv:</span><span class="sxs-lookup"><span data-stu-id="0e2f4-144">For example, the following code defines a `Person` and `Address` type as mutually recursive:</span></span>

```fsharp
// Create a Person type and use the Address type that is not defined
type Person =
  { Name: string
    Age: int
    Address: Address }
// Define the Address type which is used in the Person record
and Address =
  { Line1: string
    Line2: string
    PostCode: string
    Occupant: Person }
```

<span data-ttu-id="0e2f4-145">Wenn Sie das vorherige Beispiel ohne das `and` Schlüsselwort definieren, würde es nicht kompiliert.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-145">If you were to define the previous example without the `and` keyword, then it would not compile.</span></span> <span data-ttu-id="0e2f4-146">Das `and` Schlüsselwort ist für gegenseitig rekursive Definitionen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-146">The `and` keyword is required for mutually recursive definitions.</span></span>

## <a name="pattern-matching-with-records"></a><span data-ttu-id="0e2f4-147">Musterabgleich mit Datensätzen</span><span class="sxs-lookup"><span data-stu-id="0e2f4-147">Pattern Matching with Records</span></span>

<span data-ttu-id="0e2f4-148">Datensätze können mit Musterabgleich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-148">Records can be used with pattern matching.</span></span> <span data-ttu-id="0e2f4-149">Sie können einige Felder explizit angeben und Variablen für andere Felder bereitstellen, die zugewiesen werden, wenn eine Entsprechung auftritt.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-149">You can specify some fields explicitly and provide variables for other fields that will be assigned when a match occurs.</span></span> <span data-ttu-id="0e2f4-150">Dies wird im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-150">The following code example illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

<span data-ttu-id="0e2f4-151">Die Ausgabe dieses Codes lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-151">The output of this code is as follows.</span></span>

```console
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="records-and-members"></a><span data-ttu-id="0e2f4-152">Datensätze und Mitglieder</span><span class="sxs-lookup"><span data-stu-id="0e2f4-152">Records and members</span></span>

<span data-ttu-id="0e2f4-153">Sie können Elemente für Datensätze ähnlich wie bei Klassen angeben.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-153">You can specify members on records much like you can with classes.</span></span> <span data-ttu-id="0e2f4-154">Felder werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-154">There is no support for fields.</span></span> <span data-ttu-id="0e2f4-155">Ein gängiger Ansatz besteht darin, einen `Default` statischen Member für die einfache Daten Satz Erstellung zu definieren:</span><span class="sxs-lookup"><span data-stu-id="0e2f4-155">A common approach is to define a `Default` static member for easy record construction:</span></span>

```fsharp
type Person =
  { Name: string
    Age: int
    Address: string }

    static member Default =
        { Name = "Phillip"
          Age = 12
          Address = "123 happy fun street" }

let defaultPerson = Person.Default
```

<span data-ttu-id="0e2f4-156">Wenn Sie einen selbst Bezeichner verwenden, verweist dieser Bezeichner auf die Instanz des Datensatzes, dessen Member aufgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="0e2f4-156">If you use a self identifier, that identifier refers to the instance of the record whose member is called:</span></span>

```fsharp
type Person =
  { Name: string
    Age: int
    Address: string }

    member this.WeirdToString() =
        this.Name + this.Address + string this.Age

let p = { Name = "a"; Age = 12; Address = "abc123" }
let weirdString = p.WeirdToString()
```

## <a name="differences-between-records-and-classes"></a><span data-ttu-id="0e2f4-157">Unterschiede zwischen Datensätzen und Klassen</span><span class="sxs-lookup"><span data-stu-id="0e2f4-157">Differences Between Records and Classes</span></span>

<span data-ttu-id="0e2f4-158">Daten Satz Felder unterscheiden sich von Klassen darin, dass Sie automatisch als Eigenschaften verfügbar gemacht werden und beim Erstellen und Kopieren von Datensätzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-158">Record fields differ from classes in that they are automatically exposed as properties, and they are used in the creation and copying of records.</span></span> <span data-ttu-id="0e2f4-159">Die Daten Satz Erstellung unterscheidet sich auch von der Klassen Erstellung</span><span class="sxs-lookup"><span data-stu-id="0e2f4-159">Record construction also differs from class construction.</span></span> <span data-ttu-id="0e2f4-160">In einem Daten Recordtyp können Sie keinen Konstruktor definieren.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-160">In a record type, you cannot define a constructor.</span></span> <span data-ttu-id="0e2f4-161">Stattdessen gilt die in diesem Thema beschriebene Konstruktions Syntax.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-161">Instead, the construction syntax described in this topic applies.</span></span> <span data-ttu-id="0e2f4-162">Klassen haben keine direkte Beziehung zwischen Konstruktorparametern, Feldern und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-162">Classes have no direct relationship between constructor parameters, fields, and properties.</span></span>

<span data-ttu-id="0e2f4-163">Wie Union-und Strukturtypen haben Datensätze strukturelle Gleichheits Semantik.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-163">Like union and structure types, records have structural equality semantics.</span></span> <span data-ttu-id="0e2f4-164">Klassen verfügen über eine Verweis Gleichheits Semantik.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-164">Classes have reference equality semantics.</span></span> <span data-ttu-id="0e2f4-165">Dies wird im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-165">The following code example demonstrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

<span data-ttu-id="0e2f4-166">Die Ausgabe dieses Codes lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0e2f4-166">The output of this code is as follows:</span></span>

```console
The records are equal.
```

<span data-ttu-id="0e2f4-167">Wenn Sie denselben Code mit Klassen schreiben, sind die beiden Klassen Objekte ungleich, da die beiden Werte zwei Objekte auf dem Heap darstellen und nur die Adressen verglichen werden würden (es sei denn, der Klassentyp überschreibt die- `System.Object.Equals` Methode).</span><span class="sxs-lookup"><span data-stu-id="0e2f4-167">If you write the same code with classes, the two class objects would be unequal because the two values would represent two objects on the heap and only the addresses would be compared (unless the class type overrides the `System.Object.Equals` method).</span></span>

<span data-ttu-id="0e2f4-168">Wenn Sie Verweis Gleichheit für Datensätze benötigen, fügen Sie das Attribut `[<ReferenceEquality>]` oberhalb des Datensatzes hinzu.</span><span class="sxs-lookup"><span data-stu-id="0e2f4-168">If you need reference equality for records, add the attribute `[<ReferenceEquality>]` above the record.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e2f4-169">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e2f4-169">See also</span></span>

- [<span data-ttu-id="0e2f4-170">F#-Typen</span><span class="sxs-lookup"><span data-stu-id="0e2f4-170">F# Types</span></span>](fsharp-types.md)
- [<span data-ttu-id="0e2f4-171">Klassen</span><span class="sxs-lookup"><span data-stu-id="0e2f4-171">Classes</span></span>](classes.md)
- [<span data-ttu-id="0e2f4-172">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="0e2f4-172">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="0e2f4-173">Verweis-Gleichheit</span><span class="sxs-lookup"><span data-stu-id="0e2f4-173">Reference-Equality</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-referenceequalityattribute.html)
- [<span data-ttu-id="0e2f4-174">Mustervergleich</span><span class="sxs-lookup"><span data-stu-id="0e2f4-174">Pattern Matching</span></span>](pattern-matching.md)
