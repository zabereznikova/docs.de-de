---
title: -highentropyva
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 7934dcaada4675bf687624bef5ed1ea25e842832
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344240"
---
# <a name="-highentropyva-visual-basic"></a><span data-ttu-id="10d49-102">-highentropyva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10d49-102">-highentropyva (Visual Basic)</span></span>
<span data-ttu-id="10d49-103">Gibt an, ob eine ausführbare 64-Bit-Datei oder eine ausführbare Datei, die durch die Compileroption [-platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) gekennzeichnet ist, die zufällige Anordnung des Adressraumlayouts (Address Space Layout Randomization, ASLR) mit hoher Entropie unterstützt.</span><span class="sxs-lookup"><span data-stu-id="10d49-103">Indicates whether a 64-bit executable or an executable that's marked by the [-platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10d49-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="10d49-104">Syntax</span></span>  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="10d49-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="10d49-105">Arguments</span></span>  
 <span data-ttu-id="10d49-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="10d49-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="10d49-107">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="10d49-107">Optional.</span></span> <span data-ttu-id="10d49-108">Standardmäßig oder bei Angabe von `-highentropyva-` ist diese Option nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="10d49-108">The option is off by default or if you specify `-highentropyva-`.</span></span> <span data-ttu-id="10d49-109">Bei Angabe von `-highentropyva` oder `-highentropyva+` ist die Option aktiviert.</span><span class="sxs-lookup"><span data-stu-id="10d49-109">The option is on if you specify `-highentropyva` or `-highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10d49-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="10d49-110">Remarks</span></span>  
 <span data-ttu-id="10d49-111">Durch Angabe dieser Option können kompatible Versionen des Windows-Kernels ein höheres Maß an Entropie verwenden, wenn der Kernel das Adressraumlayout eines Prozesses als Teil von ASLR zufällig festlegt.</span><span class="sxs-lookup"><span data-stu-id="10d49-111">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="10d49-112">Wenn der Kernel ein höheres Maß an Entropie verwendet, können weit mehr Adressen Speicherbereichen, wie etwa Stapel und Heaps, zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="10d49-112">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="10d49-113">Daher ist es schwieriger, den Ort eines bestimmten Speicherbereichs zu schätzen.</span><span class="sxs-lookup"><span data-stu-id="10d49-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="10d49-114">Ist die Option aktiviert, müssen die ausführbare Zieldatei und alle Module, von denen sie abhängig ist, Zeigerwerte verarbeiten können, die größer als 4 GB sind, wenn die Module als 64-Bit-Prozess ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="10d49-114">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10d49-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10d49-115">See also</span></span>

- [<span data-ttu-id="10d49-116">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="10d49-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="10d49-117">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="10d49-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
