---
description: -highentropyva (C#-Compileroptionen)
title: -highentropyva (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /highentropyva
helpviewer_keywords:
- /highentropyva compiler option [C#]
- -highentropyva compiler option [C#]
- highentropyva compiler option [C#]
ms.assetid: eaf409b3-384e-49dd-9417-62453658f421
ms.openlocfilehash: 2c2e2780693a89072c4bb55b318be94089bf3ced
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125656"
---
# <a name="-highentropyva-c-compiler-options"></a><span data-ttu-id="02b8d-103">-highentropyva (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="02b8d-103">-highentropyva (C# Compiler Options)</span></span>
<span data-ttu-id="02b8d-104">Die Compileroption **-highentropyva** informiert den Windows-Kernel, ob eine bestimmte ausführbare Datei ASLR mit hoher Entropie (Address Space Layout Randomization, Zufällige Anordnung des Layouts des Adressraums) unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="02b8d-104">The **-highentropyva** compiler option tells the Windows kernel whether a particular executable supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02b8d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="02b8d-105">Syntax</span></span>  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="02b8d-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="02b8d-106">Arguments</span></span>  
 <span data-ttu-id="02b8d-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="02b8d-107">`+` &#124; `-`</span></span>  
 <span data-ttu-id="02b8d-108">Diese Option gibt an, dass eine ausführbare 64-Bit-Datei oder eine ausführbare Datei, die durch die Compileroption [-platform:anycpu](./platform-compiler-option.md) gekennzeichnet ist, einen virtuellen Adressbereich mit hoher Entropie unterstützt.</span><span class="sxs-lookup"><span data-stu-id="02b8d-108">This option specifies that a 64-bit executable or an executable that is marked by the [-platform:anycpu](./platform-compiler-option.md) compiler option supports a high entropy virtual address space.</span></span> <span data-ttu-id="02b8d-109">Diese Option ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="02b8d-109">The option is disabled by default.</span></span> <span data-ttu-id="02b8d-110">Verwenden Sie **-highentropyva+** oder **-highentropyva**, um sie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="02b8d-110">Use **-highentropyva+** or **-highentropyva** to enable it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02b8d-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="02b8d-111">Remarks</span></span>  
 <span data-ttu-id="02b8d-112">Die Option **-highentropyva** ermöglicht den kompatiblen Versionen des Windows-Kernels, ein höheres Maß an Entropie zu verwenden, wenn das Adressbereichlayout eines Prozesses als Teil von ASLR zufällig festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="02b8d-112">The **-highentropyva** option enables compatible versions of the Windows kernel to use higher degrees of entropy when randomizing the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="02b8d-113">Die Verwendung eines höheren Maßes an Entropie bedeutet, dass viel mehr Adressen Speicherbereichen, z.B. Stapel und Heaps, zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="02b8d-113">Using higher degrees of entropy means that a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="02b8d-114">Daher ist es schwieriger, den Ort eines bestimmten Speicherbereichs zu schätzen.</span><span class="sxs-lookup"><span data-stu-id="02b8d-114">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="02b8d-115">Wenn die Compileroption **-highentropyva** angegeben wird, müssen die ausführbare Zieldatei und alle Module, von denen sie abhängig ist, Zeigerwerte verarbeiten können, die größer als 4 Gigabyte (GB) sind, wenn sie als 64-Bit-Prozess ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="02b8d-115">When the **-highentropyva** compiler option is specified, the target executable and any modules that it depends on must be able to handle pointer values that are larger than 4 gigabytes (GB) when they are running as a 64-bit process.</span></span>
