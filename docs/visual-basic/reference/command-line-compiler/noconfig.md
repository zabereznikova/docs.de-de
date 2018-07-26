---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: bce2d98a8915e80cdecd7b67029b0c872cf70140
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37959578"
---
# <a name="-noconfig"></a><span data-ttu-id="a28d8-102">-noconfig</span><span class="sxs-lookup"><span data-stu-id="a28d8-102">-noconfig</span></span>
<span data-ttu-id="a28d8-103">Gibt an, dass der Compiler nicht automatisch die häufig verwendeten verweisen sollten [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Assemblys oder Import der `System` und `Microsoft.VisualBasic` Namespaces.</span><span class="sxs-lookup"><span data-stu-id="a28d8-103">Specifies that the compiler should not automatically reference the commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a28d8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a28d8-104">Syntax</span></span>  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="a28d8-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a28d8-105">Remarks</span></span>  
 <span data-ttu-id="a28d8-106">Die `-noconfig` -Option weist den Compiler an, nicht mit der Datei "vbc.rsp" zu kompilieren, die im selben Verzeichnis wie die Datei Vbc.exe befindet.</span><span class="sxs-lookup"><span data-stu-id="a28d8-106">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="a28d8-107">Die Datei "vbc.rsp" verweist auf die häufig verwendeten [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Assemblys und importiert die `System` und `Microsoft.VisualBasic` Namespaces.</span><span class="sxs-lookup"><span data-stu-id="a28d8-107">The Vbc.rsp file references the commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="a28d8-108">Der Compiler verweist implizit auf die Assembly "System.dll", es sei denn, die `-nostdlib` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a28d8-108">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="a28d8-109">Die `-nostdlib` -Option weist den Compiler nicht mit Vbc.rsp durch oder automatisch auf die System.dll-Assembly verweisen.</span><span class="sxs-lookup"><span data-stu-id="a28d8-109">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a28d8-110">Die Datei "mscorlib.dll" und "Microsoft.VisualBasic.dll"-Assemblys werden immer auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a28d8-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="a28d8-111">Sie können die Datei "vbc.rsp", um zusätzliche Compileroptionen angeben, die in jeder Kompilierung Vbc.exe enthalten sein sollen (außer bei Angabe der `-noconfig` Option).</span><span class="sxs-lookup"><span data-stu-id="a28d8-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="a28d8-112">Weitere Informationen finden Sie unter [@ (C# Compiler Options)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md) (@ [C#-Compileroptionen]).</span><span class="sxs-lookup"><span data-stu-id="a28d8-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="a28d8-113">Der Compiler verarbeitet die Optionen, die an die `vbc` den letzten Befehl.</span><span class="sxs-lookup"><span data-stu-id="a28d8-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="a28d8-114">Aus diesem Grund überschreibt jede Option in der Befehlszeile die Einstellung für die gleiche Option in der Datei "vbc.rsp".</span><span class="sxs-lookup"><span data-stu-id="a28d8-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a28d8-115">Die `-noconfig` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="a28d8-115">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a28d8-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a28d8-116">See Also</span></span>  
 [<span data-ttu-id="a28d8-117">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a28d8-117">-nostdlib (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nostdlib.md)  
 [<span data-ttu-id="a28d8-118">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="a28d8-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="a28d8-119">@ (Antwortdatei festlegen)</span><span class="sxs-lookup"><span data-stu-id="a28d8-119">@ (Specify Response File)</span></span>](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)  
 [<span data-ttu-id="a28d8-120">-Referenz (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a28d8-120">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
