---
description: readonly-Schlüsselwort – C#-Referenz
title: readonly-Schlüsselwort – C#-Referenz
ms.date: 04/14/2020
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: b1bab5af18216fcef2162179493dbbb59e3470cf
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137174"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="1c518-103">readonly (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="1c518-103">readonly (C# Reference)</span></span>

<span data-ttu-id="1c518-104">Das Schlüsselwort `readonly` ist ein Modifizierer, der in vier Kontexten verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="1c518-104">The `readonly` keyword is a modifier that can be used in four contexts:</span></span>

- <span data-ttu-id="1c518-105">In einer [Felddeklaration](#readonly-field-example) gibt `readonly` an, dass die Zuweisung zum Feld nur als Teil der Deklaration oder in einem Konstruktor derselben Klasse erfolgen kann.</span><span class="sxs-lookup"><span data-stu-id="1c518-105">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="1c518-106">Ein readonly-Feld kann innerhalb der Felddeklaration und des Konstruktors mehrmals zugewiesen und neu zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="1c518-106">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span>
  
  <span data-ttu-id="1c518-107">Ein `readonly`-Feld kann nicht zugewiesen werden, sobald der Konstruktor vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1c518-107">A `readonly` field can't be assigned after the constructor exits.</span></span> <span data-ttu-id="1c518-108">Diese Regel hat verschiedene Auswirkungen auf Wert- und Verweistypen:</span><span class="sxs-lookup"><span data-stu-id="1c518-108">This rule has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="1c518-109">Da Werttypen ihre Daten direkt enthalten, ist ein Feld des Werttyps `readonly` unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="1c518-109">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span>
  - <span data-ttu-id="1c518-110">Da Verweistypen einen Verweis auf ihre Daten enthalten, muss ein Feld des Verweistyps `readonly` immer auf das gleiche Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="1c518-110">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="1c518-111">Dieses Objekt ist nicht unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="1c518-111">That object isn't immutable.</span></span> <span data-ttu-id="1c518-112">Der `readonly`-Modifizierer verhindert, dass das Feld durch eine andere Instanz des Verweistyps ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="1c518-112">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="1c518-113">Der Modifizierer verhindert jedoch nicht, dass die Instanzdaten des Felds durch das schreibgeschützte Feld geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1c518-113">However, the modifier doesn't prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="1c518-114">Ein extern sichtbarer Typ, der ein extern sichtbares schreibgeschütztes Feld enthält, bei dem es sich um einen änderbaren Verweistyp handelt, kann ein Sicherheitsrisiko darstellen und die folgende Warnung auslösen: [CA2104](/visualstudio/code-quality/ca2104): „Schreibgeschützte änderbare Verweistypen nicht deklarieren.“</span><span class="sxs-lookup"><span data-stu-id="1c518-114">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="1c518-115">In einer `readonly struct`-Typdefinition weist `readonly` darauf hin, dass der Strukturtyp unveränderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1c518-115">In a `readonly struct` type definition, `readonly` indicates that the structure type is immutable.</span></span> <span data-ttu-id="1c518-116">Weitere Informationen finden Sie im Abschnitt zur [`readonly`-Struktur](../builtin-types/struct.md#readonly-struct) des Artikels [Strukturtypen](../builtin-types/struct.md).</span><span class="sxs-lookup"><span data-stu-id="1c518-116">For more information, see the [`readonly` struct](../builtin-types/struct.md#readonly-struct) section of the [Structure types](../builtin-types/struct.md) article.</span></span>
- <span data-ttu-id="1c518-117">In einer Instanzmemberdeklaration innerhalb eines Strukturtyps gibt `readonly` an, dass ein Instanzmember den Zustand einer Struktur nicht ändert.</span><span class="sxs-lookup"><span data-stu-id="1c518-117">In an instance member declaration within a structure type, `readonly` indicates that an instance member doesn't modify the state of the structure.</span></span> <span data-ttu-id="1c518-118">Weitere Informationen finden Sie im Abschnitt [`readonly`-Instanzmember](../builtin-types/struct.md#readonly-instance-members) des Artikels [Strukturtypen](../builtin-types/struct.md).</span><span class="sxs-lookup"><span data-stu-id="1c518-118">For more information, see the [`readonly` instance members](../builtin-types/struct.md#readonly-instance-members) section of the [Structure types](../builtin-types/struct.md) article.</span></span>
- <span data-ttu-id="1c518-119">In einer [`ref readonly`-Methodenrückgabe](#ref-readonly-return-example) gibt der `readonly`-Modifizierer an, dass die Methode eine Referenz zurückgibt, und Schreibvorgänge für diese Referenz nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="1c518-119">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes aren't allowed to that reference.</span></span>

<span data-ttu-id="1c518-120">Die `readonly struct`- und `ref readonly`-Kontexte wurden in C# 7.2 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1c518-120">The `readonly struct` and `ref readonly` contexts were added in C# 7.2.</span></span> <span data-ttu-id="1c518-121">`readonly`-Strukturmember wurden in C# 8.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1c518-121">`readonly` struct members were added in C# 8.0</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="1c518-122">Beispiel für ein readonly-Feld</span><span class="sxs-lookup"><span data-stu-id="1c518-122">Readonly field example</span></span>

<span data-ttu-id="1c518-123">In diesem Beispiel kann der Wert des Felds `year` nicht zur Methode `ChangeYear` geändert werden, obwohl ihm im Klassenkonstruktor ein Wert zugewiesen ist:</span><span class="sxs-lookup"><span data-stu-id="1c518-123">In this example, the value of the field `year` can't be changed in the method `ChangeYear`, even though it's assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](snippets/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="1c518-124">Sie können einem `readonly`-Feld nur in den folgenden Kontexten einen Wert zuweisen:</span><span class="sxs-lookup"><span data-stu-id="1c518-124">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="1c518-125">Wenn die Variable in der Deklaration initialisiert ist, z.B.:</span><span class="sxs-lookup"><span data-stu-id="1c518-125">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="1c518-126">In einem Instanzenkonstruktor der Klasse, die die Deklaration des Instanzfelds enthält.</span><span class="sxs-lookup"><span data-stu-id="1c518-126">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="1c518-127">Im statischen Konstruktor der Klasse, die die Deklaration des statischen Felds enthält.</span><span class="sxs-lookup"><span data-stu-id="1c518-127">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="1c518-128">Diese Konstruktorkontexte sind auch die einzigen Kontexte, in denen es zulässig ist, ein `readonly`-Feld als [out](out-parameter-modifier.md)- oder [ref](ref.md)-Parameter zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="1c518-128">These constructor contexts are also the only contexts in which it's valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="1c518-129">Das Schlüsselwort `readonly` unterscheidet sich vom Schlüsselwort [const](const.md).</span><span class="sxs-lookup"><span data-stu-id="1c518-129">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="1c518-130">Ein `const`-Feld kann nur bei der Deklaration des Felds initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="1c518-130">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="1c518-131">Ein `readonly`-Feld kann mehrere Male in der Felddeklaration und in einem Konstruktor zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="1c518-131">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="1c518-132">Daher können `readonly`-Felder abhängig vom verwendeten Konstruktor über unterschiedliche Werte verfügen.</span><span class="sxs-lookup"><span data-stu-id="1c518-132">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="1c518-133">Außerdem ist ein `const`-Feld eine Kompilierzeitkonstante, während ein `readonly`-Feld wie im folgenden Beispiel für Laufzeitkonstanten verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="1c518-133">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](snippets/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="1c518-134">Wenn Sie im vorherigen Beispiel eine Anweisung wie die folgende verwenden:</span><span class="sxs-lookup"><span data-stu-id="1c518-134">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="1c518-135">erhalten Sie die Compilerfehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="1c518-135">you'll get the compiler error message:</span></span>

<span data-ttu-id="1c518-136">**Einem schreibgeschützten Feld kann nichts zugewiesen werden (außer in einem Konstruktor oder Variableninitialisierer)**</span><span class="sxs-lookup"><span data-stu-id="1c518-136">**A readonly field cannot be assigned to (except in a constructor or a variable initializer)**</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="1c518-137">Rückgabebeispiel für ref readonly</span><span class="sxs-lookup"><span data-stu-id="1c518-137">Ref readonly return example</span></span>

<span data-ttu-id="1c518-138">Der `readonly`-Modifizierer für `ref return` gibt an, dass der zurückgegebene Verweis nicht geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="1c518-138">The `readonly` modifier on a `ref return` indicates that the returned reference can't be modified.</span></span> <span data-ttu-id="1c518-139">Das folgende Beispiel gibt einen Verweis auf den Ursprung zurück.</span><span class="sxs-lookup"><span data-stu-id="1c518-139">The following example returns a reference to the origin.</span></span> <span data-ttu-id="1c518-140">Dabei wird über den `readonly`-Modifizierer angegeben, dass die aufrufenden Funktionen den Ursprung nicht ändern können:</span><span class="sxs-lookup"><span data-stu-id="1c518-140">It uses the `readonly` modifier to indicate that callers can't modify the origin:</span></span>

[!code-csharp[readonly return example](snippets/ReadonlyKeywordExamples.cs#ReadonlyReturn)]

<span data-ttu-id="1c518-141">Der zurückgegebene Typ muss nicht `readonly struct` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1c518-141">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="1c518-142">Jeder Typ, der von `ref` zurückgegeben werden kann, kann auch von `ref readonly` zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1c518-142">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1c518-143">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="1c518-143">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

<span data-ttu-id="1c518-144">Sehen Sie sich auch die Vorschläge zur Sprachspezifikation an:</span><span class="sxs-lookup"><span data-stu-id="1c518-144">You can also see the language specification proposals:</span></span>

- [<span data-ttu-id="1c518-145">readonly-Referenz und readonly-Struktur</span><span class="sxs-lookup"><span data-stu-id="1c518-145">readonly ref and readonly struct</span></span>](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [<span data-ttu-id="1c518-146">readonly-Strukturmember</span><span class="sxs-lookup"><span data-stu-id="1c518-146">readonly struct members</span></span>](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a><span data-ttu-id="1c518-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c518-147">See also</span></span>

- [<span data-ttu-id="1c518-148">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="1c518-148">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1c518-149">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="1c518-149">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1c518-150">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="1c518-150">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="1c518-151">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="1c518-151">Modifiers</span></span>](index.md)
- [<span data-ttu-id="1c518-152">const</span><span class="sxs-lookup"><span data-stu-id="1c518-152">const</span></span>](const.md)
- [<span data-ttu-id="1c518-153">Felder</span><span class="sxs-lookup"><span data-stu-id="1c518-153">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
