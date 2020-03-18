---
title: C#-Präprozessoranweisungen
ms.date: 07/20/2015
f1_keywords:
- cs.preprocessor
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
ms.openlocfilehash: f63ba3e0bd89a88ad04b14c2f359a8cde65e8f12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "69608602"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="15e14-102">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="15e14-102">C# preprocessor directives</span></span>
<span data-ttu-id="15e14-103">Dieser Abschnitt enthält Informationen zu den folgenden C#-Präprozessoranweisungen:</span><span class="sxs-lookup"><span data-stu-id="15e14-103">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="15e14-104">#if</span><span class="sxs-lookup"><span data-stu-id="15e14-104">#if</span></span>](./preprocessor-if.md)
- [<span data-ttu-id="15e14-105">#else</span><span class="sxs-lookup"><span data-stu-id="15e14-105">#else</span></span>](./preprocessor-else.md)
- [<span data-ttu-id="15e14-106">#elif</span><span class="sxs-lookup"><span data-stu-id="15e14-106">#elif</span></span>](./preprocessor-elif.md)
- [<span data-ttu-id="15e14-107">#endif</span><span class="sxs-lookup"><span data-stu-id="15e14-107">#endif</span></span>](./preprocessor-endif.md)
- [<span data-ttu-id="15e14-108">#define</span><span class="sxs-lookup"><span data-stu-id="15e14-108">#define</span></span>](./preprocessor-define.md)
- [<span data-ttu-id="15e14-109">#undef</span><span class="sxs-lookup"><span data-stu-id="15e14-109">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="15e14-110">#warning</span><span class="sxs-lookup"><span data-stu-id="15e14-110">#warning</span></span>](./preprocessor-warning.md)
- [<span data-ttu-id="15e14-111">#error</span><span class="sxs-lookup"><span data-stu-id="15e14-111">#error</span></span>](./preprocessor-error.md)
- [<span data-ttu-id="15e14-112">#line</span><span class="sxs-lookup"><span data-stu-id="15e14-112">#line</span></span>](./preprocessor-line.md)
- [<span data-ttu-id="15e14-113">#region</span><span class="sxs-lookup"><span data-stu-id="15e14-113">#region</span></span>](./preprocessor-region.md)
- [<span data-ttu-id="15e14-114">#endregion</span><span class="sxs-lookup"><span data-stu-id="15e14-114">#endregion</span></span>](./preprocessor-endregion.md)
- [<span data-ttu-id="15e14-115">#pragma</span><span class="sxs-lookup"><span data-stu-id="15e14-115">#pragma</span></span>](./preprocessor-pragma.md)
- [<span data-ttu-id="15e14-116">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="15e14-116">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="15e14-117">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="15e14-117">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)

<span data-ttu-id="15e14-118">Weitere Informationen und Beispiele finden Sie unter den einzelnen Themen.</span><span class="sxs-lookup"><span data-stu-id="15e14-118">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="15e14-119">Obwohl der Compiler keinen separaten Präprozessor hat, werden die in diesem Abschnitt beschriebenen Anweisungen verarbeitet, als gäbe es einen.</span><span class="sxs-lookup"><span data-stu-id="15e14-119">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="15e14-120">Sie werden verwendet, um die bedingte Kompilierung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="15e14-120">They are used to help in conditional compilation.</span></span> <span data-ttu-id="15e14-121">Diese Anweisungen können Sie im Gegensatz zu C- und C++-Anweisungen nicht verwenden, um Makros zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="15e14-121">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="15e14-122">Eine Präprozessordirektive muss die einzige Anweisung in einer Zeile sein.</span><span class="sxs-lookup"><span data-stu-id="15e14-122">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="15e14-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="15e14-123">See also</span></span>

- [<span data-ttu-id="15e14-124">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="15e14-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="15e14-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="15e14-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
