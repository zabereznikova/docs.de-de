---
title: ?? -Operator – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ??_CSharpKeyword
helpviewer_keywords:
- coalesce operator [C#]
- ?? operator [C#]
- conditional-AND operator (&&) [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: e1e981f9ec6a87f6e7de1900008520cde8e46095
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633946"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="1f4cb-103">??</span><span class="sxs-lookup"><span data-stu-id="1f4cb-103">??</span></span> <span data-ttu-id="1f4cb-104">operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="1f4cb-104">operator (C# Reference)</span></span>

<span data-ttu-id="1f4cb-105">Der Operator `??` wird NULL-Sammeloperator genannt.</span><span class="sxs-lookup"><span data-stu-id="1f4cb-105">The `??` operator is called the null-coalescing operator.</span></span>  <span data-ttu-id="1f4cb-106">Der linke Operand wird zurückgegeben, falls dieser nicht NULL ist. Andernfalls wird der rechte Operand zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1f4cb-106">It returns the left-hand operand if the operand is not null; otherwise it returns the right hand operand.</span></span>

## <a name="remarks"></a><span data-ttu-id="1f4cb-107">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="1f4cb-107">Remarks</span></span>

<span data-ttu-id="1f4cb-108">Ein Typ, der NULL-Werte zulässt, kann einen Wert aus der Domäne des Typs repräsentieren, oder der Wert kann nicht definiert sein (in diesem Fall ist der Wert NULL).</span><span class="sxs-lookup"><span data-stu-id="1f4cb-108">A nullable type can represent a value from the type’s domain, or the value can be undefined (in which case the value is null).</span></span> <span data-ttu-id="1f4cb-109">Sie können mit der syntaktischen Ausdruckskraft des `??`-Operators einen entsprechenden Wert (den rechten Operand) zurückgeben, wenn der linke Operand einen Typ aufweist, der NULL-Werte zulässt und dessen Wert NULL ist.</span><span class="sxs-lookup"><span data-stu-id="1f4cb-109">You can use the `??` operator’s syntactic expressiveness to return an appropriate value (the right hand operand) when the left operand has a nullable type whose value is null.</span></span> <span data-ttu-id="1f4cb-110">Der Versuch, einen Werttyp, der auf NULL festgelegt werden kann, einem Werttyp, der nicht auf NULL festgelegt werden kann, ohne Verwendung des Operators `??` zuzuweisen, verursacht einen Kompilierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="1f4cb-110">If you try to assign a nullable value type to a non-nullable value type without using the `??` operator, you will generate a compile-time error.</span></span> <span data-ttu-id="1f4cb-111">Wenn bei einer Typumwandlung der Werttyp, der auf NULL festgelegt werden kann, aktuell nicht definiert ist, wird eine `InvalidOperationException`-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1f4cb-111">If you use a cast, and the nullable value type is currently undefined, an `InvalidOperationException` exception will be thrown.</span></span>

<span data-ttu-id="1f4cb-112">Weitere Informationen finden Sie unter [Nullable-Typen](../../programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="1f4cb-112">For more information, see [Nullable Types](../../programming-guide/nullable-types/index.md).</span></span>

<span data-ttu-id="1f4cb-113">Das Ergebnis eines ??-</span><span class="sxs-lookup"><span data-stu-id="1f4cb-113">The result of a ??</span></span> <span data-ttu-id="1f4cb-114">Operators wird nicht als Konstante angesehen, auch wenn beide Argumente Konstanten sind.</span><span class="sxs-lookup"><span data-stu-id="1f4cb-114">operator is not considered to be a constant even if both its arguments are constants.</span></span>

## <a name="example"></a><span data-ttu-id="1f4cb-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1f4cb-115">Example</span></span>

[!code-csharp[csRefOperators#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#53)]

## <a name="c-language-specification"></a><span data-ttu-id="1f4cb-116">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="1f4cb-116">C# language specification</span></span>

<span data-ttu-id="1f4cb-117">Weitere Informationen finden Sie unter [Der NULL-Sammeloperator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) in der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="1f4cb-117">For more information, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="1f4cb-118">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="1f4cb-118">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f4cb-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f4cb-119">See also</span></span>

- [<span data-ttu-id="1f4cb-120">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="1f4cb-120">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1f4cb-121">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="1f4cb-121">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1f4cb-122">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="1f4cb-122">C# operators</span></span>](index.md)
- [<span data-ttu-id="1f4cb-123">Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="1f4cb-123">Nullable Types</span></span>](../../programming-guide/nullable-types/index.md)
- <span data-ttu-id="1f4cb-124">[What exactly does 'lifted' mean?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/) (Was genau bedeutet „Lifted“?)</span><span class="sxs-lookup"><span data-stu-id="1f4cb-124">[What Exactly Does 'Lifted' mean?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)</span></span>
