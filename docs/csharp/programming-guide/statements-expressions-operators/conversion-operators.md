---
title: Konvertierungsoperatoren (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
ms.openlocfilehash: cbf6a83d43a1b3a69e82a35d5d0875f62422cd3f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44183313"
---
# <a name="conversion-operators-c-programming-guide"></a><span data-ttu-id="ee016-102">Konvertierungsoperatoren (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ee016-102">Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="ee016-103">Mit C# können Programmierer Konvertierungen für Klassen oder Strukturen deklarieren, damit Klassen oder Strukturen in andere Klassen und Strukturen und Basistypen oder aus diesen konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="ee016-103">C# enables programmers to declare conversions on classes or structs so that classes or structs can be converted to and/or from other classes or structs, or basic types.</span></span> <span data-ttu-id="ee016-104">Konvertierungen werden wie Operatoren definiert und nach dem Typ benannt, in den Sie konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="ee016-104">Conversions are defined like operators and are named for the type to which they convert.</span></span> <span data-ttu-id="ee016-105">Entweder muss der Typ des zu konvertierenden Arguments oder der Typ des Konvertierungsergebnisses, aber nicht beide, der enthaltende Typ sein.</span><span class="sxs-lookup"><span data-stu-id="ee016-105">Either the type of the argument to be converted, or the type of the result of the conversion, but not both, must be the containing type.</span></span>  
  
 [!code-csharp[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]  
  
## <a name="conversion-operators-overview"></a><span data-ttu-id="ee016-106">Überblick über Konvertierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="ee016-106">Conversion Operators Overview</span></span>  
 <span data-ttu-id="ee016-107">Konvertierungsoperatoren verfügen über folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="ee016-107">Conversion operators have the following properties:</span></span>  
  
-   <span data-ttu-id="ee016-108">Konvertierungen, die als `implicit` deklariert wurden, werden bei Bedarf automatisch durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="ee016-108">Conversions declared as `implicit` occur automatically when it is required.</span></span>  
  
-   <span data-ttu-id="ee016-109">Konvertierungen, die als `explicit` deklariert wurden, erfordern zum Aufruf eine Umwandlung.</span><span class="sxs-lookup"><span data-stu-id="ee016-109">Conversions declared as `explicit` require a cast to be called.</span></span>  
  
-   <span data-ttu-id="ee016-110">Alle Konvertierungen müssen als `static` deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="ee016-110">All conversions must be declared as `static`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ee016-111">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="ee016-111">Related Sections</span></span>  
 <span data-ttu-id="ee016-112">Weitere Informationen finden Sie unter: </span><span class="sxs-lookup"><span data-stu-id="ee016-112">For more information:</span></span>  
  
-   [<span data-ttu-id="ee016-113">Verwenden von Konvertierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="ee016-113">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [<span data-ttu-id="ee016-114">Umwandlung und Typkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="ee016-114">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [<span data-ttu-id="ee016-115">Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen</span><span class="sxs-lookup"><span data-stu-id="ee016-115">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="ee016-116">explicit</span><span class="sxs-lookup"><span data-stu-id="ee016-116">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [<span data-ttu-id="ee016-117">implicit</span><span class="sxs-lookup"><span data-stu-id="ee016-117">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [<span data-ttu-id="ee016-118">static</span><span class="sxs-lookup"><span data-stu-id="ee016-118">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a><span data-ttu-id="ee016-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee016-119">See Also</span></span>

- <xref:System.Convert>  
- [<span data-ttu-id="ee016-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ee016-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ee016-121">Chained user-defined explicit conversions in C# (Verkettete benutzerdefinierte, explizite Konvertierungen in C#)</span><span class="sxs-lookup"><span data-stu-id="ee016-121">Chained user-defined explicit conversions in C#</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)
