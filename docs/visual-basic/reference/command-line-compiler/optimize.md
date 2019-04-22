---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: eb84e0a7038e7ff8cb399ac7222b6ac1661b5bc1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842160"
---
# <a name="-optimize"></a><span data-ttu-id="cbc62-102">-optimize</span><span class="sxs-lookup"><span data-stu-id="cbc62-102">-optimize</span></span>
<span data-ttu-id="cbc62-103">Aktiviert oder deaktiviert compileroptimierungen.</span><span class="sxs-lookup"><span data-stu-id="cbc62-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbc62-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cbc62-104">Syntax</span></span>  
  
```  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="cbc62-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="cbc62-105">Arguments</span></span>  
  
|<span data-ttu-id="cbc62-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="cbc62-106">Term</span></span>|<span data-ttu-id="cbc62-107">Definition</span><span class="sxs-lookup"><span data-stu-id="cbc62-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="cbc62-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="cbc62-108">`+` &#124; `-`</span></span>|<span data-ttu-id="cbc62-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="cbc62-109">Optional.</span></span> <span data-ttu-id="cbc62-110">Die `-optimize-` Option deaktiviert compileroptimierungen.</span><span class="sxs-lookup"><span data-stu-id="cbc62-110">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="cbc62-111">Die `-optimize+` Option Optimierungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="cbc62-111">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="cbc62-112">Optimierungen sind standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="cbc62-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cbc62-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cbc62-113">Remarks</span></span>  
 <span data-ttu-id="cbc62-114">Durch Compileroptimierungen wird Ihre Ausgabedatei kleiner, schneller und effizienter.</span><span class="sxs-lookup"><span data-stu-id="cbc62-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="cbc62-115">Jedoch, weil Optimierungen führen zu neuanordnungen von Code in die Ausgabedatei `-optimize+` können Sie das Debuggen schwierig.</span><span class="sxs-lookup"><span data-stu-id="cbc62-115">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="cbc62-116">Alle Module mit generiert `-target:module` für eine Assembly auch verwenden muss `-optimize` Einstellungen wie die Assembly.</span><span class="sxs-lookup"><span data-stu-id="cbc62-116">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="cbc62-117">Weitere Informationen finden Sie unter [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="cbc62-117">For more information, see [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="cbc62-118">Sie können kombinieren die `-optimize` und `-debug` Optionen.</span><span class="sxs-lookup"><span data-stu-id="cbc62-118">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="cbc62-119">Um die set - optimieren Sie, in der integrierten Entwicklungsumgebung von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cbc62-119">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="cbc62-120">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="cbc62-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="cbc62-121">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="cbc62-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="cbc62-122">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="cbc62-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="cbc62-123">3.  Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="cbc62-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="cbc62-124">4.  Ändern der **Optimierungen aktivieren** Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="cbc62-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cbc62-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cbc62-125">Example</span></span>  
 <span data-ttu-id="cbc62-126">Der folgende code kompiliert `T2.vb` und compileroptimierungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="cbc62-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="cbc62-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cbc62-127">See also</span></span>

- [<span data-ttu-id="cbc62-128">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="cbc62-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="cbc62-129">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cbc62-129">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)
- [<span data-ttu-id="cbc62-130">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="cbc62-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="cbc62-131">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cbc62-131">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
