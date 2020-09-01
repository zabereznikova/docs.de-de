---
description: C#-Präprozessoranweisungen
title: C#-Präprozessoranweisungen
ms.date: 07/20/2015
f1_keywords:
- cs.preprocessor
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
ms.openlocfilehash: a7ffca8b39f1bd9f05193bccbb6d90e67fa262c9
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89132364"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="451e8-103">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="451e8-103">C# preprocessor directives</span></span>
<span data-ttu-id="451e8-104">Dieser Abschnitt enthält Informationen zu den folgenden C#-Präprozessoranweisungen:</span><span class="sxs-lookup"><span data-stu-id="451e8-104">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="451e8-105">#if</span><span class="sxs-lookup"><span data-stu-id="451e8-105">#if</span></span>](./preprocessor-if.md)
- [<span data-ttu-id="451e8-106">#else</span><span class="sxs-lookup"><span data-stu-id="451e8-106">#else</span></span>](./preprocessor-else.md)
- [<span data-ttu-id="451e8-107">#elif</span><span class="sxs-lookup"><span data-stu-id="451e8-107">#elif</span></span>](./preprocessor-elif.md)
- [<span data-ttu-id="451e8-108">#endif</span><span class="sxs-lookup"><span data-stu-id="451e8-108">#endif</span></span>](./preprocessor-endif.md)
- [<span data-ttu-id="451e8-109">#define</span><span class="sxs-lookup"><span data-stu-id="451e8-109">#define</span></span>](./preprocessor-define.md)
- [<span data-ttu-id="451e8-110">#undef</span><span class="sxs-lookup"><span data-stu-id="451e8-110">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="451e8-111">#warning</span><span class="sxs-lookup"><span data-stu-id="451e8-111">#warning</span></span>](./preprocessor-warning.md)
- [<span data-ttu-id="451e8-112">#error</span><span class="sxs-lookup"><span data-stu-id="451e8-112">#error</span></span>](./preprocessor-error.md)
- [<span data-ttu-id="451e8-113">#line</span><span class="sxs-lookup"><span data-stu-id="451e8-113">#line</span></span>](./preprocessor-line.md)
- [<span data-ttu-id="451e8-114">#region</span><span class="sxs-lookup"><span data-stu-id="451e8-114">#region</span></span>](./preprocessor-region.md)
- [<span data-ttu-id="451e8-115">#endregion</span><span class="sxs-lookup"><span data-stu-id="451e8-115">#endregion</span></span>](./preprocessor-endregion.md)
- [<span data-ttu-id="451e8-116">#pragma</span><span class="sxs-lookup"><span data-stu-id="451e8-116">#pragma</span></span>](./preprocessor-pragma.md)
- [<span data-ttu-id="451e8-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="451e8-117">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="451e8-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="451e8-118">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)

<span data-ttu-id="451e8-119">Weitere Informationen und Beispiele finden Sie unter den einzelnen Themen.</span><span class="sxs-lookup"><span data-stu-id="451e8-119">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="451e8-120">Obwohl der Compiler keinen separaten Präprozessor hat, werden die in diesem Abschnitt beschriebenen Anweisungen verarbeitet, als gäbe es einen.</span><span class="sxs-lookup"><span data-stu-id="451e8-120">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="451e8-121">Sie werden verwendet, um die bedingte Kompilierung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="451e8-121">They are used to help in conditional compilation.</span></span> <span data-ttu-id="451e8-122">Diese Anweisungen können Sie im Gegensatz zu C- und C++-Anweisungen nicht verwenden, um Makros zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="451e8-122">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="451e8-123">Eine Präprozessordirektive muss die einzige Anweisung in einer Zeile sein.</span><span class="sxs-lookup"><span data-stu-id="451e8-123">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="451e8-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="451e8-124">See also</span></span>

- [<span data-ttu-id="451e8-125">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="451e8-125">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="451e8-126">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="451e8-126">C# Programming Guide</span></span>](../../programming-guide/index.md)
