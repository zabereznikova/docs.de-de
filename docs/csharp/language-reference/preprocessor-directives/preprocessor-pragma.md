---
title: '#<a name="pragma-c-reference"></a>pragma (C#-Referenz)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '#pragma'
helpviewer_keywords: '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6f53bd0ed3f35f049b0a1cbb21c5b9a563f9fce9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="pragma-c-reference"></a><span data-ttu-id="1e566-102">#pragma (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="1e566-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="1e566-103">`#pragma` gibt dem Compiler spezielle Anweisungen für die Kompilierung der Datei, in der es auftritt.</span><span class="sxs-lookup"><span data-stu-id="1e566-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="1e566-104">Die Anweisungen müssen vom Compiler unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="1e566-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="1e566-105">Das heißt, Sie können `#pragma` nicht zum Erstellen von benutzerdefinierten Vorverarbeitungsanweisungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="1e566-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="1e566-106">Der Microsoft C#-Compiler unterstützt die folgenden beiden `#pragma`-Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="1e566-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="1e566-107">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="1e566-107">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="1e566-108">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="1e566-108">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="1e566-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e566-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1e566-110">Parameter</span><span class="sxs-lookup"><span data-stu-id="1e566-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="1e566-111">Der Name einer erkannten pragma-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1e566-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="1e566-112">Pragma-spezifische Argumente.</span><span class="sxs-lookup"><span data-stu-id="1e566-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e566-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e566-113">See Also</span></span>  
 [<span data-ttu-id="1e566-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="1e566-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="1e566-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="1e566-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1e566-116">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="1e566-116">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)  
 [<span data-ttu-id="1e566-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="1e566-117">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
 [<span data-ttu-id="1e566-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="1e566-118">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)
