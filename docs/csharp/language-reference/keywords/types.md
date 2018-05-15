---
title: Typen (C#-Referenz)
ms.date: 07/20/2015
helpviewer_keywords:
- types [C#]
- data types [C#], type system
ms.assetid: 16b984df-f417-4e02-b1e6-4589d4a614ea
ms.openlocfilehash: d0fe09092b438af90658d599b6a5e63cb62af580
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="types-c-reference"></a><span data-ttu-id="ea9c7-102">Typen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ea9c7-102">Types (C# Reference)</span></span>
<span data-ttu-id="ea9c7-103">Das C#-Typensystem enthält die folgenden Kategorien:</span><span class="sxs-lookup"><span data-stu-id="ea9c7-103">The C# typing system contains the following categories:</span></span>  
  
-   [<span data-ttu-id="ea9c7-104">Werttypen</span><span class="sxs-lookup"><span data-stu-id="ea9c7-104">Value types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
  
-   [<span data-ttu-id="ea9c7-105">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="ea9c7-105">Reference types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
  
-   [<span data-ttu-id="ea9c7-106">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="ea9c7-106">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
  
 <span data-ttu-id="ea9c7-107">Variablen, die Werttypen sind speichern Daten, und solche, die Verweistypen sind, verweisen auf die tatsächlichen Daten.</span><span class="sxs-lookup"><span data-stu-id="ea9c7-107">Variables that are value types store data, and those that are reference types store references to the actual data.</span></span> <span data-ttu-id="ea9c7-108">Verweistypen werden auch als Objekte bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ea9c7-108">Reference types are also referred to as objects.</span></span> <span data-ttu-id="ea9c7-109">Zeigertypen können nur im [unsafe](../../../csharp/language-reference/keywords/unsafe.md)-Modus genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="ea9c7-109">Pointer types can be used only in [unsafe](../../../csharp/language-reference/keywords/unsafe.md) mode.</span></span>  
  
 <span data-ttu-id="ea9c7-110">Es ist möglich, einen Werttyp in einen Verweistyp zu konvertieren und wieder zurück in einen Werttyp, mithilfe von [Boxing und Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span><span class="sxs-lookup"><span data-stu-id="ea9c7-110">It is possible to convert a value type to a reference type, and back again to a value type, by using [boxing and unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span> <span data-ttu-id="ea9c7-111">Mit Ausnahme eines geschachtelten Werttyps, können Verweistypen nicht in einen Werttyp konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="ea9c7-111">With the exception of a boxed value type, you cannot convert a reference type to a value type.</span></span>  
  
 <span data-ttu-id="ea9c7-112">Dieser Abschnitt beschreibt auch den [void](../../../csharp/language-reference/keywords/void.md)-Datentyp:</span><span class="sxs-lookup"><span data-stu-id="ea9c7-112">This section also introduces [void](../../../csharp/language-reference/keywords/void.md).</span></span>  
  
 <span data-ttu-id="ea9c7-113">Werttypen sind auch NULL-Werte, d.h. sie können einen zusätzlichen Zustand ohne Wert speichern.</span><span class="sxs-lookup"><span data-stu-id="ea9c7-113">Value types are also nullable, which means they can store an additional non-value state.</span></span> <span data-ttu-id="ea9c7-114">Weitere Informationen finden Sie unter [Nullable-Typen](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="ea9c7-114">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea9c7-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea9c7-115">See Also</span></span>  
 [<span data-ttu-id="ea9c7-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ea9c7-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ea9c7-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ea9c7-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ea9c7-118">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ea9c7-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="ea9c7-119">Referenztabellen für Typen</span><span class="sxs-lookup"><span data-stu-id="ea9c7-119">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)  
 [<span data-ttu-id="ea9c7-120">Umwandlung und Typkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="ea9c7-120">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
 [<span data-ttu-id="ea9c7-121">Typen</span><span class="sxs-lookup"><span data-stu-id="ea9c7-121">Types</span></span>](../../../csharp/programming-guide/types/index.md)
