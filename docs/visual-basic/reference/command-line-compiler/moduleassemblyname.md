---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: 5b26e36346858d95526f5d5ce7d4645bea1dbe05
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005477"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="ea1eb-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="ea1eb-102">-moduleassemblyname</span></span>
<span data-ttu-id="ea1eb-103">Gibt den Namen der Assembly an, zu der dieses Modul gehört.</span><span class="sxs-lookup"><span data-stu-id="ea1eb-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea1eb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea1eb-104">Syntax</span></span>  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="ea1eb-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="ea1eb-105">Arguments</span></span>  
  
|<span data-ttu-id="ea1eb-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="ea1eb-106">Term</span></span>|<span data-ttu-id="ea1eb-107">Definition</span><span class="sxs-lookup"><span data-stu-id="ea1eb-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="ea1eb-108">Der Name der Assembly, zu der dieses Modul gehört.</span><span class="sxs-lookup"><span data-stu-id="ea1eb-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea1eb-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ea1eb-109">Remarks</span></span>  
 <span data-ttu-id="ea1eb-110">Der Compiler verarbeitet die Option "`-moduleassemblyname`" nur, wenn die Option "`-target:module`" angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="ea1eb-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="ea1eb-111">Dies bewirkt, dass der Compiler ein Modul erstellt.</span><span class="sxs-lookup"><span data-stu-id="ea1eb-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="ea1eb-112">Das vom Compiler erstellte Modul ist nur für die mit der Option "`-moduleassemblyname`" angegebene Assembly gültig.</span><span class="sxs-lookup"><span data-stu-id="ea1eb-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="ea1eb-113">Wenn Sie das Modul in einer anderen Assembly platzieren, treten Laufzeitfehler auf.</span><span class="sxs-lookup"><span data-stu-id="ea1eb-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="ea1eb-114">Die Option "`-moduleassemblyname`" ist nur erforderlich, wenn Folgendes zutrifft:</span><span class="sxs-lookup"><span data-stu-id="ea1eb-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
- <span data-ttu-id="ea1eb-115">Ein Datentyp im Modul benötigt Zugriff auf einen `Friend`-Typ in einer Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="ea1eb-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
- <span data-ttu-id="ea1eb-116">Die Assembly, auf die verwiesen wird, hat Friend-Assembly-Zugriff auf die Assembly erteilt, in der das Modul erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ea1eb-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="ea1eb-117">Weitere Informationen zum Erstellen eines Moduls finden Sie unter [/Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="ea1eb-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="ea1eb-118">Weitere Informationen zu Friend-Assemblys finden Sie unter [Friend](../../../standard/assembly/friend.md)-Assemblys</span><span class="sxs-lookup"><span data-stu-id="ea1eb-118">For more information about friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ea1eb-119">Die Option "`-moduleassemblyname`" ist innerhalb der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über eine Eingabeaufforderung kompilieren.</span><span class="sxs-lookup"><span data-stu-id="ea1eb-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea1eb-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea1eb-120">See also</span></span>

- [<span data-ttu-id="ea1eb-121">Vorgehensweise: Erstellen einer Mehrfachdateiassembly</span><span class="sxs-lookup"><span data-stu-id="ea1eb-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/build-multifile-assembly.md)
- [<span data-ttu-id="ea1eb-122">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="ea1eb-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="ea1eb-123">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea1eb-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="ea1eb-124">-main</span><span class="sxs-lookup"><span data-stu-id="ea1eb-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="ea1eb-125">-Verweis (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea1eb-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="ea1eb-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="ea1eb-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [<span data-ttu-id="ea1eb-127">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="ea1eb-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="ea1eb-128">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="ea1eb-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="ea1eb-129">Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="ea1eb-129">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
