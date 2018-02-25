---
title: Nullable-Typen (C#-Programmierhandbuch)
ms.date: 05/15/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- nullable types [C#]
- C# language, nullable types
- types [C#], nullable
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9b874b265f4adb131a056ea1ef6fb5ffc820343f
ms.sourcegitcommit: 75a180acb5d8a2dbd4a52915ce8e980749fb1d05
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2018
---
# <a name="nullable-types-c-programming-guide"></a><span data-ttu-id="db235-102">Nullable-Typen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="db235-102">Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="db235-103">Auf NULL festlegbare Typen sind Instanzen der <xref:System.Nullable%601?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="db235-103">Nullable types are instances of the <xref:System.Nullable%601?displayProperty=nameWithType> struct.</span></span> <span data-ttu-id="db235-104">Ein Nullable-Typ kann den richtigen Bereich an Werten für den zugrunde liegenden Werttyp plus einen zusätzlichen `null`-Wert darstellen.</span><span class="sxs-lookup"><span data-stu-id="db235-104">A nullable type can represent the correct range of values for its underlying value type, plus an additional `null` value.</span></span> <span data-ttu-id="db235-105">Einem `Nullable<Int32>` (ausgesprochen „Nullable von Int32“) kann jeder Wert im Bereich von -2147483648 bis 2147483647 oder ein `null`-Wert zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="db235-105">For example, a `Nullable<Int32>`, pronounced "Nullable of Int32," can be assigned any value from -2147483648 to 2147483647, or it can be assigned the `null` value.</span></span> <span data-ttu-id="db235-106">Einem `Nullable<bool>` können die Werte [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) oder [null](../../../csharp/language-reference/keywords/null.md) zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="db235-106">A `Nullable<bool>` can be assigned the values [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md), or [null](../../../csharp/language-reference/keywords/null.md).</span></span> <span data-ttu-id="db235-107">Die Möglichkeit, `null` zu numerischen und booleschen Typen zuzuweisen, ist besonders nützlich, wenn Sie mit Datenbanken und anderen Datentypen mit Elementen arbeiten, denen möglicherweise kein Wert zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="db235-107">The ability to assign `null` to numeric and Boolean types is especially useful when you are dealing with databases and other data types that contain elements that may not be assigned a value.</span></span> <span data-ttu-id="db235-108">Ein boolesches Feld in einer Datenbank kann beispielsweise die Werte `true` oder `false` speichern oder nicht definiert sein.</span><span class="sxs-lookup"><span data-stu-id="db235-108">For example, a Boolean field in a database can store the values `true` or `false`, or it may be undefined.</span></span> 
  
[!code-csharp[nullable-types](../../../../samples/snippets/csharp/programming-guide/nullable-types/nullable-ex1.cs)]  
  
<span data-ttu-id="db235-109">Weitere Beispiele finden Sie unter [Verwenden von Nullable-Typen](../../../csharp/programming-guide/nullable-types/using-nullable-types.md).</span><span class="sxs-lookup"><span data-stu-id="db235-109">For more examples, see [Using Nullable Types](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)</span></span>  
  
## <a name="nullable-types-overview"></a><span data-ttu-id="db235-110">Übersicht über Nullable-Typen</span><span class="sxs-lookup"><span data-stu-id="db235-110">Nullable Types Overview</span></span>  
 <span data-ttu-id="db235-111">Nullable-Typen weisen die folgenden Eigenschaften auf:</span><span class="sxs-lookup"><span data-stu-id="db235-111">Nullable types have the following characteristics:</span></span>  
  
-   <span data-ttu-id="db235-112">Nullable-Typen stellen Werttypvariablen dar, denen der Wert `null` zugewiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="db235-112">Nullable types represent value-type variables that can be assigned the value of `null`.</span></span> <span data-ttu-id="db235-113">Sie können keinen Nullable-Typ basierend auf einem Verweistyp erstellen.</span><span class="sxs-lookup"><span data-stu-id="db235-113">You cannot create a nullable type based on a reference type.</span></span> <span data-ttu-id="db235-114">(Verweistypen unterstützen immer den `null`-Wert.)</span><span class="sxs-lookup"><span data-stu-id="db235-114">(Reference types already support the `null` value.)</span></span>  
  
-   <span data-ttu-id="db235-115">Die Syntax `T?` ist die Kurzform für <xref:System.Nullable%601>, wobei `T` ein Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="db235-115">The syntax `T?` is shorthand for <xref:System.Nullable%601>, where `T` is a value type.</span></span> <span data-ttu-id="db235-116">Die beiden Formen sind austauschbar.</span><span class="sxs-lookup"><span data-stu-id="db235-116">The two forms are interchangeable.</span></span>  
  
-   <span data-ttu-id="db235-117">Sie weisen einem Nullable-Typ einen Wert genauso zu, wie Sie es für einen regulären Werttyp tun würden, z.B. `int? x = 10;` oder `double? d = 4.108`.</span><span class="sxs-lookup"><span data-stu-id="db235-117">Assign a value to a nullable type just as you would for an ordinary value type, for example `int? x = 10;` or `double? d = 4.108`.</span></span> <span data-ttu-id="db235-118">Einem Nullable-Typ kann auch der Wert `null`:`int? x = null.` zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="db235-118">A nullable type can also be assigned the value `null`: `int? x = null.`</span></span>  
  
-   <span data-ttu-id="db235-119">Verwenden Sie die <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=nameWithType>-Methode, um entweder den zugewiesenen Wert oder den Standardwert für den zugrunde liegenden Typ zurückzugeben, wenn der Wert `null` ist, z.B. `int j = x.GetValueOrDefault();`</span><span class="sxs-lookup"><span data-stu-id="db235-119">Use the <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=nameWithType> method to return either the assigned value, or the default value for the underlying type if the value is `null`, for example `int j = x.GetValueOrDefault();`</span></span>  
  
-   <span data-ttu-id="db235-120">Verwenden Sie die schreibgeschützten Eigenschaften <xref:System.Nullable%601.HasValue%2A> und <xref:System.Nullable%601.Value%2A>, um auf NULL zu prüfen und den Wert abzurufen, wie im folgenden Beispiel gezeigt: `if(x.HasValue) j = x.Value;`</span><span class="sxs-lookup"><span data-stu-id="db235-120">Use the <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> read-only properties to test for null and retrieve the value, as shown in the following example: `if(x.HasValue) j = x.Value;`</span></span>  
  
    -   <span data-ttu-id="db235-121">Die Eigenschaft `HasValue` gibt `true` zurück, wenn die Variable einen Wert enthält, oder sie gibt `false` zurück, wenn die Variable `null` ist.</span><span class="sxs-lookup"><span data-stu-id="db235-121">The `HasValue` property returns `true` if the variable contains a value, or `false` if it is `null`.</span></span>  
  
    -   <span data-ttu-id="db235-122">Die Eigenschaft `Value` gibt einen Wert zurück, sofern einer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="db235-122">The `Value` property returns a value if one is assigned.</span></span> <span data-ttu-id="db235-123">Andernfalls wird eine <xref:System.InvalidOperationException?displayProperty=nameWithType> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="db235-123">Otherwise, a <xref:System.InvalidOperationException?displayProperty=nameWithType> is thrown.</span></span>  
  
    -   <span data-ttu-id="db235-124">Der Standardwert für `HasValue` lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="db235-124">The default value for `HasValue` is `false`.</span></span> <span data-ttu-id="db235-125">Die Eigenschaft `Value` hat keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="db235-125">The `Value` property has no default value.</span></span>  
  
    -   <span data-ttu-id="db235-126">Sie können auch die Operatoren `==` und `!=` mit einem Nullable-Typ verwenden, wie im folgenden Beispiel gezeigt: `if (x != null) y = x;`</span><span class="sxs-lookup"><span data-stu-id="db235-126">You can also use the `==` and `!=` operators with a nullable type, as shown in the following example: `if (x != null) y = x;`</span></span>  
  
-   <span data-ttu-id="db235-127">Verwenden Sie den Operator `??`, um einen Standardwert zuzuweisen, der angewendet wird, wenn ein Nullable-Typ, dessen aktueller Wert`null` lautet, einem Nicht-Nullable-Typ zugewiesen wird, z.B.: `int? x = null; int y = x ?? -1;`</span><span class="sxs-lookup"><span data-stu-id="db235-127">Use the `??` operator to assign a default value that will be applied when a nullable type whose current value is `null` is assigned to a non-nullable type, for example `int? x = null; int y = x ?? -1;`</span></span>  
  
-   <span data-ttu-id="db235-128">Geschachtelte Nullable-Typen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="db235-128">Nested nullable types are not allowed.</span></span> <span data-ttu-id="db235-129">Die folgende Zeile wird nicht kompiliert: `Nullable<Nullable<int>> n;`</span><span class="sxs-lookup"><span data-stu-id="db235-129">The following line will not compile: `Nullable<Nullable<int>> n;`</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="db235-130">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="db235-130">Related Sections</span></span>  
 <span data-ttu-id="db235-131">Weitere Informationen finden Sie unter: </span><span class="sxs-lookup"><span data-stu-id="db235-131">For more information:</span></span>  
  
-   [<span data-ttu-id="db235-132">Verwenden von Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="db235-132">Using Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
  
-   [<span data-ttu-id="db235-133">Boxing von Typen mit Nullwerten</span><span class="sxs-lookup"><span data-stu-id="db235-133">Boxing Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
  
-   [<span data-ttu-id="db235-134">?? Operator</span><span class="sxs-lookup"><span data-stu-id="db235-134">?? Operator</span></span>](../../../csharp/language-reference/operators/null-conditional-operator.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="db235-135">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="db235-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="db235-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db235-136">See Also</span></span>  
 <xref:System.Nullable>  
 [<span data-ttu-id="db235-137">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="db235-137">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="db235-138">C#</span><span class="sxs-lookup"><span data-stu-id="db235-138">C#</span></span>](../../../csharp/index.md)  
 [<span data-ttu-id="db235-139">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="db235-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 <span data-ttu-id="db235-140">[What exactly does 'lifted' mean?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/) (Was bedeutet „Lifted“ genau?)</span><span class="sxs-lookup"><span data-stu-id="db235-140">[What exactly does 'lifted' mean?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)</span></span>
