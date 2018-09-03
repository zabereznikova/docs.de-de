---
title: '#pragma (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 5ae397cc61e0c6b58ed2079369131ebb7e352eae
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43482934"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="e64e6-102">#pragma (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e64e6-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="e64e6-103">`#pragma` gibt dem Compiler spezielle Anweisungen für die Kompilierung der Datei, in der es auftritt.</span><span class="sxs-lookup"><span data-stu-id="e64e6-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="e64e6-104">Die Anweisungen müssen vom Compiler unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="e64e6-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="e64e6-105">Das heißt, Sie können `#pragma` nicht zum Erstellen von benutzerdefinierten Vorverarbeitungsanweisungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e64e6-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="e64e6-106">Der Microsoft C#-Compiler unterstützt die folgenden beiden `#pragma`-Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="e64e6-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="e64e6-107">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="e64e6-107">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="e64e6-108">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="e64e6-108">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="e64e6-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="e64e6-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e64e6-110">Parameter</span><span class="sxs-lookup"><span data-stu-id="e64e6-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="e64e6-111">Der Name einer erkannten pragma-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e64e6-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="e64e6-112">Pragma-spezifische Argumente.</span><span class="sxs-lookup"><span data-stu-id="e64e6-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e64e6-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e64e6-113">See Also</span></span>

- [<span data-ttu-id="e64e6-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="e64e6-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="e64e6-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e64e6-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="e64e6-116">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="e64e6-116">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)  
- [<span data-ttu-id="e64e6-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="e64e6-117">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
- [<span data-ttu-id="e64e6-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="e64e6-118">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)
