---
title: C#-Präprozessoranweisungen
ms.date: 07/20/2015
f1_keywords:
- cs.preprocessor
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
ms.openlocfilehash: 54067777ed2e92eea263b17cce0d4cdf13ed731d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61689319"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="75d66-102">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="75d66-102">C# preprocessor directives</span></span>
<span data-ttu-id="75d66-103">Dieser Abschnitt enthält Informationen zu den folgenden C#-Präprozessoranweisungen:</span><span class="sxs-lookup"><span data-stu-id="75d66-103">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="75d66-104">#if</span><span class="sxs-lookup"><span data-stu-id="75d66-104">#if</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)
- [<span data-ttu-id="75d66-105">#else</span><span class="sxs-lookup"><span data-stu-id="75d66-105">#else</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md)
- [<span data-ttu-id="75d66-106">#elif</span><span class="sxs-lookup"><span data-stu-id="75d66-106">#elif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md)
- [<span data-ttu-id="75d66-107">#endif</span><span class="sxs-lookup"><span data-stu-id="75d66-107">#endif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md)
- [<span data-ttu-id="75d66-108">#define</span><span class="sxs-lookup"><span data-stu-id="75d66-108">#define</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md)
- [<span data-ttu-id="75d66-109">#undef</span><span class="sxs-lookup"><span data-stu-id="75d66-109">#undef</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)
- [<span data-ttu-id="75d66-110">#warning</span><span class="sxs-lookup"><span data-stu-id="75d66-110">#warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md)
- [<span data-ttu-id="75d66-111">#error</span><span class="sxs-lookup"><span data-stu-id="75d66-111">#error</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md)
- [<span data-ttu-id="75d66-112">#line</span><span class="sxs-lookup"><span data-stu-id="75d66-112">#line</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-line.md)
- [<span data-ttu-id="75d66-113">#region</span><span class="sxs-lookup"><span data-stu-id="75d66-113">#region</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-region.md)
- [<span data-ttu-id="75d66-114">#endregion</span><span class="sxs-lookup"><span data-stu-id="75d66-114">#endregion</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md)
- [<span data-ttu-id="75d66-115">#pragma</span><span class="sxs-lookup"><span data-stu-id="75d66-115">#pragma</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma.md)
- [<span data-ttu-id="75d66-116">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="75d66-116">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)
- [<span data-ttu-id="75d66-117">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="75d66-117">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)

<span data-ttu-id="75d66-118">Weitere Informationen und Beispiele finden Sie unter den einzelnen Themen.</span><span class="sxs-lookup"><span data-stu-id="75d66-118">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="75d66-119">Obwohl der Compiler keinen separaten Präprozessor hat, werden die in diesem Abschnitt beschriebenen Anweisungen verarbeitet, als gäbe es einen.</span><span class="sxs-lookup"><span data-stu-id="75d66-119">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="75d66-120">Sie werden verwendet, um die bedingte Kompilierung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="75d66-120">They are used to help in conditional compilation.</span></span> <span data-ttu-id="75d66-121">Diese Anweisungen können Sie im Gegensatz zu C- und C++-Anweisungen nicht verwenden, um Makros zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="75d66-121">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="75d66-122">Eine Präprozessordirektive muss die einzige Anweisung in einer Zeile sein.</span><span class="sxs-lookup"><span data-stu-id="75d66-122">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="75d66-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75d66-123">See also</span></span>

- [<span data-ttu-id="75d66-124">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="75d66-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="75d66-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="75d66-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
