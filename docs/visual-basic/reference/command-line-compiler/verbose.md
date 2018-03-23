---
title: -verbose
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0523409e53a8c7ea34de7dcc24b1bce2885a183
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="-verbose"></a><span data-ttu-id="fdadd-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="fdadd-102">-verbose</span></span>
<span data-ttu-id="fdadd-103">Weist den Compiler an, um ausführliche Status- und Fehlermeldungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fdadd-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdadd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fdadd-104">Syntax</span></span>  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="fdadd-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="fdadd-105">Arguments</span></span>  
 <span data-ttu-id="fdadd-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="fdadd-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="fdadd-107">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="fdadd-107">Optional.</span></span> <span data-ttu-id="fdadd-108">Angeben von `-verbose` ist derselbe, als wenn `-verbose+`, die bewirkt, dass der Compiler ausführliche Meldungen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="fdadd-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="fdadd-109">Der Standardwert für diese Option ist `-verbose-`.</span><span class="sxs-lookup"><span data-stu-id="fdadd-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fdadd-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fdadd-110">Remarks</span></span>  
 <span data-ttu-id="fdadd-111">Die `-verbose` Option zeigt Informationen über die Gesamtanzahl von Fehlern, die vom Compiler ausgegeben, meldet, welche Assemblys geladen werden von einem Modul und zeigt an, welche Dateien gerade kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="fdadd-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fdadd-112">Die `-verbose` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="fdadd-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdadd-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fdadd-113">Example</span></span>  
 <span data-ttu-id="fdadd-114">Der folgende code kompiliert `In.vb` und weist den Compiler an, um ausführliche Statusinformationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fdadd-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="fdadd-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdadd-115">See Also</span></span>  
 [<span data-ttu-id="fdadd-116">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="fdadd-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="fdadd-117">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="fdadd-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
