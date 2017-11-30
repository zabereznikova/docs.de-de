---
title: -target:module (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /target:module
helpviewer_keywords:
- -target compiler options [C#], /target:module
- target compiler options [C#], /target:module
- /target compiler options [C#], /target:module
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2b54ea9085ecc23d4a535d440d0634c997f22615
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="targetmodule-c-compiler-options"></a><span data-ttu-id="5dd78-102">/target:module (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="5dd78-102">/target:module (C# Compiler Options)</span></span>
<span data-ttu-id="5dd78-103">Diese Option bewirkt, dass der Compiler kein Assemblymanifest generiert.</span><span class="sxs-lookup"><span data-stu-id="5dd78-103">This option causes the compiler to not generate an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dd78-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5dd78-104">Syntax</span></span>  
  
```console  
/target:module  
```  
  
## <a name="remarks"></a><span data-ttu-id="5dd78-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5dd78-105">Remarks</span></span>  
 <span data-ttu-id="5dd78-106">Standardmäßig weist die Ausgabedatei, die durch Kompilieren mit dieser Option erstellt wird, eine Dateierweiterung .NETMODULE auf.</span><span class="sxs-lookup"><span data-stu-id="5dd78-106">By default, the output file created by compiling with this option will have an extension of .netmodule.</span></span>  
  
 <span data-ttu-id="5dd78-107">Eine Datei, die nicht über ein Assemblymanifest verfügt, kann nicht von der Common Language Runtime von .NET Framework geladen werden.</span><span class="sxs-lookup"><span data-stu-id="5dd78-107">A file that does not have an assembly manifest cannot be loaded by the .NET Framework common language runtime.</span></span> <span data-ttu-id="5dd78-108">Allerdings kann eine solche Datei in das Assemblymanifest mithilfe von [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md) integriert werden.</span><span class="sxs-lookup"><span data-stu-id="5dd78-108">However, such a file can be incorporated into the assembly manifest of an assembly by means of [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="5dd78-109">Wird mehr als ein Modul in einer einzigen Kompilierung erstellt, werden [interne](../../../csharp/language-reference/keywords/internal.md) Typen in einem Modul für andere Module in der Kompilierung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5dd78-109">If more than one module is created in a single compilation, [internal](../../../csharp/language-reference/keywords/internal.md) types in one module will be available to other modules in the compilation.</span></span> <span data-ttu-id="5dd78-110">Wenn der Code in einem Modul auf `internal`-Typen in einem anderen Modul verweist, dann müssen beide Module in ein Assemblymanifest aufgenommen werden, mithilfe von **/addmodule**.</span><span class="sxs-lookup"><span data-stu-id="5dd78-110">When code in one module references `internal` types in another module, then both modules must be incorporated into an assembly manifest, by means of **/addmodule**.</span></span>  
  
 <span data-ttu-id="5dd78-111">Das Erstellen eines Moduls wird in der Visual Studio-Entwicklungsumgebung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5dd78-111">Creating a module is not supported in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="5dd78-112">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="5dd78-112">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5dd78-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5dd78-113">Example</span></span>  
 <span data-ttu-id="5dd78-114">Kompilieren Sie `in.cs`, und `in.netmodule` wird erstellt:</span><span class="sxs-lookup"><span data-stu-id="5dd78-114">Compile `in.cs`, creating `in.netmodule`:</span></span>  
  
```console  
csc /target:module in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="5dd78-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5dd78-115">See Also</span></span>  
 [<span data-ttu-id="5dd78-116">/ target (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="5dd78-116">/target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [<span data-ttu-id="5dd78-117">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="5dd78-117">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
