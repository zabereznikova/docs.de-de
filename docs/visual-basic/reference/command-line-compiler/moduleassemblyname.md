---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: a612a68cffd927f3e360406cca6d9daae4f66c86
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775624"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="eff29-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="eff29-102">-moduleassemblyname</span></span>
<span data-ttu-id="eff29-103">Gibt den Namen der Assembly an, zu der dieses Modul gehört.</span><span class="sxs-lookup"><span data-stu-id="eff29-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eff29-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eff29-104">Syntax</span></span>  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="eff29-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="eff29-105">Arguments</span></span>  
  
|<span data-ttu-id="eff29-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="eff29-106">Term</span></span>|<span data-ttu-id="eff29-107">Definition</span><span class="sxs-lookup"><span data-stu-id="eff29-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="eff29-108">Der Name der Assembly, zu der dieses Modul gehört</span><span class="sxs-lookup"><span data-stu-id="eff29-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eff29-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eff29-109">Remarks</span></span>  
 <span data-ttu-id="eff29-110">Der Compiler verarbeitet die `-moduleassemblyname`-Option nur, wenn die `-target:module`-Option angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="eff29-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="eff29-111">Dies führt dazu, dass der Compiler ein Modul erstellt.</span><span class="sxs-lookup"><span data-stu-id="eff29-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="eff29-112">Das vom Compiler erstellte Modul ist nur für die mit der `-moduleassemblyname`-Option angegebene Assembly gültig.</span><span class="sxs-lookup"><span data-stu-id="eff29-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="eff29-113">Wenn Sie das Modul in eine andere Assembly verschieben, treten Laufzeitfehler auf.</span><span class="sxs-lookup"><span data-stu-id="eff29-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="eff29-114">Die `-moduleassemblyname`-Option ist nur erforderlich, wenn Folgendes gilt:</span><span class="sxs-lookup"><span data-stu-id="eff29-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
- <span data-ttu-id="eff29-115">Ein Datentyp im Modul benötigt Zugriff auf einen `Friend`-Typ in einer Referenzassembly.</span><span class="sxs-lookup"><span data-stu-id="eff29-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
- <span data-ttu-id="eff29-116">Die Referenzassembly hat der Assembly, in die das Modul integriert wird, Friend-Assembly-Zugriff erteilt.</span><span class="sxs-lookup"><span data-stu-id="eff29-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="eff29-117">Weitere Informationen zur Erstellung eines Moduls finden Sie unter [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="eff29-117">For more information about creating a module, see [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="eff29-118">Weitere Informationen zu Friend-Assemblys finden Sie unter [Friend-Assemblys](../../../standard/assembly/friend.md).</span><span class="sxs-lookup"><span data-stu-id="eff29-118">For more information about friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eff29-119">Die Option `-moduleassemblyname` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über eine Eingabeaufforderung kompilieren.</span><span class="sxs-lookup"><span data-stu-id="eff29-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eff29-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eff29-120">See also</span></span>

- [<span data-ttu-id="eff29-121">How to: Erstellen einer Mehrfachdateiassembly</span><span class="sxs-lookup"><span data-stu-id="eff29-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/build-multifile-assembly.md)
- [<span data-ttu-id="eff29-122">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="eff29-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="eff29-123">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eff29-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="eff29-124">-main</span><span class="sxs-lookup"><span data-stu-id="eff29-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="eff29-125">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eff29-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="eff29-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="eff29-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [<span data-ttu-id="eff29-127">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="eff29-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="eff29-128">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="eff29-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="eff29-129">Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="eff29-129">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
