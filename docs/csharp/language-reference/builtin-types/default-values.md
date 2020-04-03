---
title: 'Standardwerte der C#-Typen: C#-Referenz'
description: Informationen zu den Standardwerten der C#-Typen wie bool, char, int, float, double usw.
ms.date: 12/18/2019
helpviewer_keywords:
- default [C#]
- parameterless constructor [C#]
ms.openlocfilehash: 5e34d291ec15c738f3bc9409df321ede454b6710
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507255"
---
# <a name="default-values-of-c-types-c-reference"></a><span data-ttu-id="1d201-103">Standardwerte der C#-Typen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="1d201-103">Default values of C# types (C# reference)</span></span>

<span data-ttu-id="1d201-104">In der folgenden Tabelle werden die Standardwerte von C#-Typen gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1d201-104">The following table shows the default values of C# types:</span></span>

|<span data-ttu-id="1d201-105">Typ</span><span class="sxs-lookup"><span data-stu-id="1d201-105">Type</span></span>|<span data-ttu-id="1d201-106">Standardwert</span><span class="sxs-lookup"><span data-stu-id="1d201-106">Default value</span></span>|
|---------|------------------|
|<span data-ttu-id="1d201-107">Verweistyp</span><span class="sxs-lookup"><span data-stu-id="1d201-107">Any reference type</span></span>|`null`|
|<span data-ttu-id="1d201-108">Beliebiger [integrierter integraler numerischer Typ](integral-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="1d201-108">Any [built-in integral numeric type](integral-numeric-types.md)</span></span>|<span data-ttu-id="1d201-109">0 (null)</span><span class="sxs-lookup"><span data-stu-id="1d201-109">0 (zero)</span></span>|
|<span data-ttu-id="1d201-110">Beliebiger [integrierter numerischer Gleitkommatyp](floating-point-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="1d201-110">Any [built-in floating-point numeric type](floating-point-numeric-types.md)</span></span>|<span data-ttu-id="1d201-111">0 (null)</span><span class="sxs-lookup"><span data-stu-id="1d201-111">0 (zero)</span></span>|
|[<span data-ttu-id="1d201-112">bool</span><span class="sxs-lookup"><span data-stu-id="1d201-112">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="1d201-113">char</span><span class="sxs-lookup"><span data-stu-id="1d201-113">char</span></span>](char.md)|<span data-ttu-id="1d201-114">`'\0'` (U+0000)</span><span class="sxs-lookup"><span data-stu-id="1d201-114">`'\0'` (U+0000)</span></span>|
|[<span data-ttu-id="1d201-115">enum</span><span class="sxs-lookup"><span data-stu-id="1d201-115">enum</span></span>](enum.md)|<span data-ttu-id="1d201-116">Der Wert, der vom Ausdruck `(E)0` erzeugt wird, bei dem `E` der Enumerationsbezeichner ist.</span><span class="sxs-lookup"><span data-stu-id="1d201-116">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="1d201-117">struct</span><span class="sxs-lookup"><span data-stu-id="1d201-117">struct</span></span>](struct.md)|<span data-ttu-id="1d201-118">Der Wert, der erzeugt wird, indem alle Werttypfelder auf ihre Standardwerte festgelegt werden und alle Verweistypfelder auf `null`.</span><span class="sxs-lookup"><span data-stu-id="1d201-118">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|<span data-ttu-id="1d201-119">Ein [Werttyp, der NULL-Werte zulässt](nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="1d201-119">Any [nullable value type](nullable-value-types.md)</span></span>|<span data-ttu-id="1d201-120">Eine Instanz, für die die <xref:System.Nullable%601.HasValue%2A>-Eigenschaft `false` und die <xref:System.Nullable%601.Value%2A>-Eigenschaft nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="1d201-120">An instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span> <span data-ttu-id="1d201-121">Dieser Standardwert wird auch als *NULL*-Wert eines Nullable-Werttyps bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="1d201-121">That default value is also known as the *null* value of a nullable value type.</span></span>|

<span data-ttu-id="1d201-122">Verwenden Sie den [`default`-Operator](../operators/default.md#default-operator), um wie im folgenden Beispiel den Standardwert eines Typs zu erzeugen:</span><span class="sxs-lookup"><span data-stu-id="1d201-122">Use the [`default` operator](../operators/default.md#default-operator) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="1d201-123">Ab C# 7.1 können Sie das [`default`-Literal](../operators/default.md#default-literal) verwenden, um eine Variable mit dem Standardwert des Typs zu initialisieren:</span><span class="sxs-lookup"><span data-stu-id="1d201-123">Beginning with C# 7.1, you can use the [`default` literal](../operators/default.md#default-literal) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="1d201-124">Für eine Wertart generiert der implizite parameterlose Konstruktor auch den Standardwert des Typs, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="1d201-124">For a value type, the implicit parameterless constructor also produces the default value of the type, as the following example shows:</span></span>

```csharp-interactive
var n = new System.Numerics.Complex();
Console.WriteLine(n);  // output: (0, 0)
```

<span data-ttu-id="1d201-125">Wenn die <xref:System.Type?displayProperty=nameWithType>-Instanz zur Laufzeit einen Werttyp darstellt, können Sie die <xref:System.Activator.CreateInstance(System.Type)?displayProperty=nameWithType>-Methode verwenden, um den parameterlosen Konstruktor aufzurufen, um den Standardwert des Typs abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1d201-125">At run time, if the <xref:System.Type?displayProperty=nameWithType> instance represents a value type, you can use the <xref:System.Activator.CreateInstance(System.Type)?displayProperty=nameWithType> method to invoke the parameterless constructor to obtain the default value of the type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1d201-126">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="1d201-126">C# language specification</span></span>

<span data-ttu-id="1d201-127">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="1d201-127">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="1d201-128">Standardwerte</span><span class="sxs-lookup"><span data-stu-id="1d201-128">Default values</span></span>](~/_csharplang/spec/variables.md#default-values)
- [<span data-ttu-id="1d201-129">Standardkonstruktoren</span><span class="sxs-lookup"><span data-stu-id="1d201-129">Default constructors</span></span>](~/_csharplang/spec/types.md#default-constructors)

## <a name="see-also"></a><span data-ttu-id="1d201-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d201-130">See also</span></span>

- [<span data-ttu-id="1d201-131">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="1d201-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="1d201-132">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="1d201-132">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)
