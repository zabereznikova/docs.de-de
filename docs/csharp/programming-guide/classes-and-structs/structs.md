---
title: Strukturen – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: 3f19d0485939e1923c479c1c9fdeb06572a11e14
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240384"
---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="2af2b-102">Strukturen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="2af2b-102">Structs (C# Programming Guide)</span></span>

<span data-ttu-id="2af2b-103">Strukturen werden mit dem [struct](../../language-reference/keywords/struct.md)-Schlüsselwort definiert, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="2af2b-103">Structs are defined by using the [struct](../../language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
[!code-csharp[csProgGuideObjects#39](./codesnippet/CSharp/structs_1.cs)]  
  
<span data-ttu-id="2af2b-104">Strukturen weisen größtenteils die gleiche Syntax wie Klassen auf.</span><span class="sxs-lookup"><span data-stu-id="2af2b-104">Structs share most of the same syntax as classes.</span></span> <span data-ttu-id="2af2b-105">Der Name der Struktur muss ein gültiger C#- [Bezeichnername](../inside-a-program/identifier-names.md) sein.</span><span class="sxs-lookup"><span data-stu-id="2af2b-105">The name of the struct must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span> <span data-ttu-id="2af2b-106">Strukturen sind auf folgende Weisen eingeschränkter als Klassen:</span><span class="sxs-lookup"><span data-stu-id="2af2b-106">Structs are more limited than classes in the following ways:</span></span>  
  
- <span data-ttu-id="2af2b-107">Innerhalb einer Strukturdeklaration können Felder nicht initialisiert werden, außer Sie werden als const oder static deklariert.</span><span class="sxs-lookup"><span data-stu-id="2af2b-107">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
- <span data-ttu-id="2af2b-108">Eine Struktur kann keinen Standardkonstruktor (ein Konstruktor ohne Parameter) oder Finalizer deklarieren.</span><span class="sxs-lookup"><span data-stu-id="2af2b-108">A struct cannot declare a default constructor (a constructor without parameters) or a finalizer.</span></span>  
- <span data-ttu-id="2af2b-109">Strukturen werden bei Zuweisung kopiert.</span><span class="sxs-lookup"><span data-stu-id="2af2b-109">Structs are copied on assignment.</span></span> <span data-ttu-id="2af2b-110">Wenn eine Struktur einer neuen Variable zugewiesen wird, werden alle Daten kopiert, und jede Änderung an der neuen Kopie ändert nicht die Daten für das Original.</span><span class="sxs-lookup"><span data-stu-id="2af2b-110">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="2af2b-111">Es ist wichtig, sich das zu merken, wenn Sie mit Sammlungen von Wertetypen wie `Dictionary<string, myStruct>` arbeiten.</span><span class="sxs-lookup"><span data-stu-id="2af2b-111">This is important to remember when working with collections of value types such as `Dictionary<string, myStruct>`.</span></span>  
- <span data-ttu-id="2af2b-112">Im Gegensatz zu Klassen, die Verweistypen sind, sind Strukturen Werttypen.</span><span class="sxs-lookup"><span data-stu-id="2af2b-112">Structs are value types, unlike classes, which are reference types.</span></span>  
- <span data-ttu-id="2af2b-113">Strukturen können im Gegensatz zu Klassen ohne den Operator `new` instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="2af2b-113">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
- <span data-ttu-id="2af2b-114">Strukturen können Konstruktoren deklarieren, die Parameter besitzen.</span><span class="sxs-lookup"><span data-stu-id="2af2b-114">Structs can declare constructors that have parameters.</span></span> 
- <span data-ttu-id="2af2b-115">Eine Struktur kann nicht von einer anderen Struktur oder Klasse erben, und sie kann auch nicht die Basis einer Klasse sein.</span><span class="sxs-lookup"><span data-stu-id="2af2b-115">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="2af2b-116">Alle Strukturen erben direkt von <xref:System.ValueType>, das von <xref:System.Object> erbt.</span><span class="sxs-lookup"><span data-stu-id="2af2b-116">All structs inherit directly from <xref:System.ValueType>, which inherits from <xref:System.Object>.</span></span>  
- <span data-ttu-id="2af2b-117">Eine Struktur kann Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="2af2b-117">A struct can implement interfaces.</span></span>  
- <span data-ttu-id="2af2b-118">Eine Struktur kann als ein Nullable-Typ verwendet werden und kann einen NULL-Wert zugewiesen bekommen.</span><span class="sxs-lookup"><span data-stu-id="2af2b-118">A struct can be used as a nullable type and can be assigned a null value.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2af2b-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="2af2b-119">Related sections</span></span>  

<span data-ttu-id="2af2b-120">Weitere Informationen finden Sie unter: </span><span class="sxs-lookup"><span data-stu-id="2af2b-120">For more information:</span></span>  
  
- [<span data-ttu-id="2af2b-121">Verwenden von Strukturen</span><span class="sxs-lookup"><span data-stu-id="2af2b-121">Using Structs</span></span>](using-structs.md)
- [<span data-ttu-id="2af2b-122">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="2af2b-122">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="2af2b-123">Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="2af2b-123">Nullable Types</span></span>](../nullable-types/index.md)
- [<span data-ttu-id="2af2b-124">Vorgehensweise: Unterschiede zwischen dem Übergeben einer Struktur und dem Übergeben eines Klassenverweises an eine Methode</span><span class="sxs-lookup"><span data-stu-id="2af2b-124">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method</span></span>](how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)
- [<span data-ttu-id="2af2b-125">Vorgehensweise: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen</span><span class="sxs-lookup"><span data-stu-id="2af2b-125">How to: Implement User-Defined Conversions Between Structs</span></span>](../statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)

## <a name="see-also"></a><span data-ttu-id="2af2b-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2af2b-126">See also</span></span>

- [<span data-ttu-id="2af2b-127">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2af2b-127">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="2af2b-128">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="2af2b-128">Classes and Structs</span></span>](index.md)
- [<span data-ttu-id="2af2b-129">Klassen</span><span class="sxs-lookup"><span data-stu-id="2af2b-129">Classes</span></span>](classes.md)
- [<span data-ttu-id="2af2b-130">Bezeichnernamen</span><span class="sxs-lookup"><span data-stu-id="2af2b-130">Identifier names</span></span>](../inside-a-program/identifier-names.md)
