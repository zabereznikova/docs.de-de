---
title: '#<a name="pragma-c-reference"></a>pragma (C#-Referenz)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#pragma'
dev_langs:
- CSharp
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
caps.latest.revision: 18
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
ms.openlocfilehash: e03fc387b105c1dee3b7fed93263ad8ef22d5934
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="pragma-c-reference"></a><span data-ttu-id="13a62-102">#pragma (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="13a62-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="13a62-103">`#pragma` gibt dem Compiler spezielle Anweisungen für die Kompilierung der Datei, in der es auftritt.</span><span class="sxs-lookup"><span data-stu-id="13a62-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="13a62-104">Die Anweisungen müssen vom Compiler unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="13a62-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="13a62-105">Das heißt, Sie können `#pragma` nicht zum Erstellen von benutzerdefinierten Vorverarbeitungsanweisungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="13a62-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="13a62-106">Der Microsoft C#-Compiler unterstützt die folgenden beiden `#pragma`-Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="13a62-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="13a62-107">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="13a62-107">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="13a62-108">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="13a62-108">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="13a62-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="13a62-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
#### <a name="parameters"></a><span data-ttu-id="13a62-110">Parameter</span><span class="sxs-lookup"><span data-stu-id="13a62-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="13a62-111">Der Name einer erkannten pragma-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="13a62-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="13a62-112">Pragma-spezifische Argumente.</span><span class="sxs-lookup"><span data-stu-id="13a62-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13a62-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13a62-113">See Also</span></span>  
 <span data-ttu-id="13a62-114">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="13a62-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="13a62-115">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="13a62-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="13a62-116">[C#-Präprozessoranweisungen](../../../csharp/language-reference/preprocessor-directives/index.md) </span><span class="sxs-lookup"><span data-stu-id="13a62-116">[C# Preprocessor Directives](../../../csharp/language-reference/preprocessor-directives/index.md) </span></span>  
 <span data-ttu-id="13a62-117">[#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) </span><span class="sxs-lookup"><span data-stu-id="13a62-117">[#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) </span></span>  
 [<span data-ttu-id="13a62-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="13a62-118">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)

