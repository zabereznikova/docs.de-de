---
title: "C#-Präprozessoranweisungen"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.preprocessor
dev_langs:
- CSharp
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 91bb2daefbc677fad8a3dd93b37aac996234d48c
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="7f39f-102">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="7f39f-102">C# Preprocessor Directives</span></span>
<span data-ttu-id="7f39f-103">Dieser Abschnitt enthält Informationen über die folgenden C#-Präprozessoranweisungen.</span><span class="sxs-lookup"><span data-stu-id="7f39f-103">This section contains information about the following C# preprocessor directives.</span></span>  
  
 [<span data-ttu-id="7f39f-104">#if</span><span class="sxs-lookup"><span data-stu-id="7f39f-104">#if</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)  
  
 [<span data-ttu-id="7f39f-105">#else</span><span class="sxs-lookup"><span data-stu-id="7f39f-105">#else</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md)  
  
 [<span data-ttu-id="7f39f-106">#elif</span><span class="sxs-lookup"><span data-stu-id="7f39f-106">#elif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md)  
  
 [<span data-ttu-id="7f39f-107">#endif</span><span class="sxs-lookup"><span data-stu-id="7f39f-107">#endif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md)  
  
 [<span data-ttu-id="7f39f-108">#define</span><span class="sxs-lookup"><span data-stu-id="7f39f-108">#define</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md)  
  
 [<span data-ttu-id="7f39f-109">#undef</span><span class="sxs-lookup"><span data-stu-id="7f39f-109">#undef</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)  
  
 [<span data-ttu-id="7f39f-110">#warning</span><span class="sxs-lookup"><span data-stu-id="7f39f-110">#warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md)  
  
 [<span data-ttu-id="7f39f-111">#error</span><span class="sxs-lookup"><span data-stu-id="7f39f-111">#error</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md)  
  
 [<span data-ttu-id="7f39f-112">#line</span><span class="sxs-lookup"><span data-stu-id="7f39f-112">#line</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-line.md)  
  
 [<span data-ttu-id="7f39f-113">#region</span><span class="sxs-lookup"><span data-stu-id="7f39f-113">#region</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-region.md)  
  
 [<span data-ttu-id="7f39f-114">#endregion</span><span class="sxs-lookup"><span data-stu-id="7f39f-114">#endregion</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md)  
  
 [<span data-ttu-id="7f39f-115">#pragma</span><span class="sxs-lookup"><span data-stu-id="7f39f-115">#pragma</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma.md)  
  
 [<span data-ttu-id="7f39f-116">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="7f39f-116">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="7f39f-117">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="7f39f-117">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
 <span data-ttu-id="7f39f-118">Weitere Informationen und Beispiele finden Sie unter den einzelnen Themen.</span><span class="sxs-lookup"><span data-stu-id="7f39f-118">See the individual topics for more information and examples.</span></span>  
  
 <span data-ttu-id="7f39f-119">Obwohl der Compiler keinen separaten Präprozessor hat, werden die in diesem Abschnitt beschriebenen Anweisungen verarbeitet, als gäbe es einen.</span><span class="sxs-lookup"><span data-stu-id="7f39f-119">Although the compiler does not have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="7f39f-120">Sie werden verwendet, um die bedingte Kompilierung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="7f39f-120">They are used to help in conditional compilation.</span></span> <span data-ttu-id="7f39f-121">Diese Anweisungen können Sie im Gegensatz zu C- und C++-Anweisungen nicht verwenden, um Makros zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7f39f-121">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>  
  
 <span data-ttu-id="7f39f-122">Eine Präprozessordirektive muss die einzige Anweisung in einer Zeile sein.</span><span class="sxs-lookup"><span data-stu-id="7f39f-122">A preprocessor directive must be the only instruction on a line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f39f-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f39f-123">See Also</span></span>  
 <span data-ttu-id="7f39f-124">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="7f39f-124">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 [<span data-ttu-id="7f39f-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="7f39f-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

