---
title: 'Assembly wurde nicht generiert: <error message>'
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: 530aaee40be92bf72ee4b83b4141108e9b81c8a1
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2019
ms.locfileid: "70968852"
---
# <a name="unable-to-emit-assembly-error-message"></a><span data-ttu-id="47c39-102">Die Assembly kann nicht ausgegeben \<werden: Fehlermeldung ></span><span class="sxs-lookup"><span data-stu-id="47c39-102">Unable to emit assembly: \<error message></span></span>

<span data-ttu-id="47c39-103">Der Visual Basic-Compiler ruft den Assemblylinker (*Al. exe*, auch bekannt als ALink) auf, um eine Assembly mit einem Manifest zu generieren, und der Linker meldet einen Fehler in der Ausgabe Phase der Erstellung der Assembly.</span><span class="sxs-lookup"><span data-stu-id="47c39-103">The Visual Basic compiler calls the Assembly Linker (*Al.exe*, also known as Alink) to generate an assembly with a manifest, and the linker reports an error in the emission stage of creating the assembly.</span></span>

<span data-ttu-id="47c39-104">**Fehler-ID:** BC30145</span><span class="sxs-lookup"><span data-stu-id="47c39-104">**Error ID:** BC30145</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="47c39-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="47c39-105">To correct this error</span></span>

1. <span data-ttu-id="47c39-106">Überprüfen Sie die Fehlermeldung in Anführungszeichen, und lesen Sie das Thema " [Al. exe](../../../framework/tools/al-exe-assembly-linker.md) ".</span><span class="sxs-lookup"><span data-stu-id="47c39-106">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) for further explanation and advice.</span></span>

2. <span data-ttu-id="47c39-107">Versuchen Sie, die Assembly manuell zu signieren, indem Sie entweder " [Al. exe](../../../framework/tools/al-exe-assembly-linker.md) " oder " [Sn. exe" (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="47c39-107">Try signing the assembly manually, using either the [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) or the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>

3. <span data-ttu-id="47c39-108">Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="47c39-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="47c39-109">So signieren Sie die Assembly manuell</span><span class="sxs-lookup"><span data-stu-id="47c39-109">To sign the assembly manually</span></span>

1. <span data-ttu-id="47c39-110">Verwenden Sie " [Sn. exe" (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)), um eine Datei mit einem öffentlichen/privaten Schlüsselpaar zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="47c39-110">Use the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) to create a public/private key pair file.</span></span>

   <span data-ttu-id="47c39-111">Diese Datei hat die Erweiterung " *. snk* ".</span><span class="sxs-lookup"><span data-stu-id="47c39-111">This file has an *.snk* extension.</span></span>

2. <span data-ttu-id="47c39-112">Löschen Sie den COM-Verweis, der für den Fehler verantwortlich ist, aus Ihrem Projekt.</span><span class="sxs-lookup"><span data-stu-id="47c39-112">Delete the COM reference that is generating the error from your project.</span></span>

3. <span data-ttu-id="47c39-113">Öffnen Sie die [Developer-Eingabeaufforderung für Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="47c39-113">Open the [Developer Command Prompt for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span></span>

   <span data-ttu-id="47c39-114">Geben Sie in Windows 10 die **Developer-Eingabeaufforderung** in das Suchfeld auf der Taskleiste ein.</span><span class="sxs-lookup"><span data-stu-id="47c39-114">In Windows 10, enter **Developer command prompt** into the search box on the task bar.</span></span> <span data-ttu-id="47c39-115">Wählen Sie dann in der Ergebnisliste **Developer-Eingabeaufforderung für vs 2017** aus.</span><span class="sxs-lookup"><span data-stu-id="47c39-115">Then, select **Developer Command Prompt for VS 2017** from the results list.</span></span>

4. <span data-ttu-id="47c39-116">Wechseln Sie in das Verzeichnis, in dem Sie den Assemblywrapper platzieren möchten.</span><span class="sxs-lookup"><span data-stu-id="47c39-116">Change the directory to the directory where you want to place your assembly wrapper.</span></span>

5. <span data-ttu-id="47c39-117">Geben Sie folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="47c39-117">Enter the following command:</span></span>

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   <span data-ttu-id="47c39-118">Ein Beispiel für den eigentlichen Befehl, den Sie eingeben können, ist:</span><span class="sxs-lookup"><span data-stu-id="47c39-118">An example of the actual command you might enter is:</span></span>

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > <span data-ttu-id="47c39-119">Verwenden Sie doppelte Anführungszeichen, wenn ein Pfad oder eine Datei Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="47c39-119">Use double quotation marks if a path or file contains spaces.</span></span>

6. <span data-ttu-id="47c39-120">Fügen Sie in Visual Studio einen .net-Assemblyverweis auf die soeben erstellte Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="47c39-120">In Visual Studio, add a .NET Assembly reference to the file you just created.</span></span>

## <a name="see-also"></a><span data-ttu-id="47c39-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47c39-121">See also</span></span>

- [<span data-ttu-id="47c39-122">Al.exe</span><span class="sxs-lookup"><span data-stu-id="47c39-122">Al.exe</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="47c39-123">Sn.exe (Strong Name-Tool)</span><span class="sxs-lookup"><span data-stu-id="47c39-123">Sn.exe (Strong Name Tool)</span></span>](../../../framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="47c39-124">Vorgehensweise: Erstellen eines öffentlichen/privaten Schlüsselpaars</span><span class="sxs-lookup"><span data-stu-id="47c39-124">How to: Create a Public-Private Key Pair</span></span>](../../../standard/assembly/create-public-private-key-pair.md)
- [<span data-ttu-id="47c39-125">Sprechen Sie mit uns</span><span class="sxs-lookup"><span data-stu-id="47c39-125">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
