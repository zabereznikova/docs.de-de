---
title: '#ExternalSource-Anweisung (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- '#Externalsource'
- '#ExternalSource'
- vb.ExternalSource
- Externalsource
- vb.#ExternalSource
- ExternalSource
helpviewer_keywords:
- ExternalSource directive (#ExternalSource)
- '#ExternalSource directive'
ms.assetid: 243bc6a2-34c3-4eeb-a776-9fd2bf988149
ms.openlocfilehash: dcde8507eb033d0a47d5c5d3fa36176cd63b0856
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861785"
---
# <a name="externalsource-directive"></a><span data-ttu-id="6759d-102">#ExternalSource-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6759d-102">#ExternalSource Directive</span></span>
<span data-ttu-id="6759d-103">Gibt eine Zuordnung zwischen bestimmten Codezeilen an Quelle und dem Text für die Quelle extern an.</span><span class="sxs-lookup"><span data-stu-id="6759d-103">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6759d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6759d-104">Syntax</span></span>  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="6759d-105">Teile</span><span class="sxs-lookup"><span data-stu-id="6759d-105">Parts</span></span>  
 `StringLiteral`  
 <span data-ttu-id="6759d-106">Der Pfad zu der externen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="6759d-106">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="6759d-107">Die Nummer der Zeile der ersten Zeile der externen Quelle.</span><span class="sxs-lookup"><span data-stu-id="6759d-107">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="6759d-108">Die Zeile, in dem sich der Fehler in der externen Datenquelle auf.</span><span class="sxs-lookup"><span data-stu-id="6759d-108">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="6759d-109">Beendet den `#ExternalSource`-Block.</span><span class="sxs-lookup"><span data-stu-id="6759d-109">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6759d-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6759d-110">Remarks</span></span>  
 <span data-ttu-id="6759d-111">Diese Richtlinie wird nur durch den Compiler und der Debugger verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6759d-111">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="6759d-112">Eine Quelldatei kann Direktiven für externe Quellen enthalten, die eine Zuordnung zwischen bestimmten Codezeilen in der Quelldatei zu externem Text an der Quelle, z. B. eine ASPX-Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="6759d-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="6759d-113">Wenn Fehler in den angegebenen Quellcode während der Kompilierung auftreten, werden sie identifiziert, da Sie von der externen Quelle stammen.</span><span class="sxs-lookup"><span data-stu-id="6759d-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="6759d-114">Externe quelldirektiven haben keine Auswirkungen auf die Kompilierung und können nicht geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="6759d-114">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="6759d-115">Sie sind von der Anwendung nur für die interne Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="6759d-115">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6759d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6759d-116">See Also</span></span>  
 [<span data-ttu-id="6759d-117">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="6759d-117">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
