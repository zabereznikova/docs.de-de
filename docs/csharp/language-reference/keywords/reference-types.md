---
title: Verweistypen (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c4f87363246deccf282b499aa2afee2a14d41593
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="416ba-102">Verweistypen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="416ba-102">Reference Types (C# Reference)</span></span>
<span data-ttu-id="416ba-103">Es gibt zwei Arten von Typen in C#: Verweistypen und Werttypen.</span><span class="sxs-lookup"><span data-stu-id="416ba-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="416ba-104">Variablen von Verweistypen speichern Verweise auf ihre Daten (Objekte), während Variablen von Werttypen ihre Daten direkt enthalten.</span><span class="sxs-lookup"><span data-stu-id="416ba-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="416ba-105">Bei Verweistypen können zwei Variablen auf dasselbe Objekt verweisen. Daher können auf eine Variable angewendete Operationen das Objekt beeinflussen, auf das von der anderen Variablen verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="416ba-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="416ba-106">Bei Werttypen besitzt jede Variable eine eigene Kopie der Daten, und auf eine Variable angewendete Operationen können die andere Variable nicht beeinflussen (außer im Fall von ref-Parametervariablen und out-Parametervariablen, siehe [ref](../../../csharp/language-reference/keywords/ref.md) und [Modifizierer für out-Parameter](../../../csharp/language-reference/keywords/out-parameter-modifier.md)).</span><span class="sxs-lookup"><span data-stu-id="416ba-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of ref and out parameter variables, see [ref](../../../csharp/language-reference/keywords/ref.md) and [out parameter modifier](../../../csharp/language-reference/keywords/out-parameter-modifier.md)).</span></span>  
  
 <span data-ttu-id="416ba-107">Die folgenden Schlüsselwörter werden verwendet, um Verweistypen zu deklarieren:</span><span class="sxs-lookup"><span data-stu-id="416ba-107">The following keywords are used to declare reference types:</span></span>  
  
-   [<span data-ttu-id="416ba-108">class</span><span class="sxs-lookup"><span data-stu-id="416ba-108">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="416ba-109">interface</span><span class="sxs-lookup"><span data-stu-id="416ba-109">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="416ba-110">delegate</span><span class="sxs-lookup"><span data-stu-id="416ba-110">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="416ba-111">C# enthält auch die folgenden integrierten Referenztypen:</span><span class="sxs-lookup"><span data-stu-id="416ba-111">C# also provides the following built-in reference types:</span></span>  
  
-   [<span data-ttu-id="416ba-112">dynamic</span><span class="sxs-lookup"><span data-stu-id="416ba-112">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)  
  
-   [<span data-ttu-id="416ba-113">object</span><span class="sxs-lookup"><span data-stu-id="416ba-113">object</span></span>](../../../csharp/language-reference/keywords/object.md)  
  
-   [<span data-ttu-id="416ba-114">string</span><span class="sxs-lookup"><span data-stu-id="416ba-114">string</span></span>](../../../csharp/language-reference/keywords/string.md)  
  
## <a name="see-also"></a><span data-ttu-id="416ba-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="416ba-115">See Also</span></span>  
 [<span data-ttu-id="416ba-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="416ba-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="416ba-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="416ba-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="416ba-118">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="416ba-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="416ba-119">Typen</span><span class="sxs-lookup"><span data-stu-id="416ba-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="416ba-120">Werttypen</span><span class="sxs-lookup"><span data-stu-id="416ba-120">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)
