---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: c5bf988d819a8df8aed99588abbb30e19d14b1ac
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91084982"
---
# <a name="-verbose"></a><span data-ttu-id="6746d-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="6746d-102">-verbose</span></span>

<span data-ttu-id="6746d-103">Bewirkt, dass der Compiler ausführliche Status- und Fehlermeldungen erzeugt</span><span class="sxs-lookup"><span data-stu-id="6746d-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6746d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6746d-104">Syntax</span></span>  
  
```console  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="6746d-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="6746d-105">Arguments</span></span>  

 <span data-ttu-id="6746d-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="6746d-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="6746d-107">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="6746d-107">Optional.</span></span> <span data-ttu-id="6746d-108">Wenn Sie `-verbose` angeben, ist der Effekt mit `-verbose+` identisch: Der Compiler gibt ausführliche Meldungen aus.</span><span class="sxs-lookup"><span data-stu-id="6746d-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="6746d-109">Der Standardwert für diese Option ist `-verbose-`.</span><span class="sxs-lookup"><span data-stu-id="6746d-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6746d-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6746d-110">Remarks</span></span>  

 <span data-ttu-id="6746d-111">Die Option `-verbose` zeigt Informationen zur Gesamtanzahl der Fehler an, die vom Compiler ausgegeben werden, sowie welche Dateien derzeit kompiliert werden und meldet, welche Assemblys von einem Modul geladen werden.</span><span class="sxs-lookup"><span data-stu-id="6746d-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6746d-112">Die Option `-verbose` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="6746d-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6746d-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6746d-113">Example</span></span>  

 <span data-ttu-id="6746d-114">Der folgende Code kompiliert `In.vb` und weist den Compiler an, ausführliche Statusinformationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6746d-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6746d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6746d-115">See also</span></span>

- [<span data-ttu-id="6746d-116">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="6746d-116">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="6746d-117">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="6746d-117">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
