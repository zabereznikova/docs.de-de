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
ms.openlocfilehash: 3877757185030b0dba914a79d8c760fb8033ae5f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408646"
---
# <a name="-filealign"></a><span data-ttu-id="0d6d7-102">-filealign</span><span class="sxs-lookup"><span data-stu-id="0d6d7-102">-filealign</span></span>
<span data-ttu-id="0d6d7-103">Gibt die Ausrichtung der Abschnitte der Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="0d6d7-103">Specifies where to align the sections of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d6d7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d6d7-104">Syntax</span></span>  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="0d6d7-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="0d6d7-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="0d6d7-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0d6d7-106">Required.</span></span> <span data-ttu-id="0d6d7-107">Ein Wert, der die Ausrichtung der Abschnitte in der Ausgabedatei angibt.</span><span class="sxs-lookup"><span data-stu-id="0d6d7-107">A value that specifies the alignment of sections in the output file.</span></span> <span data-ttu-id="0d6d7-108">Gültige Werte sind 512, 1024, 2048, 4096 und 8192.</span><span class="sxs-lookup"><span data-stu-id="0d6d7-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="0d6d7-109">Diese Werte sind in Bytes angegeben.</span><span class="sxs-lookup"><span data-stu-id="0d6d7-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d6d7-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0d6d7-110">Remarks</span></span>  
 <span data-ttu-id="0d6d7-111">Sie können die `-filealign`-Option verwenden, um die Ausrichtung der Abschnitte in Ihrer Ausgabedatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0d6d7-111">You can use the `-filealign` option to specify the alignment of sections in your output file.</span></span> <span data-ttu-id="0d6d7-112">Abschnitte sind Blöcke zusammenhängenden Speichers in einer Portable Executable-Datei (PE), die entweder Code oder Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="0d6d7-112">Sections are blocks of contiguous memory in a Portable Executable (PE) file that contains either code or data.</span></span> <span data-ttu-id="0d6d7-113">Die `-filealign`-Option ermöglicht es Ihnen, Ihre Anwendung mit einer nicht dem Standardwert entsprechenden Ausrichtung zu kompilieren. Die meisten Entwickler müssen diese Option nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="0d6d7-113">The `-filealign` option lets you compile your application with a nonstandard alignment; most developers do not need to use this option.</span></span>  
  
 <span data-ttu-id="0d6d7-114">Jeder Abschnitt wird an einer Grenze ausgerichtet, die einem Vielfachen des `-filealign`-Werts entspricht.</span><span class="sxs-lookup"><span data-stu-id="0d6d7-114">Each section is aligned on a boundary that is a multiple of the `-filealign` value.</span></span> <span data-ttu-id="0d6d7-115">Es gibt keinen festen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="0d6d7-115">There is no fixed default.</span></span> <span data-ttu-id="0d6d7-116">Wenn `-filealign` nicht angegeben wird, wählt der Compiler zur Kompilierzeit einen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="0d6d7-116">If `-filealign` is not specified, the compiler picks a default at compile time.</span></span>  
  
 <span data-ttu-id="0d6d7-117">Durch Angeben der Abschnittsgröße können Sie die Größe der Ausgabedatei ändern.</span><span class="sxs-lookup"><span data-stu-id="0d6d7-117">By specifying the section size, you can change the size of the output file.</span></span> <span data-ttu-id="0d6d7-118">Das Ändern der Größe kann möglicherweise für Programme hilfreich sein, die auf kleineren Geräten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0d6d7-118">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0d6d7-119">Diese Option `-filealign` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="0d6d7-119">The `-filealign` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d6d7-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d6d7-120">See also</span></span>

- [<span data-ttu-id="0d6d7-121">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="0d6d7-121">Visual Basic Command-Line Compiler</span></span>](index.md)
