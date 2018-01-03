---
title: /optimize
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e157fb0e1fcdb3899440eed02a42b16f75541989
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="optimize"></a><span data-ttu-id="93331-102">/optimize</span><span class="sxs-lookup"><span data-stu-id="93331-102">/optimize</span></span>
<span data-ttu-id="93331-103">Aktiviert oder deaktiviert compileroptimierungen.</span><span class="sxs-lookup"><span data-stu-id="93331-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93331-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="93331-104">Syntax</span></span>  
  
```  
/optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="93331-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="93331-105">Arguments</span></span>  
  
|<span data-ttu-id="93331-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="93331-106">Term</span></span>|<span data-ttu-id="93331-107">Definition</span><span class="sxs-lookup"><span data-stu-id="93331-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="93331-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="93331-108">`+` &#124; `-`</span></span>|<span data-ttu-id="93331-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="93331-109">Optional.</span></span> <span data-ttu-id="93331-110">Die `/optimize-` -Option deaktiviert compileroptimierungen.</span><span class="sxs-lookup"><span data-stu-id="93331-110">The `/optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="93331-111">Die `/optimize+` Option Optimierungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="93331-111">The `/optimize+` option enables optimizations.</span></span> <span data-ttu-id="93331-112">Optimierungen sind standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="93331-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93331-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="93331-113">Remarks</span></span>  
 <span data-ttu-id="93331-114">Durch Compileroptimierungen wird Ihre Ausgabedatei kleiner, schneller und effizienter.</span><span class="sxs-lookup"><span data-stu-id="93331-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="93331-115">Jedoch, da Optimierungen führen zu neuanordnungen von Code in die Ausgabedatei `/optimize+` können das Debuggen erschwert.</span><span class="sxs-lookup"><span data-stu-id="93331-115">However, because optimizations result in code rearrangement in the output file, `/optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="93331-116">Alle Module mit generiert `/target:module` für eine Assembly, die die gleiche verwenden muss `/optimize` Einstellungen wie die Assembly.</span><span class="sxs-lookup"><span data-stu-id="93331-116">All modules generated with `/target:module` for an assembly must use the same `/optimize` settings as the assembly.</span></span> <span data-ttu-id="93331-117">Weitere Informationen finden Sie unter [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="93331-117">For more information, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="93331-118">Sie können Kombinieren der `/optimize` und `/debug` Optionen.</span><span class="sxs-lookup"><span data-stu-id="93331-118">You can combine the `/optimize` and `/debug` options.</span></span>  
  
|<span data-ttu-id="93331-119">So legen Sie / zu optimieren, in der integrierten Entwicklungsumgebung von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="93331-119">To set /optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="93331-120">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="93331-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="93331-121">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="93331-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="93331-122">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="93331-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="93331-123">3.  Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="93331-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="93331-124">4.  Ändern der **Optimierungen aktivieren** Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="93331-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="93331-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93331-125">Example</span></span>  
 <span data-ttu-id="93331-126">Der folgende code kompiliert `T2.vb` und compileroptimierungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="93331-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```  
vbc t2.vb /optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="93331-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93331-127">See Also</span></span>  
 [<span data-ttu-id="93331-128">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="93331-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="93331-129">"/ Debug" (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93331-129">/debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [<span data-ttu-id="93331-130">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="93331-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="93331-131">/ target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93331-131">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
