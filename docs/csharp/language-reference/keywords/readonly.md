---
title: readonly-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 4a51bb0e854de127c632c28f613a7602bf09f432
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348011"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="15779-102">readonly (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="15779-102">readonly (C# Reference)</span></span>

<span data-ttu-id="15779-103">Das Schlüsselwort `readonly` ist ein Modifizierer, der in drei Kontexten verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="15779-103">The `readonly` keyword is a modifier that can be used in three contexts:</span></span>

- <span data-ttu-id="15779-104">In einer [Felddeklaration](#readonly-field-example) gibt `readonly` an, dass die Zuweisung zum Feld nur als Teil der Deklaration oder in einem Konstruktor derselben Klasse erfolgen kann.</span><span class="sxs-lookup"><span data-stu-id="15779-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="15779-105">Ein readonly-Feld kann innerhalb der Felddeklaration und des Konstruktors mehrmals zugewiesen und neu zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="15779-105">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span> 
  
  <span data-ttu-id="15779-106">Ein `readonly`-Feld kann nicht zugewiesen werden, sobald der Konstruktor vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="15779-106">A `readonly` field cannot be assigned after the constructor exits.</span></span> <span data-ttu-id="15779-107">Dies hat verschiedene Auswirkungen auf Wert- und Verweistypen:</span><span class="sxs-lookup"><span data-stu-id="15779-107">That has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="15779-108">Da Werttypen ihre Daten direkt enthalten, ist ein Feld des Werttyps `readonly` unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="15779-108">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span> 
  - <span data-ttu-id="15779-109">Da Verweistypen einen Verweis auf ihre Daten enthalten, muss ein Feld des Verweistyps `readonly` immer auf das gleiche Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="15779-109">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="15779-110">Dieses Objekt ist nicht unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="15779-110">That object is not immutable.</span></span> <span data-ttu-id="15779-111">Der `readonly`-Modifizierer verhindert, dass das Feld durch eine andere Instanz des Verweistyps ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="15779-111">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="15779-112">Der Modifizierer verhindert jedoch nicht, dass die Instanzdaten des Felds durch das schreibgeschützte Feld geändert werden.</span><span class="sxs-lookup"><span data-stu-id="15779-112">However, the modifier does not prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="15779-113">Ein extern sichtbarer Typ, der ein extern sichtbares schreibgeschütztes Feld enthält, bei dem es sich um einen änderbaren Verweistyp handelt, kann ein Sicherheitsrisiko darstellen und die folgende Warnung auslösen: [CA2104](/visualstudio/code-quality/ca2104-do-not-declare-read-only-mutable-reference-types): „Schreibgeschützte änderbare Verweistypen nicht deklarieren.“</span><span class="sxs-lookup"><span data-stu-id="15779-113">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104-do-not-declare-read-only-mutable-reference-types) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="15779-114">In einer [`readonly struct`-Definition](#readonly-struct-example) gibt `readonly` an, dass `struct` unveränderlich ist.</span><span class="sxs-lookup"><span data-stu-id="15779-114">In a [`readonly struct` definition](#readonly-struct-example), `readonly` indicates that the `struct` is immutable.</span></span>
- <span data-ttu-id="15779-115">In einer [`ref readonly`-Methodenrückgabe](#ref-readonly-return-example) gibt der `readonly`-Modifizierer an, dass die Methode eine Referenz zurückgibt, und Schreibvorgänge für diese Referenz nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="15779-115">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes are not allowed to that reference.</span></span>

<span data-ttu-id="15779-116">Die letzten beiden Kontexte wurden in C# 7.2 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="15779-116">The final two contexts were added in C# 7.2.</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="15779-117">Beispiel für ein readonly-Feld</span><span class="sxs-lookup"><span data-stu-id="15779-117">Readonly field example</span></span>

<span data-ttu-id="15779-118">In diesem Beispiel kann der Wert des Felds `year` nicht zur Methode `ChangeYear` geändert werden, obwohl ihm im Klassenkonstruktor ein Wert zugewiesen ist:</span><span class="sxs-lookup"><span data-stu-id="15779-118">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="15779-119">Sie können einem `readonly`-Feld nur in den folgenden Kontexten einen Wert zuweisen:</span><span class="sxs-lookup"><span data-stu-id="15779-119">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="15779-120">Wenn die Variable in der Deklaration initialisiert ist, z.B.:</span><span class="sxs-lookup"><span data-stu-id="15779-120">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="15779-121">In einem Instanzenkonstruktor der Klasse, die die Deklaration des Instanzfelds enthält.</span><span class="sxs-lookup"><span data-stu-id="15779-121">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="15779-122">Im statischen Konstruktor der Klasse, die die Deklaration des statischen Felds enthält.</span><span class="sxs-lookup"><span data-stu-id="15779-122">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="15779-123">Diese Konstruktorkontexte sind auch die einzigen Kontexte, in denen es gültig ist, ein `readonly`-Feld als [out](out-parameter-modifier.md)- oder [ref](ref.md)-Parameter zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="15779-123">These constructor contexts are also the only contexts in which it is valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="15779-124">Das Schlüsselwort `readonly` unterscheidet sich vom Schlüsselwort [const](const.md).</span><span class="sxs-lookup"><span data-stu-id="15779-124">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="15779-125">Ein `const`-Feld kann nur bei der Deklaration des Felds initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="15779-125">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="15779-126">Ein `readonly`-Feld kann mehrere Male in der Felddeklaration und in einem Konstruktor zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="15779-126">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="15779-127">Daher können `readonly`-Felder abhängig vom verwendeten Konstruktor über unterschiedliche Werte verfügen.</span><span class="sxs-lookup"><span data-stu-id="15779-127">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="15779-128">Außerdem ist ein `const`-Feld eine Kompilierzeitkonstante, während ein `readonly`-Feld wie im folgenden Beispiel für Laufzeitkonstanten verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="15779-128">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="15779-129">Wenn Sie im vorherigen Beispiel eine Anweisung wie die folgende verwenden:</span><span class="sxs-lookup"><span data-stu-id="15779-129">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="15779-130">erhalten Sie die Compilerfehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="15779-130">you will get the compiler error message:</span></span>

`A readonly field cannot be assigned to (except in a constructor or a variable initializer)`

## <a name="readonly-struct-example"></a><span data-ttu-id="15779-131">Beispiel für readonly struct</span><span class="sxs-lookup"><span data-stu-id="15779-131">Readonly struct example</span></span>

<span data-ttu-id="15779-132">Der `readonly`-Modifizierer für eine `struct`-Definition deklariert, dass die Struktur **unveränderlich** ist.</span><span class="sxs-lookup"><span data-stu-id="15779-132">The `readonly` modifier on a `struct` definition declares that the struct is **immutable**.</span></span> <span data-ttu-id="15779-133">Jedes Instanzfeld für `struct` muss mit `readonly` markiert sein, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="15779-133">Every instance field of the `struct` must be marked `readonly`, as shown in the following example:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]

<span data-ttu-id="15779-134">Das vorhergehende Beispiel verwendet [schreibgeschützte automatische Eigenschaften](../../properties.md#read-only), um den Speicher zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="15779-134">The preceding example uses [readonly auto properties](../../properties.md#read-only) to declare its storage.</span></span> <span data-ttu-id="15779-135">Dadurch wird der Compiler angewiesen, `readonly`-Unterstützungsfelder für diese Eigenschaften zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="15779-135">That instructs the compiler to create `readonly` backing fields for those properties.</span></span> <span data-ttu-id="15779-136">Sie können `readonly`-Felder auch direkt deklarieren:</span><span class="sxs-lookup"><span data-stu-id="15779-136">You could also declare `readonly` fields directly:</span></span>

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

<span data-ttu-id="15779-137">Das Hinzufügen eines nicht als `readonly` markierten Felds generiert den Compilerfehler `CS8340`: Instanzfelder von schreibgeschützten Strukturen müssen schreibgeschützt sein.</span><span class="sxs-lookup"><span data-stu-id="15779-137">Adding a field not marked `readonly` generates compiler error `CS8340`: "Instance fields of readonly structs must be readonly."</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="15779-138">Rückgabebeispiel für ref readonly</span><span class="sxs-lookup"><span data-stu-id="15779-138">Ref readonly return example</span></span>

<span data-ttu-id="15779-139">Der Modifizierer `readonly` für `ref return` gibt an, dass die zurückgegebene Referenz nicht geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="15779-139">The `readonly` modifier on a `ref return` indicates that the returned reference cannot be modified.</span></span> <span data-ttu-id="15779-140">Das folgende Beispiel gibt einen Verweis auf den Ursprung zurück.</span><span class="sxs-lookup"><span data-stu-id="15779-140">The following example returns a reference to the origin.</span></span> <span data-ttu-id="15779-141">Der `readonly`-Modifizierer gibt dabei an, dass die aufrufenden Funktionen den Ursprung nicht ändern können:</span><span class="sxs-lookup"><span data-stu-id="15779-141">It uses the `readonly` modifier to indicate that callers cannot modify the origin:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
<span data-ttu-id="15779-142">Der zurückgegebene Typ muss nicht `readonly struct` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="15779-142">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="15779-143">Jeder Typ, der von `ref` zurückgegeben werden kann, kann auch von `ref readonly` zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="15779-143">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="15779-144">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="15779-144">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="15779-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15779-145">See also</span></span>

- [<span data-ttu-id="15779-146">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="15779-146">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="15779-147">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="15779-147">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="15779-148">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="15779-148">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="15779-149">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="15779-149">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="15779-150">const</span><span class="sxs-lookup"><span data-stu-id="15779-150">const</span></span>](const.md)
- [<span data-ttu-id="15779-151">Felder</span><span class="sxs-lookup"><span data-stu-id="15779-151">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
