---
title: "Anweisungen, Ausdrücke und Operatoren (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- expressions [C#]
- operators [C#]
- C# language, statements
- C# language, operators
- C# language, expressions
- statements [C#]
ms.assetid: 20f8469d-5a6a-4084-ad90-0856b7e97e45
caps.latest.revision: 22
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
ms.openlocfilehash: 71988a5b9aa59b2655b4fd7b91522fe69c8064b6
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="statements-expressions-and-operators-c-programming-guide"></a><span data-ttu-id="65a3b-102">Anweisungen, Ausdrücke und Operatoren (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="65a3b-102">Statements, Expressions, and Operators (C# Programming Guide)</span></span>
<span data-ttu-id="65a3b-103">Der C#-Code, der eine Anwendung umfasst, besteht aus Anweisungen, die aus Schlüsselwörtern, Ausdrücken und Operatoren bestehen.</span><span class="sxs-lookup"><span data-stu-id="65a3b-103">The C# code that comprises an application consists of statements made up of keywords, expressions and operators.</span></span> <span data-ttu-id="65a3b-104">Dieser Abschnitt enthält Informationen bezüglich dieser wichtigen Elemente eines C#-Programms.</span><span class="sxs-lookup"><span data-stu-id="65a3b-104">This section contains information regarding these fundamental elements of a C# program.</span></span>  
  
 <span data-ttu-id="65a3b-105">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="65a3b-105">For more information, see:</span></span>  
  
-   [<span data-ttu-id="65a3b-106">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="65a3b-106">Statements</span></span>](../../../csharp/programming-guide/statements-expressions-operators/statements.md)  
  
-   [<span data-ttu-id="65a3b-107">Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="65a3b-107">Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/expressions.md)  
  
    -   [<span data-ttu-id="65a3b-108">Ausdruckskörpermember</span><span class="sxs-lookup"><span data-stu-id="65a3b-108">Expression-bodied members</span></span>](expression-bodied-members.md)
 
-   [<span data-ttu-id="65a3b-109">Operatoren</span><span class="sxs-lookup"><span data-stu-id="65a3b-109">Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
-   [<span data-ttu-id="65a3b-110">Anonyme Funktionen</span><span class="sxs-lookup"><span data-stu-id="65a3b-110">Anonymous Functions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)  
  
-   [<span data-ttu-id="65a3b-111">Überladbare Operatoren</span><span class="sxs-lookup"><span data-stu-id="65a3b-111">Overloadable Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)  
  
-   [<span data-ttu-id="65a3b-112">Konvertierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="65a3b-112">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)  
  
    -   [<span data-ttu-id="65a3b-113">Verwenden von Konvertierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="65a3b-113">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
    -   [<span data-ttu-id="65a3b-114">Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen</span><span class="sxs-lookup"><span data-stu-id="65a3b-114">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="65a3b-115">Gewusst wie: Verwenden der Operatorüberladung zum Erstellen einer Klasse für komplexe Zahlen</span><span class="sxs-lookup"><span data-stu-id="65a3b-115">How to: Use Operator Overloading to Create a Complex Number Class</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-operator-overloading-to-create-a-complex-number-class.md)  
  
-   [<span data-ttu-id="65a3b-116">Übereinstimmungsvergleiche</span><span class="sxs-lookup"><span data-stu-id="65a3b-116">Equality Comparisons</span></span>](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="65a3b-117">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="65a3b-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="65a3b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65a3b-118">See Also</span></span>  
 <span data-ttu-id="65a3b-119">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="65a3b-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="65a3b-120">Umwandlung und Typkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="65a3b-120">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)

