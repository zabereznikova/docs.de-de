---
title: Werttypen – C#-Referenz
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: b264be5d2589455562a19ef55b5ddf1a4e74ce15
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428450"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="0c888-102">Werttypen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="0c888-102">Value types (C# Reference)</span></span>

<span data-ttu-id="0c888-103">Es gibt zwei Werttypen:</span><span class="sxs-lookup"><span data-stu-id="0c888-103">There are two kinds of value types:</span></span>

- [<span data-ttu-id="0c888-104">Strukturen</span><span class="sxs-lookup"><span data-stu-id="0c888-104">Structs</span></span>](struct.md)

- [<span data-ttu-id="0c888-105">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="0c888-105">Enumerations</span></span>](enum.md)

## <a name="main-features-of-value-types"></a><span data-ttu-id="0c888-106">Hauptfunktionen von Werttypen</span><span class="sxs-lookup"><span data-stu-id="0c888-106">Main features of value types</span></span>

<span data-ttu-id="0c888-107">Eine Variable eines Werttyps enthält einen Wert des Typs.</span><span class="sxs-lookup"><span data-stu-id="0c888-107">A variable of a value type contains a value of the type.</span></span> <span data-ttu-id="0c888-108">Beispielsweise kann eine Variable von Typ `int` den `42`-Wert enthalten.</span><span class="sxs-lookup"><span data-stu-id="0c888-108">For example, a variable of the `int` type might contain the value `42`.</span></span> <span data-ttu-id="0c888-109">Dies unterscheidet sich von einer Variablen eines Referenztyps, die eine Referenz auf eine Instanz des Typs enthält, auch bekannt als Objekt.</span><span class="sxs-lookup"><span data-stu-id="0c888-109">This differs from a variable of a reference type, which contains a reference to an instance of the type, also known as an object.</span></span> <span data-ttu-id="0c888-110">Wenn Sie einer Variablen eines Werttyps einen neuen Wert zuweisen, wird der Wert kopiert.</span><span class="sxs-lookup"><span data-stu-id="0c888-110">When you assign a new value to a variable of a value type, that value is copied.</span></span> <span data-ttu-id="0c888-111">Wenn Sie einer Variablen eines Referenztyps einen neuen Wert zuweisen, wird die Referenz kopiert, nicht das Objekt selbst.</span><span class="sxs-lookup"><span data-stu-id="0c888-111">When you assign a new value to a variable of a reference type, the reference is copied, not the object itself.</span></span>

<span data-ttu-id="0c888-112">Alle Werttypen werden implizit von <xref:System.ValueType?displayProperty=nameWithType> abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="0c888-112">All value types are derived implicitly from the <xref:System.ValueType?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="0c888-113">Im Gegensatz zu Verweistypen können Sie von Werttypen keinen neuen ableiten.</span><span class="sxs-lookup"><span data-stu-id="0c888-113">Unlike with reference types, you cannot derive a new type from a value type.</span></span> <span data-ttu-id="0c888-114">Strukturen können aber wie Verweistypen Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="0c888-114">However, like reference types, structs can implement interfaces.</span></span>

<span data-ttu-id="0c888-115">Werttypvariablen können nicht standardmäßig `null` sein.</span><span class="sxs-lookup"><span data-stu-id="0c888-115">Value type variables cannot be `null` by default.</span></span> <span data-ttu-id="0c888-116">Variablen der entsprechenden [Nullable-Werttypen](../builtin-types/nullable-value-types.md) können jedoch `null` sein.</span><span class="sxs-lookup"><span data-stu-id="0c888-116">However, variables of the corresponding [nullable value types](../builtin-types/nullable-value-types.md) can be `null`.</span></span>

