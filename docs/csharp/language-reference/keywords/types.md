---
title: Typen (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- types [C#]
- data types [C#], type system
ms.assetid: 16b984df-f417-4e02-b1e6-4589d4a614ea
caps.latest.revision: 13
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
ms.openlocfilehash: 2816a5dd86e71641198a340b3a72094dffc93bdf
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="types-c-reference"></a><span data-ttu-id="5dc99-102">Typen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="5dc99-102">Types (C# Reference)</span></span>
<span data-ttu-id="5dc99-103">Das C#-Typensystem enthält die folgenden Kategorien:</span><span class="sxs-lookup"><span data-stu-id="5dc99-103">The C# typing system contains the following categories:</span></span>  
  
-   [<span data-ttu-id="5dc99-104">Werttypen</span><span class="sxs-lookup"><span data-stu-id="5dc99-104">Value types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
  
-   [<span data-ttu-id="5dc99-105">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="5dc99-105">Reference types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
  
-   [<span data-ttu-id="5dc99-106">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="5dc99-106">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
  
 <span data-ttu-id="5dc99-107">Variablen, die Werttypen sind speichern Daten, und solche, die Verweistypen sind, verweisen auf die tatsächlichen Daten.</span><span class="sxs-lookup"><span data-stu-id="5dc99-107">Variables that are value types store data, and those that are reference types store references to the actual data.</span></span> <span data-ttu-id="5dc99-108">Verweistypen werden auch als Objekte bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="5dc99-108">Reference types are also referred to as objects.</span></span> <span data-ttu-id="5dc99-109">Zeigertypen können nur im [unsafe](../../../csharp/language-reference/keywords/unsafe.md)-Modus genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="5dc99-109">Pointer types can be used only in [unsafe](../../../csharp/language-reference/keywords/unsafe.md) mode.</span></span>  
  
 <span data-ttu-id="5dc99-110">Es ist möglich, einen Werttyp in einen Verweistyp zu konvertieren und wieder zurück in einen Werttyp, mithilfe von [Boxing und Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span><span class="sxs-lookup"><span data-stu-id="5dc99-110">It is possible to convert a value type to a reference type, and back again to a value type, by using [boxing and unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span> <span data-ttu-id="5dc99-111">Mit Ausnahme eines geschachtelten Werttyps, können Verweistypen nicht in einen Werttyp konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="5dc99-111">With the exception of a boxed value type, you cannot convert a reference type to a value type.</span></span>  
  
 <span data-ttu-id="5dc99-112">Dieser Abschnitt beschreibt auch den [void](../../../csharp/language-reference/keywords/void.md)-Datentyp:</span><span class="sxs-lookup"><span data-stu-id="5dc99-112">This section also introduces [void](../../../csharp/language-reference/keywords/void.md).</span></span>  
  
 <span data-ttu-id="5dc99-113">Werttypen sind auch NULL-Werte, d.h. sie können einen zusätzlichen Zustand ohne Wert speichern.</span><span class="sxs-lookup"><span data-stu-id="5dc99-113">Value types are also nullable, which means they can store an additional non-value state.</span></span> <span data-ttu-id="5dc99-114">Weitere Informationen finden Sie unter [Nullable-Typen](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="5dc99-114">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dc99-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5dc99-115">See Also</span></span>  
 <span data-ttu-id="5dc99-116">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="5dc99-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="5dc99-117">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5dc99-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5dc99-118">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="5dc99-118">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="5dc99-119">[Referenztabellen für Typen](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span><span class="sxs-lookup"><span data-stu-id="5dc99-119">[Reference Tables for Types](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span></span>  
 <span data-ttu-id="5dc99-120">[Umwandlung und Typkonvertierungen](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="5dc99-120">[Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span></span>  
 [<span data-ttu-id="5dc99-121">Typen</span><span class="sxs-lookup"><span data-stu-id="5dc99-121">Types</span></span>](../../../csharp/programming-guide/types/index.md)

