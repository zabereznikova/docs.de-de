---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: ee7cd1b8039a8d9312a8b058cc85c41ca536ed2b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401939"
---
# <a name="-noconfig"></a><span data-ttu-id="50bbb-102">-noconfig</span><span class="sxs-lookup"><span data-stu-id="50bbb-102">-noconfig</span></span>
<span data-ttu-id="50bbb-103">Gibt an, dass der Compiler nicht automatisch auf die häufig verwendeten .NET Framework-Assemblys verweisen oder die Namespaces `System` und `Microsoft.VisualBasic` importieren soll.</span><span class="sxs-lookup"><span data-stu-id="50bbb-103">Specifies that the compiler should not automatically reference the commonly used .NET Framework assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50bbb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="50bbb-104">Syntax</span></span>  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="50bbb-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="50bbb-105">Remarks</span></span>  
 <span data-ttu-id="50bbb-106">Die Option `-noconfig` weist den Compiler an, nicht mit der Datei „Vbc.rsp“ zu kompilieren, die sich im selben Verzeichnis wie die Datei „Vbc.exe“ befindet.</span><span class="sxs-lookup"><span data-stu-id="50bbb-106">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="50bbb-107">Die Datei „Vbc.rsp“ verweist auf die gängigen .NET Framework-Assemblys und importiert die Namespaces `System` und `Microsoft.VisualBasic`.</span><span class="sxs-lookup"><span data-stu-id="50bbb-107">The Vbc.rsp file references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="50bbb-108">Der Compiler verweist implizit auf die System.dll-Assembly, sofern die Option `-nostdlib` nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="50bbb-108">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="50bbb-109">Die Option `-nostdlib` weist den Compiler an, nicht mit der Datei „Vbc.rsp“ zu kompilieren oder automatisch auf die System.dll-Assembly zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="50bbb-109">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="50bbb-110">Auf die Assemblys „Mscorlib.dll“ und „Microsoft.VisualBasic.dll“ wird immer verwiesen.</span><span class="sxs-lookup"><span data-stu-id="50bbb-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="50bbb-111">Sie können die Datei „Vbc.rsp“ so ändern, dass zusätzliche Compileroptionen angegeben werden, die in jeder Kompilierung von „Vbc.exe“ enthalten sein sollten (außer wenn die `-noconfig`-Option angeben ist).</span><span class="sxs-lookup"><span data-stu-id="50bbb-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="50bbb-112">Weitere Informationen finden Sie unter [@ (C# Compiler Options)](specify-response-file.md) (@ [C#-Compileroptionen]).</span><span class="sxs-lookup"><span data-stu-id="50bbb-112">For more information, see [@ (Specify Response File)](specify-response-file.md).</span></span>  
  
 <span data-ttu-id="50bbb-113">Der Compiler verarbeitet die an den Befehl `vbc` übergebenen Optionen zuletzt.</span><span class="sxs-lookup"><span data-stu-id="50bbb-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="50bbb-114">Aus diesem Grund überschreibt jede Option in der Befehlszeile die Einstellung für die gleiche Option in der Datei „Vbc.rsp“.</span><span class="sxs-lookup"><span data-stu-id="50bbb-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="50bbb-115">Die Option `-noconfig` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="50bbb-115">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50bbb-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50bbb-116">See also</span></span>

- [<span data-ttu-id="50bbb-117">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50bbb-117">-nostdlib (Visual Basic)</span></span>](nostdlib.md)
- [<span data-ttu-id="50bbb-118">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="50bbb-118">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="50bbb-119">@ (Antwortdatei festlegen)</span><span class="sxs-lookup"><span data-stu-id="50bbb-119">@ (Specify Response File)</span></span>](specify-response-file.md)
- [<span data-ttu-id="50bbb-120">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50bbb-120">-reference (Visual Basic)</span></span>](reference.md)
