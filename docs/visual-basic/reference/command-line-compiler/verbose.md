---
title: /verbose
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5480f828fa1f0b6d71fa649bf44513ce806bb440
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="verbose"></a><span data-ttu-id="586e2-102">/verbose</span><span class="sxs-lookup"><span data-stu-id="586e2-102">/verbose</span></span>
<span data-ttu-id="586e2-103">Weist den Compiler an, um ausführliche Status- und Fehlermeldungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="586e2-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="586e2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="586e2-104">Syntax</span></span>  
  
```  
/verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="586e2-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="586e2-105">Arguments</span></span>  
 <span data-ttu-id="586e2-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="586e2-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="586e2-107">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="586e2-107">Optional.</span></span> <span data-ttu-id="586e2-108">Angeben von `/verbose` ist derselbe, als wenn `/verbose+`, die bewirkt, dass der Compiler ausführliche Meldungen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="586e2-108">Specifying `/verbose` is the same as specifying `/verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="586e2-109">Der Standardwert für diese Option ist `/verbose-`.</span><span class="sxs-lookup"><span data-stu-id="586e2-109">The default for this option is `/verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="586e2-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="586e2-110">Remarks</span></span>  
 <span data-ttu-id="586e2-111">Die `/verbose` Option zeigt Informationen über die Gesamtanzahl von Fehlern, die vom Compiler ausgegeben, meldet, welche Assemblys geladen werden von einem Modul und zeigt an, welche Dateien gerade kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="586e2-111">The `/verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="586e2-112">Die `/verbose` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="586e2-112">The `/verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="586e2-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="586e2-113">Example</span></span>  
 <span data-ttu-id="586e2-114">Der folgende code kompiliert `In.vb` und weist den Compiler an, um ausführliche Statusinformationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="586e2-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```  
vbc /verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="586e2-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="586e2-115">See Also</span></span>  
 [<span data-ttu-id="586e2-116">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="586e2-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="586e2-117">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="586e2-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
