---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: f6d896fb0d41a8fa3ed613d29bc3fca2bd14cc5e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832790"
---
# <a name="-verbose"></a><span data-ttu-id="36140-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="36140-102">-verbose</span></span>
<span data-ttu-id="36140-103">Veranlasst den Compiler an, um ausführliche Status- und Fehlermeldungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="36140-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36140-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="36140-104">Syntax</span></span>  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="36140-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="36140-105">Arguments</span></span>  
 <span data-ttu-id="36140-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="36140-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="36140-107">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="36140-107">Optional.</span></span> <span data-ttu-id="36140-108">Angeben von `-verbose` ist derselbe, als wenn `-verbose+`, die bewirkt, dass der Compiler ausführliche Meldungen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="36140-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="36140-109">Der Standardwert für diese Option ist `-verbose-`.</span><span class="sxs-lookup"><span data-stu-id="36140-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36140-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="36140-110">Remarks</span></span>  
 <span data-ttu-id="36140-111">Die `-verbose` Option zeigt Informationen über die Gesamtanzahl von Fehlern, die vom Compiler ausgegeben, meldet, welche Assemblys von einem Modul geladen werden und zeigt an, welche Dateien gerade kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="36140-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36140-112">Die `-verbose` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="36140-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36140-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="36140-113">Example</span></span>  
 <span data-ttu-id="36140-114">Der folgende code kompiliert `In.vb` und weist den Compiler an, um ausführliche Statusinformationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="36140-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="36140-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36140-115">See also</span></span>

- [<span data-ttu-id="36140-116">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="36140-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="36140-117">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="36140-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
