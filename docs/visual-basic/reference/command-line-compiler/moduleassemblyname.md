---
title: -moduleassemblyname
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
author: rpetrusha
ms.author: ronpett
ms.openlocfilehash: 0a097ea8a7e30f25a0abb877dc496fb81d1c139f
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="03889-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="03889-102">-moduleassemblyname</span></span>
<span data-ttu-id="03889-103">Gibt den Namen der Assembly an, zu der dieses Modul gehört.</span><span class="sxs-lookup"><span data-stu-id="03889-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03889-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="03889-104">Syntax</span></span>  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="03889-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="03889-105">Arguments</span></span>  
  
|<span data-ttu-id="03889-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="03889-106">Term</span></span>|<span data-ttu-id="03889-107">Definition</span><span class="sxs-lookup"><span data-stu-id="03889-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="03889-108">Der Name der Assembly, der dieses Modul angehören soll.</span><span class="sxs-lookup"><span data-stu-id="03889-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03889-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="03889-109">Remarks</span></span>  
 <span data-ttu-id="03889-110">Der Compiler verarbeitet die `-moduleassemblyname` Option nur, wenn die `-target:module` -Option wurde angegeben.</span><span class="sxs-lookup"><span data-stu-id="03889-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="03889-111">Dies bewirkt, dass der Compiler ein Modul zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="03889-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="03889-112">Das Modul, das vom Compiler erstellten gilt nur für die Assembly mit angegebenen die `-moduleassemblyname` Option.</span><span class="sxs-lookup"><span data-stu-id="03889-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="03889-113">Wenn Sie das Modul in einer anderen Assembly platziert wird, werden zur Laufzeit Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="03889-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="03889-114">Die `-moduleassemblyname` Option ist nur erforderlich, wenn Folgendes zutrifft:</span><span class="sxs-lookup"><span data-stu-id="03889-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
-   <span data-ttu-id="03889-115">Ein Datentyp im Modul benötigt Zugriff auf eine `Friend` Typ in einer referenzierten Assembly.</span><span class="sxs-lookup"><span data-stu-id="03889-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
-   <span data-ttu-id="03889-116">Die referenzierte Assembly wurde Friend-Assembly-Zugriff auf die Assembly erteilt werden, in dem das Modul integriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="03889-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="03889-117">Weitere Informationen zum Erstellen eines Moduls finden Sie unter [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="03889-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="03889-118">Weitere Informationen zu Friend-Assemblys finden Sie unter [Friend-Assemblys](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span><span class="sxs-lookup"><span data-stu-id="03889-118">For more information about friend assemblies, see [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03889-119">Die `-moduleassemblyname` Option ist nicht innerhalb der Visual Studio-Entwicklungsumgebung verfügbar, steht er nur, wenn Sie an einer Eingabeaufforderung kompilieren.</span><span class="sxs-lookup"><span data-stu-id="03889-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03889-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03889-120">See Also</span></span>  
 [<span data-ttu-id="03889-121">Gewusst wie: Erstellen einer Mehrfachdateiassembly</span><span class="sxs-lookup"><span data-stu-id="03889-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [<span data-ttu-id="03889-122">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="03889-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="03889-123">-Ziel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03889-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="03889-124">-main</span><span class="sxs-lookup"><span data-stu-id="03889-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)  
 [<span data-ttu-id="03889-125">-Verweis (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03889-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [<span data-ttu-id="03889-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="03889-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)  
 [<span data-ttu-id="03889-127">Assemblys und der globale Assemblycache</span><span class="sxs-lookup"><span data-stu-id="03889-127">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="03889-128">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="03889-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="03889-129">Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="03889-129">Friend Assemblies</span></span>](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)
