---
title: '[]-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 01/10/2019
f1_keywords:
- '[]_CSharpKeyword'
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
ms.openlocfilehash: 9088393f61d300ee76e56e320bec17b4a79bfebb
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2019
ms.locfileid: "56835589"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="57724-102">[]-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="57724-102">[] operator (C# Reference)</span></span>

<span data-ttu-id="57724-103">Eckige Klammern (`[]`) werden in der Regel für den Zugriff auf Arrays, Indexer oder Zeigerelemente verwendet.</span><span class="sxs-lookup"><span data-stu-id="57724-103">Square brackets, `[]`, are typically used for array, indexer, or pointer element access.</span></span>

<span data-ttu-id="57724-104">Weitere Informationen zum Zeigerelementzugriff finden Sie unter [Zugreifen auf ein Arrayelement mit einem Zeiger (C#-Programmierhandbuch)](../../programming-guide/unsafe-code-pointers/how-to-access-an-array-element-with-a-pointer.md).</span><span class="sxs-lookup"><span data-stu-id="57724-104">For more information about pointer element access, see [How to: access an array element with a pointer](../../programming-guide/unsafe-code-pointers/how-to-access-an-array-element-with-a-pointer.md).</span></span>

<span data-ttu-id="57724-105">Sie verwenden eckige Klammern auch, um [Attribute](../../programming-guide/concepts/attributes/index.md) anzugeben:</span><span class="sxs-lookup"><span data-stu-id="57724-105">You also use square brackets to specify [attributes](../../programming-guide/concepts/attributes/index.md):</span></span>

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="array-access"></a><span data-ttu-id="57724-106">Arrayzugriff</span><span class="sxs-lookup"><span data-stu-id="57724-106">Array access</span></span>

<span data-ttu-id="57724-107">Im folgenden Beispiel wird der Zugriff auf Elemente des Arrays veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="57724-107">The following example demonstrates how to access array elements:</span></span>

[!code-csharp-interactive[array access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Arrays)]

<span data-ttu-id="57724-108">Wenn ein Arrayindex sich außerhalb der Grenzen der entsprechenden Dimension eines Arrays befindet, wird eine <xref:System.IndexOutOfRangeException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="57724-108">If an array index is outside the bounds of the corresponding dimension of an array, an <xref:System.IndexOutOfRangeException> is thrown.</span></span>

<span data-ttu-id="57724-109">Wie im vorherigen Beispiel gezeigt, verwenden Sie eckige Klammern auch zur Deklaration eines Arraytyps und Instanziierung von Arrayinstanzen.</span><span class="sxs-lookup"><span data-stu-id="57724-109">As the preceding example shows, you also use square brackets in declaration of an array type and instantiation of array instances.</span></span>

<span data-ttu-id="57724-110">Weitere Informationen zu Arrays finden Sie unter [Arrays](../../programming-guide/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="57724-110">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

## <a name="indexer-access"></a><span data-ttu-id="57724-111">Indexerzugriff</span><span class="sxs-lookup"><span data-stu-id="57724-111">Indexer access</span></span>

<span data-ttu-id="57724-112">Im folgenden Beispiel wird der Indexerzugriff anhand des .NET <xref:System.Collections.Generic.Dictionary%602>-Typs veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="57724-112">The following example uses .NET <xref:System.Collections.Generic.Dictionary%602> type to demonstrate indexer access:</span></span>

[!code-csharp-interactive[indexer access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Indexers)]

<span data-ttu-id="57724-113">Mit Indexern können Sie Instanzen eines benutzerdefinierten Typs auf ähnliche Weise wie ein Array indizieren.</span><span class="sxs-lookup"><span data-stu-id="57724-113">Indexers allow you to index instances of a user-defined type in the similar way as array indexing.</span></span> <span data-ttu-id="57724-114">Im Gegensatz zu Arrayindizes, die ganze Zahlen sein müssen, können die Indexerargumente mit einem beliebigen Typ deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="57724-114">Unlike array indices, which must be integer, the indexer arguments can be declared to be of any type.</span></span>

<span data-ttu-id="57724-115">Weitere Informationen über Indexer finden Sie unter [Indexer](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="57724-115">For more information about indexers, see [Indexers](../../programming-guide/indexers/index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="57724-116">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="57724-116">Operator overloadability</span></span>

<span data-ttu-id="57724-117">Elementzugriff `[]` wird nicht als überladbarer Operator betrachtet.</span><span class="sxs-lookup"><span data-stu-id="57724-117">Element access `[]` is not considered an overloadable operator.</span></span> <span data-ttu-id="57724-118">Verwenden Sie [Indexer](../../programming-guide/indexers/index.md) zur Unterstützung der Indizierung mit benutzerdefinierten Typen.</span><span class="sxs-lookup"><span data-stu-id="57724-118">Use [indexers](../../programming-guide/indexers/index.md) to support indexing with user-defined types.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="57724-119">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="57724-119">C# language specification</span></span>

<span data-ttu-id="57724-120">Weitere Informationen finden Sie in den Abschnitten [Elementzugriff](~/_csharplang/spec/expressions.md#element-access) und [Zeigerelementzugriff auf](~/_csharplang/spec/unsafe-code.md#pointer-element-access) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="57724-120">For more information, see the [Element access](~/_csharplang/spec/expressions.md#element-access) and [Pointer element access](~/_csharplang/spec/unsafe-code.md#pointer-element-access) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="57724-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57724-121">See also</span></span>

- [<span data-ttu-id="57724-122">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="57724-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="57724-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="57724-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="57724-124">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="57724-124">C# Operators</span></span>](index.md)
- [<span data-ttu-id="57724-125">Arrays</span><span class="sxs-lookup"><span data-stu-id="57724-125">Arrays</span></span>](../../programming-guide/arrays/index.md)
- [<span data-ttu-id="57724-126">Indexer</span><span class="sxs-lookup"><span data-stu-id="57724-126">Indexers</span></span>](../../programming-guide/indexers/index.md)
- [<span data-ttu-id="57724-127">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="57724-127">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="57724-128">Attribute</span><span class="sxs-lookup"><span data-stu-id="57724-128">Attributes</span></span>](../../programming-guide/concepts/attributes/index.md)
- <span data-ttu-id="57724-129">[?.- und ?[]-Operatoren](null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="57724-129">[?. and ?[] operators](null-conditional-operators.md)</span></span>