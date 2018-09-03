---
title: Schlüsselwort „operator“ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: c3bfada235993670bf158fe9803a09707b2b3251
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42929871"
---
# <a name="operator-c-reference"></a><span data-ttu-id="854a4-102">operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="854a4-102">operator (C# Reference)</span></span>

<span data-ttu-id="854a4-103">Verwenden Sie das Schlüsselwort `operator`, um einen integrierten Operator zu überladen oder um eine benutzerdefinierte Konvertierung in einer Klassen- oder Strukturdeklaration bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="854a4-103">Use the `operator` keyword to overload a built-in operator or to provide a user-defined conversion in a class or struct declaration.</span></span>

## <a name="example"></a><span data-ttu-id="854a4-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="854a4-104">Example</span></span>

<span data-ttu-id="854a4-105">Die Folgende ist eine stark vereinfachte Klasse für Bruchzahlen.</span><span class="sxs-lookup"><span data-stu-id="854a4-105">The following is a very simplified class for fractional numbers.</span></span> <span data-ttu-id="854a4-106">Sie überlädt die Operatoren `+` und `*`, um Addition und Multiplikation bei Brüchen auszuführen, und stellt einen Konvertierungsoperator bereit, der einen `Fraction`-Typ in einen `double`-Typ konvertiert.</span><span class="sxs-lookup"><span data-stu-id="854a4-106">It overloads the `+` and `*` operators to perform fractional addition and multiplication, and also provides a conversion operator that converts a `Fraction` type to a `double` type.</span></span>

[!code-csharp[csrefKeywordsConversion#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="854a4-107">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="854a4-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="854a4-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="854a4-108">See also</span></span>

- [<span data-ttu-id="854a4-109">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="854a4-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="854a4-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="854a4-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="854a4-111">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="854a4-111">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="854a4-112">implicit</span><span class="sxs-lookup"><span data-stu-id="854a4-112">implicit</span></span>](implicit.md)
- [<span data-ttu-id="854a4-113">explicit</span><span class="sxs-lookup"><span data-stu-id="854a4-113">explicit</span></span>](explicit.md)
- [<span data-ttu-id="854a4-114">Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen</span><span class="sxs-lookup"><span data-stu-id="854a4-114">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
