---
title: '#ExternalSource-Direktive (Visual Basic)'
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
ms.openlocfilehash: ac7096e998dd8d2a416dc739e1d7625e1abff7a6
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696823"
---
# <a name="externalsource-directive"></a><span data-ttu-id="a607f-102">#ExternalSource-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a607f-102">#ExternalSource Directive</span></span>
<span data-ttu-id="a607f-103">Gibt eine Zuordnung zwischen bestimmten Quell Codezeilen und Text außerhalb der Quelle an.</span><span class="sxs-lookup"><span data-stu-id="a607f-103">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a607f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a607f-104">Syntax</span></span>  
  
```vb  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="a607f-105">Teile</span><span class="sxs-lookup"><span data-stu-id="a607f-105">Parts</span></span>  
 `StringLiteral`  
 <span data-ttu-id="a607f-106">Der Pfad zur externen Quelle.</span><span class="sxs-lookup"><span data-stu-id="a607f-106">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="a607f-107">Die Zeilennummer der ersten Zeile der externen Quelle.</span><span class="sxs-lookup"><span data-stu-id="a607f-107">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="a607f-108">Die Zeile, in der der Fehler in der externen Quelle auftritt.</span><span class="sxs-lookup"><span data-stu-id="a607f-108">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="a607f-109">Beendet den `#ExternalSource`-Block.</span><span class="sxs-lookup"><span data-stu-id="a607f-109">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a607f-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a607f-110">Remarks</span></span>  
 <span data-ttu-id="a607f-111">Diese Direktive wird nur vom Compiler und vom Debugger verwendet.</span><span class="sxs-lookup"><span data-stu-id="a607f-111">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="a607f-112">Eine Quelldatei kann externe Quell Direktiven enthalten, die eine Zuordnung zwischen bestimmten Codezeilen in der Quelldatei und Text außerhalb der Quelle, z. b. einer ASPX-Datei, angeben.</span><span class="sxs-lookup"><span data-stu-id="a607f-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="a607f-113">Wenn während der Kompilierung Fehler im vorgesehenen Quellcode auftreten, werden Sie als aus der externen Quelle stammende identifiziert.</span><span class="sxs-lookup"><span data-stu-id="a607f-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="a607f-114">Externe Quell Direktiven haben keine Auswirkung auf die Kompilierung und können nicht eingebettet werden.</span><span class="sxs-lookup"><span data-stu-id="a607f-114">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="a607f-115">Sie sind nur für die interne Verwendung durch die Anwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="a607f-115">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a607f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a607f-116">See also</span></span>

- [<span data-ttu-id="a607f-117">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="a607f-117">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
