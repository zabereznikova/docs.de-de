---
title: '#<a name="externalsource-directive"></a>ExternalSource-Direktive'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "160"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f90b838e50b65b8652cd9cf6f6ee084e9552f025
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="externalsource-directive"></a><span data-ttu-id="56225-102">#ExternalSource-Anweisung</span><span class="sxs-lookup"><span data-stu-id="56225-102">#ExternalSource Directive</span></span>
<span data-ttu-id="56225-103">Gibt eine Zuordnung zwischen bestimmten Quellcodezeilen und Text für die Quelle extern an.</span><span class="sxs-lookup"><span data-stu-id="56225-103">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56225-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="56225-104">Syntax</span></span>  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="56225-105">Teile</span><span class="sxs-lookup"><span data-stu-id="56225-105">Parts</span></span>  
 `StringLiteral`  
 <span data-ttu-id="56225-106">Der Pfad mit der externen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="56225-106">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="56225-107">Die Zeilennummer der ersten Zeile der externen Quelle.</span><span class="sxs-lookup"><span data-stu-id="56225-107">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="56225-108">Die Zeile, in dem der Fehler in der externen Quelle auf.</span><span class="sxs-lookup"><span data-stu-id="56225-108">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="56225-109">Beendet den `#ExternalSource`-Block.</span><span class="sxs-lookup"><span data-stu-id="56225-109">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56225-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="56225-110">Remarks</span></span>  
 <span data-ttu-id="56225-111">Diese Richtlinie wird nur durch den Compiler und der Debugger verwendet.</span><span class="sxs-lookup"><span data-stu-id="56225-111">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="56225-112">Eine Quelldatei eventuell Direktiven für den externen Code, die was darauf hindeuten, eine Zuordnung zwischen bestimmten Codezeilen in der Quelldatei und Text außerhalb der Quelle, z. B. eine ASPX-Datei dass.</span><span class="sxs-lookup"><span data-stu-id="56225-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="56225-113">Wenn Fehler in den angegebenen Quellcode während der Kompilierung festgestellt werden, werden sie identifiziert als aus der externen Quelle stammen.</span><span class="sxs-lookup"><span data-stu-id="56225-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="56225-114">Die externe Quelle Direktiven haben keine Auswirkungen auf die Kompilierung und können nicht geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="56225-114">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="56225-115">Sie werden von der Anwendung nur für die interne Verwendung gedacht.</span><span class="sxs-lookup"><span data-stu-id="56225-115">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56225-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56225-116">See Also</span></span>  
 [<span data-ttu-id="56225-117">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="56225-117">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
