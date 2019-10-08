---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: e8daf4a49123623b6470bc3c6281869f1b9b3d0f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005371"
---
# <a name="-optimize"></a><span data-ttu-id="5f4ee-102">-optimize</span><span class="sxs-lookup"><span data-stu-id="5f4ee-102">-optimize</span></span>
<span data-ttu-id="5f4ee-103">Aktiviert oder deaktiviert Compileroptimierungen.</span><span class="sxs-lookup"><span data-stu-id="5f4ee-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f4ee-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f4ee-104">Syntax</span></span>  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="5f4ee-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="5f4ee-105">Arguments</span></span>  
  
|<span data-ttu-id="5f4ee-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="5f4ee-106">Term</span></span>|<span data-ttu-id="5f4ee-107">Definition</span><span class="sxs-lookup"><span data-stu-id="5f4ee-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="5f4ee-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="5f4ee-108">`+` &#124; `-`</span></span>|<span data-ttu-id="5f4ee-109">Optional.</span><span class="sxs-lookup"><span data-stu-id="5f4ee-109">Optional.</span></span> <span data-ttu-id="5f4ee-110">Die Option "`-optimize-`" deaktiviert Compileroptimierungen.</span><span class="sxs-lookup"><span data-stu-id="5f4ee-110">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="5f4ee-111">Mit der Option "`-optimize+`" werden Optimierungen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="5f4ee-111">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="5f4ee-112">Optimierungen sind standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5f4ee-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f4ee-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5f4ee-113">Remarks</span></span>  
 <span data-ttu-id="5f4ee-114">Durch Compileroptimierungen wird Ihre Ausgabedatei kleiner, schneller und effizienter.</span><span class="sxs-lookup"><span data-stu-id="5f4ee-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="5f4ee-115">Da Optimierungen jedoch dazu führen, dass Code in der Ausgabedatei neu angeordnet wird, kann das Debuggen durch `-optimize+` erschwert werden.</span><span class="sxs-lookup"><span data-stu-id="5f4ee-115">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="5f4ee-116">Alle Module, die mit `-target:module` für eine Assembly generiert werden, müssen die gleichen `-optimize`-Einstellungen wie die Assembly verwenden.</span><span class="sxs-lookup"><span data-stu-id="5f4ee-116">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="5f4ee-117">Weitere Informationen finden Sie unter [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="5f4ee-117">For more information, see [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="5f4ee-118">Sie können die Optionen `-optimize` und `-debug` kombinieren.</span><span class="sxs-lookup"><span data-stu-id="5f4ee-118">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="5f4ee-119">So legen Sie "-optimieren" in der integrierten Entwicklungsumgebung von Visual Studio fest</span><span class="sxs-lookup"><span data-stu-id="5f4ee-119">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="5f4ee-120">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="5f4ee-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="5f4ee-121">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="5f4ee-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="5f4ee-122">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="5f4ee-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="5f4ee-123">3.  Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="5f4ee-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="5f4ee-124">4.  Ändern Sie das Kontrollkästchen **Optimierungen aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="5f4ee-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5f4ee-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5f4ee-125">Example</span></span>  
 <span data-ttu-id="5f4ee-126">Der folgende Code kompiliert `T2.vb` und aktiviert Compileroptimierungen.</span><span class="sxs-lookup"><span data-stu-id="5f4ee-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="5f4ee-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f4ee-127">See also</span></span>

- [<span data-ttu-id="5f4ee-128">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="5f4ee-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="5f4ee-129">-Debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5f4ee-129">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)
- [<span data-ttu-id="5f4ee-130">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="5f4ee-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="5f4ee-131">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5f4ee-131">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
