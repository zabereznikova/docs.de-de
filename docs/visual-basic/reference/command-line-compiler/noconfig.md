---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: ca184fa130d62dc118d0de551ac58f3165064029
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964392"
---
# <a name="-noconfig"></a><span data-ttu-id="558e2-102">-noconfig</span><span class="sxs-lookup"><span data-stu-id="558e2-102">-noconfig</span></span>
<span data-ttu-id="558e2-103">Gibt an, dass der Compiler nicht automatisch auf die häufig verwendeten .NET Framework Assemblys `System` verweisen `Microsoft.VisualBasic` oder die-und-Namespaces importieren soll.</span><span class="sxs-lookup"><span data-stu-id="558e2-103">Specifies that the compiler should not automatically reference the commonly used .NET Framework assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="558e2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="558e2-104">Syntax</span></span>  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="558e2-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="558e2-105">Remarks</span></span>  
 <span data-ttu-id="558e2-106">Die `-noconfig` -Option weist den Compiler an, nicht mit der Datei "Vbc. rsp" zu kompilieren, die sich im selben Verzeichnis wie die Datei "Vbc. exe" befindet.</span><span class="sxs-lookup"><span data-stu-id="558e2-106">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="558e2-107">Die Datei "Vbc. rsp" verweist auf die häufig verwendeten .NET Framework Assemblys und importiert die `System` Namespaces und. `Microsoft.VisualBasic`</span><span class="sxs-lookup"><span data-stu-id="558e2-107">The Vbc.rsp file references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="558e2-108">Der Compiler verweist implizit auf die System. dll-Assembly `-nostdlib` , es sei denn, die Option wird angegeben.</span><span class="sxs-lookup"><span data-stu-id="558e2-108">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="558e2-109">Die `-nostdlib` -Option weist den Compiler an, nicht mit Vbc. rsp zu kompilieren oder automatisch auf die System. dll-Assembly zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="558e2-109">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="558e2-110">Auf die Assemblys "mscorlib. dll" und "Microsoft. VisualBasic. dll" wird immer verwiesen.</span><span class="sxs-lookup"><span data-stu-id="558e2-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="558e2-111">Sie können die Datei Vbc. rsp ändern, um zusätzliche Compileroptionen anzugeben, die in jede Vbc. exe-Kompilierung eingeschlossen werden sollen `-noconfig` (außer bei Angabe der-Option).</span><span class="sxs-lookup"><span data-stu-id="558e2-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="558e2-112">Weitere Informationen finden Sie unter [@ (C# Compiler Options)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md) (@ [C#-Compileroptionen]).</span><span class="sxs-lookup"><span data-stu-id="558e2-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="558e2-113">Der Compiler verarbeitet die Optionen, die an `vbc` den Befehl zuletzt übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="558e2-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="558e2-114">Aus diesem Grund überschreibt jede Option in der Befehlszeile die Einstellung der gleichen Option in der Datei "Vbc. rsp".</span><span class="sxs-lookup"><span data-stu-id="558e2-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="558e2-115">Die `-noconfig` Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="558e2-115">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="558e2-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="558e2-116">See also</span></span>

- [<span data-ttu-id="558e2-117">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="558e2-117">-nostdlib (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [<span data-ttu-id="558e2-118">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="558e2-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="558e2-119">@ (Antwortdatei festlegen)</span><span class="sxs-lookup"><span data-stu-id="558e2-119">@ (Specify Response File)</span></span>](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [<span data-ttu-id="558e2-120">-Verweis (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="558e2-120">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
