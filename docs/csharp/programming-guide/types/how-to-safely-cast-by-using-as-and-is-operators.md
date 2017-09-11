---
title: 'Gewusst wie: Sichere Umwandlung mit den Operatoren "as" und "is" (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- cast operators [C#], as and is operators
- as operator [C#]
- is operator [C#]
ms.assetid: c1176cea-1426-4a44-8570-3eadafa58863
caps.latest.revision: 10
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
ms.openlocfilehash: c5daa8525f45c123dabb0f59dfd29385b9e50354
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-safely-cast-by-using-as-and-is-operators-c-programming-guide"></a><span data-ttu-id="0c52d-102">Gewusst wie: Sichere Umwandlung mit den Operatoren "as" und "is" (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="0c52d-102">How to: Safely Cast by Using as and is Operators (C# Programming Guide)</span></span>
<span data-ttu-id="0c52d-103">Da Objekte polymorph sind, ist es möglich, dass eine Variable eines Basisklassentyps einen abgeleiteten Typ enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="0c52d-103">Because objects are polymorphic, it is possible for a variable of a base class type to hold a derived type.</span></span> <span data-ttu-id="0c52d-104">Um auf die Methode des abgeleiteten Typ zuzugreifen, ist es erforderlich, dass Sie den Wert wieder in den abgeleiteten Typ umwandeln.</span><span class="sxs-lookup"><span data-stu-id="0c52d-104">To access the derived type's method, it is necessary to cast the value back to the derived type.</span></span> <span data-ttu-id="0c52d-105">Wenn Sie allerdings in diesen Fällen eine Umwandlung durchführen, besteht das Risiko, dass Sie eine <xref:System.InvalidCastException> auslösen.</span><span class="sxs-lookup"><span data-stu-id="0c52d-105">However, to attempt a simple cast in these cases creates the risk of throwing an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="0c52d-106">Deshalb bietet C# die Operatoren [is](../../../csharp/language-reference/keywords/is.md) und [as](../../../csharp/language-reference/keywords/as.md).</span><span class="sxs-lookup"><span data-stu-id="0c52d-106">That is why C# provides the [is](../../../csharp/language-reference/keywords/is.md) and [as](../../../csharp/language-reference/keywords/as.md) operators.</span></span> <span data-ttu-id="0c52d-107">Sie können diese Operatoren verwenden, um zu prüfen, ob eine Umwandlung erfolgreich durchgeführt werden kann, ohne dass eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="0c52d-107">You can use these operators to test whether a cast will succeed without causing an exception to be thrown.</span></span> <span data-ttu-id="0c52d-108">Für gewöhnlich ist der `as`-Operator effizienter, da er den Umwandlungswert zurückgibt, wenn die Umwandlung erfolgreich durchgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0c52d-108">In general, the `as` operator is more efficient because it actually returns the cast value if the cast can be made successfully.</span></span> <span data-ttu-id="0c52d-109">Der `is`-Operator gibt einen booleschen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="0c52d-109">The `is` operator returns only a Boolean value.</span></span> <span data-ttu-id="0c52d-110">Er kann deshalb verwendet werden, wenn Sie nur den Typ eines Objekts bestimmen wollen, ihn aber nicht tatsächlich umwandeln müssen.</span><span class="sxs-lookup"><span data-stu-id="0c52d-110">It can therefore be used when you just want to determine an object's type but do not have to actually cast it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c52d-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0c52d-111">Example</span></span>  
 <span data-ttu-id="0c52d-112">Im folgenden Beispiel wird gezeigt, wie Sie die Operatoren `is` und `as` verwenden können, um einen Verweistyp in einen anderen umzuwandeln, ohne dass das Risiko besteht, dass eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="0c52d-112">The following examples show how to use the `is` and `as` operators to cast from one reference type to another without the risk of throwing an exception.</span></span> <span data-ttu-id="0c52d-113">In diesem Beispiel wird auch gezeigt, wie Sie den `as`-Operator mit einem auf NULL festlegbaren Werttyp verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0c52d-113">The example also shows how to use the `as` operator with nullable value types.</span></span>  
  
 <span data-ttu-id="0c52d-114">[!code-cs[csProgGuideTypes#40](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-safely-cast-by-using-as-and-is-operators_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0c52d-114">[!code-cs[csProgGuideTypes#40](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-safely-cast-by-using-as-and-is-operators_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c52d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c52d-115">See Also</span></span>  
 <span data-ttu-id="0c52d-116">[Typen](../../../csharp/programming-guide/types/index.md) </span><span class="sxs-lookup"><span data-stu-id="0c52d-116">[Types](../../../csharp/programming-guide/types/index.md) </span></span>  
 <span data-ttu-id="0c52d-117">[Umwandlung und Typkonvertierungen](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="0c52d-117">[Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span></span>  
 [<span data-ttu-id="0c52d-118">Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="0c52d-118">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)

