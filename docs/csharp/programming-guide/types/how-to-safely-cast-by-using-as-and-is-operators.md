---
title: 'Gewusst wie: Sichere Umwandlung mit den Operatoren "as" und "is" (C#-Programmierhandbuch)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- cast operators [C#], as and is operators
- as operator [C#]
- is operator [C#]
ms.assetid: c1176cea-1426-4a44-8570-3eadafa58863
caps.latest.revision: "10"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 733b67408997feb0e518db327e3eedd42f286a99
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-safely-cast-by-using-as-and-is-operators-c-programming-guide"></a><span data-ttu-id="e2641-102">Gewusst wie: Sichere Umwandlung mit den Operatoren "as" und "is" (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="e2641-102">How to: Safely Cast by Using as and is Operators (C# Programming Guide)</span></span>
<span data-ttu-id="e2641-103">Da Objekte polymorph sind, ist es möglich, dass eine Variable eines Basisklassentyps einen abgeleiteten Typ enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="e2641-103">Because objects are polymorphic, it is possible for a variable of a base class type to hold a derived type.</span></span> <span data-ttu-id="e2641-104">Um auf die Methode des abgeleiteten Typ zuzugreifen, ist es erforderlich, dass Sie den Wert wieder in den abgeleiteten Typ umwandeln.</span><span class="sxs-lookup"><span data-stu-id="e2641-104">To access the derived type's method, it is necessary to cast the value back to the derived type.</span></span> <span data-ttu-id="e2641-105">Wenn Sie allerdings in diesen Fällen eine Umwandlung durchführen, besteht das Risiko, dass Sie eine <xref:System.InvalidCastException> auslösen.</span><span class="sxs-lookup"><span data-stu-id="e2641-105">However, to attempt a simple cast in these cases creates the risk of throwing an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="e2641-106">Deshalb bietet C# die Operatoren [is](../../../csharp/language-reference/keywords/is.md) und [as](../../../csharp/language-reference/keywords/as.md).</span><span class="sxs-lookup"><span data-stu-id="e2641-106">That is why C# provides the [is](../../../csharp/language-reference/keywords/is.md) and [as](../../../csharp/language-reference/keywords/as.md) operators.</span></span> <span data-ttu-id="e2641-107">Sie können diese Operatoren verwenden, um zu prüfen, ob eine Umwandlung erfolgreich durchgeführt werden kann, ohne dass eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e2641-107">You can use these operators to test whether a cast will succeed without causing an exception to be thrown.</span></span> <span data-ttu-id="e2641-108">Für gewöhnlich ist der `as`-Operator effizienter, da er den Umwandlungswert zurückgibt, wenn die Umwandlung erfolgreich durchgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e2641-108">In general, the `as` operator is more efficient because it actually returns the cast value if the cast can be made successfully.</span></span> <span data-ttu-id="e2641-109">Der `is`-Operator gibt einen booleschen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="e2641-109">The `is` operator returns only a Boolean value.</span></span> <span data-ttu-id="e2641-110">Er kann deshalb verwendet werden, wenn Sie nur den Typ eines Objekts bestimmen wollen, ihn aber nicht tatsächlich umwandeln müssen.</span><span class="sxs-lookup"><span data-stu-id="e2641-110">It can therefore be used when you just want to determine an object's type but do not have to actually cast it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2641-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e2641-111">Example</span></span>  
 <span data-ttu-id="e2641-112">Im folgenden Beispiel wird gezeigt, wie Sie die Operatoren `is` und `as` verwenden können, um einen Verweistyp in einen anderen umzuwandeln, ohne dass das Risiko besteht, dass eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e2641-112">The following examples show how to use the `is` and `as` operators to cast from one reference type to another without the risk of throwing an exception.</span></span> <span data-ttu-id="e2641-113">In diesem Beispiel wird auch gezeigt, wie Sie den `as`-Operator mit einem auf NULL festlegbaren Werttyp verwenden können.</span><span class="sxs-lookup"><span data-stu-id="e2641-113">The example also shows how to use the `as` operator with nullable value types.</span></span>  
  
 [!code-csharp[csProgGuideTypes#40](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-safely-cast-by-using-as-and-is-operators_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="e2641-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2641-114">See Also</span></span>  
 [<span data-ttu-id="e2641-115">Typen</span><span class="sxs-lookup"><span data-stu-id="e2641-115">Types</span></span>](../../../csharp/programming-guide/types/index.md)  
 [<span data-ttu-id="e2641-116">Umwandlung und Typkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="e2641-116">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
 [<span data-ttu-id="e2641-117">Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="e2641-117">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)
