---
title: Strukturen (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: ffb5b8da6c72056620cf890f38af4e7a8116ab3e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="d3ba4-102">Strukturen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="d3ba4-102">Structs (C# Programming Guide)</span></span>
<span data-ttu-id="d3ba4-103">Strukturen werden mit dem [struct](../../../csharp/language-reference/keywords/struct.md)-Schlüsselwort definiert, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="d3ba4-103">Structs are defined by using the [struct](../../../csharp/language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]  
  
 <span data-ttu-id="d3ba4-104">Strukturen teilen sich einen großen Teil der Syntax mit Klassen, obwohl Strukturen eingeschränkter als Klassen sind:</span><span class="sxs-lookup"><span data-stu-id="d3ba4-104">Structs share most of the same syntax as classes, although structs are more limited than classes:</span></span>  
  
-   <span data-ttu-id="d3ba4-105">Innerhalb einer Strukturdeklaration können Felder nicht initialisiert werden, außer Sie werden als const oder static deklariert.</span><span class="sxs-lookup"><span data-stu-id="d3ba4-105">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
  
-   <span data-ttu-id="d3ba4-106">Eine Struktur kann keinen Standardkonstruktor (ein Konstruktor ohne Parameter) oder Finalizer deklarieren.</span><span class="sxs-lookup"><span data-stu-id="d3ba4-106">A struct cannot declare a default constructor (a constructor without parameters) or a finalizer.</span></span>  
  
-   <span data-ttu-id="d3ba4-107">Strukturen werden bei Zuweisung kopiert.</span><span class="sxs-lookup"><span data-stu-id="d3ba4-107">Structs are copied on assignment.</span></span> <span data-ttu-id="d3ba4-108">Wenn eine Struktur einer neuen Variable zugewiesen wird, werden alle Daten kopiert, und jede Änderung an der neuen Kopie ändert nicht die Daten für das Original.</span><span class="sxs-lookup"><span data-stu-id="d3ba4-108">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="d3ba4-109">Es ist wichtig, sich das zu merken, wenn Sie mit Auflistungen von Wertetypen wie Dictionary\<string, myStruct> arbeiten.</span><span class="sxs-lookup"><span data-stu-id="d3ba4-109">This is important to remember when working with collections of value types such as Dictionary\<string, myStruct>.</span></span>  
  
-   <span data-ttu-id="d3ba4-110">Strukturen sind Werttypen, und Klassen sind Verweistypen.</span><span class="sxs-lookup"><span data-stu-id="d3ba4-110">Structs are value types and classes are reference types.</span></span>  
  
-   <span data-ttu-id="d3ba4-111">Strukturen können im Gegensatz zu Klassen ohne den Operator `new` instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="d3ba4-111">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
  
-   <span data-ttu-id="d3ba4-112">Strukturen können Konstruktoren deklarieren, die Parameter besitzen.</span><span class="sxs-lookup"><span data-stu-id="d3ba4-112">Structs can declare constructors that have parameters.</span></span>  
  
-   <span data-ttu-id="d3ba4-113">Eine Struktur kann nicht von einer anderen Struktur oder Klasse erben, und sie kann auch nicht die Basis einer Klasse sein.</span><span class="sxs-lookup"><span data-stu-id="d3ba4-113">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="d3ba4-114">Alle Strukturen erben direkt von `System.ValueType`, das von `System.Object` erbt.</span><span class="sxs-lookup"><span data-stu-id="d3ba4-114">All structs inherit directly from `System.ValueType`, which inherits from `System.Object`.</span></span>  
  
-   <span data-ttu-id="d3ba4-115">Eine Struktur kann Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="d3ba4-115">A struct can implement interfaces.</span></span>  
  
-   <span data-ttu-id="d3ba4-116">Eine Struktur kann als ein Nullable-Typ verwendet werden und kann einen NULL-Wert zugewiesen bekommen.</span><span class="sxs-lookup"><span data-stu-id="d3ba4-116">A struct can be used as a nullable type and can be assigned a null value.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d3ba4-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="d3ba4-117">Related Sections</span></span>  
 <span data-ttu-id="d3ba4-118">Weitere Informationen finden Sie unter: </span><span class="sxs-lookup"><span data-stu-id="d3ba4-118">For more information:</span></span>  
  
-   [<span data-ttu-id="d3ba4-119">Verwenden von Strukturen</span><span class="sxs-lookup"><span data-stu-id="d3ba4-119">Using Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/using-structs.md)  
  
-   [<span data-ttu-id="d3ba4-120">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="d3ba4-120">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [<span data-ttu-id="d3ba4-121">Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="d3ba4-121">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
  
-   [<span data-ttu-id="d3ba4-122">Gewusst wie: Unterschiede zwischen dem Übergeben einer Struktur und dem Übergeben eines Klassenverweises an eine Methode</span><span class="sxs-lookup"><span data-stu-id="d3ba4-122">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)  
  
-   [<span data-ttu-id="d3ba4-123">Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen</span><span class="sxs-lookup"><span data-stu-id="d3ba4-123">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
## <a name="see-also"></a><span data-ttu-id="d3ba4-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3ba4-124">See Also</span></span>  
 [<span data-ttu-id="d3ba4-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d3ba4-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d3ba4-126">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="d3ba4-126">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="d3ba4-127">Klassen</span><span class="sxs-lookup"><span data-stu-id="d3ba4-127">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)
