---
title: readonly-Schlüsselwort – C#-Referenz
ms.date: 04/14/2020
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 66a096e8831f72a2216e8ba5dd9866046504624f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84368620"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="02deb-102">readonly (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="02deb-102">readonly (C# Reference)</span></span>

<span data-ttu-id="02deb-103">Das Schlüsselwort `readonly` ist ein Modifizierer, der in vier Kontexten verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="02deb-103">The `readonly` keyword is a modifier that can be used in four contexts:</span></span>

- <span data-ttu-id="02deb-104">In einer [Felddeklaration](#readonly-field-example) gibt `readonly` an, dass die Zuweisung zum Feld nur als Teil der Deklaration oder in einem Konstruktor derselben Klasse erfolgen kann.</span><span class="sxs-lookup"><span data-stu-id="02deb-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="02deb-105">Ein readonly-Feld kann innerhalb der Felddeklaration und des Konstruktors mehrmals zugewiesen und neu zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="02deb-105">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span>
  
  <span data-ttu-id="02deb-106">Ein `readonly`-Feld kann nicht zugewiesen werden, sobald der Konstruktor vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="02deb-106">A `readonly` field can't be assigned after the constructor exits.</span></span> <span data-ttu-id="02deb-107">Diese Regel hat verschiedene Auswirkungen auf Wert- und Verweistypen:</span><span class="sxs-lookup"><span data-stu-id="02deb-107">This rule has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="02deb-108">Da Werttypen ihre Daten direkt enthalten, ist ein Feld des Werttyps `readonly` unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="02deb-108">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span>
  - <span data-ttu-id="02deb-109">Da Verweistypen einen Verweis auf ihre Daten enthalten, muss ein Feld des Verweistyps `readonly` immer auf das gleiche Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="02deb-109">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="02deb-110">Dieses Objekt ist nicht unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="02deb-110">That object isn't immutable.</span></span> <span data-ttu-id="02deb-111">Der `readonly`-Modifizierer verhindert, dass das Feld durch eine andere Instanz des Verweistyps ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="02deb-111">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="02deb-112">Der Modifizierer verhindert jedoch nicht, dass die Instanzdaten des Felds durch das schreibgeschützte Feld geändert werden.</span><span class="sxs-lookup"><span data-stu-id="02deb-112">However, the modifier doesn't prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="02deb-113">Ein extern sichtbarer Typ, der ein extern sichtbares schreibgeschütztes Feld enthält, bei dem es sich um einen änderbaren Verweistyp handelt, kann ein Sicherheitsrisiko darstellen und die folgende Warnung auslösen: [CA2104](/visualstudio/code-quality/ca2104): „Schreibgeschützte änderbare Verweistypen nicht deklarieren.“</span><span class="sxs-lookup"><span data-stu-id="02deb-113">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="02deb-114">In einer `readonly struct`-Typdefinition weist `readonly` darauf hin, dass der Strukturtyp unveränderlich ist.</span><span class="sxs-lookup"><span data-stu-id="02deb-114">In a `readonly struct` type definition, `readonly` indicates that the structure type is immutable.</span></span> <span data-ttu-id="02deb-115">Weitere Informationen finden Sie im Abschnitt zur [`readonly`-Struktur](../builtin-types/struct.md#readonly-struct) des Artikels [Strukturtypen](../builtin-types/struct.md).</span><span class="sxs-lookup"><span data-stu-id="02deb-115">For more information, see the [`readonly` struct](../builtin-types/struct.md#readonly-struct) section of the [Structure types](../builtin-types/struct.md) article.</span></span>
- <span data-ttu-id="02deb-116">In einer Instanzmemberdeklaration innerhalb eines Strukturtyps gibt `readonly` an, dass ein Instanzmember den Zustand einer Struktur nicht ändert.</span><span class="sxs-lookup"><span data-stu-id="02deb-116">In an instance member declaration within a structure type, `readonly` indicates that an instance member doesn't modify the state of the structure.</span></span> <span data-ttu-id="02deb-117">Weitere Informationen finden Sie im Abschnitt [`readonly`-Instanzmember](../builtin-types/struct.md#readonly-instance-members) des Artikels [Strukturtypen](../builtin-types/struct.md).</span><span class="sxs-lookup"><span data-stu-id="02deb-117">For more information, see the [`readonly` instance members](../builtin-types/struct.md#readonly-instance-members) section of the [Structure types](../builtin-types/struct.md) article.</span></span>
- <span data-ttu-id="02deb-118">In einer [`ref readonly`-Methodenrückgabe](#ref-readonly-return-example) gibt der `readonly`-Modifizierer an, dass die Methode eine Referenz zurückgibt, und Schreibvorgänge für diese Referenz nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="02deb-118">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes aren't allowed to that reference.</span></span>

<span data-ttu-id="02deb-119">Die `readonly struct`- und `ref readonly`-Kontexte wurden in C# 7.2 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="02deb-119">The `readonly struct` and `ref readonly` contexts were added in C# 7.2.</span></span> <span data-ttu-id="02deb-120">`readonly`-Strukturmember wurden in C# 8.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="02deb-120">`readonly` struct members were added in C# 8.0</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="02deb-121">Beispiel für ein readonly-Feld</span><span class="sxs-lookup"><span data-stu-id="02deb-121">Readonly field example</span></span>

<span data-ttu-id="02deb-122">In diesem Beispiel kann der Wert des Felds `year` nicht zur Methode `ChangeYear` geändert werden, obwohl ihm im Klassenkonstruktor ein Wert zugewiesen ist:</span><span class="sxs-lookup"><span data-stu-id="02deb-122">In this example, the value of the field `year` can't be changed in the method `ChangeYear`, even though it's assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](snippets/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="02deb-123">Sie können einem `readonly`-Feld nur in den folgenden Kontexten einen Wert zuweisen:</span><span class="sxs-lookup"><span data-stu-id="02deb-123">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="02deb-124">Wenn die Variable in der Deklaration initialisiert ist, z.B.:</span><span class="sxs-lookup"><span data-stu-id="02deb-124">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="02deb-125">In einem Instanzenkonstruktor der Klasse, die die Deklaration des Instanzfelds enthält.</span><span class="sxs-lookup"><span data-stu-id="02deb-125">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="02deb-126">Im statischen Konstruktor der Klasse, die die Deklaration des statischen Felds enthält.</span><span class="sxs-lookup"><span data-stu-id="02deb-126">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="02deb-127">Diese Konstruktorkontexte sind auch die einzigen Kontexte, in denen es zulässig ist, ein `readonly`-Feld als [out](out-parameter-modifier.md)- oder [ref](ref.md)-Parameter zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="02deb-127">These constructor contexts are also the only contexts in which it's valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="02deb-128">Das Schlüsselwort `readonly` unterscheidet sich vom Schlüsselwort [const](const.md).</span><span class="sxs-lookup"><span data-stu-id="02deb-128">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="02deb-129">Ein `const`-Feld kann nur bei der Deklaration des Felds initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="02deb-129">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="02deb-130">Ein `readonly`-Feld kann mehrere Male in der Felddeklaration und in einem Konstruktor zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="02deb-130">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="02deb-131">Daher können `readonly`-Felder abhängig vom verwendeten Konstruktor über unterschiedliche Werte verfügen.</span><span class="sxs-lookup"><span data-stu-id="02deb-131">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="02deb-132">Außerdem ist ein `const`-Feld eine Kompilierzeitkonstante, während ein `readonly`-Feld wie im folgenden Beispiel für Laufzeitkonstanten verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="02deb-132">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](snippets/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="02deb-133">Wenn Sie im vorherigen Beispiel eine Anweisung wie die folgende verwenden:</span><span class="sxs-lookup"><span data-stu-id="02deb-133">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="02deb-134">erhalten Sie die Compilerfehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="02deb-134">you'll get the compiler error message:</span></span>

<span data-ttu-id="02deb-135">**Einem schreibgeschützten Feld kann nichts zugewiesen werden (außer in einem Konstruktor oder Variableninitialisierer)**</span><span class="sxs-lookup"><span data-stu-id="02deb-135">**A readonly field cannot be assigned to (except in a constructor or a variable initializer)**</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="02deb-136">Rückgabebeispiel für ref readonly</span><span class="sxs-lookup"><span data-stu-id="02deb-136">Ref readonly return example</span></span>

<span data-ttu-id="02deb-137">Der `readonly`-Modifizierer für `ref return` gibt an, dass der zurückgegebene Verweis nicht geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="02deb-137">The `readonly` modifier on a `ref return` indicates that the returned reference can't be modified.</span></span> <span data-ttu-id="02deb-138">Das folgende Beispiel gibt einen Verweis auf den Ursprung zurück.</span><span class="sxs-lookup"><span data-stu-id="02deb-138">The following example returns a reference to the origin.</span></span> <span data-ttu-id="02deb-139">Dabei wird über den `readonly`-Modifizierer angegeben, dass die aufrufenden Funktionen den Ursprung nicht ändern können:</span><span class="sxs-lookup"><span data-stu-id="02deb-139">It uses the `readonly` modifier to indicate that callers can't modify the origin:</span></span>

[!code-csharp[readonly return example](snippets/ReadonlyKeywordExamples.cs#ReadonlyReturn)]

<span data-ttu-id="02deb-140">Der zurückgegebene Typ muss nicht `readonly struct` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="02deb-140">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="02deb-141">Jeder Typ, der von `ref` zurückgegeben werden kann, kann auch von `ref readonly` zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="02deb-141">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="02deb-142">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="02deb-142">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

<span data-ttu-id="02deb-143">Sehen Sie sich auch die Vorschläge zur Sprachspezifikation an:</span><span class="sxs-lookup"><span data-stu-id="02deb-143">You can also see the language specification proposals:</span></span>

- [<span data-ttu-id="02deb-144">readonly-Referenz und readonly-Struktur</span><span class="sxs-lookup"><span data-stu-id="02deb-144">readonly ref and readonly struct</span></span>](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [<span data-ttu-id="02deb-145">readonly-Strukturmember</span><span class="sxs-lookup"><span data-stu-id="02deb-145">readonly struct members</span></span>](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a><span data-ttu-id="02deb-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02deb-146">See also</span></span>

- [<span data-ttu-id="02deb-147">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="02deb-147">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="02deb-148">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="02deb-148">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="02deb-149">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="02deb-149">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="02deb-150">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="02deb-150">Modifiers</span></span>](index.md)
- [<span data-ttu-id="02deb-151">const</span><span class="sxs-lookup"><span data-stu-id="02deb-151">const</span></span>](const.md)
- [<span data-ttu-id="02deb-152">Felder</span><span class="sxs-lookup"><span data-stu-id="02deb-152">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
