---
title: implicit (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- implicit
- implicit_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- implicit keyword [C#]
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
caps.latest.revision: 19
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
ms.openlocfilehash: e4452a3bb6da2d0d294ca26d6b957f2c1c4402fd
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="implicit-c-reference"></a><span data-ttu-id="3471e-102">implicit (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="3471e-102">implicit (C# Reference)</span></span>
<span data-ttu-id="3471e-103">Das `implicit`-Schlüsselwort wird verwendet, um einen impliziten benutzerdefinierten Typkonvertierungsoperator zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="3471e-103">The `implicit` keyword is used to declare an implicit user-defined type conversion operator.</span></span> <span data-ttu-id="3471e-104">Verwenden Sie es zur Aktivierung impliziter Konvertierungen zwischen einem benutzerdefinierten Typ und einen anderen Typ, wenn die Konvertierung mit Sicherheit nicht zu einem Datenverlust führt.</span><span class="sxs-lookup"><span data-stu-id="3471e-104">Use it to enable implicit conversions between a user-defined type and another type, if the conversion is guaranteed not to cause a loss of data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3471e-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3471e-105">Example</span></span>  
 <span data-ttu-id="3471e-106">[!code-cs[csrefKeywordsConversion#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicit_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3471e-106">[!code-cs[csrefKeywordsConversion#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicit_1.cs)]</span></span>  
  
 <span data-ttu-id="3471e-107">Durch Eliminierung unnötiger Umwandlungen können implizite Konvertierungen die Lesbarkeit des Quellcodes verbessern.</span><span class="sxs-lookup"><span data-stu-id="3471e-107">By eliminating unnecessary casts, implicit conversions can improve source code readability.</span></span> <span data-ttu-id="3471e-108">Da implizite Konvertierungen aber nicht erfordern, dass Programmierer explizit von einem Typ in den anderen umwandeln, muss darauf geachtet werden, um unerwartete Ergebnisse zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="3471e-108">However, because implicit conversions do not require programmers to explicitly cast from one type to the other, care must be taken to prevent unexpected results.</span></span> <span data-ttu-id="3471e-109">Im Allgemeinen sollten implizite Konvertierungsoperatoren keine Ausnahmen auslösen und keine Informationen verlieren, sodass sie problemlos ohne Wissen des Programmierers verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="3471e-109">In general, implicit conversion operators should never throw exceptions and never lose information so that they can be used safely without the programmer's awareness.</span></span> <span data-ttu-id="3471e-110">Wenn ein Konvertierungsoperator diese Kriterien nicht erfüllen kann, sollte er als `explicit` markiert werden.</span><span class="sxs-lookup"><span data-stu-id="3471e-110">If a conversion operator cannot meet those criteria, it should be marked `explicit`.</span></span> <span data-ttu-id="3471e-111">Weitere Informationen finden Sie unter [Verwenden von Konvertierungsoperatoren](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="3471e-111">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="3471e-112">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="3471e-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3471e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3471e-113">See Also</span></span>  
 <span data-ttu-id="3471e-114">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3471e-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3471e-115">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3471e-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3471e-116">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="3471e-116">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="3471e-117">[explicit](../../../csharp/language-reference/keywords/explicit.md) </span><span class="sxs-lookup"><span data-stu-id="3471e-117">[explicit](../../../csharp/language-reference/keywords/explicit.md) </span></span>  
 <span data-ttu-id="3471e-118">[Operator (C#-Referenz)](../../../csharp/language-reference/keywords/operator.md) </span><span class="sxs-lookup"><span data-stu-id="3471e-118">[operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md) </span></span>  
 [<span data-ttu-id="3471e-119">Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen</span><span class="sxs-lookup"><span data-stu-id="3471e-119">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)

