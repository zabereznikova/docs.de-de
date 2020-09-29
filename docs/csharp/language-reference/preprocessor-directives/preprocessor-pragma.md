---
description: '#pragma – C#-Referenz'
title: '#pragma – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 2788c2589bee149676c5cb2b4212ec7a060a47af
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168516"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="4f0ac-103">#pragma (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="4f0ac-103">#pragma (C# Reference)</span></span>

<span data-ttu-id="4f0ac-104">`#pragma` gibt dem Compiler spezielle Anweisungen für die Kompilierung der Datei, in der es auftritt.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-104">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="4f0ac-105">Die Anweisungen müssen vom Compiler unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-105">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="4f0ac-106">Das heißt, Sie können `#pragma` nicht zum Erstellen von benutzerdefinierten Vorverarbeitungsanweisungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-106">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="4f0ac-107">Der Microsoft C#-Compiler unterstützt die folgenden beiden `#pragma`-Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="4f0ac-107">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="4f0ac-108">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="4f0ac-108">#pragma warning</span></span>](./preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="4f0ac-109">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="4f0ac-109">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="4f0ac-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f0ac-110">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f0ac-111">Parameter</span><span class="sxs-lookup"><span data-stu-id="4f0ac-111">Parameters</span></span>  

 `pragma-name`  
 <span data-ttu-id="4f0ac-112">Der Name einer erkannten pragma-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-112">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="4f0ac-113">Pragma-spezifische Argumente.</span><span class="sxs-lookup"><span data-stu-id="4f0ac-113">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f0ac-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f0ac-114">See also</span></span>

- [<span data-ttu-id="4f0ac-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="4f0ac-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4f0ac-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="4f0ac-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4f0ac-117">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="4f0ac-117">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="4f0ac-118">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="4f0ac-118">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="4f0ac-119">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="4f0ac-119">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)
