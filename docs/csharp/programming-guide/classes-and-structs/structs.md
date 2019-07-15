---
title: Strukturen – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: 063d7e3b68fbe6c01ff0df4ae935fec5af6f6891
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743839"
---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="ab680-102">Strukturen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ab680-102">Structs (C# Programming Guide)</span></span>

<span data-ttu-id="ab680-103">Strukturen werden mit dem [struct](../../language-reference/keywords/struct.md)-Schlüsselwort definiert, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="ab680-103">Structs are defined by using the [struct](../../language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#39)]  
  
<span data-ttu-id="ab680-104">Strukturen weisen größtenteils die gleiche Syntax wie Klassen auf.</span><span class="sxs-lookup"><span data-stu-id="ab680-104">Structs share most of the same syntax as classes.</span></span> <span data-ttu-id="ab680-105">Der Name der Struktur muss ein gültiger C#- [Bezeichnername](../inside-a-program/identifier-names.md) sein.</span><span class="sxs-lookup"><span data-stu-id="ab680-105">The name of the struct must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span> <span data-ttu-id="ab680-106">Strukturen sind auf folgende Weisen eingeschränkter als Klassen:</span><span class="sxs-lookup"><span data-stu-id="ab680-106">Structs are more limited than classes in the following ways:</span></span>  
  
- <span data-ttu-id="ab680-107">Innerhalb einer Strukturdeklaration können Felder nicht initialisiert werden, außer Sie werden als const oder static deklariert.</span><span class="sxs-lookup"><span data-stu-id="ab680-107">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
- <span data-ttu-id="ab680-108">Eine Struktur kann keinen parameterlosen Konstruktor (einen Konstruktor ohne Parameter) oder Finalizer deklarieren.</span><span class="sxs-lookup"><span data-stu-id="ab680-108">A struct cannot declare a parameterless constructor (a constructor without parameters) or a finalizer.</span></span>  
- <span data-ttu-id="ab680-109">Strukturen werden bei Zuweisung kopiert.</span><span class="sxs-lookup"><span data-stu-id="ab680-109">Structs are copied on assignment.</span></span> <span data-ttu-id="ab680-110">Wenn eine Struktur einer neuen Variable zugewiesen wird, werden alle Daten kopiert, und jede Änderung an der neuen Kopie ändert nicht die Daten für das Original.</span><span class="sxs-lookup"><span data-stu-id="ab680-110">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="ab680-111">Es ist wichtig, sich das zu merken, wenn Sie mit Sammlungen von Wertetypen wie `Dictionary<string, myStruct>` arbeiten.</span><span class="sxs-lookup"><span data-stu-id="ab680-111">This is important to remember when working with collections of value types such as `Dictionary<string, myStruct>`.</span></span>  
- <span data-ttu-id="ab680-112">Im Gegensatz zu Klassen, die Verweistypen sind, sind Strukturen Werttypen.</span><span class="sxs-lookup"><span data-stu-id="ab680-112">Structs are value types, unlike classes, which are reference types.</span></span>  
- <span data-ttu-id="ab680-113">Strukturen können im Gegensatz zu Klassen ohne den Operator `new` instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="ab680-113">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
- <span data-ttu-id="ab680-114">Strukturen können Konstruktoren deklarieren, die Parameter besitzen.</span><span class="sxs-lookup"><span data-stu-id="ab680-114">Structs can declare constructors that have parameters.</span></span>
- <span data-ttu-id="ab680-115">Eine Struktur kann nicht von einer anderen Struktur oder Klasse erben, und sie kann auch nicht die Basis einer Klasse sein.</span><span class="sxs-lookup"><span data-stu-id="ab680-115">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="ab680-116">Alle Strukturen erben direkt von <xref:System.ValueType>, das von <xref:System.Object> erbt.</span><span class="sxs-lookup"><span data-stu-id="ab680-116">All structs inherit directly from <xref:System.ValueType>, which inherits from <xref:System.Object>.</span></span>  
- <span data-ttu-id="ab680-117">Eine Struktur kann Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="ab680-117">A struct can implement interfaces.</span></span>
- <span data-ttu-id="ab680-118">Eine Struktur kann nicht `null` sein, und eine Strukturvariable kann nicht `null` zugewiesen werden, wenn die Variable nicht als Nullable-Typ deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="ab680-118">A struct cannot be `null`, and a struct variable cannot be assigned `null` unless the variable is declared as a nullable type.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ab680-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab680-119">See also</span></span>

- [<span data-ttu-id="ab680-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ab680-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ab680-121">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="ab680-121">Classes and Structs</span></span>](index.md)
- [<span data-ttu-id="ab680-122">Klassen</span><span class="sxs-lookup"><span data-stu-id="ab680-122">Classes</span></span>](classes.md)
- [<span data-ttu-id="ab680-123">Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="ab680-123">Nullable Types</span></span>](../nullable-types/index.md)
- [<span data-ttu-id="ab680-124">Bezeichnernamen</span><span class="sxs-lookup"><span data-stu-id="ab680-124">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="ab680-125">Verwenden von Strukturen</span><span class="sxs-lookup"><span data-stu-id="ab680-125">Using Structs</span></span>](using-structs.md)
- [<span data-ttu-id="ab680-126">Vorgehensweise: Unterschiede zwischen dem Übergeben einer Struktur und dem Übergeben eines Klassenverweises an eine Methode</span><span class="sxs-lookup"><span data-stu-id="ab680-126">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method</span></span>](how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)
