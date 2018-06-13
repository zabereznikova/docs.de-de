---
title: 'Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- user-defined conversions [C#]
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
ms.openlocfilehash: 178d9e2f92c5c1989253a16d866052a1fc42c10e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339929"
---
# <a name="how-to-implement-user-defined-conversions-between-structs-c-programming-guide"></a><span data-ttu-id="d759c-102">Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="d759c-102">How to: Implement User-Defined Conversions Between Structs (C# Programming Guide)</span></span>
<span data-ttu-id="d759c-103">Dieses Beispiel definiert zwei Strukturen, `RomanNumeral` und `BinaryNumeral`, und zeigt Konvertierungen zwischen diesen.</span><span class="sxs-lookup"><span data-stu-id="d759c-103">This example defines two structs, `RomanNumeral` and `BinaryNumeral`, and demonstrates conversions between them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d759c-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d759c-104">Example</span></span>  
 [!code-csharp[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="d759c-105">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="d759c-105">Robust Programming</span></span>  
  
-   <span data-ttu-id="d759c-106">Im vorherigen Beispiel führt die Anweisung</span><span class="sxs-lookup"><span data-stu-id="d759c-106">In the previous example, the statement:</span></span>  
  
     [!code-csharp[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]  
  
     <span data-ttu-id="d759c-107">führt eine Konvertierung von `RomanNumeral` zu `BinaryNumeral` durch.</span><span class="sxs-lookup"><span data-stu-id="d759c-107">performs a conversion from a `RomanNumeral` to a `BinaryNumeral`.</span></span> <span data-ttu-id="d759c-108">Da es keine direkte Konvertierung von `RomanNumeral` zu `BinaryNumeral` gibt, wird eine Umwandlung für die Konvertierung von `RomanNumeral` zu `int` verwendet, und eine weitere Umwandlung zum Konvertieren von `int` zu `BinaryNumeral`.</span><span class="sxs-lookup"><span data-stu-id="d759c-108">Because there is no direct conversion from `RomanNumeral` to `BinaryNumeral`, a cast is used to convert from a `RomanNumeral` to an `int`, and another cast to convert from an `int` to a `BinaryNumeral`.</span></span>  
  
-   <span data-ttu-id="d759c-109">Die Anweisung</span><span class="sxs-lookup"><span data-stu-id="d759c-109">Also the statement</span></span>  
  
     [!code-csharp[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]  
  
     <span data-ttu-id="d759c-110">führt eine Konvertierung von `BinaryNumeral` zu `RomanNumeral` durch.</span><span class="sxs-lookup"><span data-stu-id="d759c-110">performs a conversion from a `BinaryNumeral` to a `RomanNumeral`.</span></span> <span data-ttu-id="d759c-111">Da `RomanNumeral` eine implizierte Konvertierung von `BinaryNumeral` definiert, ist keine Umwandlung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d759c-111">Because `RomanNumeral` defines an implicit conversion from `BinaryNumeral`, no cast is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d759c-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d759c-112">See Also</span></span>  
 [<span data-ttu-id="d759c-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="d759c-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d759c-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d759c-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d759c-115">Konvertierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="d759c-115">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)
