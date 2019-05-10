---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: 70cef109e4f2947fb4e38b9bfd19433257cce136
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663507"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="7dc22-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="7dc22-102">-moduleassemblyname</span></span>
<span data-ttu-id="7dc22-103">Gibt den Namen der Assembly an, zu der dieses Modul gehört.</span><span class="sxs-lookup"><span data-stu-id="7dc22-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dc22-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7dc22-104">Syntax</span></span>  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="7dc22-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="7dc22-105">Arguments</span></span>  
  
|<span data-ttu-id="7dc22-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="7dc22-106">Term</span></span>|<span data-ttu-id="7dc22-107">Definition</span><span class="sxs-lookup"><span data-stu-id="7dc22-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="7dc22-108">Der Name der Assembly, der dieses Modul eine angehören soll.</span><span class="sxs-lookup"><span data-stu-id="7dc22-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7dc22-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7dc22-109">Remarks</span></span>  
 <span data-ttu-id="7dc22-110">Der Compiler verarbeitet die `-moduleassemblyname` Option nur, wenn die `-target:module` -Option wurde angegeben.</span><span class="sxs-lookup"><span data-stu-id="7dc22-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="7dc22-111">Dies bewirkt, dass den Compiler ein Modul zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7dc22-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="7dc22-112">Das Modul, das vom Compiler erstellten gilt nur für die Assembly mit angegebenen die `-moduleassemblyname` Option.</span><span class="sxs-lookup"><span data-stu-id="7dc22-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="7dc22-113">Wenn Sie das Modul in einer anderen Assembly platzieren, werden Laufzeitfehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="7dc22-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="7dc22-114">Die `-moduleassemblyname` Option ist nur erforderlich, wenn Folgendes zutrifft:</span><span class="sxs-lookup"><span data-stu-id="7dc22-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
- <span data-ttu-id="7dc22-115">Ein Datentyp in das Modul benötigt Zugriff auf eine `Friend` Typ in einer referenzierten Assembly.</span><span class="sxs-lookup"><span data-stu-id="7dc22-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
- <span data-ttu-id="7dc22-116">Die referenzierte Assembly wurde Friend-Assembly-Zugriff auf die Assembly gewährt werden, in dem das Modul erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="7dc22-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="7dc22-117">Weitere Informationen zum Erstellen eines Moduls finden Sie unter [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="7dc22-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="7dc22-118">Weitere Informationen zu Friend-Assemblys, finden Sie unter [Friend-Assemblys](../../../standard/assembly/friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="7dc22-118">For more information about friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend-assemblies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7dc22-119">Die `-moduleassemblyname` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie an einer Eingabeaufforderung kompilieren.</span><span class="sxs-lookup"><span data-stu-id="7dc22-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dc22-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7dc22-120">See also</span></span>

- [<span data-ttu-id="7dc22-121">Vorgehensweise: Erstellen einer Mehrfachdateiassembly</span><span class="sxs-lookup"><span data-stu-id="7dc22-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
- [<span data-ttu-id="7dc22-122">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="7dc22-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="7dc22-123">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7dc22-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="7dc22-124">-main</span><span class="sxs-lookup"><span data-stu-id="7dc22-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="7dc22-125">-Referenz (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7dc22-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="7dc22-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="7dc22-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [<span data-ttu-id="7dc22-127">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="7dc22-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="7dc22-128">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="7dc22-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="7dc22-129">Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="7dc22-129">Friend Assemblies</span></span>](../../../standard/assembly/friend-assemblies.md)
