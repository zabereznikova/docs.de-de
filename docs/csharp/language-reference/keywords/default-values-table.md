---
title: 'Tabelle für Standardwerte: C#-Referenz'
ms.custom: seodec18
description: Erfahren Sie, wie die Standardwerte der C#-Typen lauten.
ms.date: 07/29/2019
helpviewer_keywords:
- default [C#]
- parameterless constructor [C#]
ms.openlocfilehash: 48aa294fa9e37e2e138444e493faa5474011097e
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2019
ms.locfileid: "74551822"
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="a1d04-103">Tabelle für Standardwerte (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="a1d04-103">Default values table (C# reference)</span></span>

<span data-ttu-id="a1d04-104">In der folgenden Tabelle werden die Standardwerte von C#-Typen gezeigt:</span><span class="sxs-lookup"><span data-stu-id="a1d04-104">The following table shows the default values of C# types:</span></span>

|<span data-ttu-id="a1d04-105">Typ</span><span class="sxs-lookup"><span data-stu-id="a1d04-105">Type</span></span>|<span data-ttu-id="a1d04-106">Standardwert</span><span class="sxs-lookup"><span data-stu-id="a1d04-106">Default value</span></span>|
|---------|------------------|
|<span data-ttu-id="a1d04-107">Verweistyp</span><span class="sxs-lookup"><span data-stu-id="a1d04-107">Any reference type</span></span>|`null`|
|<span data-ttu-id="a1d04-108">Beliebiger [integrierter integraler numerischer Typ](../builtin-types/integral-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="a1d04-108">Any [built-in integral numeric type](../builtin-types/integral-numeric-types.md)</span></span>|<span data-ttu-id="a1d04-109">0 (null)</span><span class="sxs-lookup"><span data-stu-id="a1d04-109">0 (zero)</span></span>|
|<span data-ttu-id="a1d04-110">Beliebiger [integrierter numerischer Gleitkommatyp](../builtin-types/floating-point-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="a1d04-110">Any [built-in floating-point numeric type](../builtin-types/floating-point-numeric-types.md)</span></span>|<span data-ttu-id="a1d04-111">0 (null)</span><span class="sxs-lookup"><span data-stu-id="a1d04-111">0 (zero)</span></span>|
|[<span data-ttu-id="a1d04-112">bool</span><span class="sxs-lookup"><span data-stu-id="a1d04-112">bool</span></span>](../builtin-types/bool.md)|`false`|
|[<span data-ttu-id="a1d04-113">char</span><span class="sxs-lookup"><span data-stu-id="a1d04-113">char</span></span>](../builtin-types/char.md)|<span data-ttu-id="a1d04-114">`'\0'` (U+0000)</span><span class="sxs-lookup"><span data-stu-id="a1d04-114">`'\0'` (U+0000)</span></span>|
|[<span data-ttu-id="a1d04-115">enum</span><span class="sxs-lookup"><span data-stu-id="a1d04-115">enum</span></span>](enum.md)|<span data-ttu-id="a1d04-116">Der Wert, der vom Ausdruck `(E)0` erzeugt wird, bei dem `E` der Enumerationsbezeichner ist.</span><span class="sxs-lookup"><span data-stu-id="a1d04-116">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="a1d04-117">struct</span><span class="sxs-lookup"><span data-stu-id="a1d04-117">struct</span></span>](struct.md)|<span data-ttu-id="a1d04-118">Der Wert, der erzeugt wird, indem alle Werttypfelder auf ihre Standardwerte festgelegt werden und alle Verweistypfelder auf `null`.</span><span class="sxs-lookup"><span data-stu-id="a1d04-118">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|<span data-ttu-id="a1d04-119">Ein [Werttyp, der NULL-Werte zulässt](../builtin-types/nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="a1d04-119">Any [nullable value type](../builtin-types/nullable-value-types.md)</span></span>|<span data-ttu-id="a1d04-120">Eine Instanz, für die die <xref:System.Nullable%601.HasValue%2A>-Eigenschaft `false` und die <xref:System.Nullable%601.Value%2A>-Eigenschaft nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="a1d04-120">An instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span> <span data-ttu-id="a1d04-121">Dieser Standardwert wird auch als *NULL*-Wert eines Nullable-Werttyps bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a1d04-121">That default value is also known as the *null* value of a nullable value type.</span></span>|

<span data-ttu-id="a1d04-122">Verwenden Sie den [default-Operator](../operators/default.md), um wie im folgenden Beispiel den Standardwert eines Typs zu erzeugen:</span><span class="sxs-lookup"><span data-stu-id="a1d04-122">Use the [default operator](../operators/default.md) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="a1d04-123">Ab C# 7.1 können Sie das [`default`-Literal](../operators/default.md#default-literal) verwenden, um eine Variable mit dem Standardwert des Typs zu initialisieren:</span><span class="sxs-lookup"><span data-stu-id="a1d04-123">Beginning with C# 7.1, you can use the [`default` literal](../operators/default.md#default-literal) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="a1d04-124">Für eine Wertart generiert der implizite parameterlose Konstruktor auch den Standardwert des Typs, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="a1d04-124">For a value type, the implicit parameterless constructor also produces the default value of the type, as the following example shows:</span></span>

```csharp-interactive
var n = new System.Numerics.Complex();
Console.WriteLine(n);  // output: (0, 0)
```

## <a name="c-language-specification"></a><span data-ttu-id="a1d04-125">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="a1d04-125">C# language specification</span></span>

<span data-ttu-id="a1d04-126">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="a1d04-126">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="a1d04-127">Standardwerte</span><span class="sxs-lookup"><span data-stu-id="a1d04-127">Default values</span></span>](~/_csharplang/spec/variables.md#default-values)
- [<span data-ttu-id="a1d04-128">Standardkonstruktoren</span><span class="sxs-lookup"><span data-stu-id="a1d04-128">Default constructors</span></span>](~/_csharplang/spec/types.md#default-constructors)

## <a name="see-also"></a><span data-ttu-id="a1d04-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1d04-129">See also</span></span>

- [<span data-ttu-id="a1d04-130">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="a1d04-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="a1d04-131">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="a1d04-131">C# keywords</span></span>](index.md)
- [<span data-ttu-id="a1d04-132">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="a1d04-132">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="a1d04-133">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="a1d04-133">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)
