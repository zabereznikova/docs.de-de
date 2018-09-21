---
title: Datensätze (F#)
description: Erfahren Sie, wie f#-Datensätzen für einfache Aggregate benannter Werte, optional mit Membern darstellen.
ms.date: 05/16/2016
ms.openlocfilehash: 6103d96b6b80a9e2ed168755958dbe800f7fa862
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "46537539"
---
# <a name="records"></a><span data-ttu-id="e4d68-103">Datensätze</span><span class="sxs-lookup"><span data-stu-id="e4d68-103">Records</span></span>

<span data-ttu-id="e4d68-104">Datensätze stellen einfache Aggregate benannter Werte dar, optional mit Membern.</span><span class="sxs-lookup"><span data-stu-id="e4d68-104">Records represent simple aggregates of named values, optionally with members.</span></span>  <span data-ttu-id="e4d68-105">Ab f# 4.1, können sie entweder den Strukturen oder Verweistypen sein.</span><span class="sxs-lookup"><span data-stu-id="e4d68-105">Starting with F# 4.1, they can either be structs or reference types.</span></span>  <span data-ttu-id="e4d68-106">Sie sind Verweistypen standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="e4d68-106">They are reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="e4d68-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4d68-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] typename =
    { [ mutable ] label1 : type1;
      [ mutable ] label2 : type2;
      ... }
    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="e4d68-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e4d68-108">Remarks</span></span>

<span data-ttu-id="e4d68-109">In der vorherigen Syntax *Typename* ist der Name des Datensatztyps, *label1* und *label2* sind Namen von Werten, um genannte *Bezeichnungen*, und *type1* und *Typ2* sind die Typen dieser Werte.</span><span class="sxs-lookup"><span data-stu-id="e4d68-109">In the previous syntax, *typename* is the name of the record type, *label1* and *label2* are names of values, referred to as *labels*, and *type1* and *type2* are the types of these values.</span></span> <span data-ttu-id="e4d68-110">*Memberliste* ist die optionale Liste von Elementen für den Typ.</span><span class="sxs-lookup"><span data-stu-id="e4d68-110">*member-list* is the optional list of members for the type.</span></span>  <span data-ttu-id="e4d68-111">Sie können die `[<Struct>]` Attribut um einen Datensatz, der ein Verweistyp ist, statt einen Eintrag für die Struktur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e4d68-111">You can use the `[<Struct>]` attribute to create a struct record rather than a record which is a reference type.</span></span>

<span data-ttu-id="e4d68-112">Es folgen einige Beispiele.</span><span class="sxs-lookup"><span data-stu-id="e4d68-112">Following are some examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

<span data-ttu-id="e4d68-113">Wenn jede Bezeichnung in einer separaten Zeile ist, ist das Semikolon optional.</span><span class="sxs-lookup"><span data-stu-id="e4d68-113">When each label is on a separate line, the semicolon is optional.</span></span>

<span data-ttu-id="e4d68-114">Sie können Werte in Ausdrücken, die als bekannt festlegen *aufzeichnen Ausdrücke*.</span><span class="sxs-lookup"><span data-stu-id="e4d68-114">You can set values in expressions known as *record expressions*.</span></span> <span data-ttu-id="e4d68-115">Der Compiler leitet den Typ von Bezeichnungen verwendet (wenn die Bezeichnungen ausreichend unterscheiden, andere Eintragstypen werden).</span><span class="sxs-lookup"><span data-stu-id="e4d68-115">The compiler infers the type from the labels used (if the labels are sufficiently distinct from those of other record types).</span></span> <span data-ttu-id="e4d68-116">Geschweifte Klammern ({}) einschließen der Datensatzausdruck.</span><span class="sxs-lookup"><span data-stu-id="e4d68-116">Braces ({ }) enclose the record expression.</span></span> <span data-ttu-id="e4d68-117">Der folgende Code zeigt einen Datensatzausdruck, der einen Datensatz mit drei Float-Elemente mit Bezeichnungen initialisiert `x`, `y` und `z`.</span><span class="sxs-lookup"><span data-stu-id="e4d68-117">The following code shows a record expression that initializes a record with three float elements with labels `x`, `y` and `z`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

<span data-ttu-id="e4d68-118">Verwenden Sie nicht die abgekürzte Form aus, wenn möglicherweise einen anderen Typ, der auch die gleichen Bezeichnungen aufweist.</span><span class="sxs-lookup"><span data-stu-id="e4d68-118">Do not use the shortened form if there could be another type that also has the same labels.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

<span data-ttu-id="e4d68-119">Die Bezeichnungen von der die zuletzt deklarierte Typ haben Vorrang gegenüber denen des zuvor deklarierten Typs im vorherigen Beispiel `mypoint3D` wird davon ausgegangen werden `Point3D`.</span><span class="sxs-lookup"><span data-stu-id="e4d68-119">The labels of the most recently declared type take precedence over those of the previously declared type, so in the preceding example, `mypoint3D` is inferred to be `Point3D`.</span></span> <span data-ttu-id="e4d68-120">Sie können den Datensatztyp, wie im folgenden Code explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="e4d68-120">You can explicitly specify the record type, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

<span data-ttu-id="e4d68-121">Methoden können für Record-Typen, genau wie bei Klassentypen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="e4d68-121">Methods can be defined for record types just as for class types.</span></span>

## <a name="creating-records-by-using-record-expressions"></a><span data-ttu-id="e4d68-122">Erstellen von Datensätzen mithilfe von Datensatz-Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="e4d68-122">Creating Records by Using Record Expressions</span></span>

<span data-ttu-id="e4d68-123">Sie können Einträge initialisieren, indem Sie mit den Bezeichnungen, die im Datensatz definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e4d68-123">You can initialize records by using the labels that are defined in the record.</span></span> <span data-ttu-id="e4d68-124">Ein Ausdruck, der dieses wird als bezeichnet ein *aufzeichnen Ausdruck*.</span><span class="sxs-lookup"><span data-stu-id="e4d68-124">An expression that does this is referred to as a *record expression*.</span></span> <span data-ttu-id="e4d68-125">Verwenden Sie geschweifte Klammern zum Einschließen der Datensatzausdruck und verwenden Sie das Semikolon als Trennzeichen ein.</span><span class="sxs-lookup"><span data-stu-id="e4d68-125">Use braces to enclose the record expression and use the semicolon as a delimiter.</span></span>

<span data-ttu-id="e4d68-126">Das folgende Beispiel zeigt, wie Sie einen Datensatz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e4d68-126">The following example shows how to create a record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

<span data-ttu-id="e4d68-127">Die Semikolons aus, nachdem das letzte Feld in der Datensatzausdruck und in der Typdefinition sind optional, unabhängig davon, ob die Felder in einer Zeile.</span><span class="sxs-lookup"><span data-stu-id="e4d68-127">The semicolons after the last field in the record expression and in the type definition are optional, regardless of whether the fields are all in one line.</span></span>

<span data-ttu-id="e4d68-128">Wenn Sie einen Datensatz erstellen, müssen Sie Werte für jedes Feld angeben.</span><span class="sxs-lookup"><span data-stu-id="e4d68-128">When you create a record, you must supply values for each field.</span></span> <span data-ttu-id="e4d68-129">Sie können nicht auf die Werte der anderen Felder in den Initialisierungsausdruck für ein Feld verweisen.</span><span class="sxs-lookup"><span data-stu-id="e4d68-129">You cannot refer to the values of other fields in the initialization expression for any field.</span></span>

<span data-ttu-id="e4d68-130">Im folgenden Code, den Typ des `myRecord2` wird abgeleitet aus den Namen der Felder.</span><span class="sxs-lookup"><span data-stu-id="e4d68-130">In the following code, the type of `myRecord2` is inferred from the names of the fields.</span></span> <span data-ttu-id="e4d68-131">Optional können Sie den Typnamen explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="e4d68-131">Optionally, you can specify the type name explicitly.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="e4d68-132">Eine andere Form der Datensatzkonstruktion kann nützlich sein, beim Kopieren eines vorhandenen Datensatzes, und möglicherweise einige Werte der Felder ändern.</span><span class="sxs-lookup"><span data-stu-id="e4d68-132">Another form of record construction can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span> <span data-ttu-id="e4d68-133">Die folgende Codezeile veranschaulicht dies.</span><span class="sxs-lookup"><span data-stu-id="e4d68-133">The following line of code illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

<span data-ttu-id="e4d68-134">Diese Form des datensatzausdrucks heißt die *kopieren und Aktualisieren des Datensatzes Ausdruck*.</span><span class="sxs-lookup"><span data-stu-id="e4d68-134">This form of the record expression is called the *copy and update record expression*.</span></span>

<span data-ttu-id="e4d68-135">Datensätze sind standardmäßig nicht verändert werden. Allerdings können Sie leicht geänderte Datensätze mithilfe eines Ausdrucks kopieren und aktualisieren erstellen.</span><span class="sxs-lookup"><span data-stu-id="e4d68-135">Records are immutable by default; however, you can easily create modified records by using a copy and update expression.</span></span> <span data-ttu-id="e4d68-136">Sie können auch explizit ein veränderlichen Feld angeben.</span><span class="sxs-lookup"><span data-stu-id="e4d68-136">You can also explicitly specify a mutable field.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

<span data-ttu-id="e4d68-137">Verwenden Sie das DefaultValue-Attribut nicht mit Feldern Datensatzes an.</span><span class="sxs-lookup"><span data-stu-id="e4d68-137">Don't use the DefaultValue attribute with record fields.</span></span> <span data-ttu-id="e4d68-138">Ein besserer Ansatz ist Standardinstanzen von Datensätzen mit Feldern, die initialisiert werden, auf die Standardwerte definieren und dann eine Kopie verwenden und aktualisieren Datensatzausdruck ein, um alle Felder festgelegt, die von den Standardwerten abweichen.</span><span class="sxs-lookup"><span data-stu-id="e4d68-138">A better approach is to define default instances of records with fields that are initialized to default values and then use a copy and update record expression to set any fields that differ from the default values.</span></span>

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

## <a name="pattern-matching-with-records"></a><span data-ttu-id="e4d68-139">Musterabgleich mit Datensätzen</span><span class="sxs-lookup"><span data-stu-id="e4d68-139">Pattern Matching with Records</span></span>

<span data-ttu-id="e4d68-140">Datensätze können mit dem Mustervergleich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e4d68-140">Records can be used with pattern matching.</span></span> <span data-ttu-id="e4d68-141">Sie können einige Felder explizit angeben und Bereitstellen von Variablen für die anderen Felder, die zugewiesen werden soll, wenn eine Übereinstimmung auftritt.</span><span class="sxs-lookup"><span data-stu-id="e4d68-141">You can specify some fields explicitly and provide variables for other fields that will be assigned when a match occurs.</span></span> <span data-ttu-id="e4d68-142">Dies wird im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e4d68-142">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

<span data-ttu-id="e4d68-143">Die Ausgabe dieses Codes lautet wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="e4d68-143">The output of this code is as follows.</span></span>

```
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a><span data-ttu-id="e4d68-144">Unterschiede zwischen Datensätzen und Klassen</span><span class="sxs-lookup"><span data-stu-id="e4d68-144">Differences Between Records and Classes</span></span>

<span data-ttu-id="e4d68-145">Datensatzfelder unterscheiden sich von Klassen, sie werden automatisch als Eigenschaften verfügbar gemacht, und es handelt sich bei der Erstellung verwendet und der Datensätze kopieren.</span><span class="sxs-lookup"><span data-stu-id="e4d68-145">Record fields differ from classes in that they are automatically exposed as properties, and they are used in the creation and copying of records.</span></span> <span data-ttu-id="e4d68-146">Datensatzkonstruktion unterscheidet sich auch von der Klassenkonstruktion.</span><span class="sxs-lookup"><span data-stu-id="e4d68-146">Record construction also differs from class construction.</span></span> <span data-ttu-id="e4d68-147">Einen Konstruktor kann nicht in einem Datensatz vom Typ definiert werden.</span><span class="sxs-lookup"><span data-stu-id="e4d68-147">In a record type, you cannot define a constructor.</span></span> <span data-ttu-id="e4d68-148">Stattdessen gilt die Konstruktionssyntax, die in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e4d68-148">Instead, the construction syntax described in this topic applies.</span></span> <span data-ttu-id="e4d68-149">Klassen verfügen über keine direkte Beziehung zwischen Konstruktorparameter, Felder und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="e4d68-149">Classes have no direct relationship between constructor parameters, fields, and properties.</span></span>

<span data-ttu-id="e4d68-150">Wie Union- und Struktur enthalten Datensätze strukturelle Gleichheit-Semantik.</span><span class="sxs-lookup"><span data-stu-id="e4d68-150">Like union and structure types, records have structural equality semantics.</span></span> <span data-ttu-id="e4d68-151">Klassen verfügen über Gleichheitssemantik auf.</span><span class="sxs-lookup"><span data-stu-id="e4d68-151">Classes have reference equality semantics.</span></span> <span data-ttu-id="e4d68-152">Dies wird im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e4d68-152">The following code example demonstrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

<span data-ttu-id="e4d68-153">Die Ausgabe dieses Codes lautet wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="e4d68-153">The output of this code is as follows:</span></span>

```
The records are equal.
```

<span data-ttu-id="e4d68-154">Wenn Sie den gleichen Code mit Klassen schreiben, die beiden Klassenobjekte wäre ungleich daran, dass zwei Objekte auf dem Heap die beiden Werte darstellen, und nur die Adressen verglichen werden sollen (es sei denn, der den Klassentyp überschreibt die `System.Object.Equals` Methode).</span><span class="sxs-lookup"><span data-stu-id="e4d68-154">If you write the same code with classes, the two class objects would be unequal because the two values would represent two objects on the heap and only the addresses would be compared (unless the class type overrides the `System.Object.Equals` method).</span></span>

<span data-ttu-id="e4d68-155">Wenn Sie überprüft die Gleichheit für Datensätze verweisen müssen, fügen Sie das Attribut `[<ReferenceEquality>]` über dem Datensatz.</span><span class="sxs-lookup"><span data-stu-id="e4d68-155">If you need reference equality for records, add the attribute `[<ReferenceEquality>]` above the record.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4d68-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4d68-156">See also</span></span>

- [<span data-ttu-id="e4d68-157">F#-Typen</span><span class="sxs-lookup"><span data-stu-id="e4d68-157">F# Types</span></span>](fsharp-types.md)
- [<span data-ttu-id="e4d68-158">Klassen</span><span class="sxs-lookup"><span data-stu-id="e4d68-158">Classes</span></span>](classes.md)
- [<span data-ttu-id="e4d68-159">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="e4d68-159">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="e4d68-160">Verweisgleichheit</span><span class="sxs-lookup"><span data-stu-id="e4d68-160">Reference-Equality</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)
- [<span data-ttu-id="e4d68-161">Mustervergleich</span><span class="sxs-lookup"><span data-stu-id="e4d68-161">Pattern Matching</span></span>](pattern-matching.md)
