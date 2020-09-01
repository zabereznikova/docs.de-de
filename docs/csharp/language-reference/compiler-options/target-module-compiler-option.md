---
description: -target:module (C#-Compileroptionen)
title: -target:module (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /target:module
helpviewer_keywords:
- -target compiler options [C#], /target:module
- target compiler options [C#], /target:module
- /target compiler options [C#], /target:module
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
ms.openlocfilehash: 2c592d2fe001bb0908a06a6eb3287a39040b8715
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128451"
---
# <a name="-targetmodule-c-compiler-options"></a><span data-ttu-id="a39dd-103">-target:module (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="a39dd-103">-target:module (C# Compiler Options)</span></span>
<span data-ttu-id="a39dd-104">Diese Option bewirkt, dass der Compiler kein Assemblymanifest generiert.</span><span class="sxs-lookup"><span data-stu-id="a39dd-104">This option causes the compiler to not generate an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a39dd-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a39dd-105">Syntax</span></span>  
  
```console  
-target:module  
```  
  
## <a name="remarks"></a><span data-ttu-id="a39dd-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a39dd-106">Remarks</span></span>  
 <span data-ttu-id="a39dd-107">Standardmäßig weist die Ausgabedatei, die durch Kompilieren mit dieser Option erstellt wird, eine Dateierweiterung .NETMODULE auf.</span><span class="sxs-lookup"><span data-stu-id="a39dd-107">By default, the output file created by compiling with this option will have an extension of .netmodule.</span></span>  
  
 <span data-ttu-id="a39dd-108">Eine Datei, die nicht über ein Assemblymanifest verfügt, kann nicht von der Common Language Runtime von .NET Framework geladen werden.</span><span class="sxs-lookup"><span data-stu-id="a39dd-108">A file that does not have an assembly manifest cannot be loaded by the .NET Framework common language runtime.</span></span> <span data-ttu-id="a39dd-109">Allerdings kann eine solche Datei mithilfe von [-addmodule](./addmodule-compiler-option.md) in das Assemblymanifest integriert werden.</span><span class="sxs-lookup"><span data-stu-id="a39dd-109">However, such a file can be incorporated into the assembly manifest of an assembly by means of [-addmodule](./addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="a39dd-110">Wird mehr als ein Modul in einer einzigen Kompilierung erstellt, werden [interne](../keywords/internal.md) Typen in einem Modul für andere Module in der Kompilierung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a39dd-110">If more than one module is created in a single compilation, [internal](../keywords/internal.md) types in one module will be available to other modules in the compilation.</span></span> <span data-ttu-id="a39dd-111">Wenn der Code in einem Modul auf `internal`-Typen in einem anderen Modul verweist, dann müssen beide Module mithilfe von **-addmodule** in ein Assemblymanifest aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="a39dd-111">When code in one module references `internal` types in another module, then both modules must be incorporated into an assembly manifest, by means of **-addmodule**.</span></span>  
  
 <span data-ttu-id="a39dd-112">Das Erstellen eines Moduls wird in der Visual Studio-Entwicklungsumgebung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a39dd-112">Creating a module is not supported in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="a39dd-113">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="a39dd-113">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a39dd-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a39dd-114">Example</span></span>  
 <span data-ttu-id="a39dd-115">Kompilieren Sie `in.cs`, und `in.netmodule` wird erstellt:</span><span class="sxs-lookup"><span data-stu-id="a39dd-115">Compile `in.cs`, creating `in.netmodule`:</span></span>  
  
```console  
csc -target:module in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="a39dd-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a39dd-116">See also</span></span>

- [<span data-ttu-id="a39dd-117">-target (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="a39dd-117">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="a39dd-118">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="a39dd-118">C# Compiler Options</span></span>](./index.md)
