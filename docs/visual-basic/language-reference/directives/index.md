---
title: Anweisungen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: 38d54feae5cf7bf41a825d1f6000811e2b56f319
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44187275"
---
# <a name="directives-visual-basic"></a><span data-ttu-id="e309a-102">Anweisungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e309a-102">Directives (Visual Basic)</span></span>
<span data-ttu-id="e309a-103">In den Themen in diesem Abschnitt werden die Visual Basic-Quellcode-Compileranweisungen dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="e309a-103">The topics in this section document the Visual Basic source code compiler directives.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e309a-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e309a-104">In This Section</span></span>  
 <span data-ttu-id="e309a-105">[#Const-Anweisung](../../../visual-basic/language-reference/directives/const-directive.md) – Definieren einer Compilerkonstanten</span><span class="sxs-lookup"><span data-stu-id="e309a-105">[#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md) -- Define a compiler constant</span></span>  
  
 <span data-ttu-id="e309a-106">[#ExternalSource-Anweisung](../../../visual-basic/language-reference/directives/externalsource-directive.md) – angeben einer Zuordnung zwischen Quellzeilen und Text für die Quelle extern</span><span class="sxs-lookup"><span data-stu-id="e309a-106">[#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md) -- Indicate a mapping between source lines and text external to the source</span></span>  
  
 <span data-ttu-id="e309a-107">[#If... ... #Else Direktiven](../../../visual-basic/language-reference/directives/if-then-else-directives.md) --kompilieren Sie ausgewählte Codeblöcke</span><span class="sxs-lookup"><span data-stu-id="e309a-107">[#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) -- Compile selected blocks of code</span></span>  
  
 <span data-ttu-id="e309a-108">[#Region-Anweisung](../../../visual-basic/language-reference/directives/region-directive.md) --reduzieren und Ausblenden von Codeabschnitten im Visual Studio-Editor</span><span class="sxs-lookup"><span data-stu-id="e309a-108">[#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) -- Collapse and hide sections of code in the Visual Studio editor</span></span>  
  
 <span data-ttu-id="e309a-109">**#Disable, #Enable** --deaktivieren und aktivieren Sie bestimmte Warnungen für Codebereiche.</span><span class="sxs-lookup"><span data-stu-id="e309a-109">**#Disable, #Enable** -- Disable and enable specific warnings for regions of code.</span></span>  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 <span data-ttu-id="e309a-110">Sie können auch eine durch Kommas getrennte Liste von Warncodes deaktivieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e309a-110">You can disable and enable a comma-separated list of warning codes too.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e309a-111">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="e309a-111">Related Sections</span></span>  
 [<span data-ttu-id="e309a-112">Sprachreferenz zu Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e309a-112">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
  
 [<span data-ttu-id="e309a-113">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e309a-113">Visual Basic</span></span>](../../../visual-basic/index.md)
