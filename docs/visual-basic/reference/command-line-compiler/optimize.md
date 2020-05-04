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
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005371"
---
# <a name="-optimize"></a><span data-ttu-id="02a3f-102">-optimize</span><span class="sxs-lookup"><span data-stu-id="02a3f-102">-optimize</span></span>
<span data-ttu-id="02a3f-103">Aktiviert oder deaktiviert Compileroptimierungen.</span><span class="sxs-lookup"><span data-stu-id="02a3f-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02a3f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="02a3f-104">Syntax</span></span>  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="02a3f-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="02a3f-105">Arguments</span></span>  
  
|<span data-ttu-id="02a3f-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="02a3f-106">Term</span></span>|<span data-ttu-id="02a3f-107">Definition</span><span class="sxs-lookup"><span data-stu-id="02a3f-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="02a3f-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="02a3f-108">`+` &#124; `-`</span></span>|<span data-ttu-id="02a3f-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="02a3f-109">Optional.</span></span> <span data-ttu-id="02a3f-110">Die `-optimize-`-Option deaktiviert Compileroptimierungen.</span><span class="sxs-lookup"><span data-stu-id="02a3f-110">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="02a3f-111">Die `-optimize+`-Option aktiviert Optimierungen.</span><span class="sxs-lookup"><span data-stu-id="02a3f-111">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="02a3f-112">Optimierungen sind standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="02a3f-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02a3f-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="02a3f-113">Remarks</span></span>  
 <span data-ttu-id="02a3f-114">Durch Compileroptimierungen wird Ihre Ausgabedatei kleiner, schneller und effizienter.</span><span class="sxs-lookup"><span data-stu-id="02a3f-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="02a3f-115">Da Optimierungen jedoch zu Neuanordnungen von Code in der Ausgabedatei führen, kann `-optimize+` das Debuggen erschweren.</span><span class="sxs-lookup"><span data-stu-id="02a3f-115">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="02a3f-116">Alle mit `-target:module` generierten Module für eine Assembly müssen dieselben `-optimize`-Einstellungen wie die Assembly verwenden.</span><span class="sxs-lookup"><span data-stu-id="02a3f-116">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="02a3f-117">Weitere Informationen finden Sie unter [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="02a3f-117">For more information, see [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="02a3f-118">Sie können die Optionen `-optimize` und `-debug` kombinieren.</span><span class="sxs-lookup"><span data-stu-id="02a3f-118">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="02a3f-119">So legen Sie -optimize in der integrierten Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="02a3f-119">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="02a3f-120">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="02a3f-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="02a3f-121">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="02a3f-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="02a3f-122">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="02a3f-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="02a3f-123">3.  Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="02a3f-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="02a3f-124">4.  Ändern Sie das Kontrollkästchen **Optimierungen aktivieren** entsprechend.</span><span class="sxs-lookup"><span data-stu-id="02a3f-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="02a3f-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="02a3f-125">Example</span></span>  
 <span data-ttu-id="02a3f-126">Der folgende Code kompiliert `T2.vb` und aktiviert Compileroptimierungen.</span><span class="sxs-lookup"><span data-stu-id="02a3f-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="02a3f-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02a3f-127">See also</span></span>

- [<span data-ttu-id="02a3f-128">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="02a3f-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="02a3f-129">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02a3f-129">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)
- [<span data-ttu-id="02a3f-130">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="02a3f-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="02a3f-131">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02a3f-131">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
