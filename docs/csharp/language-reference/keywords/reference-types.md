---
title: Verweistypen (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.referencetypes
dev_langs:
- CSharp
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
caps.latest.revision: 15
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
ms.openlocfilehash: ed7b9c8ed4aa1136c09049c8ffd6c68beeeb2a48
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="reference-types-c-reference"></a><span data-ttu-id="ac72a-102">Verweistypen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ac72a-102">Reference Types (C# Reference)</span></span>
<span data-ttu-id="ac72a-103">Es gibt zwei Arten von Typen in C#: Verweistypen und Werttypen.</span><span class="sxs-lookup"><span data-stu-id="ac72a-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="ac72a-104">Variablen von Verweistypen speichern Verweise auf ihre Daten (Objekte), während Variablen von Werttypen ihre Daten direkt enthalten.</span><span class="sxs-lookup"><span data-stu-id="ac72a-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="ac72a-105">Bei Verweistypen können zwei Variablen auf dasselbe Objekt verweisen. Daher können auf eine Variable angewendete Operationen das Objekt beeinflussen, auf das von der anderen Variablen verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="ac72a-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="ac72a-106">Bei Werttypen besitzt jede Variable eine eigene Kopie der Daten, und auf eine Variable angewendete Operationen können die andere Variable nicht beeinflussen (außer im Fall von ref-Parametervariablen und out-Parametervariablen, siehe [ref](../../../csharp/language-reference/keywords/ref.md) und [Modifizierer für out-Parameter](../../../csharp/language-reference/keywords/out-parameter-modifier.md)).</span><span class="sxs-lookup"><span data-stu-id="ac72a-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of ref and out parameter variables, see [ref](../../../csharp/language-reference/keywords/ref.md) and [out parameter modifier](../../../csharp/language-reference/keywords/out-parameter-modifier.md)).</span></span>  
  
 <span data-ttu-id="ac72a-107">Die folgenden Schlüsselwörter werden verwendet, um Verweistypen zu deklarieren:</span><span class="sxs-lookup"><span data-stu-id="ac72a-107">The following keywords are used to declare reference types:</span></span>  
  
-   [<span data-ttu-id="ac72a-108">class</span><span class="sxs-lookup"><span data-stu-id="ac72a-108">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="ac72a-109">interface</span><span class="sxs-lookup"><span data-stu-id="ac72a-109">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="ac72a-110">delegate</span><span class="sxs-lookup"><span data-stu-id="ac72a-110">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="ac72a-111">C# enthält auch die folgenden integrierten Referenztypen:</span><span class="sxs-lookup"><span data-stu-id="ac72a-111">C# also provides the following built-in reference types:</span></span>  
  
-   [<span data-ttu-id="ac72a-112">dynamic</span><span class="sxs-lookup"><span data-stu-id="ac72a-112">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)  
  
-   [<span data-ttu-id="ac72a-113">object</span><span class="sxs-lookup"><span data-stu-id="ac72a-113">object</span></span>](../../../csharp/language-reference/keywords/object.md)  
  
-   [<span data-ttu-id="ac72a-114">string</span><span class="sxs-lookup"><span data-stu-id="ac72a-114">string</span></span>](../../../csharp/language-reference/keywords/string.md)  
  
## <a name="see-also"></a><span data-ttu-id="ac72a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac72a-115">See Also</span></span>  
 <span data-ttu-id="ac72a-116">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ac72a-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ac72a-117">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ac72a-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ac72a-118">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="ac72a-118">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="ac72a-119">[Typen](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="ac72a-119">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 [<span data-ttu-id="ac72a-120">Werttypen</span><span class="sxs-lookup"><span data-stu-id="ac72a-120">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)

