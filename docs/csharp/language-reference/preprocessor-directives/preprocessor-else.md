---
description: '#else – C#-Referenz'
title: '#else – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
ms.openlocfilehash: fb1a9f30a42c78b5c4c7323ec213ab8c20b9bb76
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138175"
---
# <a name="else-c-reference"></a><span data-ttu-id="c7619-103">#else (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c7619-103">#else (C# Reference)</span></span>
<span data-ttu-id="c7619-104">Mit `#else` können Sie eine zusammengesetzte bedingte Anweisung erstellen, sodass der Compiler, wenn keiner der Ausdrücke in den vorangehenden [#if](./preprocessor-if.md)-Anweisungen oder (optional) [#elif](./preprocessor-elif.md)-Anweisungen auf `true` festgelegt ist, den gesamten Code zwischen `#else` und der darauffolgenden `#endif`-Anweisung auswertet.</span><span class="sxs-lookup"><span data-stu-id="c7619-104">`#else` lets you create a compound conditional directive, so that, if none of the expressions in the preceding [#if](./preprocessor-if.md) or (optional) [#elif](./preprocessor-elif.md) directives evaluate to `true`, the compiler will evaluate all code between `#else` and the subsequent `#endif`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7619-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c7619-105">Remarks</span></span>  
 <span data-ttu-id="c7619-106">[#endif](./preprocessor-endif.md) muss die nächste Präprozessoranweisung nach `#else` sein.</span><span class="sxs-lookup"><span data-stu-id="c7619-106">[#endif](./preprocessor-endif.md) must be the next preprocessor directive after `#else`.</span></span> <span data-ttu-id="c7619-107">Unter [#if](./preprocessor-if.md) finden Sie ein Beispiel zur Verwendung von `#else`.</span><span class="sxs-lookup"><span data-stu-id="c7619-107">See [#if](./preprocessor-if.md) for an example of how to use `#else`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7619-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7619-108">See also</span></span>

- [<span data-ttu-id="c7619-109">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c7619-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c7619-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c7619-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c7619-111">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="c7619-111">C# Preprocessor Directives</span></span>](./index.md)
