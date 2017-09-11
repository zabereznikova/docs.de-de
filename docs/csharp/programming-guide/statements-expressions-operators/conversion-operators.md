---
title: Konvertierungsoperatoren (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c12fd13d6526d79363f973ce2a944c4823bf4104
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="conversion-operators-c-programming-guide"></a><span data-ttu-id="9dbb9-102">Konvertierungsoperatoren (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="9dbb9-102">Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="9dbb9-103">Mit C# können Programmierer Konvertierungen für Klassen oder Strukturen deklarieren, damit Klassen oder Strukturen in andere Klassen und Strukturen und Basistypen oder aus diesen konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="9dbb9-103">C# enables programmers to declare conversions on classes or structs so that classes or structs can be converted to and/or from other classes or structs, or basic types.</span></span> <span data-ttu-id="9dbb9-104">Konvertierungen werden wie Operatoren definiert und nach dem Typ benannt, in den Sie konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="9dbb9-104">Conversions are defined like operators and are named for the type to which they convert.</span></span> <span data-ttu-id="9dbb9-105">Entweder muss der Typ des zu konvertierenden Arguments oder der Typ des Konvertierungsergebnisses, aber nicht beide, der enthaltende Typ sein.</span><span class="sxs-lookup"><span data-stu-id="9dbb9-105">Either the type of the argument to be converted, or the type of the result of the conversion, but not both, must be the containing type.</span></span>  
  
 <span data-ttu-id="9dbb9-106">[!code-cs[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9dbb9-106">[!code-cs[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]</span></span>  
  
## <a name="conversion-operators-overview"></a><span data-ttu-id="9dbb9-107">Überblick über Konvertierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="9dbb9-107">Conversion Operators Overview</span></span>  
 <span data-ttu-id="9dbb9-108">Konvertierungsoperatoren verfügen über folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="9dbb9-108">Conversion operators have the following properties:</span></span>  
  
-   <span data-ttu-id="9dbb9-109">Konvertierungen, die als `implicit` deklariert wurden, werden bei Bedarf automatisch durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="9dbb9-109">Conversions declared as `implicit` occur automatically when it is required.</span></span>  
  
-   <span data-ttu-id="9dbb9-110">Konvertierungen, die als `explicit` deklariert wurden, erfordern zum Aufruf eine Umwandlung.</span><span class="sxs-lookup"><span data-stu-id="9dbb9-110">Conversions declared as `explicit` require a cast to be called.</span></span>  
  
-   <span data-ttu-id="9dbb9-111">Alle Konvertierungen müssen als `static` deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="9dbb9-111">All conversions must be declared as `static`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9dbb9-112">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="9dbb9-112">Related Sections</span></span>  
 <span data-ttu-id="9dbb9-113">Weitere Informationen finden Sie unter: </span><span class="sxs-lookup"><span data-stu-id="9dbb9-113">For more information:</span></span>  
  
-   [<span data-ttu-id="9dbb9-114">Verwenden von Konvertierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="9dbb9-114">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [<span data-ttu-id="9dbb9-115">Umwandlung und Typkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="9dbb9-115">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [<span data-ttu-id="9dbb9-116">Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen</span><span class="sxs-lookup"><span data-stu-id="9dbb9-116">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="9dbb9-117">explicit</span><span class="sxs-lookup"><span data-stu-id="9dbb9-117">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [<span data-ttu-id="9dbb9-118">implicit</span><span class="sxs-lookup"><span data-stu-id="9dbb9-118">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [<span data-ttu-id="9dbb9-119">static</span><span class="sxs-lookup"><span data-stu-id="9dbb9-119">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a><span data-ttu-id="9dbb9-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9dbb9-120">See Also</span></span>  
 <span data-ttu-id="9dbb9-121"><xref:System.Convert></span><span class="sxs-lookup"><span data-stu-id="9dbb9-121"><xref:System.Convert></span></span>   
 <span data-ttu-id="9dbb9-122">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9dbb9-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="9dbb9-123">Chained user-defined explicit conversions in C# (Verkettete benutzerdefinierte, explizite Konvertierungen in C#)</span><span class="sxs-lookup"><span data-stu-id="9dbb9-123">Chained user-defined explicit conversions in C#</span></span>](http://go.microsoft.com/fwlink/?LinkId=112384)

