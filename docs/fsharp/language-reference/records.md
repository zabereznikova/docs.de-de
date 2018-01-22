---
title: "Datensätze (F#)"
description: "Erfahren Sie, wie einfache Aggregate benannter Werte, optional mit Mitgliedern von f#-Datensätzen darstellen."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3a3701ea-4308-4fa1-9b5c-b955c470f17a
ms.openlocfilehash: 478ab74ad32cc6e53daffd1bd6229729149d2a1e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="records"></a><span data-ttu-id="9a057-104">Datensätze</span><span class="sxs-lookup"><span data-stu-id="9a057-104">Records</span></span>

<span data-ttu-id="9a057-105">Datensätze stellen einfache Aggregate benannter Werte dar, optional mit Membern.</span><span class="sxs-lookup"><span data-stu-id="9a057-105">Records represent simple aggregates of named values, optionally with members.</span></span>  <span data-ttu-id="9a057-106">Ab f# 4.1, können sie entweder den Strukturen oder Verweistypen sein.</span><span class="sxs-lookup"><span data-stu-id="9a057-106">Starting with F# 4.1, they can either be structs or reference types.</span></span>  <span data-ttu-id="9a057-107">Diese sind standardmäßig Verweistypen.</span><span class="sxs-lookup"><span data-stu-id="9a057-107">They are reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="9a057-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a057-108">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] typename = {
    [ mutable ] label1 : type1;
    [ mutable ] label2 : type2;
    ...
}
    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="9a057-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9a057-109">Remarks</span></span>
<span data-ttu-id="9a057-110">In der vorherigen Syntax *Typename* ist der Name des Datensatztyps, *label1* und *label2* sind Namen von Werten, die so genannte *Bezeichnungen*, und *Typ1* und *Typ2* sind die folgenden Werte sind.</span><span class="sxs-lookup"><span data-stu-id="9a057-110">In the previous syntax, *typename* is the name of the record type, *label1* and *label2* are names of values, referred to as *labels*, and *type1* and *type2* are the types of these values.</span></span> <span data-ttu-id="9a057-111">*Memberliste* ist die optionale Liste von Elementen für den Typ.</span><span class="sxs-lookup"><span data-stu-id="9a057-111">*member-list* is the optional list of members for the type.</span></span>  <span data-ttu-id="9a057-112">Sie können die `[<Struct>]` Attribut um einen Datensatz, der ein Verweistyp ist, anstatt einen Datensatz für die Struktur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9a057-112">You can use the `[<Struct>]` attribute to create a struct record rather than a record which is a reference type.</span></span>

<span data-ttu-id="9a057-113">Es folgen einige Beispiele.</span><span class="sxs-lookup"><span data-stu-id="9a057-113">Following are some examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

<span data-ttu-id="9a057-114">Wenn jede Bezeichnung in einer separaten Zeile befindet, ist das Semikolon optional.</span><span class="sxs-lookup"><span data-stu-id="9a057-114">When each label is on a separate line, the semicolon is optional.</span></span>

<span data-ttu-id="9a057-115">Sie können Werte in Ausdrücken, die genannte festlegen *aufzeichnen Ausdrücke*.</span><span class="sxs-lookup"><span data-stu-id="9a057-115">You can set values in expressions known as *record expressions*.</span></span> <span data-ttu-id="9a057-116">Der Compiler leitet den Typ von Bezeichnungen verwendet (wenn die Bezeichnungen ausreichend von den anderen Datensatztypen unterscheiden).</span><span class="sxs-lookup"><span data-stu-id="9a057-116">The compiler infers the type from the labels used (if the labels are sufficiently distinct from those of other record types).</span></span> <span data-ttu-id="9a057-117">Geschweifte Klammern ({}) schließen Sie den Datensatzausdruck.</span><span class="sxs-lookup"><span data-stu-id="9a057-117">Braces ({ }) enclose the record expression.</span></span> <span data-ttu-id="9a057-118">Der folgende Code zeigt einen Datensatzausdruck, der einen Datensatz mit drei "float"-Elementen mit Bezeichnungen initialisiert `x`, `y` und `z`.</span><span class="sxs-lookup"><span data-stu-id="9a057-118">The following code shows a record expression that initializes a record with three float elements with labels `x`, `y` and `z`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

<span data-ttu-id="9a057-119">Verwenden Sie die abgekürzte Form nicht, wenn es kann einen anderen Typ, der auch die Bezeichnungen gleichen verfügt.</span><span class="sxs-lookup"><span data-stu-id="9a057-119">Do not use the shortened form if there could be another type that also has the same labels.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

<span data-ttu-id="9a057-120">Die Bezeichnungen der meisten zuletzt deklarierten Typ haben Vorrang gegenüber denen des zuvor deklarierten Typs im vorherigen Beispiel `mypoint3D` wird davon ausgegangen werden `Point3D`.</span><span class="sxs-lookup"><span data-stu-id="9a057-120">The labels of the most recently declared type take precedence over those of the previously declared type, so in the preceding example, `mypoint3D` is inferred to be `Point3D`.</span></span> <span data-ttu-id="9a057-121">Sie können den Datensatztyp, wie im folgenden Code explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="9a057-121">You can explicitly specify the record type, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

