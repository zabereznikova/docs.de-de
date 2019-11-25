---
title: Strukturen – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: 35b39da0b15c41b7b2c7a6567bea5dca3fb430e7
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73970321"
---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="b7181-102">Strukturen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b7181-102">Structs (C# Programming Guide)</span></span>

<span data-ttu-id="b7181-103">Strukturen werden mit dem [struct](../../language-reference/keywords/struct.md)-Schlüsselwort definiert, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="b7181-103">Structs are defined by using the [struct](../../language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#39)]  
  
<span data-ttu-id="b7181-104">Strukturen weisen größtenteils die gleiche Syntax wie Klassen auf.</span><span class="sxs-lookup"><span data-stu-id="b7181-104">Structs share most of the same syntax as classes.</span></span> <span data-ttu-id="b7181-105">Der Name der Struktur muss ein gültiger C#- [Bezeichnername](../inside-a-program/identifier-names.md) sein.</span><span class="sxs-lookup"><span data-stu-id="b7181-105">The name of the struct must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span> <span data-ttu-id="b7181-106">Strukturen sind auf folgende Weisen eingeschränkter als Klassen:</span><span class="sxs-lookup"><span data-stu-id="b7181-106">Structs are more limited than classes in the following ways:</span></span>  
  
- <span data-ttu-id="b7181-107">Innerhalb einer Strukturdeklaration können Felder nicht initialisiert werden, außer Sie werden als const oder static deklariert.</span><span class="sxs-lookup"><span data-stu-id="b7181-107">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
- <span data-ttu-id="b7181-108">Eine Struktur kann keinen parameterlosen Konstruktor (einen Konstruktor ohne Parameter) oder Finalizer deklarieren.</span><span class="sxs-lookup"><span data-stu-id="b7181-108">A struct cannot declare a parameterless constructor (a constructor without parameters) or a finalizer.</span></span>  
- <span data-ttu-id="b7181-109">Strukturen werden bei Zuweisung kopiert.</span><span class="sxs-lookup"><span data-stu-id="b7181-109">Structs are copied on assignment.</span></span> <span data-ttu-id="b7181-110">Wenn eine Struktur einer neuen Variable zugewiesen wird, werden alle Daten kopiert, und jede Änderung an der neuen Kopie ändert nicht die Daten für das Original.</span><span class="sxs-lookup"><span data-stu-id="b7181-110">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="b7181-111">Es ist wichtig, sich das zu merken, wenn Sie mit Sammlungen von Wertetypen wie `Dictionary<string, myStruct>` arbeiten.</span><span class="sxs-lookup"><span data-stu-id="b7181-111">This is important to remember when working with collections of value types such as `Dictionary<string, myStruct>`.</span></span>  
- <span data-ttu-id="b7181-112">Im Gegensatz zu Klassen, die Verweistypen sind, sind Strukturen Werttypen.</span><span class="sxs-lookup"><span data-stu-id="b7181-112">Structs are value types, unlike classes, which are reference types.</span></span>  
- <span data-ttu-id="b7181-113">Strukturen können im Gegensatz zu Klassen ohne den Operator `new` instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="b7181-113">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
- <span data-ttu-id="b7181-114">Strukturen können Konstruktoren deklarieren, die Parameter besitzen.</span><span class="sxs-lookup"><span data-stu-id="b7181-114">Structs can declare constructors that have parameters.</span></span>
- <span data-ttu-id="b7181-115">Eine Struktur kann nicht von einer anderen Struktur oder Klasse erben, und sie kann auch nicht die Basis einer Klasse sein.</span><span class="sxs-lookup"><span data-stu-id="b7181-115">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="b7181-116">Alle Strukturen erben direkt von <xref:System.ValueType>, das von <xref:System.Object> erbt.</span><span class="sxs-lookup"><span data-stu-id="b7181-116">All structs inherit directly from <xref:System.ValueType>, which inherits from <xref:System.Object>.</span></span>  
- <span data-ttu-id="b7181-117">Eine Struktur kann Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="b7181-117">A struct can implement interfaces.</span></span>
- <span data-ttu-id="b7181-118">Eine Struktur kann nicht `null` sein, und eine Strukturvariable kann nicht `null` zugewiesen werden, wenn die Variable nicht als Nullable-Werttyp deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="b7181-118">A struct cannot be `null`, and a struct variable cannot be assigned `null` unless the variable is declared as a nullable value type.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b7181-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7181-119">See also</span></span>

- [<span data-ttu-id="b7181-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b7181-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b7181-121">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="b7181-121">Classes and Structs</span></span>](index.md)
- [<span data-ttu-id="b7181-122">Klassen</span><span class="sxs-lookup"><span data-stu-id="b7181-122">Classes</span></span>](classes.md)
- [<span data-ttu-id="b7181-123">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="b7181-123">Nullable value types</span></span>](../../language-reference/builtin-types/nullable-value-types.md)
- [<span data-ttu-id="b7181-124">Bezeichnernamen</span><span class="sxs-lookup"><span data-stu-id="b7181-124">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="b7181-125">Verwenden von Strukturen</span><span class="sxs-lookup"><span data-stu-id="b7181-125">Using Structs</span></span>](using-structs.md)
- [<span data-ttu-id="b7181-126">Unterschiede zwischen dem Übergeben einer Struktur und dem Übergeben eines Klassenverweises an eine Methode</span><span class="sxs-lookup"><span data-stu-id="b7181-126">How to know the difference between passing a struct and passing a class reference to a method</span></span>](how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)
