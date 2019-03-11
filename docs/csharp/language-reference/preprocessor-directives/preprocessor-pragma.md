---
title: '#pragma – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 8b39d6760a5e30986d5d4bbe9bb1281dbf6742a2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471006"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="3d3d1-102">#pragma (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="3d3d1-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="3d3d1-103">`#pragma` gibt dem Compiler spezielle Anweisungen für die Kompilierung der Datei, in der es auftritt.</span><span class="sxs-lookup"><span data-stu-id="3d3d1-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="3d3d1-104">Die Anweisungen müssen vom Compiler unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="3d3d1-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="3d3d1-105">Das heißt, Sie können `#pragma` nicht zum Erstellen von benutzerdefinierten Vorverarbeitungsanweisungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="3d3d1-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="3d3d1-106">Der Microsoft C#-Compiler unterstützt die folgenden beiden `#pragma`-Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="3d3d1-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="3d3d1-107">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="3d3d1-107">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="3d3d1-108">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="3d3d1-108">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="3d3d1-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d3d1-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d3d1-110">Parameter</span><span class="sxs-lookup"><span data-stu-id="3d3d1-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="3d3d1-111">Der Name einer erkannten pragma-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="3d3d1-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="3d3d1-112">Pragma-spezifische Argumente.</span><span class="sxs-lookup"><span data-stu-id="3d3d1-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d3d1-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d3d1-113">See also</span></span>

- [<span data-ttu-id="3d3d1-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="3d3d1-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="3d3d1-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3d3d1-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="3d3d1-116">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="3d3d1-116">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
- [<span data-ttu-id="3d3d1-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="3d3d1-117">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)
- [<span data-ttu-id="3d3d1-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="3d3d1-118">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)