<span data-ttu-id="9a057-122">Methoden können für Datensatztypen, so wie für Klassentypen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="9a057-122">Methods can be defined for record types just as for class types.</span></span>

## <a name="creating-records-by-using-record-expressions"></a><span data-ttu-id="9a057-123">Erstellen von Datensätzen mithilfe von Datensatz-Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="9a057-123">Creating Records by Using Record Expressions</span></span>
<span data-ttu-id="9a057-124">Sie können Datensätze initialisieren, indem Sie die Bezeichnungen, die im Datensatz definiert sind.</span><span class="sxs-lookup"><span data-stu-id="9a057-124">You can initialize records by using the labels that are defined in the record.</span></span> <span data-ttu-id="9a057-125">Ein Ausdruck, die dies tut wird als bezeichnet eine *aufzeichnen Ausdruck*.</span><span class="sxs-lookup"><span data-stu-id="9a057-125">An expression that does this is referred to as a *record expression*.</span></span> <span data-ttu-id="9a057-126">Verwenden Sie geschweifte Klammern, um schließen die Datensatzausdruck ein, und verwenden Sie das Semikolon als Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="9a057-126">Use braces to enclose the record expression and use the semicolon as a delimiter.</span></span>

<span data-ttu-id="9a057-127">Im folgende Beispiel wird gezeigt, wie einen Datensatz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="9a057-127">The following example shows how to create a record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

<span data-ttu-id="9a057-128">Die Semikolons nach dem letzten Feld im Datensatzausdruck und in der Definition sind optional, unabhängig davon, ob die Felder vollständig in einer Zeile.</span><span class="sxs-lookup"><span data-stu-id="9a057-128">The semicolons after the last field in the record expression and in the type definition are optional, regardless of whether the fields are all in one line.</span></span>

<span data-ttu-id="9a057-129">Wenn Sie einen Datensatz zu erstellen, müssen Sie Werte für jedes Feld angeben.</span><span class="sxs-lookup"><span data-stu-id="9a057-129">When you create a record, you must supply values for each field.</span></span> <span data-ttu-id="9a057-130">Sie können nicht mit den Werten anderer Felder in der Initialisierungsausdruck für ein Feld verweisen.</span><span class="sxs-lookup"><span data-stu-id="9a057-130">You cannot refer to the values of other fields in the initialization expression for any field.</span></span>

<span data-ttu-id="9a057-131">Im folgenden Code, den Typ des `myRecord2` wird von den Namen der Felder abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="9a057-131">In the following code, the type of `myRecord2` is inferred from the names of the fields.</span></span> <span data-ttu-id="9a057-132">Optional können Sie den vollständigen Typnamen explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="9a057-132">Optionally, you can specify the type name explicitly.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="9a057-133">Eine andere Form der Erstellung des Datensatzes kann nützlich sein, wenn müssen Sie einen vorhandenen Datensatz kopieren und möglicherweise einige der Werte der Felder ändern.</span><span class="sxs-lookup"><span data-stu-id="9a057-133">Another form of record construction can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span> <span data-ttu-id="9a057-134">Dies wird anhand der folgenden Codezeile veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9a057-134">The following line of code illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

<span data-ttu-id="9a057-135">Diese Form des Ausdrucks Datensatz wird aufgerufen, die *kopieren und update der Datensatz Ausdruck*.</span><span class="sxs-lookup"><span data-stu-id="9a057-135">This form of the record expression is called the *copy and update record expression*.</span></span>

<span data-ttu-id="9a057-136">Datensätze sind standardmäßig unveränderlich. Allerdings können Sie leicht geänderten Datensätze mithilfe eines Ausdrucks kopieren und Update erstellen.</span><span class="sxs-lookup"><span data-stu-id="9a057-136">Records are immutable by default; however, you can easily create modified records by using a copy and update expression.</span></span> <span data-ttu-id="9a057-137">Sie können auch explizit ein veränderlichen Feld angeben.</span><span class="sxs-lookup"><span data-stu-id="9a057-137">You can also explicitly specify a mutable field.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

<span data-ttu-id="9a057-138">Verwenden Sie das DefaultValue-Attribut nicht mit Feldern Datensatzes.</span><span class="sxs-lookup"><span data-stu-id="9a057-138">Don't use the DefaultValue attribute with record fields.</span></span> <span data-ttu-id="9a057-139">Ein besserer Ansatz ist zum Standardinstanzen von Datensätzen mit Feldern, die initialisiert werden mit Standardwerten zu definieren und dann eine Kopie verwenden und aktualisieren Datensatzausdruck ein, um alle Felder festlegen, die von den Standardwerten abweichen.</span><span class="sxs-lookup"><span data-stu-id="9a057-139">A better approach is to define default instances of records with fields that are initialized to default values and then use a copy and update record expression to set any fields that differ from the default values.</span></span>

