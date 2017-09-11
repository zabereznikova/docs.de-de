---
title: / highentropyva (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
caps.latest.revision: 12
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
ms.openlocfilehash: ef482f142e07e96eabf93bd2223b0d24f351553b
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="highentropyva-visual-basic"></a><span data-ttu-id="955f1-102">/highentropyva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="955f1-102">/highentropyva (Visual Basic)</span></span>
<span data-ttu-id="955f1-103">Gibt an, ob eine 64-Bit-ausführbare Datei oder eine ausführbare Datei, die von markiert ist die [/Platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) Compileroption Address Space Layout Randomization (ASLR) mit hohen Entropie unterstützt.</span><span class="sxs-lookup"><span data-stu-id="955f1-103">Indicates whether a 64-bit executable or an executable that's marked by the [/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="955f1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="955f1-104">Syntax</span></span>  
  
```  
/highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="955f1-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="955f1-105">Arguments</span></span>  
 <span data-ttu-id="955f1-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="955f1-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="955f1-107">Optional.</span><span class="sxs-lookup"><span data-stu-id="955f1-107">Optional.</span></span> <span data-ttu-id="955f1-108">Die Option ist standardmäßig deaktiviert, oder wenn Sie angeben, `/highentropyva-`.</span><span class="sxs-lookup"><span data-stu-id="955f1-108">The option is off by default or if you specify `/highentropyva-`.</span></span> <span data-ttu-id="955f1-109">Die Option ist die Angabe `/highentropyva` oder `/highentropyva+`.</span><span class="sxs-lookup"><span data-stu-id="955f1-109">The option is on if you specify `/highentropyva` or `/highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="955f1-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="955f1-110">Remarks</span></span>  
 <span data-ttu-id="955f1-111">Wenn Sie diese Option angeben, können kompatible Versionen des Windows-Kernels höheres Maß an Entropie, wenn der Kernel das Layout für die Adressen Speicherplatz eines Prozesses als Teil von ASLR Einzelteilen.</span><span class="sxs-lookup"><span data-stu-id="955f1-111">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="955f1-112">Wenn der Kernel höheres Maß an Entropie verwendet wird, kann eine größere Anzahl von Adressen Speicherbereiche, z. B. Stapel und Heaps zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="955f1-112">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="955f1-113">Daher ist es schwieriger, den Ort eines bestimmten Speicherbereichs zu schätzen.</span><span class="sxs-lookup"><span data-stu-id="955f1-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="955f1-114">Wenn die Option auf der ausführbaren Zieldatei und alle Module auf muss denen es abhängig ist, sein Zeigerwerte verarbeiten, die größer als 4 Gigabyte (GB) sind, wenn diese Module als 64-Bit-Prozesse ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="955f1-114">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="955f1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="955f1-115">See Also</span></span>  
 <span data-ttu-id="955f1-116">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="955f1-116">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="955f1-117"> [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="955f1-117"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
