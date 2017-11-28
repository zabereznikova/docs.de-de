---
title: Konvertierungsoperatoren (C#-Programmierhandbuch)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
caps.latest.revision: "22"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5277c1160c604ee56ff575df5bd603e115588d21
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="conversion-operators-c-programming-guide"></a><span data-ttu-id="22f96-102">Konvertierungsoperatoren (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="22f96-102">Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="22f96-103">Mit C# können Programmierer Konvertierungen für Klassen oder Strukturen deklarieren, damit Klassen oder Strukturen in andere Klassen und Strukturen und Basistypen oder aus diesen konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="22f96-103">C# enables programmers to declare conversions on classes or structs so that classes or structs can be converted to and/or from other classes or structs, or basic types.</span></span> <span data-ttu-id="22f96-104">Konvertierungen werden wie Operatoren definiert und nach dem Typ benannt, in den Sie konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="22f96-104">Conversions are defined like operators and are named for the type to which they convert.</span></span> <span data-ttu-id="22f96-105">Entweder muss der Typ des zu konvertierenden Arguments oder der Typ des Konvertierungsergebnisses, aber nicht beide, der enthaltende Typ sein.</span><span class="sxs-lookup"><span data-stu-id="22f96-105">Either the type of the argument to be converted, or the type of the result of the conversion, but not both, must be the containing type.</span></span>  
  
 [!code-csharp[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]  
  
## <a name="conversion-operators-overview"></a><span data-ttu-id="22f96-106">Überblick über Konvertierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="22f96-106">Conversion Operators Overview</span></span>  
 <span data-ttu-id="22f96-107">Konvertierungsoperatoren verfügen über folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="22f96-107">Conversion operators have the following properties:</span></span>  
  
-   <span data-ttu-id="22f96-108">Konvertierungen, die als `implicit` deklariert wurden, werden bei Bedarf automatisch durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="22f96-108">Conversions declared as `implicit` occur automatically when it is required.</span></span>  
  
-   <span data-ttu-id="22f96-109">Konvertierungen, die als `explicit` deklariert wurden, erfordern zum Aufruf eine Umwandlung.</span><span class="sxs-lookup"><span data-stu-id="22f96-109">Conversions declared as `explicit` require a cast to be called.</span></span>  
  
-   <span data-ttu-id="22f96-110">Alle Konvertierungen müssen als `static` deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="22f96-110">All conversions must be declared as `static`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="22f96-111">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="22f96-111">Related Sections</span></span>  
 <span data-ttu-id="22f96-112">Weitere Informationen finden Sie unter: </span><span class="sxs-lookup"><span data-stu-id="22f96-112">For more information:</span></span>  
  
-   [<span data-ttu-id="22f96-113">Verwenden von Konvertierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="22f96-113">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [<span data-ttu-id="22f96-114">Umwandlung und Typkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="22f96-114">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [<span data-ttu-id="22f96-115">Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen</span><span class="sxs-lookup"><span data-stu-id="22f96-115">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="22f96-116">explicit</span><span class="sxs-lookup"><span data-stu-id="22f96-116">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [<span data-ttu-id="22f96-117">implicit</span><span class="sxs-lookup"><span data-stu-id="22f96-117">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [<span data-ttu-id="22f96-118">static</span><span class="sxs-lookup"><span data-stu-id="22f96-118">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a><span data-ttu-id="22f96-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22f96-119">See Also</span></span>  
 <xref:System.Convert>  
 [<span data-ttu-id="22f96-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="22f96-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="22f96-121">Chained user-defined explicit conversions in C# (Verkettete benutzerdefinierte, explizite Konvertierungen in C#)</span><span class="sxs-lookup"><span data-stu-id="22f96-121">Chained user-defined explicit conversions in C#</span></span>](http://go.microsoft.com/fwlink/?LinkId=112384)