```fsharp
// Rather than use [<DefaultValue>], define a default record.
type MyRecord =
{
    field1 : int
    field2 : int
}

let defaultRecord1 = { field1 = 0; field2 = 0 }
let defaultRecord2 = { field1 = 1; field2 = 25 }

// Use the with keyword to populate only a few chosen fields
// and leave the rest with default values.
let rr3 = { defaultRecord1 with field2 = 42 }
```

## <a name="pattern-matching-with-records"></a><span data-ttu-id="9a057-140">Mustervergleich mit Datensätzen</span><span class="sxs-lookup"><span data-stu-id="9a057-140">Pattern Matching with Records</span></span>
<span data-ttu-id="9a057-141">Datensätze können mit dem Mustervergleich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9a057-141">Records can be used with pattern matching.</span></span> <span data-ttu-id="9a057-142">Sie können einige Felder explizit angeben und Bereitstellen von Variablen für die anderen Felder, die zugewiesen wird, wenn eine Übereinstimmung auftritt.</span><span class="sxs-lookup"><span data-stu-id="9a057-142">You can specify some fields explicitly and provide variables for other fields that will be assigned when a match occurs.</span></span> <span data-ttu-id="9a057-143">Dies wird im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9a057-143">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

<span data-ttu-id="9a057-144">Die Ausgabe dieses Codes lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="9a057-144">The output of this code is as follows.</span></span>

```
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a><span data-ttu-id="9a057-145">Unterschiede zwischen Datensätzen und Klassen</span><span class="sxs-lookup"><span data-stu-id="9a057-145">Differences Between Records and Classes</span></span>
<span data-ttu-id="9a057-146">Datensatzfelder unterscheiden sich von Klassen, sie werden automatisch als Eigenschaften verfügbar gemacht, und es handelt sich bei der Erstellung verwendet und Kopieren von Datensätzen.</span><span class="sxs-lookup"><span data-stu-id="9a057-146">Record fields differ from classes in that they are automatically exposed as properties, and they are used in the creation and copying of records.</span></span> <span data-ttu-id="9a057-147">Datensatz Konstruktion unterscheidet sich auch von der Klassenkonstruktion.</span><span class="sxs-lookup"><span data-stu-id="9a057-147">Record construction also differs from class construction.</span></span> <span data-ttu-id="9a057-148">Einen Konstruktor kann nicht definieren, in einen Datensatztyp.</span><span class="sxs-lookup"><span data-stu-id="9a057-148">In a record type, you cannot define a constructor.</span></span> <span data-ttu-id="9a057-149">Stattdessen gilt die Konstruktionssyntax, die in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9a057-149">Instead, the construction syntax described in this topic applies.</span></span> <span data-ttu-id="9a057-150">Klassen verfügen über keine direkte Beziehung zwischen Konstruktorparameter, Felder und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="9a057-150">Classes have no direct relationship between constructor parameters, fields, and properties.</span></span>

<span data-ttu-id="9a057-151">Wie Union "und" Struktur weisen Datensätze strukturelle Gleichheitssemantik auf.</span><span class="sxs-lookup"><span data-stu-id="9a057-151">Like union and structure types, records have structural equality semantics.</span></span> <span data-ttu-id="9a057-152">Klassen verfügen über Gleichheitssemantik auf.</span><span class="sxs-lookup"><span data-stu-id="9a057-152">Classes have reference equality semantics.</span></span> <span data-ttu-id="9a057-153">Dies wird im folgenden Codebeispiel wird veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9a057-153">The following code example demonstrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

<span data-ttu-id="9a057-154">Wenn Sie den gleichen Code mit Klassen schreiben, die zwei Klassenobjekte wäre ungleich daran, dass die beiden Werte zwei Objekte auf dem Heap darstellen und nur die Adressen verglichen werden würde (es sei denn, der Klassentyp überschreibt die `System.Object.Equals` Methode).</span><span class="sxs-lookup"><span data-stu-id="9a057-154">If you write the same code with classes, the two class objects would be unequal because the two values would represent two objects on the heap and only the addresses would be compared (unless the class type overrides the `System.Object.Equals` method).</span></span>

<span data-ttu-id="9a057-155">Wenn Sie auf Gleichheit Datensätze verweisen müssen, fügen Sie das Attribut `[<ReferenceEquality>]` oberhalb des Datensatzes.</span><span class="sxs-lookup"><span data-stu-id="9a057-155">If you need reference equality for records, add the attribute `[<ReferenceEquality>]` above the record.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a057-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a057-156">See Also</span></span>
[<span data-ttu-id="9a057-157">F#-Typen</span><span class="sxs-lookup"><span data-stu-id="9a057-157">F# Types</span></span>](fsharp-types.md)

[<span data-ttu-id="9a057-158">Klassen</span><span class="sxs-lookup"><span data-stu-id="9a057-158">Classes</span></span>](classes.md)

[<span data-ttu-id="9a057-159">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="9a057-159">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="9a057-160">Verweisgleichheit</span><span class="sxs-lookup"><span data-stu-id="9a057-160">Reference-Equality</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)

[<span data-ttu-id="9a057-161">Mustervergleich</span><span class="sxs-lookup"><span data-stu-id="9a057-161">Pattern Matching</span></span>](pattern-matching.md)
