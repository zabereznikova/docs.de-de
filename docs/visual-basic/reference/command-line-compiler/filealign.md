---
title: -filealign
ms.date: 03/10/2018
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
ms.openlocfilehash: db70749f28592ae6711b6d9544f8704af9416490
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50181721"
---
# <a name="-filealign"></a><span data-ttu-id="03d4c-102">-filealign</span><span class="sxs-lookup"><span data-stu-id="03d4c-102">-filealign</span></span>
<span data-ttu-id="03d4c-103">Gibt die Ausrichtung der Abschnitte der Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="03d4c-103">Specifies where to align the sections of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03d4c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="03d4c-104">Syntax</span></span>  
  
```  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="03d4c-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="03d4c-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="03d4c-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="03d4c-106">Required.</span></span> <span data-ttu-id="03d4c-107">Ein Wert, der die Ausrichtung der Abschnitte in der Ausgabedatei angibt.</span><span class="sxs-lookup"><span data-stu-id="03d4c-107">A value that specifies the alignment of sections in the output file.</span></span> <span data-ttu-id="03d4c-108">Gültige Werte sind 512, 1024, 2048, 4096 und 8192.</span><span class="sxs-lookup"><span data-stu-id="03d4c-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="03d4c-109">Diese Werte sind in Bytes angegeben.</span><span class="sxs-lookup"><span data-stu-id="03d4c-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03d4c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="03d4c-110">Remarks</span></span>  
 <span data-ttu-id="03d4c-111">Sie können die `-filealign` Option aus, um die Ausrichtung der Abschnitte in Ihrer Ausgabedatei angeben.</span><span class="sxs-lookup"><span data-stu-id="03d4c-111">You can use the `-filealign` option to specify the alignment of sections in your output file.</span></span> <span data-ttu-id="03d4c-112">Abschnitte sind zusammenhängende Speicherblöcke in einer PE (Portable Executable)-Datei, die entweder Code oder Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="03d4c-112">Sections are blocks of contiguous memory in a Portable Executable (PE) file that contains either code or data.</span></span> <span data-ttu-id="03d4c-113">Die `-filealign` Option können Sie Ihre Anwendung mit einer nicht standardmäßigen Ausrichtung kompilieren; die meisten Entwickler müssen sich nicht auf diese Option verwenden.</span><span class="sxs-lookup"><span data-stu-id="03d4c-113">The `-filealign` option lets you compile your application with a nonstandard alignment; most developers do not need to use this option.</span></span>  
  
 <span data-ttu-id="03d4c-114">Jeder Abschnitt orientiert sich an einer Grenze, die ein Vielfaches von ist das `-filealign` Wert.</span><span class="sxs-lookup"><span data-stu-id="03d4c-114">Each section is aligned on a boundary that is a multiple of the `-filealign` value.</span></span> <span data-ttu-id="03d4c-115">Es gibt keinen festen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="03d4c-115">There is no fixed default.</span></span> <span data-ttu-id="03d4c-116">Wenn `-filealign` nicht angegeben wird, wählt der Compiler einen Standardwert zum Zeitpunkt der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="03d4c-116">If `-filealign` is not specified, the compiler picks a default at compile time.</span></span>  
  
 <span data-ttu-id="03d4c-117">Durch Angeben der Abschnittsgröße, können Sie die Größe der Ausgabedatei ändern.</span><span class="sxs-lookup"><span data-stu-id="03d4c-117">By specifying the section size, you can change the size of the output file.</span></span> <span data-ttu-id="03d4c-118">Das Ändern der Größe kann möglicherweise für Programme hilfreich sein, die auf kleineren Geräten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="03d4c-118">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03d4c-119">Die `-filealign` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="03d4c-119">The `-filealign` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03d4c-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03d4c-120">See Also</span></span>  
 [<span data-ttu-id="03d4c-121">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="03d4c-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
