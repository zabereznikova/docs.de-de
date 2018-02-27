---
title: "Gewusst wie: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile"
ms.date: 09/29/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.build.commandline
helpviewer_keywords:
- csc.exe, command-line builds
- Visual C#, command-line builds
- command-line compilers, Visual C#
- Vsvars32.bat
- builds [C#], command-line
- compilers, invoking from command line
- Vcvars32.bat file
- command line [C#], building from
- Visual C# compiler, enabling
- compiling source code, from command line
ms.assetid: 7ec09480-5612-4f6a-8d00-ad90ea9bca5d
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 298006629bedf33e4d2521a88c010fcce824585c
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a><span data-ttu-id="d5d7d-102">Gewusst wie: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="d5d7d-102">How to: Set Environment Variables for the Visual Studio Command Line</span></span>

<span data-ttu-id="d5d7d-103">Die Umgebungsvariablen, die für Befehlszeilenbuilds erforderlich sind, werden durch die Datei VSDevCmd.bat festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d5d7d-103">The VsDevCmd.bat file sets the appropriate environment variables to enable command-line builds.</span></span> <span data-ttu-id="d5d7d-104">Weitere Informationen zu VsDevCmd.bat finden Sie im [Knowledge Base-Artikel Q248802](https://support.microsoft.com/help/248802/you-receive-the-out-of-environment-space-error-message-when-you-execut).</span><span class="sxs-lookup"><span data-stu-id="d5d7d-104">For more information about VsDevCmd.bat, see [Knowledge Base article Q248802](https://support.microsoft.com/help/248802/you-receive-the-out-of-environment-space-error-message-when-you-execut).</span></span>  

> [!NOTE]
> <span data-ttu-id="d5d7d-105">Bei der Datei VsDevCmd.bat handelt es sich um eine neue Datei, die im Lieferumfang von Visual Studio 2017 enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="d5d7d-105">The VsDevCmd.bat file is a new file delivered with Visual Studio 2017.</span></span> <span data-ttu-id="d5d7d-106">In Visual Studio 2015 und früheren Versionen wurde für den gleichen Zweck VSVARS32.bat verwendet.</span><span class="sxs-lookup"><span data-stu-id="d5d7d-106">Visual Studio 2015 and earlier versions used VSVARS32.bat for the same purpose.</span></span> <span data-ttu-id="d5d7d-107">Diese Datei wurde unter „\Programme\Microsoft Visual Studio\\*Version*\Common7\Tools“ oder „Programme (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools“ gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d5d7d-107">This file was stored in \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools.</span></span>
  
<span data-ttu-id="d5d7d-108">Falls die aktuelle Version von Visual Studio auf einem Computer installiert ist, der zusätzlich über eine frühere Version von Visual Studio verfügt, sollten Sie die Dateien VsDevCmd.bat und VSVARS32.BAT aus unterschiedlichen Versionen nicht im selben Eingabeaufforderungsfenster ausführen.</span><span class="sxs-lookup"><span data-stu-id="d5d7d-108">If the current version of Visual Studio is installed on a computer that also has an earlier version of Visual Studio, you should not run VsDevCmd.bat and VSVARS32.BAT from different versions in the same Command Prompt window.</span></span> <span data-ttu-id="d5d7d-109">Stattdessen sollten Sie den Befehl für jede Version in ihrem eigenen Fenster ausführen.</span><span class="sxs-lookup"><span data-stu-id="d5d7d-109">Instead, you should run the command for each version in its own window.</span></span>
  
### <a name="to-run-vsdevcmdbat"></a><span data-ttu-id="d5d7d-110">Ausführen von VsDevCmd.BAT</span><span class="sxs-lookup"><span data-stu-id="d5d7d-110">To run VsDevCmd.BAT</span></span>  
  
1.  <span data-ttu-id="d5d7d-111">Öffnen Sie über das Menü **Start** die **Developer-Eingabeaufforderung für VS 2017**.</span><span class="sxs-lookup"><span data-stu-id="d5d7d-111">From the **Start** menu, open the **Developer Command Prompt for VS 2017**.</span></span>  <span data-ttu-id="d5d7d-112">Sie befindet sich im Ordner **Visual Studio 2017**.</span><span class="sxs-lookup"><span data-stu-id="d5d7d-112">It's in the **Visual Studio 2017** folder.</span></span>
  
2.  <span data-ttu-id="d5d7d-113">Wechseln Sie zum Unterverzeichnis „Programme\Microsoft Visual Studio\\*Version*\\*Angebot*\Common7\Tools“ oder „Programme (x86)\Microsoft Visual Studio\\*Version*\\*Angebot*\Common7\Tools“ Ihrer Installation.</span><span class="sxs-lookup"><span data-stu-id="d5d7d-113">Change to the \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools or \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools subdirectory of your installation.</span></span>  <span data-ttu-id="d5d7d-114">(Die *Version* lautet für die aktuelle Version *2017*.</span><span class="sxs-lookup"><span data-stu-id="d5d7d-114">(*Version* is *2017* for the current version.</span></span> <span data-ttu-id="d5d7d-115">*Angebot* ist einer der Werte *Enterprise*, *Professional* oder *Community*.)</span><span class="sxs-lookup"><span data-stu-id="d5d7d-115">*Offering* is one of *Enterprise*, *Professional* or *Community*.)</span></span>
  
3.  <span data-ttu-id="d5d7d-116">Führen Sie VsDevCmd.bat aus, indem Sie **VsDevCmd** eingeben.</span><span class="sxs-lookup"><span data-stu-id="d5d7d-116">Run VsDevCmd.bat by typing **VsDevCmd**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="d5d7d-117">VsDevCmd.bat kann auf verschiedenen Computern unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="d5d7d-117">VsDevCmd.bat can vary from computer to computer.</span></span> <span data-ttu-id="d5d7d-118">Falls die Datei VsDevCmd.bat nicht vorhanden oder beschädigt ist, sollten Sie sie nicht durch die VsDevCmd.bat-Datei eines anderen Computers ersetzen.</span><span class="sxs-lookup"><span data-stu-id="d5d7d-118">Do not replace a missing or damaged VsDevCmd.bat file with a VsDevCmd.bat from another computer.</span></span> <span data-ttu-id="d5d7d-119">Führen Sie stattdessen Setup erneut aus, um die fehlende Datei zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="d5d7d-119">Instead, rerun setup to replace the missing file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5d7d-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5d7d-120">See Also</span></span>  
 [<span data-ttu-id="d5d7d-121">Erstellen über die Befehlszeile mit csc.exe</span><span class="sxs-lookup"><span data-stu-id="d5d7d-121">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
