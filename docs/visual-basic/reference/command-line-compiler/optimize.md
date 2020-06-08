---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: 337cb794ef9a405a178f1998cbe27b5da7709382
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397440"
---
# <a name="-optimize"></a><span data-ttu-id="0aa40-102">-optimize</span><span class="sxs-lookup"><span data-stu-id="0aa40-102">-optimize</span></span>
<span data-ttu-id="0aa40-103">Aktiviert oder deaktiviert Compileroptimierungen.</span><span class="sxs-lookup"><span data-stu-id="0aa40-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0aa40-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0aa40-104">Syntax</span></span>  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0aa40-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="0aa40-105">Arguments</span></span>  
  
|<span data-ttu-id="0aa40-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="0aa40-106">Term</span></span>|<span data-ttu-id="0aa40-107">Definition</span><span class="sxs-lookup"><span data-stu-id="0aa40-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="0aa40-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="0aa40-108">`+` &#124; `-`</span></span>|<span data-ttu-id="0aa40-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0aa40-109">Optional.</span></span> <span data-ttu-id="0aa40-110">Die `-optimize-`-Option deaktiviert Compileroptimierungen.</span><span class="sxs-lookup"><span data-stu-id="0aa40-110">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="0aa40-111">Die `-optimize+`-Option aktiviert Optimierungen.</span><span class="sxs-lookup"><span data-stu-id="0aa40-111">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="0aa40-112">Optimierungen sind standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="0aa40-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0aa40-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0aa40-113">Remarks</span></span>  
 <span data-ttu-id="0aa40-114">Durch Compileroptimierungen wird Ihre Ausgabedatei kleiner, schneller und effizienter.</span><span class="sxs-lookup"><span data-stu-id="0aa40-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="0aa40-115">Da Optimierungen jedoch zu Neuanordnungen von Code in der Ausgabedatei führen, kann `-optimize+` das Debuggen erschweren.</span><span class="sxs-lookup"><span data-stu-id="0aa40-115">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="0aa40-116">Alle mit `-target:module` generierten Module für eine Assembly müssen dieselben `-optimize`-Einstellungen wie die Assembly verwenden.</span><span class="sxs-lookup"><span data-stu-id="0aa40-116">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="0aa40-117">Weitere Informationen finden Sie unter [-target (Visual Basic)](target.md).</span><span class="sxs-lookup"><span data-stu-id="0aa40-117">For more information, see [-target (Visual Basic)](target.md).</span></span>  
  
 <span data-ttu-id="0aa40-118">Sie können die Optionen `-optimize` und `-debug` kombinieren.</span><span class="sxs-lookup"><span data-stu-id="0aa40-118">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="0aa40-119">So legen Sie -optimize in der integrierten Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="0aa40-119">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="0aa40-120">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="0aa40-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="0aa40-121">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="0aa40-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="0aa40-122">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="0aa40-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="0aa40-123">3.  Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="0aa40-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="0aa40-124">4.  Ändern Sie das Kontrollkästchen **Optimierungen aktivieren** entsprechend.</span><span class="sxs-lookup"><span data-stu-id="0aa40-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0aa40-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0aa40-125">Example</span></span>  
 <span data-ttu-id="0aa40-126">Der folgende Code kompiliert `T2.vb` und aktiviert Compileroptimierungen.</span><span class="sxs-lookup"><span data-stu-id="0aa40-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="0aa40-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0aa40-127">See also</span></span>

- [<span data-ttu-id="0aa40-128">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="0aa40-128">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="0aa40-129">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0aa40-129">-debug (Visual Basic)</span></span>](debug.md)
- [<span data-ttu-id="0aa40-130">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="0aa40-130">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="0aa40-131">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0aa40-131">-target (Visual Basic)</span></span>](target.md)
