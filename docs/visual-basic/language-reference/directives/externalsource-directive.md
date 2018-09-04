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
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43556317"
---
# <a name="externalsource-directive"></a><span data-ttu-id="936c1-102">#ExternalSource-Anweisung</span><span class="sxs-lookup"><span data-stu-id="936c1-102">#ExternalSource Directive</span></span>
<span data-ttu-id="936c1-103">Gibt eine Zuordnung zwischen bestimmten Codezeilen an Quelle und dem Text für die Quelle extern an.</span><span class="sxs-lookup"><span data-stu-id="936c1-103">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="936c1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="936c1-104">Syntax</span></span>  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="936c1-105">Teile</span><span class="sxs-lookup"><span data-stu-id="936c1-105">Parts</span></span>  
 `StringLiteral`  
 <span data-ttu-id="936c1-106">Der Pfad zu der externen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="936c1-106">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="936c1-107">Die Nummer der Zeile der ersten Zeile der externen Quelle.</span><span class="sxs-lookup"><span data-stu-id="936c1-107">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="936c1-108">Die Zeile, in dem sich der Fehler in der externen Datenquelle auf.</span><span class="sxs-lookup"><span data-stu-id="936c1-108">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="936c1-109">Beendet den `#ExternalSource`-Block.</span><span class="sxs-lookup"><span data-stu-id="936c1-109">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="936c1-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="936c1-110">Remarks</span></span>  
 <span data-ttu-id="936c1-111">Diese Richtlinie wird nur durch den Compiler und der Debugger verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="936c1-111">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="936c1-112">Eine Quelldatei kann Direktiven für externe Quellen enthalten, die eine Zuordnung zwischen bestimmten Codezeilen in der Quelldatei zu externem Text an der Quelle, z. B. eine ASPX-Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="936c1-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="936c1-113">Wenn Fehler in den angegebenen Quellcode während der Kompilierung auftreten, werden sie identifiziert, da Sie von der externen Quelle stammen.</span><span class="sxs-lookup"><span data-stu-id="936c1-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="936c1-114">Externe quelldirektiven haben keine Auswirkungen auf die Kompilierung und können nicht geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="936c1-114">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="936c1-115">Sie sind von der Anwendung nur für die interne Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="936c1-115">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="936c1-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="936c1-116">See Also</span></span>  
 [<span data-ttu-id="936c1-117">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="936c1-117">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
