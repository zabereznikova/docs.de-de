---
title: 'Vorgehensweise: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- user-defined conversions [C#]
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
ms.openlocfilehash: 4b38271c1aaf582c8c58b7198765b679cdfe4881
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499563"
---
# <a name="how-to-implement-user-defined-conversions-between-structs-c-programming-guide"></a><span data-ttu-id="2bb37-102">Vorgehensweise: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="2bb37-102">How to: Implement User-Defined Conversions Between Structs (C# Programming Guide)</span></span>
<span data-ttu-id="2bb37-103">Dieses Beispiel definiert zwei Strukturen, `RomanNumeral` und `BinaryNumeral`, und zeigt Konvertierungen zwischen diesen.</span><span class="sxs-lookup"><span data-stu-id="2bb37-103">This example defines two structs, `RomanNumeral` and `BinaryNumeral`, and demonstrates conversions between them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bb37-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2bb37-104">Example</span></span>  
 [!code-csharp[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="2bb37-105">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="2bb37-105">Robust Programming</span></span>  
  
-   <span data-ttu-id="2bb37-106">Im vorherigen Beispiel führt die Anweisung</span><span class="sxs-lookup"><span data-stu-id="2bb37-106">In the previous example, the statement:</span></span>  
  
     [!code-csharp[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]  
  
     <span data-ttu-id="2bb37-107">führt eine Konvertierung von `RomanNumeral` zu `BinaryNumeral` durch.</span><span class="sxs-lookup"><span data-stu-id="2bb37-107">performs a conversion from a `RomanNumeral` to a `BinaryNumeral`.</span></span> <span data-ttu-id="2bb37-108">Da es keine direkte Konvertierung von `RomanNumeral` zu `BinaryNumeral` gibt, wird eine Umwandlung für die Konvertierung von `RomanNumeral` zu `int` verwendet, und eine weitere Umwandlung zum Konvertieren von `int` zu `BinaryNumeral`.</span><span class="sxs-lookup"><span data-stu-id="2bb37-108">Because there is no direct conversion from `RomanNumeral` to `BinaryNumeral`, a cast is used to convert from a `RomanNumeral` to an `int`, and another cast to convert from an `int` to a `BinaryNumeral`.</span></span>  
  
-   <span data-ttu-id="2bb37-109">Die Anweisung</span><span class="sxs-lookup"><span data-stu-id="2bb37-109">Also the statement</span></span>  
  
     [!code-csharp[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]  
  
     <span data-ttu-id="2bb37-110">führt eine Konvertierung von `BinaryNumeral` zu `RomanNumeral` durch.</span><span class="sxs-lookup"><span data-stu-id="2bb37-110">performs a conversion from a `BinaryNumeral` to a `RomanNumeral`.</span></span> <span data-ttu-id="2bb37-111">Da `RomanNumeral` eine implizierte Konvertierung von `BinaryNumeral` definiert, ist keine Umwandlung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2bb37-111">Because `RomanNumeral` defines an implicit conversion from `BinaryNumeral`, no cast is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bb37-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2bb37-112">See also</span></span>

- [<span data-ttu-id="2bb37-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="2bb37-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="2bb37-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2bb37-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="2bb37-115">Konvertierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="2bb37-115">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)
