---
title: / noconfig | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fe3271e4a119e0c40370a7351bb39188f4d1c8ef
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="noconfig"></a><span data-ttu-id="fc51a-102">/noconfig</span><span class="sxs-lookup"><span data-stu-id="fc51a-102">/noconfig</span></span>
<span data-ttu-id="fc51a-103">Gibt an, dass der Compiler nicht automatisch der häufig verwendeten verweisen sollten [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Assemblys oder Importieren der `System` und `Microsoft.VisualBasic` Namespaces.</span><span class="sxs-lookup"><span data-stu-id="fc51a-103">Specifies that the compiler should not automatically reference the commonly used [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc51a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc51a-104">Syntax</span></span>  
  
```  
/noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="fc51a-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fc51a-105">Remarks</span></span>  
 <span data-ttu-id="fc51a-106">Die `/noconfig` Option weist den Compiler an, nicht mit der Datei Vbc.rsp kompilieren, die sich im gleichen Verzeichnis wie die Datei Vbc.exe befindet.</span><span class="sxs-lookup"><span data-stu-id="fc51a-106">The `/noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="fc51a-107">Die Datei Vbc.rsp verweist auf die häufig verwendeten [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Assemblys und importiert die `System` und `Microsoft.VisualBasic` Namespaces.</span><span class="sxs-lookup"><span data-stu-id="fc51a-107">The Vbc.rsp file references the commonly used [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="fc51a-108">Der Compiler verweist implizit auf die Assembly System.dll, es sei denn, die `/nostdlib` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fc51a-108">The compiler implicitly references the System.dll assembly unless the `/nostdlib` option is specified.</span></span> <span data-ttu-id="fc51a-109">Die `/nostdlib` Option weist den Compiler nicht mit Vbc.rsp kompiliert oder automatisch auf die Assembly System.dll.</span><span class="sxs-lookup"><span data-stu-id="fc51a-109">The `/nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc51a-110">Die "mscorlib.dll" und "Microsoft.VisualBasic.dll" wird immer verwiesen.</span><span class="sxs-lookup"><span data-stu-id="fc51a-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="fc51a-111">Sie können die Datei Vbc.rsp bearbeiten zusätzliche Compileroptionen angibt, die in jeder Vbc.exe-Kompilierung enthalten sein soll (außer bei Angabe der `/noconfig` Option).</span><span class="sxs-lookup"><span data-stu-id="fc51a-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `/noconfig` option).</span></span> <span data-ttu-id="fc51a-112">Weitere Informationen finden Sie unter [@ (C# Compiler Options)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md) (@ [C#-Compileroptionen]).</span><span class="sxs-lookup"><span data-stu-id="fc51a-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="fc51a-113">Der Compiler verarbeitet die Optionen zum Übergeben der `vbc` den letzten Befehl.</span><span class="sxs-lookup"><span data-stu-id="fc51a-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="fc51a-114">Aus diesem Grund überschreibt jede Option in der Befehlszeile die Einstellung derselben Option in der Vbc.rsp-Datei.</span><span class="sxs-lookup"><span data-stu-id="fc51a-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc51a-115">Die `/noconfig` Option ist nicht verfügbar in der Visual Studio Development Environment; es ist nur beim Kompilieren von der Befehlszeile aus.</span><span class="sxs-lookup"><span data-stu-id="fc51a-115">The `/noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc51a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc51a-116">See Also</span></span>  
 <span data-ttu-id="fc51a-117">[/ nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md) </span><span class="sxs-lookup"><span data-stu-id="fc51a-117">[/nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md) </span></span>  
<span data-ttu-id="fc51a-118"> [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="fc51a-118"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="fc51a-119"> [@ (Antwortdatei festlegen)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md) </span><span class="sxs-lookup"><span data-stu-id="fc51a-119"> [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md) </span></span>  
<span data-ttu-id="fc51a-120"> [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)</span><span class="sxs-lookup"><span data-stu-id="fc51a-120"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)</span></span>
