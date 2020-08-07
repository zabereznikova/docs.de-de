---
title: Boxing und Unboxing – C#-Programmierhandbuch
description: Erfahren Sie mehr über Boxing und Unboxing in der C#-Programmierung. Hier finden Sie Codebeispiele und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
f1_keywords:
- cs.boxing
helpviewer_keywords:
- C# language, boxing
- C# language, unboxing
- unboxing [C#]
- boxing [C#]
ms.assetid: 8da9bbf4-bce9-4b08-b2e5-f64c11c56514
ms.openlocfilehash: 5a5bfcc79de8ba3ff66ca8aab9d86d69d89f9221
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380695"
---
# <a name="boxing-and-unboxing-c-programming-guide"></a><span data-ttu-id="75e19-104">Boxing und Unboxing (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="75e19-104">Boxing and Unboxing (C# Programming Guide)</span></span>

<span data-ttu-id="75e19-105">Beim Boxing handelt es sich um die Konvertierung eines [Werttyps](../../language-reference/builtin-types/value-types.md) in den Typ `object` oder in einen beliebigen anderen Schnittstellentyp, der durch diesen Werttyp implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="75e19-105">Boxing is the process of converting a [value type](../../language-reference/builtin-types/value-types.md) to the type `object` or to any interface type implemented by this value type.</span></span> <span data-ttu-id="75e19-106">Wenn die Common Language Runtime (CLR) für einen Werttyp das Boxing durchführt, wird der Wert mit einer <xref:System.Object?displayProperty=nameWithType>-Instanz umschlossen und im verwalteten Heap gespeichert.</span><span class="sxs-lookup"><span data-stu-id="75e19-106">When the common language runtime (CLR) boxes a value type, it wraps the value inside a <xref:System.Object?displayProperty=nameWithType> instance and stores it on the managed heap.</span></span> <span data-ttu-id="75e19-107">Durch Unboxing wird der Werttyp aus dem Objekt extrahiert.</span><span class="sxs-lookup"><span data-stu-id="75e19-107">Unboxing extracts the value type from the object.</span></span> <span data-ttu-id="75e19-108">Boxing ist implizit, Unboxing ist explizit.</span><span class="sxs-lookup"><span data-stu-id="75e19-108">Boxing is implicit; unboxing is explicit.</span></span> <span data-ttu-id="75e19-109">Das Konzept von Boxing und Unboxing unterliegt der einheitlichen C#-Ansicht des Typsystems, in dem ein Wert eines beliebigen Typs als Objekt behandelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="75e19-109">The concept of boxing and unboxing underlies the C# unified view of the type system in which a value of any type can be treated as an object.</span></span>

<span data-ttu-id="75e19-110">Im folgenden Beispiel wird die ganzzahlige Variable `i` mittels *Boxing* konvertiert und dem Objekt `o` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="75e19-110">In the following example, the integer variable `i` is *boxed* and assigned to object `o`.</span></span>

[!code-csharp[csProgGuideTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#14)]

<span data-ttu-id="75e19-111">Das Objekt `o` kann dann mittels Unboxing zurückkonvertiert und der ganzzahligen Variablen `i` zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="75e19-111">The object `o` can then be unboxed and assigned to integer variable `i`:</span></span>

[!code-csharp[csProgGuideTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#15)]

<span data-ttu-id="75e19-112">Die folgenden Beispiele veranschaulichen, wie Boxing in C# verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="75e19-112">The following examples illustrate how boxing is used in C#.</span></span>

[!code-csharp[csProgGuideTypes#47](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#47)]

## <a name="performance"></a><span data-ttu-id="75e19-113">Leistung</span><span class="sxs-lookup"><span data-stu-id="75e19-113">Performance</span></span>

<span data-ttu-id="75e19-114">Im Verhältnis zu einfachen Zuweisungen sind Boxing und Unboxing rechentechnisch aufwändige Prozesse.</span><span class="sxs-lookup"><span data-stu-id="75e19-114">In relation to simple assignments, boxing and unboxing are computationally expensive processes.</span></span> <span data-ttu-id="75e19-115">Wenn ein Werttyp mittels Boxing konvertiert wird, muss ein neues Objekt zugeordnet und erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="75e19-115">When a value type is boxed, a new object must be allocated and constructed.</span></span> <span data-ttu-id="75e19-116">Die für Unboxing erforderliche Umwandlung ist ebenfalls, jedoch in geringerem Maße rechentechnisch aufwändig.</span><span class="sxs-lookup"><span data-stu-id="75e19-116">To a lesser degree, the cast required for unboxing is also expensive computationally.</span></span> <span data-ttu-id="75e19-117">Weitere Informationen finden Sie unter [Leistung](../../../framework/performance/performance-tips.md).</span><span class="sxs-lookup"><span data-stu-id="75e19-117">For more information, see [Performance](../../../framework/performance/performance-tips.md).</span></span>

## <a name="boxing"></a><span data-ttu-id="75e19-118">Boxing</span><span class="sxs-lookup"><span data-stu-id="75e19-118">Boxing</span></span>

<span data-ttu-id="75e19-119">Boxing wird verwendet, um Werttypen im Heap der Garbage Collection zu speichern.</span><span class="sxs-lookup"><span data-stu-id="75e19-119">Boxing is used to store value types in the garbage-collected heap.</span></span> <span data-ttu-id="75e19-120">Beim Boxing handelt es sich um die implizite Konvertierung eines [Werttyps](../../language-reference/builtin-types/value-types.md) in den Typ `object` oder in einen beliebigen anderen Schnittstellentyp, der durch diesen Werttyp implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="75e19-120">Boxing is an implicit conversion of a [value type](../../language-reference/builtin-types/value-types.md) to the type `object` or to any interface type implemented by this value type.</span></span> <span data-ttu-id="75e19-121">Beim Boxing eines Werttyps wird auf dem Heap eine Objektinstanz zugeordnet. Anschließend wird der Wert in das neue Objekt kopiert.</span><span class="sxs-lookup"><span data-stu-id="75e19-121">Boxing a value type allocates an object instance on the heap and copies the value into the new object.</span></span>

<span data-ttu-id="75e19-122">Beachten Sie die folgende Deklaration einer Werttypvariablen:</span><span class="sxs-lookup"><span data-stu-id="75e19-122">Consider the following declaration of a value-type variable:</span></span>

[!code-csharp[csProgGuideTypes#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#17)]

<span data-ttu-id="75e19-123">Mit der folgenden Anweisung wird der Boxing-Vorgang implizit auf die Variable `i` angewendet:</span><span class="sxs-lookup"><span data-stu-id="75e19-123">The following statement implicitly applies the boxing operation on the variable `i`:</span></span>

[!code-csharp[csProgGuideTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#18)]

<span data-ttu-id="75e19-124">Diese Anweisung bewirkt, dass der Objektverweis `o` auf dem Stapel erstellt wird, der auf einen Wert vom Typ `int` auf dem Heap verweist.</span><span class="sxs-lookup"><span data-stu-id="75e19-124">The result of this statement is creating an object reference `o`, on the stack, that references a value of the type `int`, on the heap.</span></span> <span data-ttu-id="75e19-125">Dieser Wert ist eine Kopie des Werttyps, der der Variablen `i` zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="75e19-125">This value is a copy of the value-type value assigned to the variable `i`.</span></span> <span data-ttu-id="75e19-126">In der folgenden Abbildung der Boxing-Konversation ist der Unterschied zwischen den Variablen `i` und `o` dargestellt.</span><span class="sxs-lookup"><span data-stu-id="75e19-126">The difference between the two variables, `i` and `o`, is illustrated in the following image of boxing conversion:</span></span>

![Abbildung, die den Unterschied zwischen den Variablen „i“ und „o“ zeigt.](./media/boxing-and-unboxing/boxing-operation-i-o-variables.gif)

<span data-ttu-id="75e19-128">Es auch möglich, das Boxing wie im folgenden Beispiel explizit auszuführen. Explizites Boxing ist jedoch nie erforderlich:</span><span class="sxs-lookup"><span data-stu-id="75e19-128">It is also possible to perform the boxing explicitly as in the following example, but explicit boxing is never required:</span></span>

[!code-csharp[csProgGuideTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#19)]

## <a name="description"></a><span data-ttu-id="75e19-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="75e19-129">Description</span></span>

<span data-ttu-id="75e19-130">In diesem Beispiel wird die Ganzzahlvariable `i` mittels Boxing in das Objekt `o` konvertiert.</span><span class="sxs-lookup"><span data-stu-id="75e19-130">This example converts an integer variable `i` to an object `o` by using boxing.</span></span> <span data-ttu-id="75e19-131">Anschließend wird der in der Variablen `i` gespeicherte Wert von `123` in `456` geändert.</span><span class="sxs-lookup"><span data-stu-id="75e19-131">Then, the value stored in the variable `i` is changed from `123` to `456`.</span></span> <span data-ttu-id="75e19-132">Das Beispiel veranschaulicht, dass der ursprüngliche Werttyp und das durch Boxing entstehende Objekt unterschiedliche Speicherorte verwenden und daher verschiedene Werte speichern können.</span><span class="sxs-lookup"><span data-stu-id="75e19-132">The example shows that the original value type and the boxed object use separate memory locations, and therefore can store different values.</span></span>

## <a name="example"></a><span data-ttu-id="75e19-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="75e19-133">Example</span></span>

[!code-csharp[csProgGuideTypes#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#16)]

## <a name="unboxing"></a><span data-ttu-id="75e19-134">Unboxing</span><span class="sxs-lookup"><span data-stu-id="75e19-134">Unboxing</span></span>

<span data-ttu-id="75e19-135">Beim Unboxing handelt es sich um eine explizite Konvertierung vom `object`-Typ in einen [Werttyp](../../language-reference/builtin-types/value-types.md) bzw. von einem Schnittstellentyp in einen Werttyp, durch den die Schnittstelle implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="75e19-135">Unboxing is an explicit conversion from the type `object` to a [value type](../../language-reference/builtin-types/value-types.md) or from an interface type to a value type that implements the interface.</span></span> <span data-ttu-id="75e19-136">Ein Unboxing-Vorgang umfasst folgende Schritte:</span><span class="sxs-lookup"><span data-stu-id="75e19-136">An unboxing operation consists of:</span></span>

- <span data-ttu-id="75e19-137">Überprüfen der Objektinstanz, um sicherzustellen, dass es sich um einen mittels Boxing "verpackten" Wert des jeweiligen Werttyps handelt.</span><span class="sxs-lookup"><span data-stu-id="75e19-137">Checking the object instance to make sure that it is a boxed value of the given value type.</span></span>

- <span data-ttu-id="75e19-138">Kopieren des Werts aus der Instanz in die Werttypvariable.</span><span class="sxs-lookup"><span data-stu-id="75e19-138">Copying the value from the instance into the value-type variable.</span></span>

<span data-ttu-id="75e19-139">Anhand der folgenden Anweisungen werden sowohl Boxing-Vorgänge als auch Unboxing-Vorgänge veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="75e19-139">The following statements demonstrate both boxing and unboxing operations:</span></span>

[!code-csharp[csProgGuideTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#21)]

<span data-ttu-id="75e19-140">In der folgenden Abbildung ist das Ergebnis der vorherigen Anweisungen dargestellt:</span><span class="sxs-lookup"><span data-stu-id="75e19-140">The following figure demonstrates the result of the previous statements:</span></span>

![Abbildung einer Unboxing-Konvertierung.](./media/boxing-and-unboxing/unboxing-conversion-operation.gif)

<span data-ttu-id="75e19-142">Damit das Unboxing eines Werttypen zur Laufzeit erfolgreich verläuft, muss das zu konvertierende Element ein Verweis auf ein Objekt sein, das zuvor durch Boxing einer Instanz dieses Werttyps erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="75e19-142">For the unboxing of value types to succeed at run time, the item being unboxed must be a reference to an object that was previously created by boxing an instance of that value type.</span></span> <span data-ttu-id="75e19-143">Der Versuch, ein Unboxing durchzuführen, `null` löst ein <xref:System.NullReferenceException> aus.</span><span class="sxs-lookup"><span data-stu-id="75e19-143">Attempting to unbox `null` causes a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="75e19-144">Der Versuch, einen Verweis auf einen nicht kompatiblen Werttyp mittels Unboxing zu konvertieren, führt zu einer <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="75e19-144">Attempting to unbox a reference to an incompatible value type causes an <xref:System.InvalidCastException>.</span></span>

## <a name="example"></a><span data-ttu-id="75e19-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="75e19-145">Example</span></span>

<span data-ttu-id="75e19-146">Im folgenden Beispiel wird ein Fall von ungültigem Unboxing und der sich daraus ergebenden `InvalidCastException` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="75e19-146">The following example demonstrates a case of invalid unboxing and the resulting `InvalidCastException`.</span></span> <span data-ttu-id="75e19-147">Bei Verwendung von `try` und `catch` wird eine Fehlermeldung angezeigt, wenn der Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="75e19-147">Using `try` and `catch`, an error message is displayed when the error occurs.</span></span>

[!code-csharp[csProgGuideTypes#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#20)]

<span data-ttu-id="75e19-148">Dieses Programm gibt Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="75e19-148">This program outputs:</span></span>

`Specified cast is not valid. Error: Incorrect unboxing.`

<span data-ttu-id="75e19-149">Wenn Sie die Anweisung</span><span class="sxs-lookup"><span data-stu-id="75e19-149">If you change the statement:</span></span>

```csharp
int j = (short) o;
```

<span data-ttu-id="75e19-150">in:</span><span class="sxs-lookup"><span data-stu-id="75e19-150">to:</span></span>

```csharp
int j = (int) o;
```

<span data-ttu-id="75e19-151">ändern, wird die Konvertierung ausgeführt und Folgendes ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="75e19-151">the conversion will be performed, and you will get the output:</span></span>

`Unboxing OK.`

## <a name="c-language-specification"></a><span data-ttu-id="75e19-152">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="75e19-152">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="75e19-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75e19-153">See also</span></span>

- [<span data-ttu-id="75e19-154">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="75e19-154">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="75e19-155">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="75e19-155">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="75e19-156">Werttypen</span><span class="sxs-lookup"><span data-stu-id="75e19-156">Value types</span></span>](../../language-reference/builtin-types/value-types.md)
