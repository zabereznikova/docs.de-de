---
title: / filealign | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
caps.latest.revision: 14
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
ms.openlocfilehash: 5e0cd0a2a7e4c88df1087faee963f541c325b272
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="filealign"></a><span data-ttu-id="16798-102">/filealign</span><span class="sxs-lookup"><span data-stu-id="16798-102">/filealign</span></span>
<span data-ttu-id="16798-103">Gibt die Ausrichtung der Abschnitte der Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="16798-103">Specifies where to align the sections of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16798-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="16798-104">Syntax</span></span>  
  
```  
/filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="16798-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="16798-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="16798-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="16798-106">Required.</span></span> <span data-ttu-id="16798-107">Ein Wert, der die Ausrichtung der Abschnitte in der Ausgabedatei angibt.</span><span class="sxs-lookup"><span data-stu-id="16798-107">A value that specifies the alignment of sections in the output file.</span></span> <span data-ttu-id="16798-108">Gültige Werte sind 512, 1024, 2048, 4096 und 8192.</span><span class="sxs-lookup"><span data-stu-id="16798-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="16798-109">Diese Werte werden in Bytes.</span><span class="sxs-lookup"><span data-stu-id="16798-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16798-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="16798-110">Remarks</span></span>  
 <span data-ttu-id="16798-111">Sie können die `/filealign` Option, um die Ausrichtung der Abschnitte in der Ausgabedatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="16798-111">You can use the `/filealign` option to specify the alignment of sections in your output file.</span></span> <span data-ttu-id="16798-112">Abschnitte sind zusammenhängende Arbeitsspeicherblöcke in einer PE (Portable Executable)-Datei, die entweder Code oder Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="16798-112">Sections are blocks of contiguous memory in a Portable Executable (PE) file that contains either code or data.</span></span> <span data-ttu-id="16798-113">Die `/filealign` -Option können Sie Ihre Anwendung mit einer nicht standardmäßigen Ausrichtung kompilieren, die meisten Entwickler müssen nicht auf diese Option verwenden.</span><span class="sxs-lookup"><span data-stu-id="16798-113">The `/filealign` option lets you compile your application with a nonstandard alignment; most developers do not need to use this option.</span></span>  
  
 <span data-ttu-id="16798-114">Jeder Abschnitt wird an einer Grenze, die ein Vielfaches von ausgerichtet der `/filealign` Wert.</span><span class="sxs-lookup"><span data-stu-id="16798-114">Each section is aligned on a boundary that is a multiple of the `/filealign` value.</span></span> <span data-ttu-id="16798-115">Es gibt keinen festen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="16798-115">There is no fixed default.</span></span> <span data-ttu-id="16798-116">Wenn `/filealign` nicht angegeben wird, wählt der Compiler einen Standardwert zum Zeitpunkt der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="16798-116">If `/filealign` is not specified, the compiler picks a default at compile time.</span></span>  
  
 <span data-ttu-id="16798-117">Durch Angeben der, können Sie die Größe der Ausgabedatei ändern.</span><span class="sxs-lookup"><span data-stu-id="16798-117">By specifying the section size, you can change the size of the output file.</span></span> <span data-ttu-id="16798-118">Ändern der Größe für Programme möglicherweise hilfreich, die auf kleineren Geräten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="16798-118">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="16798-119">Die `/filealign` Option ist nicht verfügbar in der Visual Studio Development Environment; es ist nur beim Kompilieren von der Befehlszeile aus.</span><span class="sxs-lookup"><span data-stu-id="16798-119">The `/filealign` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16798-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16798-120">See Also</span></span>  
 [<span data-ttu-id="16798-121">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="16798-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
