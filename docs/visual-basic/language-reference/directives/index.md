---
title: Anweisungen
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: b5fcf3cb8801bc99dd2096c28cc41ebefeb34592
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409997"
---
# <a name="directives-visual-basic"></a><span data-ttu-id="09b7a-102">Anweisungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09b7a-102">Directives (Visual Basic)</span></span>

<span data-ttu-id="09b7a-103">In den Themen in diesem Abschnitt werden die Visual Basic-Quellcode-Compilerdirektiven dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="09b7a-103">The topics in this section document the Visual Basic source code compiler directives.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="09b7a-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="09b7a-104">In This Section</span></span>  

 <span data-ttu-id="09b7a-105">[#Const Direktive](const-directive.md) : Definieren einer Compilerkonstante</span><span class="sxs-lookup"><span data-stu-id="09b7a-105">[#Const Directive](const-directive.md) -- Define a compiler constant</span></span>  
  
 <span data-ttu-id="09b7a-106">[#ExternalSource-Direktive](externalsource-directive.md) : gibt eine Zuordnung zwischen Quellzeilen und Text außerhalb der Quelle an.</span><span class="sxs-lookup"><span data-stu-id="09b7a-106">[#ExternalSource Directive](externalsource-directive.md) -- Indicate a mapping between source lines and text external to the source</span></span>  
  
 <span data-ttu-id="09b7a-107">[#If... Then... #else Direktiven](if-then-else-directives.md) : Kompilieren Sie ausgewählte Code Blöcke.</span><span class="sxs-lookup"><span data-stu-id="09b7a-107">[#If...Then...#Else Directives](if-then-else-directives.md) -- Compile selected blocks of code</span></span>  
  
 <span data-ttu-id="09b7a-108">[#Region Direktive](region-directive.md) : reduzieren und Ausblenden von Code Abschnitten im Visual Studio-Editor</span><span class="sxs-lookup"><span data-stu-id="09b7a-108">[#Region Directive](region-directive.md) -- Collapse and hide sections of code in the Visual Studio editor</span></span>  
  
 <span data-ttu-id="09b7a-109">**#Disable #enable** -deaktivieren und aktivieren Sie bestimmte Warnungen für Code Bereiche.</span><span class="sxs-lookup"><span data-stu-id="09b7a-109">**#Disable, #Enable** -- Disable and enable specific warnings for regions of code.</span></span>  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 <span data-ttu-id="09b7a-110">Sie können auch eine durch Kommas getrennte Liste von Warncodes deaktivieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="09b7a-110">You can disable and enable a comma-separated list of warning codes too.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="09b7a-111">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="09b7a-111">Related Sections</span></span>  

 [<span data-ttu-id="09b7a-112">Sprachreferenz zu Visual Basic</span><span class="sxs-lookup"><span data-stu-id="09b7a-112">Visual Basic Language Reference</span></span>](../index.md)  
  