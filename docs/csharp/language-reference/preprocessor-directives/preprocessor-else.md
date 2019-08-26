---
title: '#else – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
ms.openlocfilehash: d6a514f71b3526b2ffe347cdd971b81907fb0aad
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69605718"
---
# <a name="else-c-reference"></a><span data-ttu-id="58e9a-102">#else (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="58e9a-102">#else (C# Reference)</span></span>
<span data-ttu-id="58e9a-103">Mit `#else` können Sie eine zusammengesetzte bedingte Anweisung erstellen, sodass der Compiler, wenn keiner der Ausdrücke in den vorangehenden [#if](./preprocessor-if.md)-Anweisungen oder (optional) [#elif](./preprocessor-elif.md)-Anweisungen auf `true` festgelegt ist, den gesamten Code zwischen `#else` und der darauffolgenden `#endif`-Anweisung auswertet.</span><span class="sxs-lookup"><span data-stu-id="58e9a-103">`#else` lets you create a compound conditional directive, so that, if none of the expressions in the preceding [#if](./preprocessor-if.md) or (optional) [#elif](./preprocessor-elif.md) directives evaluate to `true`, the compiler will evaluate all code between `#else` and the subsequent `#endif`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58e9a-104">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="58e9a-104">Remarks</span></span>  
 <span data-ttu-id="58e9a-105">[#endif](./preprocessor-endif.md) muss die nächste Präprozessoranweisung nach `#else` sein.</span><span class="sxs-lookup"><span data-stu-id="58e9a-105">[#endif](./preprocessor-endif.md) must be the next preprocessor directive after `#else`.</span></span> <span data-ttu-id="58e9a-106">Unter [#if](./preprocessor-if.md) finden Sie ein Beispiel zur Verwendung von `#else`.</span><span class="sxs-lookup"><span data-stu-id="58e9a-106">See [#if](./preprocessor-if.md) for an example of how to use `#else`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58e9a-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58e9a-107">See also</span></span>

- [<span data-ttu-id="58e9a-108">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="58e9a-108">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="58e9a-109">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="58e9a-109">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="58e9a-110">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="58e9a-110">C# Preprocessor Directives</span></span>](./index.md)
