---
title: Tabelle für Standardwerte – C#-Referenz
ms.custom: seodec18
description: Erfahren Sie, was die Standardwerte der C#-Werttypen sind.
ms.date: 08/23/2018
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- parameterless constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], parameterless constructor
- types [C#], parameterless constructor return values
ms.openlocfilehash: ec5fb4681f0e0562c5aefdf336841416f96bdf98
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661413"
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="eac59-103">Tabelle für Standardwerte (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="eac59-103">Default values table (C# Reference)</span></span>

<span data-ttu-id="eac59-104">In der folgenden Tabelle werden die Standardwerte von [Werttypen](value-types.md) gezeigt.</span><span class="sxs-lookup"><span data-stu-id="eac59-104">The following table shows the default values of [value types](value-types.md).</span></span>

|<span data-ttu-id="eac59-105">Werttyp</span><span class="sxs-lookup"><span data-stu-id="eac59-105">Value type</span></span>|<span data-ttu-id="eac59-106">Standardwert</span><span class="sxs-lookup"><span data-stu-id="eac59-106">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="eac59-107">bool</span><span class="sxs-lookup"><span data-stu-id="eac59-107">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="eac59-108">byte</span><span class="sxs-lookup"><span data-stu-id="eac59-108">byte</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="eac59-109">0</span><span class="sxs-lookup"><span data-stu-id="eac59-109">0</span></span>|
|[<span data-ttu-id="eac59-110">char</span><span class="sxs-lookup"><span data-stu-id="eac59-110">char</span></span>](char.md)|<span data-ttu-id="eac59-111">'\0'</span><span class="sxs-lookup"><span data-stu-id="eac59-111">'\0'</span></span>|
|[<span data-ttu-id="eac59-112">decimal</span><span class="sxs-lookup"><span data-stu-id="eac59-112">decimal</span></span>](../builtin-types/floating-point-numeric-types.md)|<span data-ttu-id="eac59-113">0M</span><span class="sxs-lookup"><span data-stu-id="eac59-113">0M</span></span>|
|[<span data-ttu-id="eac59-114">double</span><span class="sxs-lookup"><span data-stu-id="eac59-114">double</span></span>](../builtin-types/floating-point-numeric-types.md)|<span data-ttu-id="eac59-115">0.0D</span><span class="sxs-lookup"><span data-stu-id="eac59-115">0.0D</span></span>|
|[<span data-ttu-id="eac59-116">enum</span><span class="sxs-lookup"><span data-stu-id="eac59-116">enum</span></span>](enum.md)|<span data-ttu-id="eac59-117">Der Wert, der vom Ausdruck `(E)0` erzeugt wird, bei dem `E` der Enumerationsbezeichner ist.</span><span class="sxs-lookup"><span data-stu-id="eac59-117">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="eac59-118">float</span><span class="sxs-lookup"><span data-stu-id="eac59-118">float</span></span>](../builtin-types/floating-point-numeric-types.md)|<span data-ttu-id="eac59-119">0.0F</span><span class="sxs-lookup"><span data-stu-id="eac59-119">0.0F</span></span>|
|[<span data-ttu-id="eac59-120">int</span><span class="sxs-lookup"><span data-stu-id="eac59-120">int</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="eac59-121">0</span><span class="sxs-lookup"><span data-stu-id="eac59-121">0</span></span>|
|[<span data-ttu-id="eac59-122">long</span><span class="sxs-lookup"><span data-stu-id="eac59-122">long</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="eac59-123">0L</span><span class="sxs-lookup"><span data-stu-id="eac59-123">0L</span></span>|
|[<span data-ttu-id="eac59-124">sbyte</span><span class="sxs-lookup"><span data-stu-id="eac59-124">sbyte</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="eac59-125">0</span><span class="sxs-lookup"><span data-stu-id="eac59-125">0</span></span>|
|[<span data-ttu-id="eac59-126">short</span><span class="sxs-lookup"><span data-stu-id="eac59-126">short</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="eac59-127">0</span><span class="sxs-lookup"><span data-stu-id="eac59-127">0</span></span>|
|[<span data-ttu-id="eac59-128">struct</span><span class="sxs-lookup"><span data-stu-id="eac59-128">struct</span></span>](struct.md)|<span data-ttu-id="eac59-129">Der Wert, der erzeugt wird, indem alle Werttypfelder auf ihre Standardwerte festgelegt werden und alle Verweistypfelder auf `null`.</span><span class="sxs-lookup"><span data-stu-id="eac59-129">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="eac59-130">uint</span><span class="sxs-lookup"><span data-stu-id="eac59-130">uint</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="eac59-131">0</span><span class="sxs-lookup"><span data-stu-id="eac59-131">0</span></span>|
|[<span data-ttu-id="eac59-132">ulong</span><span class="sxs-lookup"><span data-stu-id="eac59-132">ulong</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="eac59-133">0</span><span class="sxs-lookup"><span data-stu-id="eac59-133">0</span></span>|
|[<span data-ttu-id="eac59-134">ushort</span><span class="sxs-lookup"><span data-stu-id="eac59-134">ushort</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="eac59-135">0</span><span class="sxs-lookup"><span data-stu-id="eac59-135">0</span></span>|

## <a name="remarks"></a><span data-ttu-id="eac59-136">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="eac59-136">Remarks</span></span>

<span data-ttu-id="eac59-137">Sie können keine nicht initialisierten Variablen in C# verwenden.</span><span class="sxs-lookup"><span data-stu-id="eac59-137">You cannot use uninitialized variables in C#.</span></span> <span data-ttu-id="eac59-138">Sie können eine Variable mit dem Standardwert des Typs initialisieren.</span><span class="sxs-lookup"><span data-stu-id="eac59-138">You can initialize a variable with the default value of its type.</span></span> <span data-ttu-id="eac59-139">Sie können den Standardwert eines Typs verwenden, um den Standardwert des [optionalen Arguments](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments) einer Methode festzulegen.</span><span class="sxs-lookup"><span data-stu-id="eac59-139">You also can use the default value of a type to specify the default value of a method's [optional argument](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments).</span></span>

<span data-ttu-id="eac59-140">Verwenden Sie den [Standardwertausdruck](../../programming-guide/statements-expressions-operators/default-value-expressions.md), um den Standardwert eines Typs wie im folgenden Beispiel zu erzeugen:</span><span class="sxs-lookup"><span data-stu-id="eac59-140">Use the [default value expression](../../programming-guide/statements-expressions-operators/default-value-expressions.md) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="eac59-141">Ab C# 7.1 können Sie das [`default`-Literal](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) verwenden, um eine Variable mit dem Standardwert des Typs zu initialisieren:</span><span class="sxs-lookup"><span data-stu-id="eac59-141">Beginning with C# 7.1, you can use the [`default` literal](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="eac59-142">Sie können auch den parameterlosen Konstruktor oder den impliziten parameterlosen Konstruktor verwenden, um den Standardwert eines Werttyps zu erzeugen. Dies wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="eac59-142">You also can use the parameterless constructor or the implicit parameterless constructor to produce the default value of a value type, as the following example shows.</span></span> <span data-ttu-id="eac59-143">Weitere Informationen zu Konstruktoren finden Sie im Artikel [Konstruktoren](../../programming-guide/classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="eac59-143">For more information about constructors, see the [Constructors](../../programming-guide/classes-and-structs/constructors.md) article.</span></span>

```csharp
int a = new int();
```

<span data-ttu-id="eac59-144">Der Standardwert eines beliebigen [Verweistyps](reference-types.md) ist `null`.</span><span class="sxs-lookup"><span data-stu-id="eac59-144">The default value of any [reference type](reference-types.md) is `null`.</span></span> <span data-ttu-id="eac59-145">Der Standardwert eines [Nullable-Typs](../../programming-guide/nullable-types/index.md) ist eine Instanz, deren <xref:System.Nullable%601.HasValue%2A>-Eigenschaft `false` und die <xref:System.Nullable%601.Value%2A>-Eigenschaft nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="eac59-145">The default value of a [nullable type](../../programming-guide/nullable-types/index.md) is an instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span>

## <a name="see-also"></a><span data-ttu-id="eac59-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eac59-146">See also</span></span>

- [<span data-ttu-id="eac59-147">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="eac59-147">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="eac59-148">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="eac59-148">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="eac59-149">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="eac59-149">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="eac59-150">Werttypen</span><span class="sxs-lookup"><span data-stu-id="eac59-150">Value types</span></span>](value-types.md)
- [<span data-ttu-id="eac59-151">Tabelle der Werttypen</span><span class="sxs-lookup"><span data-stu-id="eac59-151">Value types table</span></span>](value-types-table.md)
- [<span data-ttu-id="eac59-152">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="eac59-152">Built-in types table</span></span>](built-in-types-table.md)
