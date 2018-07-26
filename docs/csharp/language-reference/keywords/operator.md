---
title: operator (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: d633a46e21f913aa8c05289dccfb63e71efd697e
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37959543"
---
# <a name="operator-c-reference"></a><span data-ttu-id="5900e-102">operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="5900e-102">operator (C# Reference)</span></span>
<span data-ttu-id="5900e-103">Verwenden Sie das Schlüsselwort `operator`, um einen integrierten Operator zu überladen oder um eine benutzerdefinierte Konvertierung in einer Klassen- oder Strukturdeklaration bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="5900e-103">Use the `operator` keyword to overload a built-in operator or to provide a user-defined conversion in a class or struct declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5900e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5900e-104">Example</span></span>  
 <span data-ttu-id="5900e-105">Die Folgende ist eine stark vereinfachte Klasse für Bruchzahlen.</span><span class="sxs-lookup"><span data-stu-id="5900e-105">The following is a very simplified class for fractional numbers.</span></span> <span data-ttu-id="5900e-106">Sie überlädt die Operatoren `+` und `*`, um Addition und Multiplikation bei Brüchen auszuführen, und stellt einen Konvertierungsoperator bereit, der einen `Fraction`-Typ in einen `double`-Typ konvertiert.</span><span class="sxs-lookup"><span data-stu-id="5900e-106">It overloads the `+` and `*` operators to perform fractional addition and multiplication, and also provides a conversion operator that converts a `Fraction` type to a `double` type.</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="5900e-107">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="5900e-107">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5900e-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5900e-108">See Also</span></span>  
 [<span data-ttu-id="5900e-109">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="5900e-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5900e-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="5900e-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5900e-111">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5900e-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="5900e-112">implicit</span><span class="sxs-lookup"><span data-stu-id="5900e-112">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
 [<span data-ttu-id="5900e-113">explicit</span><span class="sxs-lookup"><span data-stu-id="5900e-113">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
 [<span data-ttu-id="5900e-114">Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen</span><span class="sxs-lookup"><span data-stu-id="5900e-114">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
