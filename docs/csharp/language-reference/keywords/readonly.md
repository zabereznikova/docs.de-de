---
title: Schlüsselwort „readonly“ (C#-Referenz)
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: d09ce4ea972a3064298eebdf0b8b80999ee8441e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44227284"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="877e4-102">readonly (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="877e4-102">readonly (C# Reference)</span></span>

<span data-ttu-id="877e4-103">Das Schlüsselwort `readonly` ist ein Modifizierer, der in drei Kontexten verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="877e4-103">The `readonly` keyword is a modifier that can be used in three contexts:</span></span>

- <span data-ttu-id="877e4-104">In einer [Felddeklaration](#readonly-field-example) gibt `readonly` an, dass die Zuweisung zum Feld nur als Teil der Deklaration oder in einem Konstruktor derselben Klasse erfolgen kann.</span><span class="sxs-lookup"><span data-stu-id="877e4-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span>
- <span data-ttu-id="877e4-105">In einer [`readonly struct`-Definition](#readonly-struct-example) gibt `readonly` an, dass `struct` unveränderlich ist.</span><span class="sxs-lookup"><span data-stu-id="877e4-105">In a [`readonly struct` definition](#readonly-struct-example), `readonly` indicates that the `struct` is immutable.</span></span>
- <span data-ttu-id="877e4-106">In einer [`ref readonly`-Methodenrückgabe](#ref-readonly-return-example) gibt der `readonly`-Modifizierer an, dass die Methode eine Referenz zurückgibt, und Schreibvorgänge für diese Referenz nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="877e4-106">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes are not allowed to that reference.</span></span>

<span data-ttu-id="877e4-107">Die letzten beiden Kontexte wurden in C# 7.2 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="877e4-107">The final two contexts were added in C# 7.2.</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="877e4-108">Beispiel für ein readonly-Feld</span><span class="sxs-lookup"><span data-stu-id="877e4-108">Readonly field example</span></span>

<span data-ttu-id="877e4-109">In diesem Beispiel kann der Wert des Felds `year` nicht zur Methode `ChangeYear` geändert werden, obwohl ihm im Klassenkonstruktor ein Wert zugewiesen ist:</span><span class="sxs-lookup"><span data-stu-id="877e4-109">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="877e4-110">Sie können einem `readonly`-Feld nur in den folgenden Kontexten einen Wert zuweisen:</span><span class="sxs-lookup"><span data-stu-id="877e4-110">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="877e4-111">Wenn die Variable in der Deklaration initialisiert ist, z.B.:</span><span class="sxs-lookup"><span data-stu-id="877e4-111">When the variable is initialized in the declaration, for example:</span></span>

```csharp
public readonly int y = 5;
```

- <span data-ttu-id="877e4-112">In einem Instanzenkonstruktor der Klasse, die die Deklaration des Instanzfelds enthält.</span><span class="sxs-lookup"><span data-stu-id="877e4-112">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="877e4-113">Im statischen Konstruktor der Klasse, die die Deklaration des statischen Felds enthält.</span><span class="sxs-lookup"><span data-stu-id="877e4-113">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="877e4-114">Diese Konstruktorkontexte sind auch die einzigen Kontexte, in denen es gültig ist, ein `readonly`-Feld als [out](out-parameter-modifier.md)- oder [ref](ref.md)-Parameter zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="877e4-114">These constructor contexts are also the only contexts in which it is valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="877e4-115">Das Schlüsselwort `readonly` unterscheidet sich vom Schlüsselwort [const](const.md).</span><span class="sxs-lookup"><span data-stu-id="877e4-115">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="877e4-116">Ein `const`-Feld kann nur bei der Deklaration des Felds initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="877e4-116">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="877e4-117">Ein `readonly`-Feld kann entweder bei der Deklaration oder in einem Konstruktor initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="877e4-117">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="877e4-118">Daher können `readonly`-Felder abhängig vom verwendeten Konstruktor über unterschiedliche Werte verfügen.</span><span class="sxs-lookup"><span data-stu-id="877e4-118">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="877e4-119">Außerdem ist ein `const`-Feld eine Kompilierzeitkonstante, während ein `readonly`-Feld wie im folgenden Beispiel für Laufzeitkonstanten verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="877e4-119">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>

```csharp
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="877e4-120">Wenn Sie im vorherigen Beispiel eine Anweisung wie die folgende verwenden:</span><span class="sxs-lookup"><span data-stu-id="877e4-120">In the preceding example, if you use a statement like the following example:</span></span>

`p2.y = 66;        // Error`

<span data-ttu-id="877e4-121">erhalten Sie die Compilerfehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="877e4-121">you will get the compiler error message:</span></span>

`A readonly field cannot be assigned to (except in a constructor or a variable initializer)`

## <a name="readonly-struct-example"></a><span data-ttu-id="877e4-122">Beispiel für readonly struct</span><span class="sxs-lookup"><span data-stu-id="877e4-122">Readonly struct example</span></span>

<span data-ttu-id="877e4-123">Der `readonly`-Modifizierer für eine `struct`-Definition deklariert, dass die Struktur **unveränderlich** ist.</span><span class="sxs-lookup"><span data-stu-id="877e4-123">The `readonly` modifier on a `struct` definition declares that the struct is **immutable**.</span></span> <span data-ttu-id="877e4-124">Jedes Instanzfeld für `struct` muss mit `readonly` markiert sein, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="877e4-124">Every instance field of the `struct` must be marked `readonly`, as shown in the following example:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]

<span data-ttu-id="877e4-125">Das vorhergehende Beispiel verwendet [schreibgeschützte automatische Eigenschaften](../../properties.md#read-only), um den Speicher zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="877e4-125">The preceding example uses [readonly auto properties](../../properties.md#read-only) to declare its storage.</span></span> <span data-ttu-id="877e4-126">Dadurch wird der Compiler angewiesen, `readonly`-Unterstützungsfelder für diese Eigenschaften zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="877e4-126">That instructs the compiler to create `readonly` backing fields for those properties.</span></span> <span data-ttu-id="877e4-127">Sie können `readonly`-Felder auch direkt deklarieren:</span><span class="sxs-lookup"><span data-stu-id="877e4-127">You could also declare `readonly` fields directly:</span></span>

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

<span data-ttu-id="877e4-128">Das Hinzufügen eines Felds, das nicht mit `readonly` markiert ist, erzeugt den Compilerfehler `CS8340`: „Instanzfelder oder schreibgeschützten Strukturen müssen schreibgeschützt sein.“</span><span class="sxs-lookup"><span data-stu-id="877e4-128">Adding a field not marked `readonly` generates compiler error `CS8340`: "Instance fields of readonly structs must be readonly."</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="877e4-129">Rückgabebeispiel für ref readonly</span><span class="sxs-lookup"><span data-stu-id="877e4-129">Ref readonly return example</span></span>

<span data-ttu-id="877e4-130">Der Modifizierer `readonly` für `ref return` gibt an, dass die zurückgegebene Referenz nicht geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="877e4-130">The `readonly` modifier on a `ref return` indicates that the returned reference cannot be modified.</span></span> <span data-ttu-id="877e4-131">Das folgende Beispiel gibt einen Verweis auf den Ursprung zurück.</span><span class="sxs-lookup"><span data-stu-id="877e4-131">The following example returns a reference to the origin.</span></span> <span data-ttu-id="877e4-132">Der `readonly`-Modifizierer gibt dabei an, dass die aufrufenden Funktionen den Ursprung nicht ändern können:</span><span class="sxs-lookup"><span data-stu-id="877e4-132">It uses the `readonly` modifier to indicate that callers cannot modify the origin:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
<span data-ttu-id="877e4-133">Der zurückgegebene Typ muss nicht `readonly struct` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="877e4-133">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="877e4-134">Jeder Typ, der von `ref` zurückgegeben werden kann, kann auch von `ref readonly` zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="877e4-134">Any type that can be returned by `ref` can be returned by `ref readonly`</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="877e4-135">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="877e4-135">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="877e4-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="877e4-136">See also</span></span>

- [<span data-ttu-id="877e4-137">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="877e4-137">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="877e4-138">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="877e4-138">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="877e4-139">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="877e4-139">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="877e4-140">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="877e4-140">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="877e4-141">const</span><span class="sxs-lookup"><span data-stu-id="877e4-141">const</span></span>](const.md)
- [<span data-ttu-id="877e4-142">Felder</span><span class="sxs-lookup"><span data-stu-id="877e4-142">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
