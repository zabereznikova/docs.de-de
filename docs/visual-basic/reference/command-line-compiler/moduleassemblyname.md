---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: 9fb9287f9472d4b33eff4cb601aff5eed370b2c0
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91065566"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="b4f65-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="b4f65-102">-moduleassemblyname</span></span>

<span data-ttu-id="b4f65-103">Gibt den Namen der Assembly an, zu der dieses Modul gehört.</span><span class="sxs-lookup"><span data-stu-id="b4f65-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4f65-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4f65-104">Syntax</span></span>  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="b4f65-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="b4f65-105">Arguments</span></span>  
  
|<span data-ttu-id="b4f65-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="b4f65-106">Term</span></span>|<span data-ttu-id="b4f65-107">Definition</span><span class="sxs-lookup"><span data-stu-id="b4f65-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="b4f65-108">Der Name der Assembly, zu der dieses Modul gehört</span><span class="sxs-lookup"><span data-stu-id="b4f65-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4f65-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b4f65-109">Remarks</span></span>  

 <span data-ttu-id="b4f65-110">Der Compiler verarbeitet die `-moduleassemblyname`-Option nur, wenn die `-target:module`-Option angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="b4f65-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="b4f65-111">Dies führt dazu, dass der Compiler ein Modul erstellt.</span><span class="sxs-lookup"><span data-stu-id="b4f65-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="b4f65-112">Das vom Compiler erstellte Modul ist nur für die mit der `-moduleassemblyname`-Option angegebene Assembly gültig.</span><span class="sxs-lookup"><span data-stu-id="b4f65-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="b4f65-113">Wenn Sie das Modul in eine andere Assembly verschieben, treten Laufzeitfehler auf.</span><span class="sxs-lookup"><span data-stu-id="b4f65-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="b4f65-114">Die `-moduleassemblyname`-Option ist nur erforderlich, wenn Folgendes gilt:</span><span class="sxs-lookup"><span data-stu-id="b4f65-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
- <span data-ttu-id="b4f65-115">Ein Datentyp im Modul benötigt Zugriff auf einen `Friend`-Typ in einer Referenzassembly.</span><span class="sxs-lookup"><span data-stu-id="b4f65-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
- <span data-ttu-id="b4f65-116">Die Referenzassembly hat der Assembly, in die das Modul integriert wird, Friend-Assembly-Zugriff erteilt.</span><span class="sxs-lookup"><span data-stu-id="b4f65-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="b4f65-117">Weitere Informationen zur Erstellung eines Moduls finden Sie unter [-target (Visual Basic)](target.md).</span><span class="sxs-lookup"><span data-stu-id="b4f65-117">For more information about creating a module, see [-target (Visual Basic)](target.md).</span></span> <span data-ttu-id="b4f65-118">Weitere Informationen zu Friend-Assemblys finden Sie unter [Friend-Assemblys](../../../standard/assembly/friend.md).</span><span class="sxs-lookup"><span data-stu-id="b4f65-118">For more information about friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b4f65-119">Die Option `-moduleassemblyname` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über eine Eingabeaufforderung kompilieren.</span><span class="sxs-lookup"><span data-stu-id="b4f65-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4f65-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4f65-120">See also</span></span>

- [<span data-ttu-id="b4f65-121">How to: Erstellen einer Mehrfachdateiassembly</span><span class="sxs-lookup"><span data-stu-id="b4f65-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/build-multifile-assembly.md)
- [<span data-ttu-id="b4f65-122">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="b4f65-122">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="b4f65-123">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4f65-123">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="b4f65-124">-main</span><span class="sxs-lookup"><span data-stu-id="b4f65-124">-main</span></span>](main.md)
- [<span data-ttu-id="b4f65-125">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4f65-125">-reference (Visual Basic)</span></span>](reference.md)
- [<span data-ttu-id="b4f65-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="b4f65-126">-addmodule</span></span>](addmodule.md)
- [<span data-ttu-id="b4f65-127">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="b4f65-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="b4f65-128">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="b4f65-128">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="b4f65-129">Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="b4f65-129">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
