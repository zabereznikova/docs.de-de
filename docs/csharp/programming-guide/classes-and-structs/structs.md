---
title: Strukturen – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: 609169d4624802f679f9661b7aa0596403cc48e7
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261619"
---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="b7dd2-102">Strukturen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b7dd2-102">Structs (C# Programming Guide)</span></span>

<span data-ttu-id="b7dd2-103">Strukturen werden mit dem [struct](../../language-reference/keywords/struct.md)-Schlüsselwort definiert, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="b7dd2-103">Structs are defined by using the [struct](../../language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
[!code-csharp[csProgGuideObjects#39](./codesnippet/CSharp/structs_1.cs)]  
  
<span data-ttu-id="b7dd2-104">Strukturen weisen größtenteils die gleiche Syntax wie Klassen auf.</span><span class="sxs-lookup"><span data-stu-id="b7dd2-104">Structs share most of the same syntax as classes.</span></span> <span data-ttu-id="b7dd2-105">Der Name der Struktur muss ein gültiger C#- [Bezeichnername](../inside-a-program/identifier-names.md) sein.</span><span class="sxs-lookup"><span data-stu-id="b7dd2-105">The name of the struct must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span> <span data-ttu-id="b7dd2-106">Strukturen sind auf folgende Weisen eingeschränkter als Klassen:</span><span class="sxs-lookup"><span data-stu-id="b7dd2-106">Structs are more limited than classes in the following ways:</span></span>  
  
- <span data-ttu-id="b7dd2-107">Innerhalb einer Strukturdeklaration können Felder nicht initialisiert werden, außer Sie werden als const oder static deklariert.</span><span class="sxs-lookup"><span data-stu-id="b7dd2-107">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
- <span data-ttu-id="b7dd2-108">Eine Struktur kann keinen Standardkonstruktor (ein Konstruktor ohne Parameter) oder Finalizer deklarieren.</span><span class="sxs-lookup"><span data-stu-id="b7dd2-108">A struct cannot declare a default constructor (a constructor without parameters) or a finalizer.</span></span>  
- <span data-ttu-id="b7dd2-109">Strukturen werden bei Zuweisung kopiert.</span><span class="sxs-lookup"><span data-stu-id="b7dd2-109">Structs are copied on assignment.</span></span> <span data-ttu-id="b7dd2-110">Wenn eine Struktur einer neuen Variable zugewiesen wird, werden alle Daten kopiert, und jede Änderung an der neuen Kopie ändert nicht die Daten für das Original.</span><span class="sxs-lookup"><span data-stu-id="b7dd2-110">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="b7dd2-111">Es ist wichtig, sich das zu merken, wenn Sie mit Sammlungen von Wertetypen wie `Dictionary<string, myStruct>` arbeiten.</span><span class="sxs-lookup"><span data-stu-id="b7dd2-111">This is important to remember when working with collections of value types such as `Dictionary<string, myStruct>`.</span></span>  
- <span data-ttu-id="b7dd2-112">Im Gegensatz zu Klassen, die Verweistypen sind, sind Strukturen Werttypen.</span><span class="sxs-lookup"><span data-stu-id="b7dd2-112">Structs are value types, unlike classes, which are reference types.</span></span>  
- <span data-ttu-id="b7dd2-113">Strukturen können im Gegensatz zu Klassen ohne den Operator `new` instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="b7dd2-113">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
- <span data-ttu-id="b7dd2-114">Strukturen können Konstruktoren deklarieren, die Parameter besitzen.</span><span class="sxs-lookup"><span data-stu-id="b7dd2-114">Structs can declare constructors that have parameters.</span></span> 
- <span data-ttu-id="b7dd2-115">Eine Struktur kann nicht von einer anderen Struktur oder Klasse erben, und sie kann auch nicht die Basis einer Klasse sein.</span><span class="sxs-lookup"><span data-stu-id="b7dd2-115">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="b7dd2-116">Alle Strukturen erben direkt von <xref:System.ValueType>, das von <xref:System.Object> erbt.</span><span class="sxs-lookup"><span data-stu-id="b7dd2-116">All structs inherit directly from <xref:System.ValueType>, which inherits from <xref:System.Object>.</span></span>  
- <span data-ttu-id="b7dd2-117">Eine Struktur kann Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="b7dd2-117">A struct can implement interfaces.</span></span> 
- <span data-ttu-id="b7dd2-118">Eine Struktur kann nicht `null` sein, und eine Strukturvariable kann nicht `null` zugewiesen werden, wenn die Variable nicht als Nullable-Typ deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="b7dd2-118">A struct cannot be `null`, and a struct variable cannot be assigned `null` unless the variable is declared as a nullable type.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="b7dd2-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="b7dd2-119">Related sections</span></span>  

<span data-ttu-id="b7dd2-120">Weitere Informationen finden Sie unter: </span><span class="sxs-lookup"><span data-stu-id="b7dd2-120">For more information:</span></span>  
  
- [<span data-ttu-id="b7dd2-121">Verwenden von Strukturen</span><span class="sxs-lookup"><span data-stu-id="b7dd2-121">Using Structs</span></span>](using-structs.md)
- [<span data-ttu-id="b7dd2-122">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="b7dd2-122">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="b7dd2-123">Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="b7dd2-123">Nullable Types</span></span>](../nullable-types/index.md)
- [<span data-ttu-id="b7dd2-124">Vorgehensweise: Unterschiede zwischen dem Übergeben einer Struktur und dem Übergeben eines Klassenverweises an eine Methode</span><span class="sxs-lookup"><span data-stu-id="b7dd2-124">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method</span></span>](how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)
- [<span data-ttu-id="b7dd2-125">Vorgehensweise: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen</span><span class="sxs-lookup"><span data-stu-id="b7dd2-125">How to: Implement User-Defined Conversions Between Structs</span></span>](../statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)

## <a name="see-also"></a><span data-ttu-id="b7dd2-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7dd2-126">See also</span></span>

- [<span data-ttu-id="b7dd2-127">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b7dd2-127">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b7dd2-128">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="b7dd2-128">Classes and Structs</span></span>](index.md)
- [<span data-ttu-id="b7dd2-129">Klassen</span><span class="sxs-lookup"><span data-stu-id="b7dd2-129">Classes</span></span>](classes.md)
- [<span data-ttu-id="b7dd2-130">Bezeichnernamen</span><span class="sxs-lookup"><span data-stu-id="b7dd2-130">Identifier names</span></span>](../inside-a-program/identifier-names.md)
