---
title: '#pragma – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 216adebae8a498ef2f4263f46f8ccd7a20d9202f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622376"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="2e190-102">#pragma (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="2e190-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="2e190-103">`#pragma` gibt dem Compiler spezielle Anweisungen für die Kompilierung der Datei, in der es auftritt.</span><span class="sxs-lookup"><span data-stu-id="2e190-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="2e190-104">Die Anweisungen müssen vom Compiler unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="2e190-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="2e190-105">Das heißt, Sie können `#pragma` nicht zum Erstellen von benutzerdefinierten Vorverarbeitungsanweisungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e190-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="2e190-106">Der Microsoft C#-Compiler unterstützt die folgenden beiden `#pragma`-Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="2e190-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="2e190-107">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="2e190-107">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="2e190-108">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="2e190-108">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="2e190-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e190-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2e190-110">Parameter</span><span class="sxs-lookup"><span data-stu-id="2e190-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="2e190-111">Der Name einer erkannten pragma-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2e190-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="2e190-112">Pragma-spezifische Argumente.</span><span class="sxs-lookup"><span data-stu-id="2e190-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e190-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e190-113">See also</span></span>

- [<span data-ttu-id="2e190-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="2e190-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="2e190-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2e190-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="2e190-116">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="2e190-116">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
- [<span data-ttu-id="2e190-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="2e190-117">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)
- [<span data-ttu-id="2e190-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="2e190-118">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)
