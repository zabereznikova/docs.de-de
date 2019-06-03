---
title: typeof – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
ms.openlocfilehash: 7962a3d0a5885e64701cb9d9a4d689cd982b9830
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422553"
---
# <a name="typeof-c-reference"></a><span data-ttu-id="d024a-102">typeof (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d024a-102">typeof (C# Reference)</span></span>

<span data-ttu-id="d024a-103">Wird zum Abrufen des Objekts <xref:System.Type?displayProperty=nameWithType> eines Typs verwendet.</span><span class="sxs-lookup"><span data-stu-id="d024a-103">Used to obtain the <xref:System.Type?displayProperty=nameWithType> object for a type.</span></span> <span data-ttu-id="d024a-104">Der Ausdruck `typeof` weist folgende Form auf:</span><span class="sxs-lookup"><span data-stu-id="d024a-104">A `typeof` expression takes the following form:</span></span>

```csharp
System.Type type = typeof(int);
```

## <a name="remarks"></a><span data-ttu-id="d024a-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d024a-105">Remarks</span></span>

<span data-ttu-id="d024a-106">Um den Runtime-Typ eines Ausdrucks zu erhalten, können Sie die .NET Framework-Methode <xref:System.Object.GetType%2A> wie in folgendem Beispiel verwenden:</span><span class="sxs-lookup"><span data-stu-id="d024a-106">To obtain the run-time type of an expression, you can use the .NET Framework method <xref:System.Object.GetType%2A>, as in the following example:</span></span>

```csharp
int i = 0;
System.Type type = i.GetType();
```

<span data-ttu-id="d024a-107">Operator `typeof` kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="d024a-107">The `typeof` operator cannot be overloaded.</span></span>

<span data-ttu-id="d024a-108">Der Operator `typeof` kann auch bei offenen generischen Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d024a-108">The `typeof` operator can also be used on open generic types.</span></span> <span data-ttu-id="d024a-109">Typen mit mehr als einem Parameter müssen die entsprechende Anzahl von Kommas in der Spezifikation haben.</span><span class="sxs-lookup"><span data-stu-id="d024a-109">Types with more than one type parameter must have the appropriate number of commas in the specification.</span></span> <span data-ttu-id="d024a-110"><xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWIthType> verfügt z.B. über zwei Typargumente, also verwenden Sie ein Komma:</span><span class="sxs-lookup"><span data-stu-id="d024a-110">For example, the <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWIthType> has two type arguments, so you use one comma:</span></span>

```csharp
Type t = typeof(System.Collection.Generic.Dictionary<,>);
```

<span data-ttu-id="d024a-111">Das folgende Beispiel zeigt, wie Sie bestimmen, ob der Rückgabetyp einer Methode ein generischer <xref:System.Collections.Generic.IEnumerable%601> ist.</span><span class="sxs-lookup"><span data-stu-id="d024a-111">The following example shows how to determine whether the return type of a method is a generic <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="d024a-112"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> gibt `null` zurück, wenn der Rückgabetyp kein generischer <xref:System.Collections.Generic.IEnumerable%601>-Typ ist.</span><span class="sxs-lookup"><span data-stu-id="d024a-112"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> will return `null` if the return type is not an <xref:System.Collections.Generic.IEnumerable%601> generic type.</span></span>

[!code-csharp[typeof_3.cs](~/samples/snippets/csharp/keywords/typeof/typeof_3.cs)]

## <a name="example"></a><span data-ttu-id="d024a-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d024a-113">Example</span></span>

[!code-csharp[csrefKeywordsOperator#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#12)] 

## <a name="example"></a><span data-ttu-id="d024a-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d024a-114">Example</span></span>

<span data-ttu-id="d024a-115">Dieses Beispiel verwendet die <xref:System.Object.GetType%2A>-Methode um den Typ zu bestimmen, der verwendet wird, um das Ergebnis einer numerischen Berechnung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d024a-115">This sample uses the <xref:System.Object.GetType%2A> method to determine the type that is used to contain the result of a numeric calculation.</span></span> <span data-ttu-id="d024a-116">Dies hängt vom Speicherbedarf der resultierenden Zahl ab.</span><span class="sxs-lookup"><span data-stu-id="d024a-116">This depends on the storage requirements of the resulting number.</span></span>

[!code-csharp[csrefKeywordsOperator#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#13)]

## <a name="c-language-specification"></a><span data-ttu-id="d024a-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="d024a-117">C# language specification</span></span>

<span data-ttu-id="d024a-118">Weitere Informationen finden Sie unter [Der typeof-Operator](~/_csharplang/spec/expressions.md#the-typeof-operator) in der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="d024a-118">For more information, see [The typeof operator](~/_csharplang/spec/expressions.md#the-typeof-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="d024a-119">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="d024a-119">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="d024a-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d024a-120">See also</span></span>

- <xref:System.Type?displayProperty=nameWithType>
- [<span data-ttu-id="d024a-121">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="d024a-121">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="d024a-122">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d024a-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="d024a-123">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d024a-123">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="d024a-124">is</span><span class="sxs-lookup"><span data-stu-id="d024a-124">is</span></span>](../../../csharp/language-reference/keywords/is.md)