<span data-ttu-id="0c888-117">Jeder Werttyp hat einen impliziten parameterlosen Konstruktor, der den Standardwert dieses Typs initialisiert.</span><span class="sxs-lookup"><span data-stu-id="0c888-117">Each value type has an implicit parameterless constructor that initializes the default value of that type.</span></span> <span data-ttu-id="0c888-118">Informationen zu den Standardwerten von Werttypen finden Sie unter [Tabelle für Standardwerte](default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="0c888-118">For information about default values of value types, see [Default values table](default-values-table.md).</span></span>

## <a name="simple-types"></a><span data-ttu-id="0c888-119">Einfache Typen</span><span class="sxs-lookup"><span data-stu-id="0c888-119">Simple types</span></span>

<span data-ttu-id="0c888-120">Die *einfachen Typen* sind eine Reihe von vordefinierten Strukturtypen, die von C# bereitgestellt werden, und umfassen die folgenden Typen:</span><span class="sxs-lookup"><span data-stu-id="0c888-120">The *simple types* are a set of predefined struct types provided by C# and comprise the following types:</span></span>

- <span data-ttu-id="0c888-121">[Ganzzahltypen](../builtin-types/integral-numeric-types.md): ganzzahlige numerische Typen und der [char](../builtin-types/char.md)-Typ</span><span class="sxs-lookup"><span data-stu-id="0c888-121">[Integral types](../builtin-types/integral-numeric-types.md): integer numeric types and the [char](../builtin-types/char.md) type</span></span>
- [<span data-ttu-id="0c888-122">Gleitkommatypen</span><span class="sxs-lookup"><span data-stu-id="0c888-122">Floating-point types</span></span>](../builtin-types/floating-point-numeric-types.md)
- [<span data-ttu-id="0c888-123">bool</span><span class="sxs-lookup"><span data-stu-id="0c888-123">bool</span></span>](bool.md)

<span data-ttu-id="0c888-124">Die einfachen Typen werden durch Schlüsselwörter identifiziert, aber diese Schlüsselwörter sind einfach Aliase für vordefinierte Strukturtypen im Namespace <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="0c888-124">The simple types are identified through keywords, but these keywords are simply aliases for predefined struct types in the <xref:System> namespace.</span></span> <span data-ttu-id="0c888-125">[int](../builtin-types/integral-numeric-types.md) ist z.B. ein Alias von <xref:System.Int32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0c888-125">For example, [int](../builtin-types/integral-numeric-types.md) is an alias of <xref:System.Int32?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0c888-126">Eine vollständige Liste der Aliase finden Sie unter [Tabelle integrierter Typen](built-in-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="0c888-126">For a complete list of aliases, see [Built-in types table](built-in-types-table.md).</span></span>

<span data-ttu-id="0c888-127">Die einfachen Typen unterscheiden sich von anderen Strukturtypen dadurch, dass sie bestimmte zusätzliche Vorgänge ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="0c888-127">The simple types differ from other struct types in that they permit certain additional operations:</span></span>

- <span data-ttu-id="0c888-128">Einfache Typen können mithilfe von Literalen initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="0c888-128">Simple types can be initialized by using literals.</span></span> <span data-ttu-id="0c888-129">`'A'` ist beispielsweise ein Literal vom Typ `char`, und `2001` ist ein Literal vom Typ `int`.</span><span class="sxs-lookup"><span data-stu-id="0c888-129">For example, `'A'` is a literal of the type `char` and `2001` is a literal of the type `int`.</span></span>

- <span data-ttu-id="0c888-130">Konstanten der einfachen Typen können Sie mit dem Schlüsselwort [const](const.md) deklarieren.</span><span class="sxs-lookup"><span data-stu-id="0c888-130">You can declare constants of the simple types with the [const](const.md) keyword.</span></span> <span data-ttu-id="0c888-131">Es ist nicht möglich, Konstanten anderer Strukturtypen zu haben.</span><span class="sxs-lookup"><span data-stu-id="0c888-131">It's not possible to have constants of other struct types.</span></span>

- <span data-ttu-id="0c888-132">Konstante Ausdrücke, deren Operanden alle einfache Typkonstanten sind, werden zur Kompilierzeit ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="0c888-132">Constant expressions, whose operands are all simple type constants, are evaluated at compile time.</span></span>

<span data-ttu-id="0c888-133">Weitere Informationen finden Sie im Abschnitt [Einfache Typen](~/_csharplang/spec/types.md#simple-types) der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="0c888-133">For more information, see the [Simple types](~/_csharplang/spec/types.md#simple-types) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="initializing-value-types"></a><span data-ttu-id="0c888-134">Initialisieren von Werttypen</span><span class="sxs-lookup"><span data-stu-id="0c888-134">Initializing value types</span></span>

<span data-ttu-id="0c888-135">Lokale Variablen in C# müssen vor ihrer Verwendung initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="0c888-135">Local variables in C# must be initialized before they are used.</span></span> <span data-ttu-id="0c888-136">Sie könnten eine lokale Variable beispielsweise ohne Initialisierung wie im folgenden Beispiel deklarieren:</span><span class="sxs-lookup"><span data-stu-id="0c888-136">For example, you might declare a local variable without initialization as in the following example:</span></span>

```csharp
int myInt;
```

<span data-ttu-id="0c888-137">Sie können sie nicht verwenden, bis Sie sie initialisiert haben.</span><span class="sxs-lookup"><span data-stu-id="0c888-137">You cannot use it before you initialize it.</span></span> <span data-ttu-id="0c888-138">Sie können sie mit der folgenden Anweisung initialisieren:</span><span class="sxs-lookup"><span data-stu-id="0c888-138">You can initialize it using the following statement:</span></span>

```csharp
myInt = new int();  // Invoke parameterless constructor for int type.
```

<span data-ttu-id="0c888-139">Diese Anweisung entspricht der folgenden Anweisung:</span><span class="sxs-lookup"><span data-stu-id="0c888-139">This statement is equivalent to the following statement:</span></span>

```csharp
myInt = 0;         // Assign an initial value, 0 in this example.
```

<span data-ttu-id="0c888-140">Natürlich können Sie sich die Deklaration und die Initialisierung in derselben Anweisung befinden, wie in den folgenden Beispielen dargestellt:</span><span class="sxs-lookup"><span data-stu-id="0c888-140">You can, of course, have the declaration and the initialization in the same statement as in the following examples:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="0c888-141">– oder –</span><span class="sxs-lookup"><span data-stu-id="0c888-141">–or–</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="0c888-142">Durch die Verwendung des Operators [new](../operators/new-operator.md) wird der parameterlose Konstruktor des angegebenen Typs aufgerufen und der Variablen der Standardwert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0c888-142">Using the [new](../operators/new-operator.md) operator calls the parameterless constructor of the specific type and assigns the default value to the variable.</span></span> <span data-ttu-id="0c888-143">Im vorherigen Beispiel hat der parameterlose Konstruktor `myInt` den Wert `0` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0c888-143">In the preceding example, the parameterless constructor assigned the value `0` to `myInt`.</span></span> <span data-ttu-id="0c888-144">Weitere Informationen zu Werten, die durch Aufrufen parameterloser Konstruktoren zugewiesen werden, finden Sie in der [Tabelle für Standardwerte](default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="0c888-144">For more information about values assigned by calling parameterless constructors, see [Default values table](default-values-table.md).</span></span>

<span data-ttu-id="0c888-145">Verwenden Sie bei benutzerdefinierten Typen [new](../operators/new-operator.md) zum Aufrufen des parameterlosen Konstruktors.</span><span class="sxs-lookup"><span data-stu-id="0c888-145">With user-defined types, use [new](../operators/new-operator.md) to invoke the parameterless constructor.</span></span> <span data-ttu-id="0c888-146">Die folgende Anweisung ruft beispielsweise den parameterlosen Konstruktor der `Point`-Struktur auf:</span><span class="sxs-lookup"><span data-stu-id="0c888-146">For example, the following statement invokes the parameterless constructor of the `Point` struct:</span></span>

```csharp
var p = new Point(); // Invoke parameterless constructor for the struct.
```

<span data-ttu-id="0c888-147">Nach diesem Aufruf gilt die Struktur als definitiv zugewiesen. Das bedeutet, dass alle ihre Member mit ihren Standardwerten initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="0c888-147">After this call, the struct is considered to be definitely assigned; that is, all its members are initialized to their default values.</span></span>

<span data-ttu-id="0c888-148">Weitere Informationen zum `new`-Operator finden Sie unter [neu](../operators/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="0c888-148">For more information about the `new` operator, see [new](../operators/new-operator.md).</span></span>

<span data-ttu-id="0c888-149">Informationen zum Formatieren der Ausgabe von numerischen Typen finden Sie unter [Tabelle zur Formatierung numerischer Ergebnisse](formatting-numeric-results-table.md).</span><span class="sxs-lookup"><span data-stu-id="0c888-149">For information about formatting the output of numeric types, see [Formatting numeric results table](formatting-numeric-results-table.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0c888-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c888-150">See also</span></span>

- [<span data-ttu-id="0c888-151">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="0c888-151">C# reference</span></span>](../index.md)
- [<span data-ttu-id="0c888-152">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="0c888-152">C# keywords</span></span>](index.md)
- [<span data-ttu-id="0c888-153">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="0c888-153">Reference types</span></span>](reference-types.md)
- [<span data-ttu-id="0c888-154">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="0c888-154">Nullable value types</span></span>](../builtin-types/nullable-value-types.md)
