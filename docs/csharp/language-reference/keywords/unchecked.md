---
title: unchecked (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- unchecked_CSharpKeyword
- unchecked
dev_langs:
- CSharp
helpviewer_keywords:
- unchecked keyword [C#]
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5878a2412e6c85da85b1a3b8c2a8255b51e67137
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="unchecked-c-reference"></a><span data-ttu-id="d0fc5-102">unchecked (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d0fc5-102">unchecked (C# Reference)</span></span>
<span data-ttu-id="d0fc5-103">Das Schlüsselwort `unchecked` wird verwendet, um eine Überlaufüberprüfung bei arithmetischen Operationen für ganzzahlige Typen und Konvertierungen zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="d0fc5-103">The `unchecked` keyword is used to suppress overflow-checking for integral-type arithmetic operations and conversions.</span></span>  
  
 <span data-ttu-id="d0fc5-104">Wenn ein Ausdruck in einem ungeprüften Kontext einen Wert erzeugt, der außerhalb des Bereichs des Zieltyps ist, wird der Überlauf nicht gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="d0fc5-104">In an unchecked context, if an expression produces a value that is outside the range of the destination type, the overflow is not flagged.</span></span> <span data-ttu-id="d0fc5-105">Da z.B. die Berechnung im folgenden Beispiel in einem `unchecked`-Block oder -Ausdruck ausgeführt wird, wird ignoriert, dass das Ergebnis zu groß für eine Ganzzahl ist, und `int1` bekommt den Wert -2.147.483.639 zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d0fc5-105">For example, because the calculation in the following example is performed in an `unchecked` block or expression, the fact that the result is too large for an integer is ignored, and `int1` is assigned the value -2,147,483,639.</span></span>  
  
 <span data-ttu-id="d0fc5-106">[!code-cs[csrefKeywordsChecked#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d0fc5-106">[!code-cs[csrefKeywordsChecked#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_1.cs)]</span></span>  
  
 <span data-ttu-id="d0fc5-107">Wenn die `unchecked`-Umgebung entfernt wird, tritt ein Kompilierungsfehler auf.</span><span class="sxs-lookup"><span data-stu-id="d0fc5-107">If the `unchecked` environment is removed, a compilation error occurs.</span></span> <span data-ttu-id="d0fc5-108">Der Überlauf kann zur Kompilierzeit erkannt werden, da alle Begriffe des Ausdrucks Konstanten sind.</span><span class="sxs-lookup"><span data-stu-id="d0fc5-108">The overflow can be detected at compile time because all the terms of the expression are constants.</span></span>  
  
 <span data-ttu-id="d0fc5-109">Ausdrücke, die nicht konstante Begriffe enthalten, sind standardmäßig zur Kompilier- und Laufzeit deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="d0fc5-109">Expressions that contain non-constant terms are unchecked by default at compile time and run time.</span></span> <span data-ttu-id="d0fc5-110">Informationen zum Aktivieren einer überprüften Umgebung finden Sie unter [checked](../../../csharp/language-reference/keywords/checked.md).</span><span class="sxs-lookup"><span data-stu-id="d0fc5-110">See [checked](../../../csharp/language-reference/keywords/checked.md) for information about enabling a checked environment.</span></span>  
  
 <span data-ttu-id="d0fc5-111">Da die Überprüfung auf Überlauf Zeit in Anspruch nimmt, kann die Verwendung von einem nicht überprüften Code in Situationen, in denen keine Überlaufgefahr besteht, die Leistung verbessern.</span><span class="sxs-lookup"><span data-stu-id="d0fc5-111">Because checking for overflow takes time, the use of unchecked code in situations where there is no danger of overflow might improve performance.</span></span> <span data-ttu-id="d0fc5-112">Wenn jedoch ein Überlauf möglich ist, sollte eine überprüfte Umgebung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d0fc5-112">However, if overflow is a possibility, a checked environment should be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0fc5-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d0fc5-113">Example</span></span>  
 <span data-ttu-id="d0fc5-114">Im folgenden Beispiel wird die Verwendung des Schlüsselworts `unchecked` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d0fc5-114">This sample shows how to use the `unchecked` keyword.</span></span>  
  
 <span data-ttu-id="d0fc5-115">[!code-cs[csrefKeywordsChecked#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d0fc5-115">[!code-cs[csrefKeywordsChecked#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d0fc5-116">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="d0fc5-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d0fc5-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0fc5-117">See Also</span></span>  
 <span data-ttu-id="d0fc5-118">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d0fc5-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d0fc5-119">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d0fc5-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d0fc5-120">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="d0fc5-120">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="d0fc5-121">[Checked und unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md) </span><span class="sxs-lookup"><span data-stu-id="d0fc5-121">[Checked and Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md) </span></span>  
 [<span data-ttu-id="d0fc5-122">checked</span><span class="sxs-lookup"><span data-stu-id="d0fc5-122">checked</span></span>](../../../csharp/language-reference/keywords/checked.md)

