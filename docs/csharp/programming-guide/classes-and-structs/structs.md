---
title: Strukturen (C#-Programmierhandbuch)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
caps.latest.revision: "31"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 475d9b96e078270faf6c841a62e6031556e8e539
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="f4602-102">Strukturen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="f4602-102">Structs (C# Programming Guide)</span></span>
<span data-ttu-id="f4602-103">Strukturen werden mit dem [struct](../../../csharp/language-reference/keywords/struct.md)-Schlüsselwort definiert, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="f4602-103">Structs are defined by using the [struct](../../../csharp/language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]  
  
 <span data-ttu-id="f4602-104">Strukturen teilen sich einen großen Teil der Syntax mit Klassen, obwohl Strukturen eingeschränkter als Klassen sind:</span><span class="sxs-lookup"><span data-stu-id="f4602-104">Structs share most of the same syntax as classes, although structs are more limited than classes:</span></span>  
  
-   <span data-ttu-id="f4602-105">Innerhalb einer Strukturdeklaration können Felder nicht initialisiert werden, außer Sie werden als const oder static deklariert.</span><span class="sxs-lookup"><span data-stu-id="f4602-105">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
  
-   <span data-ttu-id="f4602-106">Eine Struktur kann keinen Standardkonstruktor (ein Konstruktor ohne Parameter) oder Finalizer deklarieren.</span><span class="sxs-lookup"><span data-stu-id="f4602-106">A struct cannot declare a default constructor (a constructor without parameters) or a finalizer.</span></span>  
  
-   <span data-ttu-id="f4602-107">Strukturen werden bei Zuweisung kopiert.</span><span class="sxs-lookup"><span data-stu-id="f4602-107">Structs are copied on assignment.</span></span> <span data-ttu-id="f4602-108">Wenn eine Struktur einer neuen Variable zugewiesen wird, werden alle Daten kopiert, und jede Änderung an der neuen Kopie ändert nicht die Daten für das Original.</span><span class="sxs-lookup"><span data-stu-id="f4602-108">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="f4602-109">Es ist wichtig, sich das zu merken, wenn Sie mit Auflistungen von Wertetypen wie Dictionary\<string, myStruct> arbeiten.</span><span class="sxs-lookup"><span data-stu-id="f4602-109">This is important to remember when working with collections of value types such as Dictionary\<string, myStruct>.</span></span>  
  
-   <span data-ttu-id="f4602-110">Strukturen sind Werttypen, und Klassen sind Verweistypen.</span><span class="sxs-lookup"><span data-stu-id="f4602-110">Structs are value types and classes are reference types.</span></span>  
  
-   <span data-ttu-id="f4602-111">Strukturen können im Gegensatz zu Klassen ohne den Operator `new` instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="f4602-111">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
  
-   <span data-ttu-id="f4602-112">Strukturen können Konstruktoren deklarieren, die Parameter besitzen.</span><span class="sxs-lookup"><span data-stu-id="f4602-112">Structs can declare constructors that have parameters.</span></span>  
  
-   <span data-ttu-id="f4602-113">Eine Struktur kann nicht von einer anderen Struktur oder Klasse erben, und sie kann auch nicht die Basis einer Klasse sein.</span><span class="sxs-lookup"><span data-stu-id="f4602-113">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="f4602-114">Alle Strukturen erben direkt von `System.ValueType`, das von `System.Object` erbt.</span><span class="sxs-lookup"><span data-stu-id="f4602-114">All structs inherit directly from `System.ValueType`, which inherits from `System.Object`.</span></span>  
  
-   <span data-ttu-id="f4602-115">Eine Struktur kann Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="f4602-115">A struct can implement interfaces.</span></span>  
  
-   <span data-ttu-id="f4602-116">Eine Struktur kann als ein Nullable-Typ verwendet werden und kann einen NULL-Wert zugewiesen bekommen.</span><span class="sxs-lookup"><span data-stu-id="f4602-116">A struct can be used as a nullable type and can be assigned a null value.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f4602-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="f4602-117">Related Sections</span></span>  
 <span data-ttu-id="f4602-118">Weitere Informationen finden Sie unter: </span><span class="sxs-lookup"><span data-stu-id="f4602-118">For more information:</span></span>  
  
-   [<span data-ttu-id="f4602-119">Verwenden von Strukturen</span><span class="sxs-lookup"><span data-stu-id="f4602-119">Using Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/using-structs.md)  
  
-   [<span data-ttu-id="f4602-120">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="f4602-120">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [<span data-ttu-id="f4602-121">Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="f4602-121">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
  
-   [<span data-ttu-id="f4602-122">Gewusst wie: Unterschiede zwischen dem Übergeben einer Struktur und dem Übergeben eines Klassenverweises an eine Methode</span><span class="sxs-lookup"><span data-stu-id="f4602-122">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)  
  
-   [<span data-ttu-id="f4602-123">Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen</span><span class="sxs-lookup"><span data-stu-id="f4602-123">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
## <a name="see-also"></a><span data-ttu-id="f4602-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4602-124">See Also</span></span>  
 [<span data-ttu-id="f4602-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f4602-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f4602-126">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="f4602-126">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="f4602-127">Klassen</span><span class="sxs-lookup"><span data-stu-id="f4602-127">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)
