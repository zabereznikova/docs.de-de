---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: 8c5bc1d2ce331b8fe9461f91d64fbeab5a070b59
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004974"
---
# <a name="-verbose"></a><span data-ttu-id="ca284-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="ca284-102">-verbose</span></span>
<span data-ttu-id="ca284-103">Bewirkt, dass der Compiler ausführliche Status-und Fehlermeldungen erzeugt.</span><span class="sxs-lookup"><span data-stu-id="ca284-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca284-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca284-104">Syntax</span></span>  
  
```console  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="ca284-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="ca284-105">Arguments</span></span>  
 <span data-ttu-id="ca284-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="ca284-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="ca284-107">Optional.</span><span class="sxs-lookup"><span data-stu-id="ca284-107">Optional.</span></span> <span data-ttu-id="ca284-108">Das Angeben von `-verbose` ist identisch mit dem Angeben von `-verbose+`, was bewirkt, dass der Compiler ausführliche Meldungen ausgibt.</span><span class="sxs-lookup"><span data-stu-id="ca284-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="ca284-109">Der Standardwert für diese Option ist `-verbose-`.</span><span class="sxs-lookup"><span data-stu-id="ca284-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca284-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ca284-110">Remarks</span></span>  
 <span data-ttu-id="ca284-111">Die Option `-verbose` zeigt Informationen zur Gesamtanzahl von Fehlern an, die vom Compiler ausgegeben werden, meldet, welche Assemblys von einem Modul geladen werden, und zeigt an, welche Dateien derzeit kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="ca284-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca284-112">Die Option "`-verbose`" ist innerhalb der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="ca284-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca284-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ca284-113">Example</span></span>  
 <span data-ttu-id="ca284-114">Der folgende Code kompiliert `In.vb` und weist den Compiler an, ausführliche Statusinformationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ca284-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca284-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca284-115">See also</span></span>

- [<span data-ttu-id="ca284-116">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="ca284-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="ca284-117">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="ca284-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
