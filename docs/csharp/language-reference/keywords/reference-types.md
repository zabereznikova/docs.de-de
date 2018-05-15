---
title: Verweistypen (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: cca9826c658581be38866410d5f966b1c7c35772
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="8b555-102">Verweistypen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="8b555-102">Reference Types (C# Reference)</span></span>
<span data-ttu-id="8b555-103">Es gibt zwei Arten von Typen in C#: Verweistypen und Werttypen.</span><span class="sxs-lookup"><span data-stu-id="8b555-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="8b555-104">Variablen von Verweistypen speichern Verweise auf ihre Daten (Objekte), während Variablen von Werttypen ihre Daten direkt enthalten.</span><span class="sxs-lookup"><span data-stu-id="8b555-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="8b555-105">Bei Verweistypen können zwei Variablen auf dasselbe Objekt verweisen. Daher können auf eine Variable angewendete Operationen das Objekt beeinflussen, auf das von der anderen Variablen verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="8b555-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="8b555-106">Bei Werttypen besitzt jede Variable eine eigene Kopie der Daten, und auf eine Variable angewendete Operationen können die andere Variable nicht beeinflussen (außer im Fall von ref- und out-Parametervariablen, siehe [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) und [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md)-Parametermodifizierer).</span><span class="sxs-lookup"><span data-stu-id="8b555-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) and [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter modifier).</span></span>  
  
 <span data-ttu-id="8b555-107">Die folgenden Schlüsselwörter werden verwendet, um Verweistypen zu deklarieren:</span><span class="sxs-lookup"><span data-stu-id="8b555-107">The following keywords are used to declare reference types:</span></span>  
  
-   [<span data-ttu-id="8b555-108">class</span><span class="sxs-lookup"><span data-stu-id="8b555-108">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="8b555-109">interface</span><span class="sxs-lookup"><span data-stu-id="8b555-109">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="8b555-110">delegate</span><span class="sxs-lookup"><span data-stu-id="8b555-110">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="8b555-111">C# enthält auch die folgenden integrierten Referenztypen:</span><span class="sxs-lookup"><span data-stu-id="8b555-111">C# also provides the following built-in reference types:</span></span>  
  
-   [<span data-ttu-id="8b555-112">dynamic</span><span class="sxs-lookup"><span data-stu-id="8b555-112">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)  
  
-   [<span data-ttu-id="8b555-113">object</span><span class="sxs-lookup"><span data-stu-id="8b555-113">object</span></span>](../../../csharp/language-reference/keywords/object.md)  
  
-   [<span data-ttu-id="8b555-114">string</span><span class="sxs-lookup"><span data-stu-id="8b555-114">string</span></span>](../../../csharp/language-reference/keywords/string.md)  
  
## <a name="see-also"></a><span data-ttu-id="8b555-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b555-115">See Also</span></span>  
 [<span data-ttu-id="8b555-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="8b555-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8b555-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="8b555-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8b555-118">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8b555-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="8b555-119">Typen</span><span class="sxs-lookup"><span data-stu-id="8b555-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="8b555-120">Werttypen</span><span class="sxs-lookup"><span data-stu-id="8b555-120">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)
