---
title: 'Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- user-defined conversions [C#]
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
caps.latest.revision: 11
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
ms.openlocfilehash: cc8856bb3bf8943c1b6648f7d81447a3e59b9489
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-implement-user-defined-conversions-between-structs-c-programming-guide"></a><span data-ttu-id="bf76c-102">Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="bf76c-102">How to: Implement User-Defined Conversions Between Structs (C# Programming Guide)</span></span>
<span data-ttu-id="bf76c-103">Dieses Beispiel definiert zwei Strukturen, `RomanNumeral` und `BinaryNumeral`, und zeigt Konvertierungen zwischen diesen.</span><span class="sxs-lookup"><span data-stu-id="bf76c-103">This example defines two structs, `RomanNumeral` and `BinaryNumeral`, and demonstrates conversions between them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf76c-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bf76c-104">Example</span></span>  
 <span data-ttu-id="bf76c-105">[!code-cs[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bf76c-105">[!code-cs[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="bf76c-106">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="bf76c-106">Robust Programming</span></span>  
  
-   <span data-ttu-id="bf76c-107">Im vorherigen Beispiel führt die Anweisung</span><span class="sxs-lookup"><span data-stu-id="bf76c-107">In the previous example, the statement:</span></span>  
  
     <span data-ttu-id="bf76c-108">[!code-cs[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="bf76c-108">[!code-cs[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]</span></span>  
  
     <span data-ttu-id="bf76c-109">führt eine Konvertierung von `RomanNumeral` zu `BinaryNumeral` durch.</span><span class="sxs-lookup"><span data-stu-id="bf76c-109">performs a conversion from a `RomanNumeral` to a `BinaryNumeral`.</span></span> <span data-ttu-id="bf76c-110">Da es keine direkte Konvertierung von `RomanNumeral` zu `BinaryNumeral` gibt, wird eine Umwandlung für die Konvertierung von `RomanNumeral` zu `int` verwendet, und eine weitere Umwandlung zum Konvertieren von `int` zu `BinaryNumeral`.</span><span class="sxs-lookup"><span data-stu-id="bf76c-110">Because there is no direct conversion from `RomanNumeral` to `BinaryNumeral`, a cast is used to convert from a `RomanNumeral` to an `int`, and another cast to convert from an `int` to a `BinaryNumeral`.</span></span>  
  
-   <span data-ttu-id="bf76c-111">Die Anweisung</span><span class="sxs-lookup"><span data-stu-id="bf76c-111">Also the statement</span></span>  
  
     <span data-ttu-id="bf76c-112">[!code-cs[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="bf76c-112">[!code-cs[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]</span></span>  
  
     <span data-ttu-id="bf76c-113">führt ebenso eine Konvertierung von einem `BinaryNumeral` zu einem `RomanNumeral` durch.</span><span class="sxs-lookup"><span data-stu-id="bf76c-113">performs a conversion from a `BinaryNumeral` to a `RomanNumeral`.</span></span> <span data-ttu-id="bf76c-114">Da `RomanNumeral` eine implizierte Konvertierung von `BinaryNumeral` definiert, ist keine Umwandlung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bf76c-114">Because `RomanNumeral` defines an implicit conversion from `BinaryNumeral`, no cast is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf76c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf76c-115">See Also</span></span>  
 <span data-ttu-id="bf76c-116">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="bf76c-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="bf76c-117">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bf76c-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="bf76c-118">Konvertierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="bf76c-118">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)

