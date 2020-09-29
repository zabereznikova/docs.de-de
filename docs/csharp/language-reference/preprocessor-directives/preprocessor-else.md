---
description: '#else – C#-Referenz'
title: '#else – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
ms.openlocfilehash: f0dc8c34672c3e9e5a2207211794fbc8099640c5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168672"
---
# <a name="else-c-reference"></a><span data-ttu-id="d4580-103">#else (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d4580-103">#else (C# Reference)</span></span>

<span data-ttu-id="d4580-104">Mit `#else` können Sie eine zusammengesetzte bedingte Anweisung erstellen, sodass der Compiler, wenn keiner der Ausdrücke in den vorangehenden [#if](./preprocessor-if.md)-Anweisungen oder (optional) [#elif](./preprocessor-elif.md)-Anweisungen auf `true` festgelegt ist, den gesamten Code zwischen `#else` und der darauffolgenden `#endif`-Anweisung auswertet.</span><span class="sxs-lookup"><span data-stu-id="d4580-104">`#else` lets you create a compound conditional directive, so that, if none of the expressions in the preceding [#if](./preprocessor-if.md) or (optional) [#elif](./preprocessor-elif.md) directives evaluate to `true`, the compiler will evaluate all code between `#else` and the subsequent `#endif`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4580-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d4580-105">Remarks</span></span>  

 <span data-ttu-id="d4580-106">[#endif](./preprocessor-endif.md) muss die nächste Präprozessoranweisung nach `#else` sein.</span><span class="sxs-lookup"><span data-stu-id="d4580-106">[#endif](./preprocessor-endif.md) must be the next preprocessor directive after `#else`.</span></span> <span data-ttu-id="d4580-107">Unter [#if](./preprocessor-if.md) finden Sie ein Beispiel zur Verwendung von `#else`.</span><span class="sxs-lookup"><span data-stu-id="d4580-107">See [#if](./preprocessor-if.md) for an example of how to use `#else`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4580-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4580-108">See also</span></span>

- [<span data-ttu-id="d4580-109">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="d4580-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d4580-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d4580-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d4580-111">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="d4580-111">C# Preprocessor Directives</span></span>](./index.md)
