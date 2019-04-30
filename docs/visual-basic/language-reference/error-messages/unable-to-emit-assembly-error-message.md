---
title: 'Assembly wurde nicht generiert: <error message>'
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: d564f4f4462a691504297d65575956c5f06691ca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936278"
---
# <a name="unable-to-emit-assembly-error-message"></a><span data-ttu-id="4ed6f-102">Assembly wurde nicht generiert: \<Fehlermeldung ></span><span class="sxs-lookup"><span data-stu-id="4ed6f-102">Unable to emit assembly: \<error message></span></span>

<span data-ttu-id="4ed6f-103">Visual Basic-Compiler Ruft den Assemblylinker (*Al.exe*, auch bekannt als Alink) zum Generieren einer Assembly mit einem Manifest und der Linker meldet einen Fehler verwendet, in der Ausgabephase der Assemblyerstellung.</span><span class="sxs-lookup"><span data-stu-id="4ed6f-103">The Visual Basic compiler calls the Assembly Linker (*Al.exe*, also known as Alink) to generate an assembly with a manifest, and the linker reports an error in the emission stage of creating the assembly.</span></span>

<span data-ttu-id="4ed6f-104">**Fehler-ID:** BC30145</span><span class="sxs-lookup"><span data-stu-id="4ed6f-104">**Error ID:** BC30145</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="4ed6f-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="4ed6f-105">To correct this error</span></span>

1. <span data-ttu-id="4ed6f-106">Überprüfen Sie die angegebene Fehlermeldung, und wenden Sie sich an das Thema [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) für weitere erläuterungen und Hinweise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4ed6f-106">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) for further explanation and advice.</span></span>

2. <span data-ttu-id="4ed6f-107">Versuchen Sie es manuell zu signieren der Assemblys, entweder die [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) oder [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="4ed6f-107">Try signing the assembly manually, using either the [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) or the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>

3. <span data-ttu-id="4ed6f-108">Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4ed6f-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="4ed6f-109">So signieren Sie die Assembly manuell</span><span class="sxs-lookup"><span data-stu-id="4ed6f-109">To sign the assembly manually</span></span>

1. <span data-ttu-id="4ed6f-110">Verwenden Sie die [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) zum Erstellen einer Datei Paar aus privatem und öffentlichem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="4ed6f-110">Use the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) to create a public/private key pair file.</span></span>

   <span data-ttu-id="4ed6f-111">Diese Datei enthält eine *snk* Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="4ed6f-111">This file has an *.snk* extension.</span></span>

2. <span data-ttu-id="4ed6f-112">Löschen Sie den COM-Verweis, der für den Fehler verantwortlich ist, aus Ihrem Projekt.</span><span class="sxs-lookup"><span data-stu-id="4ed6f-112">Delete the COM reference that is generating the error from your project.</span></span>

3. <span data-ttu-id="4ed6f-113">Öffnen der [Developer-Eingabeaufforderung für Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="4ed6f-113">Open the [Developer Command Prompt for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span></span>

   <span data-ttu-id="4ed6f-114">Geben Sie im Windows 10, **Developer-Eingabeaufforderung** in das Suchfeld auf der Taskleiste.</span><span class="sxs-lookup"><span data-stu-id="4ed6f-114">In Windows 10, enter **Developer command prompt** into the search box on the task bar.</span></span> <span data-ttu-id="4ed6f-115">Wählen Sie dann **Developer-Eingabeaufforderung für Visual Studio 2017** in der Ergebnisliste aus.</span><span class="sxs-lookup"><span data-stu-id="4ed6f-115">Then, select **Developer Command Prompt for VS 2017** from the results list.</span></span>

4. <span data-ttu-id="4ed6f-116">Wechseln Sie zu dem Verzeichnis, in dem Sie den Assemblywrapper platzieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4ed6f-116">Change the directory to the directory where you want to place your assembly wrapper.</span></span>

5. <span data-ttu-id="4ed6f-117">Geben Sie folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="4ed6f-117">Enter the following command:</span></span>

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   <span data-ttu-id="4ed6f-118">Ein Beispiel der eigentliche Befehl Ihnen eingegebenen ist:</span><span class="sxs-lookup"><span data-stu-id="4ed6f-118">An example of the actual command you might enter is:</span></span>

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > <span data-ttu-id="4ed6f-119">Verwenden Sie doppelte Anführungszeichen, wenn ein Pfad- oder Dateiname Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="4ed6f-119">Use double quotation marks if a path or file contains spaces.</span></span>

6. <span data-ttu-id="4ed6f-120">Fügen Sie in Visual Studio einen .NET Framework-Assembly-Verweis auf die Datei, die Sie gerade erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="4ed6f-120">In Visual Studio, add a .NET Assembly reference to the file you just created.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ed6f-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ed6f-121">See also</span></span>

- [<span data-ttu-id="4ed6f-122">Al.exe</span><span class="sxs-lookup"><span data-stu-id="4ed6f-122">Al.exe</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="4ed6f-123">Sn.exe (Strong Name-Tool)</span><span class="sxs-lookup"><span data-stu-id="4ed6f-123">Sn.exe (Strong Name Tool)</span></span>](../../../framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="4ed6f-124">Vorgehensweise: Erstellen eines öffentlichen/privaten Schlüsselpaars</span><span class="sxs-lookup"><span data-stu-id="4ed6f-124">How to: Create a Public-Private Key Pair</span></span>](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)
- [<span data-ttu-id="4ed6f-125">Sprechen Sie mit uns</span><span class="sxs-lookup"><span data-stu-id="4ed6f-125">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)