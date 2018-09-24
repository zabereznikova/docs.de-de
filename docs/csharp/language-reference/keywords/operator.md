---
title: Schlüsselwort „operator“ (C#-Referenz)
description: Vorgehensweise beim Überladen eines integrierten C#-Operators
ms.date: 08/27/2018
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: 1e11d7767b61becc39b1158fae9cb2abe997e4bd
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46525749"
---
# <a name="operator-c-reference"></a><span data-ttu-id="15572-103">operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="15572-103">operator (C# Reference)</span></span>

<span data-ttu-id="15572-104">Verwenden Sie das Schlüsselwort `operator`, um einen integrierten Operator zu überladen oder um eine benutzerdefinierte Konvertierung in einer Klassen- oder Strukturdeklaration bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="15572-104">Use the `operator` keyword to overload a built-in operator or to provide a user-defined conversion in a class or struct declaration.</span></span>

<span data-ttu-id="15572-105">Zum Überladen eines Operators in einer benutzerdefinierten Klasse oder Struktur müssen Sie eine Operatordeklaration im entsprechenden Typ erstellen.</span><span class="sxs-lookup"><span data-stu-id="15572-105">To overload an operator on a custom class or struct, you create an operator declaration in the corresponding type.</span></span> <span data-ttu-id="15572-106">Die Operatordeklaration, die einen integrierten C#-Operator überlädt, muss die folgenden Regeln erfüllen:</span><span class="sxs-lookup"><span data-stu-id="15572-106">The operator declaration that overloads a built-in C# operator must satisfy the following rules:</span></span>

- <span data-ttu-id="15572-107">Sie enthält sowohl einen `public`- als auch einen `static`-Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="15572-107">It includes both a `public` and a `static` modifier.</span></span>
- <span data-ttu-id="15572-108">Sie enthält `operator X`, wobei `X` für den Namen oder das Symbol des überladenen Operators steht.</span><span class="sxs-lookup"><span data-stu-id="15572-108">It includes `operator X` where `X` is the name or symbol of the operator being overloaded.</span></span>
- <span data-ttu-id="15572-109">Unäre Operatoren verfügen über einen Parameter. Demgegenüber weisen binäre Operatoren zwei Parameter auf.</span><span class="sxs-lookup"><span data-stu-id="15572-109">Unary operators have one parameter, and binary operators have two parameters.</span></span> <span data-ttu-id="15572-110">In jedem Fall muss mindestens ein Parameter denselben Typ wie die Klasse oder Struktur aufweisen, die den Operator deklariert.</span><span class="sxs-lookup"><span data-stu-id="15572-110">In each case, at least one parameter must be the same type as the class or struct that declares the operator.</span></span>

<span data-ttu-id="15572-111">Weitere Informationen zum Definieren von Konvertierungsoperatoren finden Sie in den [expliziten](explicit.md) und [impliziten](implicit.md) Keyword-Artikeln.</span><span class="sxs-lookup"><span data-stu-id="15572-111">For information about how to define conversion operators, see the [explicit](explicit.md) and [implicit](implicit.md) keyword articles.</span></span>

<span data-ttu-id="15572-112">Eine Übersicht über die C#-Operatoren, die überladen werden können, finden Sie im Artikel [Überladbare Operatoren](../../programming-guide/statements-expressions-operators/overloadable-operators.md).</span><span class="sxs-lookup"><span data-stu-id="15572-112">For an overview of the C# operators that can be overloaded, see the [Overloadable operators](../../programming-guide/statements-expressions-operators/overloadable-operators.md) article.</span></span>

## <a name="example"></a><span data-ttu-id="15572-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="15572-113">Example</span></span>

<span data-ttu-id="15572-114">Im folgenden Beispiel wird ein `Fraction`-Typ definiert, der Bruchzahlen darstellt.</span><span class="sxs-lookup"><span data-stu-id="15572-114">The following example defines a `Fraction` type that represents fractional numbers.</span></span> <span data-ttu-id="15572-115">Sie überlädt die Operatoren `+` und `*`, um Addition und Multiplikation bei Brüchen auszuführen, und stellt einen Konvertierungsoperator bereit, der einen `Fraction`-Typ in einen `double`-Typ konvertiert.</span><span class="sxs-lookup"><span data-stu-id="15572-115">It overloads the `+` and `*` operators to perform fractional addition and multiplication, and also provides a conversion operator that converts a `Fraction` type to a `double` type.</span></span>

[!code-csharp[csrefKeywordsConversion#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="15572-116">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="15572-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="15572-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15572-117">See also</span></span>

- [<span data-ttu-id="15572-118">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="15572-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="15572-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="15572-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="15572-120">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="15572-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="15572-121">implicit</span><span class="sxs-lookup"><span data-stu-id="15572-121">implicit</span></span>](implicit.md)
- [<span data-ttu-id="15572-122">explicit</span><span class="sxs-lookup"><span data-stu-id="15572-122">explicit</span></span>](explicit.md)
- [<span data-ttu-id="15572-123">Überladbare Operatoren</span><span class="sxs-lookup"><span data-stu-id="15572-123">Overloadable operators</span></span>](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [<span data-ttu-id="15572-124">Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen</span><span class="sxs-lookup"><span data-stu-id="15572-124">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
