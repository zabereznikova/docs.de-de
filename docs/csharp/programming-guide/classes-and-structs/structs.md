---
title: Strukturen (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
caps.latest.revision: 31
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
ms.openlocfilehash: ce12f402c0748ea6729c82e3f188c0a58f63d628
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="d38ee-102">Strukturen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="d38ee-102">Structs (C# Programming Guide)</span></span>
<span data-ttu-id="d38ee-103">Strukturen werden mit dem [struct](../../../csharp/language-reference/keywords/struct.md)-Schlüsselwort definiert, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="d38ee-103">Structs are defined by using the [struct](../../../csharp/language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
 <span data-ttu-id="d38ee-104">[!code-cs[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d38ee-104">[!code-cs[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]</span></span>  
  
 <span data-ttu-id="d38ee-105">Strukturen teilen sich einen großen Teil der Syntax mit Klassen, obwohl Strukturen eingeschränkter als Klassen sind:</span><span class="sxs-lookup"><span data-stu-id="d38ee-105">Structs share most of the same syntax as classes, although structs are more limited than classes:</span></span>  
  
-   <span data-ttu-id="d38ee-106">Innerhalb einer Strukturdeklaration können Felder nicht initialisiert werden, außer Sie werden als const oder static deklariert.</span><span class="sxs-lookup"><span data-stu-id="d38ee-106">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
  
-   <span data-ttu-id="d38ee-107">Eine Struktur kann keinen Standardkonstruktor (ein Konstruktor ohne Parameter) oder Finalizer deklarieren.</span><span class="sxs-lookup"><span data-stu-id="d38ee-107">A struct cannot declare a default constructor (a constructor without parameters) or a finalizer.</span></span>  
  
-   <span data-ttu-id="d38ee-108">Strukturen werden bei Zuweisung kopiert.</span><span class="sxs-lookup"><span data-stu-id="d38ee-108">Structs are copied on assignment.</span></span> <span data-ttu-id="d38ee-109">Wenn eine Struktur einer neuen Variable zugewiesen wird, werden alle Daten kopiert, und jede Änderung an der neuen Kopie ändert nicht die Daten für das Original.</span><span class="sxs-lookup"><span data-stu-id="d38ee-109">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="d38ee-110">Es ist wichtig, sich das zu merken, wenn Sie mit Auflistungen von Wertetypen wie Dictionary\<string, myStruct> arbeiten.</span><span class="sxs-lookup"><span data-stu-id="d38ee-110">This is important to remember when working with collections of value types such as Dictionary\<string, myStruct>.</span></span>  
  
-   <span data-ttu-id="d38ee-111">Strukturen sind Werttypen, und Klassen sind Verweistypen.</span><span class="sxs-lookup"><span data-stu-id="d38ee-111">Structs are value types and classes are reference types.</span></span>  
  
-   <span data-ttu-id="d38ee-112">Strukturen können im Gegensatz zu Klassen ohne den Operator `new` instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="d38ee-112">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
  
-   <span data-ttu-id="d38ee-113">Strukturen können Konstruktoren deklarieren, die Parameter besitzen.</span><span class="sxs-lookup"><span data-stu-id="d38ee-113">Structs can declare constructors that have parameters.</span></span>  
  
-   <span data-ttu-id="d38ee-114">Eine Struktur kann nicht von einer anderen Struktur oder Klasse erben, und sie kann auch nicht die Basis einer Klasse sein.</span><span class="sxs-lookup"><span data-stu-id="d38ee-114">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="d38ee-115">Alle Strukturen erben direkt von `System.ValueType`, das von `System.Object` erbt.</span><span class="sxs-lookup"><span data-stu-id="d38ee-115">All structs inherit directly from `System.ValueType`, which inherits from `System.Object`.</span></span>  
  
-   <span data-ttu-id="d38ee-116">Eine Struktur kann Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="d38ee-116">A struct can implement interfaces.</span></span>  
  
-   <span data-ttu-id="d38ee-117">Eine Struktur kann als ein Nullable-Typ verwendet werden und kann einen NULL-Wert zugewiesen bekommen.</span><span class="sxs-lookup"><span data-stu-id="d38ee-117">A struct can be used as a nullable type and can be assigned a null value.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d38ee-118">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="d38ee-118">Related Sections</span></span>  
 <span data-ttu-id="d38ee-119">Weitere Informationen finden Sie unter: </span><span class="sxs-lookup"><span data-stu-id="d38ee-119">For more information:</span></span>  
  
-   [<span data-ttu-id="d38ee-120">Verwenden von Strukturen</span><span class="sxs-lookup"><span data-stu-id="d38ee-120">Using Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/using-structs.md)  
  
-   [<span data-ttu-id="d38ee-121">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="d38ee-121">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [<span data-ttu-id="d38ee-122">Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="d38ee-122">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
  
-   [<span data-ttu-id="d38ee-123">Gewusst wie: Unterschiede zwischen dem Übergeben einer Struktur und dem Übergeben eines Klassenverweises an eine Methode</span><span class="sxs-lookup"><span data-stu-id="d38ee-123">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)  
  
-   [<span data-ttu-id="d38ee-124">Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen</span><span class="sxs-lookup"><span data-stu-id="d38ee-124">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
## <a name="see-also"></a><span data-ttu-id="d38ee-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d38ee-125">See Also</span></span>  
 <span data-ttu-id="d38ee-126">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d38ee-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d38ee-127">[Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="d38ee-127">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 [<span data-ttu-id="d38ee-128">Klassen</span><span class="sxs-lookup"><span data-stu-id="d38ee-128">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)

