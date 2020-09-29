---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: d4b50d56373676bf78a7591102095209401c907d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097591"
---
# <a name="-optimize"></a><span data-ttu-id="f7340-102">-optimize</span><span class="sxs-lookup"><span data-stu-id="f7340-102">-optimize</span></span>

<span data-ttu-id="f7340-103">Aktiviert oder deaktiviert Compileroptimierungen.</span><span class="sxs-lookup"><span data-stu-id="f7340-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7340-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f7340-104">Syntax</span></span>  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f7340-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="f7340-105">Arguments</span></span>  
  
|<span data-ttu-id="f7340-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="f7340-106">Term</span></span>|<span data-ttu-id="f7340-107">Definition</span><span class="sxs-lookup"><span data-stu-id="f7340-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="f7340-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="f7340-108">`+` &#124; `-`</span></span>|<span data-ttu-id="f7340-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="f7340-109">Optional.</span></span> <span data-ttu-id="f7340-110">Die `-optimize-`-Option deaktiviert Compileroptimierungen.</span><span class="sxs-lookup"><span data-stu-id="f7340-110">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="f7340-111">Die `-optimize+`-Option aktiviert Optimierungen.</span><span class="sxs-lookup"><span data-stu-id="f7340-111">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="f7340-112">Optimierungen sind standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f7340-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7340-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f7340-113">Remarks</span></span>  

 <span data-ttu-id="f7340-114">Durch Compileroptimierungen wird Ihre Ausgabedatei kleiner, schneller und effizienter.</span><span class="sxs-lookup"><span data-stu-id="f7340-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="f7340-115">Da Optimierungen jedoch zu Neuanordnungen von Code in der Ausgabedatei führen, kann `-optimize+` das Debuggen erschweren.</span><span class="sxs-lookup"><span data-stu-id="f7340-115">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="f7340-116">Alle mit `-target:module` generierten Module für eine Assembly müssen dieselben `-optimize`-Einstellungen wie die Assembly verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7340-116">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="f7340-117">Weitere Informationen finden Sie unter [-target (Visual Basic)](target.md).</span><span class="sxs-lookup"><span data-stu-id="f7340-117">For more information, see [-target (Visual Basic)](target.md).</span></span>  
  
 <span data-ttu-id="f7340-118">Sie können die Optionen `-optimize` und `-debug` kombinieren.</span><span class="sxs-lookup"><span data-stu-id="f7340-118">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="f7340-119">So legen Sie -optimize in der integrierten Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="f7340-119">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="f7340-120">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="f7340-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="f7340-121">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="f7340-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="f7340-122">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="f7340-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="f7340-123">3.  Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="f7340-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="f7340-124">4.  Ändern Sie das Kontrollkästchen **Optimierungen aktivieren** entsprechend.</span><span class="sxs-lookup"><span data-stu-id="f7340-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f7340-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f7340-125">Example</span></span>  

 <span data-ttu-id="f7340-126">Der folgende Code kompiliert `T2.vb` und aktiviert Compileroptimierungen.</span><span class="sxs-lookup"><span data-stu-id="f7340-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="f7340-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7340-127">See also</span></span>

- [<span data-ttu-id="f7340-128">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="f7340-128">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="f7340-129">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7340-129">-debug (Visual Basic)</span></span>](debug.md)
- [<span data-ttu-id="f7340-130">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="f7340-130">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="f7340-131">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7340-131">-target (Visual Basic)</span></span>](target.md)
