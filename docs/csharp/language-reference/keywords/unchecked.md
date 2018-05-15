---
title: unchecked (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- unchecked_CSharpKeyword
- unchecked
helpviewer_keywords:
- unchecked keyword [C#]
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
ms.openlocfilehash: d7a48950b7158be3cd589c20fbfe0661f3c9c5af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="unchecked-c-reference"></a><span data-ttu-id="5794e-102">unchecked (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="5794e-102">unchecked (C# Reference)</span></span>
<span data-ttu-id="5794e-103">Das Schlüsselwort `unchecked` wird verwendet, um eine Überlaufüberprüfung bei arithmetischen Operationen für ganzzahlige Typen und Konvertierungen zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="5794e-103">The `unchecked` keyword is used to suppress overflow-checking for integral-type arithmetic operations and conversions.</span></span>  
  
 <span data-ttu-id="5794e-104">Wenn ein Ausdruck in einem ungeprüften Kontext einen Wert erzeugt, der außerhalb des Bereichs des Zieltyps ist, wird der Überlauf nicht gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="5794e-104">In an unchecked context, if an expression produces a value that is outside the range of the destination type, the overflow is not flagged.</span></span> <span data-ttu-id="5794e-105">Da z.B. die Berechnung im folgenden Beispiel in einem `unchecked`-Block oder -Ausdruck ausgeführt wird, wird ignoriert, dass das Ergebnis zu groß für eine Ganzzahl ist, und `int1` bekommt den Wert -2.147.483.639 zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="5794e-105">For example, because the calculation in the following example is performed in an `unchecked` block or expression, the fact that the result is too large for an integer is ignored, and `int1` is assigned the value -2,147,483,639.</span></span>  
  
 [!code-csharp[csrefKeywordsChecked#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_1.cs)]  
  
 <span data-ttu-id="5794e-106">Wenn die `unchecked`-Umgebung entfernt wird, tritt ein Kompilierungsfehler auf.</span><span class="sxs-lookup"><span data-stu-id="5794e-106">If the `unchecked` environment is removed, a compilation error occurs.</span></span> <span data-ttu-id="5794e-107">Der Überlauf kann zur Kompilierzeit erkannt werden, da alle Begriffe des Ausdrucks Konstanten sind.</span><span class="sxs-lookup"><span data-stu-id="5794e-107">The overflow can be detected at compile time because all the terms of the expression are constants.</span></span>  
  
 <span data-ttu-id="5794e-108">Ausdrücke, die nicht konstante Begriffe enthalten, sind standardmäßig zur Kompilier- und Laufzeit deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5794e-108">Expressions that contain non-constant terms are unchecked by default at compile time and run time.</span></span> <span data-ttu-id="5794e-109">Informationen zum Aktivieren einer überprüften Umgebung finden Sie unter [checked](../../../csharp/language-reference/keywords/checked.md).</span><span class="sxs-lookup"><span data-stu-id="5794e-109">See [checked](../../../csharp/language-reference/keywords/checked.md) for information about enabling a checked environment.</span></span>  
  
 <span data-ttu-id="5794e-110">Da die Überprüfung auf Überlauf Zeit in Anspruch nimmt, kann die Verwendung von einem nicht überprüften Code in Situationen, in denen keine Überlaufgefahr besteht, die Leistung verbessern.</span><span class="sxs-lookup"><span data-stu-id="5794e-110">Because checking for overflow takes time, the use of unchecked code in situations where there is no danger of overflow might improve performance.</span></span> <span data-ttu-id="5794e-111">Wenn jedoch ein Überlauf möglich ist, sollte eine überprüfte Umgebung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5794e-111">However, if overflow is a possibility, a checked environment should be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5794e-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5794e-112">Example</span></span>  
 <span data-ttu-id="5794e-113">Im folgenden Beispiel wird die Verwendung des Schlüsselworts `unchecked` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="5794e-113">This sample shows how to use the `unchecked` keyword.</span></span>  
  
 [!code-csharp[csrefKeywordsChecked#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="5794e-114">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="5794e-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5794e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5794e-115">See Also</span></span>  
 [<span data-ttu-id="5794e-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="5794e-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5794e-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="5794e-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5794e-118">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5794e-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="5794e-119">AKtiviert und nicht aktiviert</span><span class="sxs-lookup"><span data-stu-id="5794e-119">Checked and Unchecked</span></span>](../../../csharp/language-reference/keywords/checked-and-unchecked.md)  
 [<span data-ttu-id="5794e-120">checked</span><span class="sxs-lookup"><span data-stu-id="5794e-120">checked</span></span>](../../../csharp/language-reference/keywords/checked.md)
