---
title: Operator -- (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
ms.openlocfilehash: 615b100447233856ab3740d075d69e3ae19285fd
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44210428"
---
# <a name="---operator-c-reference"></a><span data-ttu-id="dc922-102">Operator -- (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="dc922-102">-- Operator (C# Reference)</span></span>
<span data-ttu-id="dc922-103">Der Dekrementoperator (`--`) verringert seinen Operanden um 1.</span><span class="sxs-lookup"><span data-stu-id="dc922-103">The decrement operator (`--`) decrements its operand by 1.</span></span> <span data-ttu-id="dc922-104">Der Dekrementoperator kann vor oder hinter seinem Operanden angezeigt werden: `--variable` und `variable--`.</span><span class="sxs-lookup"><span data-stu-id="dc922-104">The decrement operator can appear before or after its operand: `--variable` and `variable--`.</span></span> <span data-ttu-id="dc922-105">Die erste Form stellt eine Präfixdekrementoperation dar.</span><span class="sxs-lookup"><span data-stu-id="dc922-105">The first form is a prefix decrement operation.</span></span> <span data-ttu-id="dc922-106">Das Ergebnis der Operation ist der Wert des Operanden, „nachdem“ er vermindert worden ist.</span><span class="sxs-lookup"><span data-stu-id="dc922-106">The result of the operation is the value of the operand "after" it has been decremented.</span></span> <span data-ttu-id="dc922-107">Die zweite Form stellt eine Postfixdekrementoperation dar.</span><span class="sxs-lookup"><span data-stu-id="dc922-107">The second form is a postfix decrement operation.</span></span> <span data-ttu-id="dc922-108">Das Ergebnis der Operation ist der Wert des Operanden, bevor er vermindert worden ist.</span><span class="sxs-lookup"><span data-stu-id="dc922-108">The result of the operation is the value of the operand "before" it has been decremented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc922-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dc922-109">Remarks</span></span>  
 <span data-ttu-id="dc922-110">Für alle numerischen Typen und Enumerationstypen sind Dekrementoperatoren vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="dc922-110">Numeric and enumeration types have predefined decrement operators.</span></span>  
  
 <span data-ttu-id="dc922-111">Benutzerdefinierte Typen können den Operator `--` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="dc922-111">User-defined types can overload the `--` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="dc922-112">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="dc922-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc922-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dc922-113">Example</span></span>  
 [!code-csharp[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="dc922-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc922-114">See Also</span></span>

- [<span data-ttu-id="dc922-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="dc922-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="dc922-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="dc922-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="dc922-117">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="dc922-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
