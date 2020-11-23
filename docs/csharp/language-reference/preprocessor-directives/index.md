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
ms.openlocfilehash: 1269522b2687b76292f7b796a4ffc8095f23442e
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099060"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="96cee-103">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="96cee-103">C# preprocessor directives</span></span>

<span data-ttu-id="96cee-104">Dieser Abschnitt enthält Informationen zu den folgenden C#-Präprozessoranweisungen:</span><span class="sxs-lookup"><span data-stu-id="96cee-104">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="96cee-105">#if</span><span class="sxs-lookup"><span data-stu-id="96cee-105">#if</span></span>](./preprocessor-if.md)
- [<span data-ttu-id="96cee-106">#else</span><span class="sxs-lookup"><span data-stu-id="96cee-106">#else</span></span>](./preprocessor-else.md)
- [<span data-ttu-id="96cee-107">#elif</span><span class="sxs-lookup"><span data-stu-id="96cee-107">#elif</span></span>](./preprocessor-elif.md)
- [<span data-ttu-id="96cee-108">#endif</span><span class="sxs-lookup"><span data-stu-id="96cee-108">#endif</span></span>](./preprocessor-endif.md)
- [<span data-ttu-id="96cee-109">#define</span><span class="sxs-lookup"><span data-stu-id="96cee-109">#define</span></span>](./preprocessor-define.md)
- [<span data-ttu-id="96cee-110">#undef</span><span class="sxs-lookup"><span data-stu-id="96cee-110">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="96cee-111">#warning</span><span class="sxs-lookup"><span data-stu-id="96cee-111">#warning</span></span>](./preprocessor-warning.md)
- [<span data-ttu-id="96cee-112">#error</span><span class="sxs-lookup"><span data-stu-id="96cee-112">#error</span></span>](./preprocessor-error.md)
- [<span data-ttu-id="96cee-113">#line</span><span class="sxs-lookup"><span data-stu-id="96cee-113">#line</span></span>](./preprocessor-line.md)
- [<span data-ttu-id="96cee-114">#nullable</span><span class="sxs-lookup"><span data-stu-id="96cee-114">#nullable</span></span>](./preprocessor-nullable.md)
- [<span data-ttu-id="96cee-115">#region</span><span class="sxs-lookup"><span data-stu-id="96cee-115">#region</span></span>](./preprocessor-region.md)
- [<span data-ttu-id="96cee-116">#endregion</span><span class="sxs-lookup"><span data-stu-id="96cee-116">#endregion</span></span>](./preprocessor-endregion.md)
- [<span data-ttu-id="96cee-117">#pragma</span><span class="sxs-lookup"><span data-stu-id="96cee-117">#pragma</span></span>](./preprocessor-pragma.md)
- [<span data-ttu-id="96cee-118">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="96cee-118">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="96cee-119">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="96cee-119">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)

<span data-ttu-id="96cee-120">Weitere Informationen und Beispiele finden Sie unter den einzelnen Themen.</span><span class="sxs-lookup"><span data-stu-id="96cee-120">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="96cee-121">Obwohl der Compiler keinen separaten Präprozessor hat, werden die in diesem Abschnitt beschriebenen Anweisungen verarbeitet, als gäbe es einen.</span><span class="sxs-lookup"><span data-stu-id="96cee-121">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="96cee-122">Sie werden verwendet, um die bedingte Kompilierung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="96cee-122">They are used to help in conditional compilation.</span></span> <span data-ttu-id="96cee-123">Diese Anweisungen können Sie im Gegensatz zu C- und C++-Anweisungen nicht verwenden, um Makros zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="96cee-123">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="96cee-124">Eine Präprozessordirektive muss die einzige Anweisung in einer Zeile sein.</span><span class="sxs-lookup"><span data-stu-id="96cee-124">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="96cee-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96cee-125">See also</span></span>

- [<span data-ttu-id="96cee-126">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="96cee-126">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="96cee-127">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="96cee-127">C# Programming Guide</span></span>](../../programming-guide/index.md)
