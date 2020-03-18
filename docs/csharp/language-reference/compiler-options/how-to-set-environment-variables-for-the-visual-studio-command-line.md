---
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
ms.openlocfilehash: 99e2a837877494dd4c7e0106047bce3cc39a9282
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75342363"
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a><span data-ttu-id="0a5e6-102">Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="0a5e6-102">How to set environment variables for the Visual Studio Command Line</span></span>

<span data-ttu-id="0a5e6-103">Die Umgebungsvariablen, die für Befehlszeilenbuilds erforderlich sind, werden durch die Datei VSDevCmd.bat festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0a5e6-103">The VsDevCmd.bat file sets the appropriate environment variables to enable command-line builds.</span></span>

> [!NOTE]
> <span data-ttu-id="0a5e6-104">In Visual Studio 2015 und früheren Versionen wurde für den gleichen Zweck „VSVARS32.bat“ (nicht „VsDevCmd.bat“) verwendet.</span><span class="sxs-lookup"><span data-stu-id="0a5e6-104">Visual Studio 2015 and earlier versions used VSVARS32.bat, not VsDevCmd.bat for the same purpose.</span></span> <span data-ttu-id="0a5e6-105">Diese Datei wurde unter „\Programme\Microsoft Visual Studio\\*Version*\Common7\Tools“ oder „Programme (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools“ gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0a5e6-105">This file was stored in \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools.</span></span>

<span data-ttu-id="0a5e6-106">Falls die aktuelle Version von Visual Studio auf einem Computer installiert ist, der zusätzlich über eine frühere Version von Visual Studio verfügt, sollten Sie die Dateien VsDevCmd.bat und VSVARS32.BAT aus unterschiedlichen Versionen nicht im selben Eingabeaufforderungsfenster ausführen.</span><span class="sxs-lookup"><span data-stu-id="0a5e6-106">If the current version of Visual Studio is installed on a computer that also has an earlier version of Visual Studio, you should not run VsDevCmd.bat and VSVARS32.BAT from different versions in the same Command Prompt window.</span></span> <span data-ttu-id="0a5e6-107">Stattdessen sollten Sie den Befehl für jede Version in ihrem eigenen Fenster ausführen.</span><span class="sxs-lookup"><span data-stu-id="0a5e6-107">Instead, you should run the command for each version in its own window.</span></span>

### <a name="to-run-vsdevcmdbat"></a><span data-ttu-id="0a5e6-108">Ausführen von VsDevCmd.BAT</span><span class="sxs-lookup"><span data-stu-id="0a5e6-108">To run VsDevCmd.BAT</span></span>

1. <span data-ttu-id="0a5e6-109">Öffnen Sie über das Menü **Start** die **Developer-Eingabeaufforderung für VS 2019**.</span><span class="sxs-lookup"><span data-stu-id="0a5e6-109">From the **Start** menu, open the **Developer Command Prompt for VS 2019**.</span></span>  <span data-ttu-id="0a5e6-110">Die Datei befindet sich im Ordner **Visual Studio 2019**.</span><span class="sxs-lookup"><span data-stu-id="0a5e6-110">It's in the **Visual Studio 2019** folder.</span></span>

2. <span data-ttu-id="0a5e6-111">Wechseln Sie zum Unterverzeichnis „Programme\Microsoft Visual Studio\\*Version*\\*Angebot*\Common7\Tools“ oder „Programme (x86)\Microsoft Visual Studio\\*Version*\\*Angebot*\Common7\Tools“ Ihrer Installation.</span><span class="sxs-lookup"><span data-stu-id="0a5e6-111">Change to the \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools or \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools subdirectory of your installation.</span></span>  <span data-ttu-id="0a5e6-112">(Die *Version* lautet für die aktuelle Version *2019*.</span><span class="sxs-lookup"><span data-stu-id="0a5e6-112">(*Version* is *2019* for the current version.</span></span> <span data-ttu-id="0a5e6-113">*Angebot* ist einer der Werte *Enterprise*, *Professional* oder *Community*.)</span><span class="sxs-lookup"><span data-stu-id="0a5e6-113">*Offering* is one of *Enterprise*, *Professional* or *Community*.)</span></span>

3. <span data-ttu-id="0a5e6-114">Führen Sie VsDevCmd.bat aus, indem Sie **VsDevCmd** eingeben.</span><span class="sxs-lookup"><span data-stu-id="0a5e6-114">Run VsDevCmd.bat by typing **VsDevCmd**.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="0a5e6-115">VsDevCmd.bat kann auf verschiedenen Computern unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="0a5e6-115">VsDevCmd.bat can vary from computer to computer.</span></span> <span data-ttu-id="0a5e6-116">Falls die Datei VsDevCmd.bat nicht vorhanden oder beschädigt ist, sollten Sie sie nicht durch die VsDevCmd.bat-Datei eines anderen Computers ersetzen.</span><span class="sxs-lookup"><span data-stu-id="0a5e6-116">Do not replace a missing or damaged VsDevCmd.bat file with a VsDevCmd.bat from another computer.</span></span> <span data-ttu-id="0a5e6-117">Führen Sie stattdessen Setup erneut aus, um die fehlende Datei zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="0a5e6-117">Instead, rerun setup to replace the missing file.</span></span>

### <a name="available-options-for-vsdevcmdbat"></a><span data-ttu-id="0a5e6-118">Verfügbare Optionen für „VsDevCmd.BAT“</span><span class="sxs-lookup"><span data-stu-id="0a5e6-118">Available options for VsDevCmd.BAT</span></span>

<span data-ttu-id="0a5e6-119">Um die verfügbaren Optionen für „VsDevCmd.BAT“ anzuzeigen, führen Sie den Befehl mit der `-help`-Option aus:</span><span class="sxs-lookup"><span data-stu-id="0a5e6-119">To see the available options for VsDevCmd.BAT, run the command with the `-help` option:</span></span>

```console
VsDevCmd.bat -help
```

## <a name="see-also"></a><span data-ttu-id="0a5e6-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0a5e6-120">See also</span></span>

- [<span data-ttu-id="0a5e6-121">Erstellen über die Befehlszeile mit csc.exe</span><span class="sxs-lookup"><span data-stu-id="0a5e6-121">Command-line Building With csc.exe</span></span>](./command-line-building-with-csc-exe.md)
