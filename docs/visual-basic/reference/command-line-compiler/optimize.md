---
title: -Optimierung
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: 2f066835c5f864538f281d4c58772e0e60c132f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-optimize"></a><span data-ttu-id="0beb5-102">-Optimierung</span><span class="sxs-lookup"><span data-stu-id="0beb5-102">-optimize</span></span>
<span data-ttu-id="0beb5-103">Aktiviert oder deaktiviert compileroptimierungen.</span><span class="sxs-lookup"><span data-stu-id="0beb5-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0beb5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0beb5-104">Syntax</span></span>  
  
```  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0beb5-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="0beb5-105">Arguments</span></span>  
  
|<span data-ttu-id="0beb5-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="0beb5-106">Term</span></span>|<span data-ttu-id="0beb5-107">Definition</span><span class="sxs-lookup"><span data-stu-id="0beb5-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="0beb5-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="0beb5-108">`+` &#124; `-`</span></span>|<span data-ttu-id="0beb5-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0beb5-109">Optional.</span></span> <span data-ttu-id="0beb5-110">Die `-optimize-` -Option deaktiviert compileroptimierungen.</span><span class="sxs-lookup"><span data-stu-id="0beb5-110">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="0beb5-111">Die `-optimize+` Option Optimierungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0beb5-111">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="0beb5-112">Optimierungen sind standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="0beb5-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0beb5-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0beb5-113">Remarks</span></span>  
 <span data-ttu-id="0beb5-114">Durch Compileroptimierungen wird Ihre Ausgabedatei kleiner, schneller und effizienter.</span><span class="sxs-lookup"><span data-stu-id="0beb5-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="0beb5-115">Jedoch, da Optimierungen führen zu neuanordnungen von Code in die Ausgabedatei `-optimize+` können das Debuggen erschwert.</span><span class="sxs-lookup"><span data-stu-id="0beb5-115">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="0beb5-116">Alle Module mit generiert `-target:module` für eine Assembly, die die gleiche verwenden muss `-optimize` Einstellungen wie die Assembly.</span><span class="sxs-lookup"><span data-stu-id="0beb5-116">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="0beb5-117">Weitere Informationen finden Sie unter [-Ziel (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="0beb5-117">For more information, see [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="0beb5-118">Sie können Kombinieren der `-optimize` und `-debug` Optionen.</span><span class="sxs-lookup"><span data-stu-id="0beb5-118">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="0beb5-119">Zum Festlegen von - Optimierung in der integrierten Entwicklungsumgebung von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0beb5-119">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="0beb5-120">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="0beb5-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="0beb5-121">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="0beb5-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="0beb5-122">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="0beb5-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="0beb5-123">3.  Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="0beb5-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="0beb5-124">4.  Ändern der **Optimierungen aktivieren** Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="0beb5-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0beb5-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0beb5-125">Example</span></span>  
 <span data-ttu-id="0beb5-126">Der folgende code kompiliert `T2.vb` und compileroptimierungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0beb5-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="0beb5-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0beb5-127">See Also</span></span>  
 [<span data-ttu-id="0beb5-128">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="0beb5-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="0beb5-129">-Debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0beb5-129">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [<span data-ttu-id="0beb5-130">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="0beb5-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="0beb5-131">-Ziel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0beb5-131">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
