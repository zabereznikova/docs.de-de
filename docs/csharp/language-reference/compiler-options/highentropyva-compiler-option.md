---
title: -highentropyva (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /highentropyva
helpviewer_keywords:
- /highentropyva compiler option [C#]
- -highentropyva compiler option [C#]
- highentropyva compiler option [C#]
ms.assetid: eaf409b3-384e-49dd-9417-62453658f421
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d0b9a7a53545623ae5d5692b52973744adbcc299
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="-highentropyva-c-compiler-options"></a><span data-ttu-id="9094b-102">-highentropyva (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="9094b-102">-highentropyva (C# Compiler Options)</span></span>
<span data-ttu-id="9094b-103">Die Compileroption **-highentropyva** informiert den Windows-Kernel, ob eine bestimmte ausführbare Datei ASLR mit hoher Entropie (Address Space Layout Randomization, Zufällige Anordnung des Layouts des Adressraums) unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="9094b-103">The **-highentropyva** compiler option tells the Windows kernel whether a particular executable supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9094b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9094b-104">Syntax</span></span>  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="9094b-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="9094b-105">Arguments</span></span>  
 <span data-ttu-id="9094b-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="9094b-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="9094b-107">Diese Option gibt an, dass eine ausführbare 64-Bit-Datei oder eine ausführbare Datei, die durch die Compileroption [-platform:anycpu](../../../csharp/language-reference/compiler-options/platform-compiler-option.md) gekennzeichnet ist, einen virtuellen Adressbereich mit hoher Entropie unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9094b-107">This option specifies that a 64-bit executable or an executable that is marked by the [-platform:anycpu](../../../csharp/language-reference/compiler-options/platform-compiler-option.md) compiler option supports a high entropy virtual address space.</span></span> <span data-ttu-id="9094b-108">Diese Option ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9094b-108">The option is disabled by default.</span></span> <span data-ttu-id="9094b-109">Verwenden Sie **-highentropyva+** oder **-highentropyva**, um sie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9094b-109">Use **-highentropyva+** or **-highentropyva** to enable it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9094b-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9094b-110">Remarks</span></span>  
 <span data-ttu-id="9094b-111">Die Option **-highentropyva** ermöglicht den kompatiblen Versionen des Windows-Kernels, ein höheres Maß an Entropie zu verwenden, wenn das Adressbereichlayout eines Prozesses als Teil von ASLR zufällig festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="9094b-111">The **-highentropyva** option enables compatible versions of the Windows kernel to use higher degrees of entropy when randomizing the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="9094b-112">Die Verwendung eines höheren Maßes an Entropie bedeutet, dass viel mehr Adressen Speicherbereichen, z.B. Stapel und Heaps, zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="9094b-112">Using higher degrees of entropy means that a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="9094b-113">Daher ist es schwieriger, den Ort eines bestimmten Speicherbereichs zu schätzen.</span><span class="sxs-lookup"><span data-stu-id="9094b-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="9094b-114">Wenn die Compileroption **-highentropyva** angegeben wird, müssen die ausführbare Zieldatei und alle Module, von denen sie abhängig ist, Zeigerwerte verarbeiten können, die größer als 4 Gigabyte (GB) sind, wenn sie als 64-Bit-Prozess ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9094b-114">When the **-highentropyva** compiler option is specified, the target executable and any modules that it depends on must be able to handle pointer values that are larger than 4 gigabytes (GB) when they are running as a 64-bit process.</span></span>
