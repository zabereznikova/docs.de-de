---
title: Anweisungen
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: b5e857198351b30c0d7a38dce1a9e6d1209b5258
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74838142"
---
# <a name="directives-visual-basic"></a><span data-ttu-id="94b60-102">Anweisungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94b60-102">Directives (Visual Basic)</span></span>

<span data-ttu-id="94b60-103">In den Themen in diesem Abschnitt werden die Visual Basic-Quellcode-Compilerdirektiven dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="94b60-103">The topics in this section document the Visual Basic source code compiler directives.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="94b60-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="94b60-104">In This Section</span></span>  

 <span data-ttu-id="94b60-105">[#Const Direktive](../../../visual-basic/language-reference/directives/const-directive.md) : Definieren einer Compilerkonstante</span><span class="sxs-lookup"><span data-stu-id="94b60-105">[#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md) -- Define a compiler constant</span></span>  
  
 <span data-ttu-id="94b60-106">[#ExternalSource-Direktive](../../../visual-basic/language-reference/directives/externalsource-directive.md) : gibt eine Zuordnung zwischen Quellzeilen und Text außerhalb der Quelle an.</span><span class="sxs-lookup"><span data-stu-id="94b60-106">[#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md) -- Indicate a mapping between source lines and text external to the source</span></span>  
  
 <span data-ttu-id="94b60-107">[#If... Then... #else Direktiven](../../../visual-basic/language-reference/directives/if-then-else-directives.md) : Kompilieren Sie ausgewählte Code Blöcke.</span><span class="sxs-lookup"><span data-stu-id="94b60-107">[#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) -- Compile selected blocks of code</span></span>  
  
 <span data-ttu-id="94b60-108">[#Region Direktive](../../../visual-basic/language-reference/directives/region-directive.md) : reduzieren und Ausblenden von Code Abschnitten im Visual Studio-Editor</span><span class="sxs-lookup"><span data-stu-id="94b60-108">[#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) -- Collapse and hide sections of code in the Visual Studio editor</span></span>  
  
 <span data-ttu-id="94b60-109">**#Disable #enable** -deaktivieren und aktivieren Sie bestimmte Warnungen für Code Bereiche.</span><span class="sxs-lookup"><span data-stu-id="94b60-109">**#Disable, #Enable** -- Disable and enable specific warnings for regions of code.</span></span>  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 <span data-ttu-id="94b60-110">Sie können auch eine durch Kommas getrennte Liste von Warncodes deaktivieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="94b60-110">You can disable and enable a comma-separated list of warning codes too.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="94b60-111">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="94b60-111">Related Sections</span></span>  

 [<span data-ttu-id="94b60-112">Sprachreferenz zu Visual Basic</span><span class="sxs-lookup"><span data-stu-id="94b60-112">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
  