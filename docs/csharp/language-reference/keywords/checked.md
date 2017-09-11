---
title: checked (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- checked_CSharpKeyword
- checked
dev_langs:
- CSharp
helpviewer_keywords:
- checked keyword [C#]
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
caps.latest.revision: 24
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
ms.openlocfilehash: abe34772c0f07b0a43f7299088bf5ea9a1d2aa78
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="checked-c-reference"></a><span data-ttu-id="f48b4-102">checked (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f48b4-102">checked (C# Reference)</span></span>
<span data-ttu-id="f48b4-103">Das Schlüsselwort `checked` wird verwendet, um eine Überlaufüberprüfung bei arithmetischen Operationen für ganzzahlige Typen und Konvertierungen explizit zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f48b4-103">The `checked` keyword is used to explicitly enable overflow checking for integral-type arithmetic operations and conversions.</span></span>  
  
 <span data-ttu-id="f48b4-104">Standardmäßig bewirkt ein Ausdruck, der nur konstante Werte enthält, einen Compilerfehler, wenn der Ausdruck einen Wert erzeugt, der außerhalb des Bereichs des Zieltyps liegt.</span><span class="sxs-lookup"><span data-stu-id="f48b4-104">By default, an expression that contains only constant values causes a compiler error if the expression produces a value that is outside the range of the destination type.</span></span> <span data-ttu-id="f48b4-105">Wenn der Ausdruck einen oder mehrere nicht konstante Werte enthält, erkennt der Compiler den Überlauf nicht.</span><span class="sxs-lookup"><span data-stu-id="f48b4-105">If the expression contains one or more non-constant values, the compiler does not detect the overflow.</span></span> <span data-ttu-id="f48b4-106">Die Auswertung des Ausdrucks, der im folgenden Beispiel `i2` zugewiesen ist, verursacht keinen Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="f48b4-106">Evaluating the expression assigned to `i2` in the following example does not cause a compiler error.</span></span>  
  
 <span data-ttu-id="f48b4-107">[!code-cs[csrefKeywordsChecked#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f48b4-107">[!code-cs[csrefKeywordsChecked#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_1.cs)]</span></span>  
  
 <span data-ttu-id="f48b4-108">Standardmäßig werden diese nicht konstanten Ausdrücke zur Laufzeit auch nicht auf Überläufe überprüft und lösen keine Überlaufausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="f48b4-108">By default, these non-constant expressions are not checked for overflow at run time either, and they do not raise overflow exceptions.</span></span> <span data-ttu-id="f48b4-109">Das vorherige Beispiel zeigt -2,147,483,639 als Summe von zwei ganzen Zahlen.</span><span class="sxs-lookup"><span data-stu-id="f48b4-109">The previous example displays -2,147,483,639 as the sum of two positive integers.</span></span>  
  
 <span data-ttu-id="f48b4-110">Die Überlaufüberprüfung kann durch Compileroptionen, Umgebungskonfiguration oder Verwendung des `checked`-Schlüsselworts aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f48b4-110">Overflow checking can be enabled by compiler options, environment configuration, or use of the `checked` keyword.</span></span> <span data-ttu-id="f48b4-111">In den folgenden Beispielen wird veranschaulicht, wie Sie einen `checked`-Ausdruck oder einen `checked`-Block verwenden, um den Überlauf zu erkennen, der von der vorherigen Summe zur Laufzeit erzeugt wird.</span><span class="sxs-lookup"><span data-stu-id="f48b4-111">The following examples demonstrate how to use a `checked` expression or a `checked` block to detect the overflow that is produced by the previous sum at run time.</span></span> <span data-ttu-id="f48b4-112">In beiden Beispielen wird eine Überlaufausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="f48b4-112">Both examples raise an overflow exception.</span></span>  
  
 <span data-ttu-id="f48b4-113">[!code-cs[csrefKeywordsChecked#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f48b4-113">[!code-cs[csrefKeywordsChecked#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_2.cs)]</span></span>  
  
 <span data-ttu-id="f48b4-114">Das [unchecked](../../../csharp/language-reference/keywords/unchecked.md)-Schlüsselwort kann verwendet werden, um die Überlaufüberprüfung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="f48b4-114">The [unchecked](../../../csharp/language-reference/keywords/unchecked.md) keyword can be used to prevent overflow checking.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f48b4-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f48b4-115">Example</span></span>  
 <span data-ttu-id="f48b4-116">Dieses Beispiel zeigt, wie mit `checked` die Überlaufüberprüfung zur Laufzeit aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="f48b4-116">This sample shows how to use `checked` to enable overflow checking at run time.</span></span>  
  
 <span data-ttu-id="f48b4-117">[!code-cs[csrefKeywordsChecked#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="f48b4-117">[!code-cs[csrefKeywordsChecked#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_3.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f48b4-118">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="f48b4-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f48b4-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f48b4-119">See Also</span></span>  
 <span data-ttu-id="f48b4-120">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f48b4-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f48b4-121">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f48b4-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f48b4-122">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="f48b4-122">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="f48b4-123">[Checked und Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md) </span><span class="sxs-lookup"><span data-stu-id="f48b4-123">[Checked and Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md) </span></span>  
 [<span data-ttu-id="f48b4-124">unchecked</span><span class="sxs-lookup"><span data-stu-id="f48b4-124">unchecked</span></span>](../../../csharp/language-reference/keywords/unchecked.md)

