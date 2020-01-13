---
title: '#else – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
ms.openlocfilehash: 967ef38687b739ef3bea3f8923ab26bba0b6cea9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712558"
---
# <a name="else-c-reference"></a><span data-ttu-id="58699-102">#else (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="58699-102">#else (C# Reference)</span></span>
<span data-ttu-id="58699-103">Mit `#else` können Sie eine zusammengesetzte bedingte Anweisung erstellen, sodass der Compiler, wenn keiner der Ausdrücke in den vorangehenden [#if](./preprocessor-if.md)-Anweisungen oder (optional) [#elif](./preprocessor-elif.md)-Anweisungen auf `true` festgelegt ist, den gesamten Code zwischen `#else` und der darauffolgenden `#endif`-Anweisung auswertet.</span><span class="sxs-lookup"><span data-stu-id="58699-103">`#else` lets you create a compound conditional directive, so that, if none of the expressions in the preceding [#if](./preprocessor-if.md) or (optional) [#elif](./preprocessor-elif.md) directives evaluate to `true`, the compiler will evaluate all code between `#else` and the subsequent `#endif`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58699-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="58699-104">Remarks</span></span>  
 <span data-ttu-id="58699-105">[#endif](./preprocessor-endif.md) muss die nächste Präprozessoranweisung nach `#else` sein.</span><span class="sxs-lookup"><span data-stu-id="58699-105">[#endif](./preprocessor-endif.md) must be the next preprocessor directive after `#else`.</span></span> <span data-ttu-id="58699-106">Unter [#if](./preprocessor-if.md) finden Sie ein Beispiel zur Verwendung von `#else`.</span><span class="sxs-lookup"><span data-stu-id="58699-106">See [#if](./preprocessor-if.md) for an example of how to use `#else`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58699-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58699-107">See also</span></span>

- [<span data-ttu-id="58699-108">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="58699-108">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="58699-109">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="58699-109">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="58699-110">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="58699-110">C# Preprocessor Directives</span></span>](./index.md)
