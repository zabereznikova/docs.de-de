---
title: readonly-Schlüsselwort – C#-Referenz
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: c3db8f7791e510768608e834339526fb82771979
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451940"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="49d5a-102">readonly (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="49d5a-102">readonly (C# Reference)</span></span>

<span data-ttu-id="49d5a-103">Das Schlüsselwort `readonly` ist ein Modifizierer, der in vier Kontexten verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="49d5a-103">The `readonly` keyword is a modifier that can be used in four contexts:</span></span>

- <span data-ttu-id="49d5a-104">In einer [Felddeklaration](#readonly-field-example) gibt `readonly` an, dass die Zuweisung zum Feld nur als Teil der Deklaration oder in einem Konstruktor derselben Klasse erfolgen kann.</span><span class="sxs-lookup"><span data-stu-id="49d5a-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="49d5a-105">Ein readonly-Feld kann innerhalb der Felddeklaration und des Konstruktors mehrmals zugewiesen und neu zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="49d5a-105">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span> 
  
  <span data-ttu-id="49d5a-106">Ein `readonly`-Feld kann nicht zugewiesen werden, sobald der Konstruktor vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="49d5a-106">A `readonly` field can't be assigned after the constructor exits.</span></span> <span data-ttu-id="49d5a-107">Diese Regel hat verschiedene Auswirkungen auf Wert- und Verweistypen:</span><span class="sxs-lookup"><span data-stu-id="49d5a-107">This rule has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="49d5a-108">Da Werttypen ihre Daten direkt enthalten, ist ein Feld des Werttyps `readonly` unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="49d5a-108">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span> 
  - <span data-ttu-id="49d5a-109">Da Verweistypen einen Verweis auf ihre Daten enthalten, muss ein Feld des Verweistyps `readonly` immer auf das gleiche Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="49d5a-109">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="49d5a-110">Dieses Objekt ist nicht unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="49d5a-110">That object isn't immutable.</span></span> <span data-ttu-id="49d5a-111">Der `readonly`-Modifizierer verhindert, dass das Feld durch eine andere Instanz des Verweistyps ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="49d5a-111">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="49d5a-112">Der Modifizierer verhindert jedoch nicht, dass die Instanzdaten des Felds durch das schreibgeschützte Feld geändert werden.</span><span class="sxs-lookup"><span data-stu-id="49d5a-112">However, the modifier doesn't prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="49d5a-113">Ein extern sichtbarer Typ, der ein extern sichtbares schreibgeschütztes Feld enthält, bei dem es sich um einen änderbaren Verweistyp handelt, kann ein Sicherheitsrisiko darstellen und die folgende Warnung auslösen: [CA2104](/visualstudio/code-quality/ca2104): „Schreibgeschützte änderbare Verweistypen nicht deklarieren.“</span><span class="sxs-lookup"><span data-stu-id="49d5a-113">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="49d5a-114">In einer [`readonly struct`-Definition](#readonly-struct-example) gibt `readonly` an, dass `struct` unveränderlich ist.</span><span class="sxs-lookup"><span data-stu-id="49d5a-114">In a [`readonly struct` definition](#readonly-struct-example), `readonly` indicates that the `struct` is immutable.</span></span>
- <span data-ttu-id="49d5a-115">In einer [`readonly`-Memberdefinition](#readonly-member-examples) gibt `readonly` an, dass ein Member von `struct` den internen Zustand der Struktur nicht verändert.</span><span class="sxs-lookup"><span data-stu-id="49d5a-115">In a [`readonly` member definition](#readonly-member-examples), `readonly` indicates that a member of a `struct` doesn't mutate the struct's internal state.</span></span>
- <span data-ttu-id="49d5a-116">In einer [`ref readonly`-Methodenrückgabe](#ref-readonly-return-example) gibt der `readonly`-Modifizierer an, dass die Methode eine Referenz zurückgibt, und Schreibvorgänge für diese Referenz nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="49d5a-116">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes aren't allowed to that reference.</span></span>

<span data-ttu-id="49d5a-117">Die `readonly struct`- und `ref readonly`-Kontexte wurden in C# 7.2 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="49d5a-117">The `readonly struct` and `ref readonly` contexts were added in C# 7.2.</span></span> <span data-ttu-id="49d5a-118">`readonly`-Strukturmember wurden in C# 8.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="49d5a-118">`readonly` struct members were added in C# 8.0</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="49d5a-119">Beispiel für ein readonly-Feld</span><span class="sxs-lookup"><span data-stu-id="49d5a-119">Readonly field example</span></span>

<span data-ttu-id="49d5a-120">In diesem Beispiel kann der Wert des Felds `year` nicht zur Methode `ChangeYear` geändert werden, obwohl ihm im Klassenkonstruktor ein Wert zugewiesen ist:</span><span class="sxs-lookup"><span data-stu-id="49d5a-120">In this example, the value of the field `year` can't be changed in the method `ChangeYear`, even though it's assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="49d5a-121">Sie können einem `readonly`-Feld nur in den folgenden Kontexten einen Wert zuweisen:</span><span class="sxs-lookup"><span data-stu-id="49d5a-121">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="49d5a-122">Wenn die Variable in der Deklaration initialisiert ist, z.B.:</span><span class="sxs-lookup"><span data-stu-id="49d5a-122">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="49d5a-123">In einem Instanzenkonstruktor der Klasse, die die Deklaration des Instanzfelds enthält.</span><span class="sxs-lookup"><span data-stu-id="49d5a-123">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="49d5a-124">Im statischen Konstruktor der Klasse, die die Deklaration des statischen Felds enthält.</span><span class="sxs-lookup"><span data-stu-id="49d5a-124">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="49d5a-125">Diese Konstruktorkontexte sind auch die einzigen Kontexte, in denen es zulässig ist, ein `readonly`-Feld als [out](out-parameter-modifier.md)- oder [ref](ref.md)-Parameter zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="49d5a-125">These constructor contexts are also the only contexts in which it's valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="49d5a-126">Das Schlüsselwort `readonly` unterscheidet sich vom Schlüsselwort [const](const.md).</span><span class="sxs-lookup"><span data-stu-id="49d5a-126">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="49d5a-127">Ein `const`-Feld kann nur bei der Deklaration des Felds initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="49d5a-127">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="49d5a-128">Ein `readonly`-Feld kann mehrere Male in der Felddeklaration und in einem Konstruktor zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="49d5a-128">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="49d5a-129">Daher können `readonly`-Felder abhängig vom verwendeten Konstruktor über unterschiedliche Werte verfügen.</span><span class="sxs-lookup"><span data-stu-id="49d5a-129">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="49d5a-130">Außerdem ist ein `const`-Feld eine Kompilierzeitkonstante, während ein `readonly`-Feld wie im folgenden Beispiel für Laufzeitkonstanten verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="49d5a-130">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="49d5a-131">Wenn Sie im vorherigen Beispiel eine Anweisung wie die folgende verwenden:</span><span class="sxs-lookup"><span data-stu-id="49d5a-131">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="49d5a-132">erhalten Sie die Compilerfehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="49d5a-132">you'll get the compiler error message:</span></span>

<span data-ttu-id="49d5a-133">**Einem schreibgeschützten Feld kann nichts zugewiesen werden (außer in einem Konstruktor oder Variableninitialisierer)**</span><span class="sxs-lookup"><span data-stu-id="49d5a-133">**A readonly field cannot be assigned to (except in a constructor or a variable initializer)**</span></span>

## <a name="readonly-struct-example"></a><span data-ttu-id="49d5a-134">Beispiel für readonly struct</span><span class="sxs-lookup"><span data-stu-id="49d5a-134">Readonly struct example</span></span>

<span data-ttu-id="49d5a-135">Der `readonly`-Modifizierer für eine `struct`-Definition deklariert, dass die Struktur **unveränderlich** ist.</span><span class="sxs-lookup"><span data-stu-id="49d5a-135">The `readonly` modifier on a `struct` definition declares that the struct is **immutable**.</span></span> <span data-ttu-id="49d5a-136">Jedes Instanzfeld für `struct` muss mit `readonly` markiert sein, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="49d5a-136">Every instance field of the `struct` must be marked `readonly`, as shown in the following example:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]

<span data-ttu-id="49d5a-137">Das vorhergehende Beispiel verwendet [schreibgeschützte automatische Eigenschaften](../../properties.md#read-only), um den Speicher zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="49d5a-137">The preceding example uses [readonly auto properties](../../properties.md#read-only) to declare its storage.</span></span> <span data-ttu-id="49d5a-138">Dadurch wird der Compiler angewiesen, `readonly`-Unterstützungsfelder für diese Eigenschaften zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="49d5a-138">That instructs the compiler to create `readonly` backing fields for those properties.</span></span> <span data-ttu-id="49d5a-139">Sie können `readonly`-Felder auch direkt deklarieren:</span><span class="sxs-lookup"><span data-stu-id="49d5a-139">You could also declare `readonly` fields directly:</span></span>

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

<span data-ttu-id="49d5a-140">Das Hinzufügen eines nicht als `readonly` markierten Felds generiert den Compilerfehler `CS8340`: Instanzfelder von schreibgeschützten Strukturen müssen schreibgeschützt sein.</span><span class="sxs-lookup"><span data-stu-id="49d5a-140">Adding a field not marked `readonly` generates compiler error `CS8340`: "Instance fields of readonly structs must be readonly."</span></span>

## <a name="readonly-member-examples"></a><span data-ttu-id="49d5a-141">Beispiele für readonly-Member</span><span class="sxs-lookup"><span data-stu-id="49d5a-141">Readonly member examples</span></span>

<span data-ttu-id="49d5a-142">Gegebenenfalls möchten Sie eine Struktur erstellen, die Veränderungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="49d5a-142">Other times, you may create a struct that supports mutation.</span></span> <span data-ttu-id="49d5a-143">In diesen Fällen wird der interne Zustand der Struktur durch einige der Instanzmember wahrscheinlich nicht verändert.</span><span class="sxs-lookup"><span data-stu-id="49d5a-143">In those cases, several of the instance members likely won't modify the internal state of the struct.</span></span> <span data-ttu-id="49d5a-144">Dann können Sie diese Instanzmember mit dem `readonly`-Modifizierer deklarieren.</span><span class="sxs-lookup"><span data-stu-id="49d5a-144">You can declare those instance members with the `readonly` modifier.</span></span> <span data-ttu-id="49d5a-145">Mithilfe des Compilers können Sie die Umsetzung Ihrer Absicht erzwingen.</span><span class="sxs-lookup"><span data-stu-id="49d5a-145">The compiler enforces your intent.</span></span> <span data-ttu-id="49d5a-146">Wenn dieses Member den Zustand direkt ändert oder auf ein Member zugreift, das nicht ebenfalls mit dem `readonly`-Modifizierer deklariert ist, führt dies zu einem Kompilierzeitfehler.</span><span class="sxs-lookup"><span data-stu-id="49d5a-146">If that member modifies state directly or accesses a member that isn't also declared with the `readonly` modifier, the result is a compile-time error.</span></span> <span data-ttu-id="49d5a-147">Der `readonly`-Modifizierer ist für `struct`-Member gültig, nicht für `class`- oder `interface`-Memberdeklarationen.</span><span class="sxs-lookup"><span data-stu-id="49d5a-147">The `readonly` modifier is valid on `struct` members, not `class` or `interface` member declarations.</span></span>

<span data-ttu-id="49d5a-148">Es ergeben sich zwei Vorteile, wenn Sie den `readonly`-Modifizierer auf anwendbare `struct`-Methoden anwenden.</span><span class="sxs-lookup"><span data-stu-id="49d5a-148">You gain two advantages by applying the `readonly` modifier to applicable `struct` methods.</span></span> <span data-ttu-id="49d5a-149">Der wichtigste Vorteil ist, dass der Compiler Ihre Absicht durchsetzt.</span><span class="sxs-lookup"><span data-stu-id="49d5a-149">Most importantly, the compiler enforces your intent.</span></span> <span data-ttu-id="49d5a-150">Den Zustand verändernder Code ist in einer `readonly`-Methode nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="49d5a-150">Code that modifies state isn't valid in a `readonly` method.</span></span> <span data-ttu-id="49d5a-151">Auch der `readonly`-Modifizierer kann vom Compiler eingesetzt werden, um Leistungsoptimierungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="49d5a-151">The compiler may also make use of the `readonly` modifier to enable performance optimizations.</span></span> <span data-ttu-id="49d5a-152">Wenn große `struct`-Typen durch den `in`-Verweis übergeben werden, muss der Compiler eine defensive Kopie erzeugen, falls der Zustand der Struktur geändert wird.</span><span class="sxs-lookup"><span data-stu-id="49d5a-152">When large `struct` types are passed by `in` reference, the compiler must generate a defensive copy if the state of the struct might be modified.</span></span> <span data-ttu-id="49d5a-153">Wenn nur auf `readonly`-Member zugegriffen wird, darf der Compiler die defensive Kopie nicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="49d5a-153">If only `readonly` members are accessed, the compiler may not create the defensive copy.</span></span>

<span data-ttu-id="49d5a-154">Der `readonly`-Modifizierer ist für die meisten Member einer `struct`-Methode gültig, einschließlich Methoden, die die in <xref:System.Object?displayProperty=nameWithType> deklarierte Methoden außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="49d5a-154">The `readonly` modifier is valid on most members of a `struct`, including methods that override methods declared in <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="49d5a-155">Es gibt einige Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="49d5a-155">There are some restrictions:</span></span>

- <span data-ttu-id="49d5a-156">Sie können keine statischen `readonly`-Methoden oder -Eigenschaften deklarieren.</span><span class="sxs-lookup"><span data-stu-id="49d5a-156">You can't declare `readonly` static methods or properties.</span></span>
- <span data-ttu-id="49d5a-157">Sie können keine `readonly`-Konstruktoren deklarieren.</span><span class="sxs-lookup"><span data-stu-id="49d5a-157">You can't declare `readonly` constructors.</span></span>

<span data-ttu-id="49d5a-158">Sie können den `readonly`-Modifizierer zu einer Eigenschafts- oder Indexerdeklaration hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="49d5a-158">You can add the `readonly` modifier to a property or indexer declaration:</span></span>

```csharp
readonly public int Counter
{
  get { return 0; }
  set {} // not useful, but legal
}
```

<span data-ttu-id="49d5a-159">Außerdem können Sie den `readonly`-Modifizierer zu einzelnen `get`- oder `set`-Accessoren einer Eigenschaft oder eines Indexers hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="49d5a-159">You may also add the `readonly` modifier to individual `get` or `set` accessors of a property or indexer:</span></span>

```csharp
public int Counter
{
  readonly get { return _counter; }
  set { _counter = value; }
}
int _counter;
```

<span data-ttu-id="49d5a-160">Sie dürfen den `readonly`-Modifizierer nicht sowohl zu einer Eigenschaft als auch zu einem Accessor bzw. mehreren Accessoren derselben Eigenschaft hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="49d5a-160">You may not add the `readonly` modifier to both a property and one or more of that same property's accessors.</span></span> <span data-ttu-id="49d5a-161">Für Indexer gilt die gleiche Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="49d5a-161">That same restriction applies to indexers.</span></span>

<span data-ttu-id="49d5a-162">Der Compiler wendet den `readonly`-Modifizierer implizit auf automatisch implementierte Eigenschaften an, bei denen der vom Compiler implementierte Code den Zustand nicht ändert.</span><span class="sxs-lookup"><span data-stu-id="49d5a-162">The compiler implicitly applies the `readonly` modifier to auto-implemented properties where the compiler implemented code doesn't modify state.</span></span> <span data-ttu-id="49d5a-163">Dies entspricht den folgenden Deklarationen:</span><span class="sxs-lookup"><span data-stu-id="49d5a-163">It's equivalent to the following declarations:</span></span>

```csharp
public readonly int Index { get; }
// Or:
public int Number { readonly get; }
public string Message { readonly get; set; }
``` 

<span data-ttu-id="49d5a-164">An diesen Stellen können Sie den `readonly`-Modifizierer hinzufügen, aber er hat keinen sinnvollen Effekt.</span><span class="sxs-lookup"><span data-stu-id="49d5a-164">You may add the `readonly` modifier in those locations, but it will have no meaningful effect.</span></span> <span data-ttu-id="49d5a-165">Sie dürfen den `readonly`-Modifizierer nicht zu einem Setter für eine automatisch implementierte Eigenschaft oder zu einer automatisch implementierten Eigenschaft für Lese-/Schreibzugriff hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="49d5a-165">You may not add the `readonly` modifier to an auto-implemented property setter, or to a read/write auto-implemented property.</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="49d5a-166">Rückgabebeispiel für ref readonly</span><span class="sxs-lookup"><span data-stu-id="49d5a-166">Ref readonly return example</span></span>

<span data-ttu-id="49d5a-167">Der `readonly`-Modifizierer für `ref return` gibt an, dass der zurückgegebene Verweis nicht geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="49d5a-167">The `readonly` modifier on a `ref return` indicates that the returned reference can't be modified.</span></span> <span data-ttu-id="49d5a-168">Das folgende Beispiel gibt einen Verweis auf den Ursprung zurück.</span><span class="sxs-lookup"><span data-stu-id="49d5a-168">The following example returns a reference to the origin.</span></span> <span data-ttu-id="49d5a-169">Dabei wird über den `readonly`-Modifizierer angegeben, dass die aufrufenden Funktionen den Ursprung nicht ändern können:</span><span class="sxs-lookup"><span data-stu-id="49d5a-169">It uses the `readonly` modifier to indicate that callers can't modify the origin:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
<span data-ttu-id="49d5a-170">Der zurückgegebene Typ muss nicht `readonly struct` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="49d5a-170">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="49d5a-171">Jeder Typ, der von `ref` zurückgegeben werden kann, kann auch von `ref readonly` zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="49d5a-171">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="49d5a-172">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="49d5a-172">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

<span data-ttu-id="49d5a-173">Sehen Sie sich auch die Vorschläge zur Sprachspezifikation an:</span><span class="sxs-lookup"><span data-stu-id="49d5a-173">You can also see the language specification proposals:</span></span>

- [<span data-ttu-id="49d5a-174">readonly-Referenz und readonly-Struktur</span><span class="sxs-lookup"><span data-stu-id="49d5a-174">readonly ref and readonly struct</span></span>](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [<span data-ttu-id="49d5a-175">readonly-Strukturmember</span><span class="sxs-lookup"><span data-stu-id="49d5a-175">readonly struct members</span></span>](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a><span data-ttu-id="49d5a-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49d5a-176">See also</span></span>

- [<span data-ttu-id="49d5a-177">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="49d5a-177">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="49d5a-178">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="49d5a-178">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="49d5a-179">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="49d5a-179">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="49d5a-180">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="49d5a-180">Modifiers</span></span>](index.md)
- [<span data-ttu-id="49d5a-181">const</span><span class="sxs-lookup"><span data-stu-id="49d5a-181">const</span></span>](const.md)
- [<span data-ttu-id="49d5a-182">Felder</span><span class="sxs-lookup"><span data-stu-id="49d5a-182">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
