---
description: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile
title: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile
ms.date: 12/20/2019
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
ms.openlocfilehash: b985c85e2fddce459ed68b3d07ba7d54a8b2d0a7
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "89125604"
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a><span data-ttu-id="c50df-103">Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="c50df-103">How to set environment variables for the Visual Studio Command Line</span></span>

<span data-ttu-id="c50df-104">Die Umgebungsvariablen, die für Befehlszeilenbuilds erforderlich sind, werden durch die Datei VSDevCmd.bat festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c50df-104">The VsDevCmd.bat file sets the appropriate environment variables to enable command-line builds.</span></span>

> [!NOTE]
> <span data-ttu-id="c50df-105">In Visual Studio 2015 und früheren Versionen wurde für den gleichen Zweck „VSVARS32.bat“ (nicht „VsDevCmd.bat“) verwendet.</span><span class="sxs-lookup"><span data-stu-id="c50df-105">Visual Studio 2015 and earlier versions used VSVARS32.bat, not VsDevCmd.bat for the same purpose.</span></span> <span data-ttu-id="c50df-106">Diese Datei wurde unter „\Programme\Microsoft Visual Studio\\*Version*\Common7\Tools“ oder „Programme (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools“ gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c50df-106">This file was stored in \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools.</span></span>

<span data-ttu-id="c50df-107">Falls die aktuelle Version von Visual Studio auf einem Computer installiert ist, der zusätzlich über eine frühere Version von Visual Studio verfügt, sollten Sie die Dateien VsDevCmd.bat und VSVARS32.BAT aus unterschiedlichen Versionen nicht im selben Eingabeaufforderungsfenster ausführen.</span><span class="sxs-lookup"><span data-stu-id="c50df-107">If the current version of Visual Studio is installed on a computer that also has an earlier version of Visual Studio, you should not run VsDevCmd.bat and VSVARS32.BAT from different versions in the same Command Prompt window.</span></span> <span data-ttu-id="c50df-108">Stattdessen sollten Sie den Befehl für jede Version in ihrem eigenen Fenster ausführen.</span><span class="sxs-lookup"><span data-stu-id="c50df-108">Instead, you should run the command for each version in its own window.</span></span>

### <a name="to-run-vsdevcmdbat"></a><span data-ttu-id="c50df-109">Ausführen von VsDevCmd.BAT</span><span class="sxs-lookup"><span data-stu-id="c50df-109">To run VsDevCmd.BAT</span></span>

1. <span data-ttu-id="c50df-110">Öffnen Sie über das Menü **Start** die **Developer-Eingabeaufforderung für VS 2019**.</span><span class="sxs-lookup"><span data-stu-id="c50df-110">From the **Start** menu, open the **Developer Command Prompt for VS 2019**.</span></span>  <span data-ttu-id="c50df-111">Die Datei befindet sich im Ordner **Visual Studio 2019**.</span><span class="sxs-lookup"><span data-stu-id="c50df-111">It's in the **Visual Studio 2019** folder.</span></span>

2. <span data-ttu-id="c50df-112">Wechseln Sie zum Unterverzeichnis „Programme\Microsoft Visual Studio\\*Version*\\*Angebot*\Common7\Tools“ oder „Programme (x86)\Microsoft Visual Studio\\*Version*\\*Angebot*\Common7\Tools“ Ihrer Installation.</span><span class="sxs-lookup"><span data-stu-id="c50df-112">Change to the \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools or \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools subdirectory of your installation.</span></span>  <span data-ttu-id="c50df-113">(Die *Version* lautet für die aktuelle Version *2019*.</span><span class="sxs-lookup"><span data-stu-id="c50df-113">(*Version* is *2019* for the current version.</span></span> <span data-ttu-id="c50df-114">*Angebot* ist einer der Werte *Enterprise*, *Professional* oder *Community*.)</span><span class="sxs-lookup"><span data-stu-id="c50df-114">*Offering* is one of *Enterprise*, *Professional* or *Community*.)</span></span>

3. <span data-ttu-id="c50df-115">Führen Sie VsDevCmd.bat aus, indem Sie **VsDevCmd** eingeben.</span><span class="sxs-lookup"><span data-stu-id="c50df-115">Run VsDevCmd.bat by typing **VsDevCmd**.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="c50df-116">VsDevCmd.bat kann auf verschiedenen Computern unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="c50df-116">VsDevCmd.bat can vary from computer to computer.</span></span> <span data-ttu-id="c50df-117">Falls die Datei VsDevCmd.bat nicht vorhanden oder beschädigt ist, sollten Sie sie nicht durch die VsDevCmd.bat-Datei eines anderen Computers ersetzen.</span><span class="sxs-lookup"><span data-stu-id="c50df-117">Do not replace a missing or damaged VsDevCmd.bat file with a VsDevCmd.bat from another computer.</span></span> <span data-ttu-id="c50df-118">Führen Sie stattdessen Setup erneut aus, um die fehlende Datei zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="c50df-118">Instead, rerun setup to replace the missing file.</span></span>

### <a name="available-options-for-vsdevcmdbat"></a><span data-ttu-id="c50df-119">Verfügbare Optionen für „VsDevCmd.BAT“</span><span class="sxs-lookup"><span data-stu-id="c50df-119">Available options for VsDevCmd.BAT</span></span>

<span data-ttu-id="c50df-120">Um die verfügbaren Optionen für „VsDevCmd.BAT“ anzuzeigen, führen Sie den Befehl mit der `-help`-Option aus:</span><span class="sxs-lookup"><span data-stu-id="c50df-120">To see the available options for VsDevCmd.BAT, run the command with the `-help` option:</span></span>

```console
VsDevCmd.bat -help
```

## <a name="see-also"></a><span data-ttu-id="c50df-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c50df-121">See also</span></span>

- [<span data-ttu-id="c50df-122">Erstellen über die Befehlszeile mit csc.exe</span><span class="sxs-lookup"><span data-stu-id="c50df-122">Command-line Building With csc.exe</span></span>](./command-line-building-with-csc-exe.md)
