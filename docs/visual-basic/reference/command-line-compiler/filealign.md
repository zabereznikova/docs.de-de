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
ms.openlocfilehash: 2893c1760a856a7d736e9c03ba33d9771722b5b2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929471"
---
# <a name="-filealign"></a><span data-ttu-id="88e2b-102">-filealign</span><span class="sxs-lookup"><span data-stu-id="88e2b-102">-filealign</span></span>
<span data-ttu-id="88e2b-103">Gibt die Ausrichtung der Abschnitte der Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="88e2b-103">Specifies where to align the sections of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88e2b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="88e2b-104">Syntax</span></span>  
  
```  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="88e2b-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="88e2b-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="88e2b-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="88e2b-106">Required.</span></span> <span data-ttu-id="88e2b-107">Ein-Wert, der die Ausrichtung der Abschnitte in der Ausgabedatei angibt.</span><span class="sxs-lookup"><span data-stu-id="88e2b-107">A value that specifies the alignment of sections in the output file.</span></span> <span data-ttu-id="88e2b-108">Gültige Werte sind 512, 1024, 2048, 4096 und 8192.</span><span class="sxs-lookup"><span data-stu-id="88e2b-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="88e2b-109">Diese Werte sind in Bytes angegeben.</span><span class="sxs-lookup"><span data-stu-id="88e2b-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88e2b-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="88e2b-110">Remarks</span></span>  
 <span data-ttu-id="88e2b-111">Sie können die `-filealign` -Option verwenden, um die Ausrichtung von Abschnitten in der Ausgabedatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="88e2b-111">You can use the `-filealign` option to specify the alignment of sections in your output file.</span></span> <span data-ttu-id="88e2b-112">Abschnitte sind Blöcke des zusammenhängenden Speichers in einer portablen ausführbaren Datei (PE), die entweder Code oder Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="88e2b-112">Sections are blocks of contiguous memory in a Portable Executable (PE) file that contains either code or data.</span></span> <span data-ttu-id="88e2b-113">Mit `-filealign` der-Option können Sie die Anwendung mit einer nicht standardmäßigen Ausrichtung kompilieren; die meisten Entwickler müssen diese Option nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="88e2b-113">The `-filealign` option lets you compile your application with a nonstandard alignment; most developers do not need to use this option.</span></span>  
  
 <span data-ttu-id="88e2b-114">Jeder Abschnitt wird an einer Grenze ausgerichtet, die ein Vielfaches des `-filealign` Werts ist.</span><span class="sxs-lookup"><span data-stu-id="88e2b-114">Each section is aligned on a boundary that is a multiple of the `-filealign` value.</span></span> <span data-ttu-id="88e2b-115">Es gibt keinen festen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="88e2b-115">There is no fixed default.</span></span> <span data-ttu-id="88e2b-116">Wenn `-filealign` nicht angegeben ist, wählt der Compiler zum Zeitpunkt der Kompilierung einen Standardwert aus.</span><span class="sxs-lookup"><span data-stu-id="88e2b-116">If `-filealign` is not specified, the compiler picks a default at compile time.</span></span>  
  
 <span data-ttu-id="88e2b-117">Durch Angeben der Abschnitts Größe können Sie die Größe der Ausgabedatei ändern.</span><span class="sxs-lookup"><span data-stu-id="88e2b-117">By specifying the section size, you can change the size of the output file.</span></span> <span data-ttu-id="88e2b-118">Das Ändern der Größe kann möglicherweise für Programme hilfreich sein, die auf kleineren Geräten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="88e2b-118">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="88e2b-119">Die `-filealign` Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="88e2b-119">The `-filealign` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88e2b-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88e2b-120">See also</span></span>

- [<span data-ttu-id="88e2b-121">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="88e2b-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
