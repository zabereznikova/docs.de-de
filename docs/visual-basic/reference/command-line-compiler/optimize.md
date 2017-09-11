---
title: / optimize | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization, enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: f01ab17d4a2f5d123538294a7a13d7a6d7a40267
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="optimize"></a><span data-ttu-id="d3f91-102">/optimize</span><span class="sxs-lookup"><span data-stu-id="d3f91-102">/optimize</span></span>
<span data-ttu-id="d3f91-103">Aktiviert oder deaktiviert die Compiler-Optimierungen.</span><span class="sxs-lookup"><span data-stu-id="d3f91-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3f91-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3f91-104">Syntax</span></span>  
  
```  
/optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d3f91-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="d3f91-105">Arguments</span></span>  
  
|<span data-ttu-id="d3f91-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="d3f91-106">Term</span></span>|<span data-ttu-id="d3f91-107">Definition</span><span class="sxs-lookup"><span data-stu-id="d3f91-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="d3f91-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="d3f91-108">`+` &#124; `-`</span></span>|<span data-ttu-id="d3f91-109">Optional.</span><span class="sxs-lookup"><span data-stu-id="d3f91-109">Optional.</span></span> <span data-ttu-id="d3f91-110">Die `/optimize-` Option compileroptimierungen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="d3f91-110">The `/optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="d3f91-111">Die `/optimize+` -Option aktiviert Optimierungen.</span><span class="sxs-lookup"><span data-stu-id="d3f91-111">The `/optimize+` option enables optimizations.</span></span> <span data-ttu-id="d3f91-112">Standardmäßig sind Optimierungen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="d3f91-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3f91-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d3f91-113">Remarks</span></span>  
 <span data-ttu-id="d3f91-114">Compileroptimierungen stellen Ihre Ausgabedatei kleiner, schneller und effizienter.</span><span class="sxs-lookup"><span data-stu-id="d3f91-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="d3f91-115">Jedoch, da Optimierungen führen zu neuanordnungen von Code in der Ausgabedatei `/optimize+` kann das Debuggen erschwert.</span><span class="sxs-lookup"><span data-stu-id="d3f91-115">However, because optimizations result in code rearrangement in the output file, `/optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="d3f91-116">Alle Module mit generiert `/target:module` für eine Assembly, die die gleiche verwenden muss `/optimize` Einstellungen wie die Assembly.</span><span class="sxs-lookup"><span data-stu-id="d3f91-116">All modules generated with `/target:module` for an assembly must use the same `/optimize` settings as the assembly.</span></span> <span data-ttu-id="d3f91-117">Weitere Informationen finden Sie unter [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="d3f91-117">For more information, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="d3f91-118">Sie können Kombinieren der `/optimize` und `/debug` Optionen.</span><span class="sxs-lookup"><span data-stu-id="d3f91-118">You can combine the `/optimize` and `/debug` options.</span></span>  
  
|<span data-ttu-id="d3f91-119">So legen Sie / optimieren, in der Visual Studio-IDE</span><span class="sxs-lookup"><span data-stu-id="d3f91-119">To set /optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="d3f91-120">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="d3f91-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d3f91-121">Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="d3f91-121">On the **Project** menu, click **Properties**.</span></span><br />     <span data-ttu-id="d3f91-122">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="d3f91-122">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="d3f91-123">2.  Klicken Sie auf die **Kompilieren** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="d3f91-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="d3f91-124">3.  Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="d3f91-124">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="d3f91-125">4.  Ändern der **Optimierungen aktivieren** das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="d3f91-125">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d3f91-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d3f91-126">Example</span></span>  
 <span data-ttu-id="d3f91-127">Der folgende code kompiliert `T2.vb` und compileroptimierungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d3f91-127">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```  
vbc t2.vb /optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3f91-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3f91-128">See Also</span></span>  
 <span data-ttu-id="d3f91-129">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="d3f91-129">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="d3f91-130"> [/ Debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md) </span><span class="sxs-lookup"><span data-stu-id="d3f91-130"> [/debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md) </span></span>  
<span data-ttu-id="d3f91-131"> [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="d3f91-131"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="d3f91-132"> [/ target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)</span><span class="sxs-lookup"><span data-stu-id="d3f91-132"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)</span></span>
