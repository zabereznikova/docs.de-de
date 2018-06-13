---
title: 'Assembly kann nicht ausgegeben: &lt;Fehlermeldung&gt;'
ms.date: 07/20/2015
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: 8f497069088ad30a3be58d02caa0a32f7f1b21b7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595172"
---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a><span data-ttu-id="72d38-102">Assembly kann nicht ausgegeben: &lt;Fehlermeldung&gt;</span><span class="sxs-lookup"><span data-stu-id="72d38-102">Unable to emit assembly: &lt;error message&gt;</span></span>
<span data-ttu-id="72d38-103">Visual Basic-Compiler Ruft den Assemblylinker (Al.exe, auch bekannt als Alink) auf eine Assembly mit einem Manifest zu erstellen, mit der Linker in der Ausgabephase der Assemblyerstellung ein Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="72d38-103">The Visual Basic compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest, with the linker reporting an error in the emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="72d38-104">**Fehler-ID:** BC30145</span><span class="sxs-lookup"><span data-stu-id="72d38-104">**Error ID:** BC30145</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="72d38-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="72d38-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="72d38-106">Überprüfen Sie die angegebene Fehlermeldung, und wenden Sie sich an das Thema [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="72d38-106">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="72d38-107">für weitere erläuterungen und Hinweise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="72d38-107">for further explanation and advice.</span></span>  
  
2.  <span data-ttu-id="72d38-108">Wiederholen Sie die Assembly manuell zu signieren, entweder die [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) oder [Sn.exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="72d38-108">Try signing the assembly manually, using either the [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) or the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>  
  
3.  <span data-ttu-id="72d38-109">Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="72d38-109">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="72d38-110">So signieren Sie die Assembly manuell</span><span class="sxs-lookup"><span data-stu-id="72d38-110">To sign the assembly manually</span></span>  
  
1.  <span data-ttu-id="72d38-111">Verwenden Sie [Sn.exe (Strong Name-Tool)][Sn.exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) um ein öffentliches/privates Schlüsselpaar-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="72d38-111">Use the [Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) to create a public/private key pair file.</span></span>  
  
     <span data-ttu-id="72d38-112">Die Dateierweiterung dieser Datei lautet .snk.</span><span class="sxs-lookup"><span data-stu-id="72d38-112">This file has a .snk extension.</span></span>  
  
2.  <span data-ttu-id="72d38-113">Löschen Sie den COM-Verweis, der für den Fehler verantwortlich ist, aus Ihrem Projekt.</span><span class="sxs-lookup"><span data-stu-id="72d38-113">Delete the COM reference that is generating the error from your project.</span></span>  
  
3.  <span data-ttu-id="72d38-114">Vom Windows **starten** Sie im Menü **Programme**, zeigen Sie auf **Microsoft Visual Studio 2008**, zeigen Sie auf **Visual Studio-Tools**, und Klicken Sie dann auf **Visual Studio 2008-Eingabeaufforderung**.</span><span class="sxs-lookup"><span data-stu-id="72d38-114">From the Windows **Start** menu, point to **Programs**, point to **Microsoft Visual Studio 2008**, point to **Visual Studio Tools**, and then click **Visual Studio 2008 Command Prompt**.</span></span>  
  
4.  <span data-ttu-id="72d38-115">Wechseln Sie in das Verzeichnis, in das Sie den Assemblywrapper platzieren möchten.</span><span class="sxs-lookup"><span data-stu-id="72d38-115">Move to the directory where you want to place your assembly wrapper.</span></span>  
  
5.  <span data-ttu-id="72d38-116">Geben Sie den folgenden Code ein.</span><span class="sxs-lookup"><span data-stu-id="72d38-116">Type the following code.</span></span>  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     <span data-ttu-id="72d38-117">Im Folgenden finden Sie ein Beispiel für den von Ihnen eingegebenen Code.</span><span class="sxs-lookup"><span data-stu-id="72d38-117">An example of the code you might enter would be the following.</span></span>  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     <span data-ttu-id="72d38-118">Verwenden Sie doppelte Anführungszeichen ("), wenn ein Pfad oder eine Datei Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="72d38-118">Use double quotation marks (") if a path or file contains spaces.</span></span>  
  
6.  <span data-ttu-id="72d38-119">Fügen Sie in Visual Studio einen .NET Framework-Assembly-Verweis auf die Datei, die Sie gerade erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="72d38-119">In Visual Studio, add a .NET Assembly reference to the file you just created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72d38-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72d38-120">See Also</span></span>  
 
 <span data-ttu-id="72d38-121">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="72d38-121">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span>  
 <span data-ttu-id="72d38-122">[Sn.exe (Strong Name-Tool)] [Sn.exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="72d38-122">[Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>  
 [<span data-ttu-id="72d38-123">Vorgehensweise: Erstellen eines öffentlichen/privaten Schlüsselpaars</span><span class="sxs-lookup"><span data-stu-id="72d38-123">How to: Create a Public-Private Key Pair</span></span>](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)  
 [<span data-ttu-id="72d38-124">Sprechen Sie mit uns</span><span class="sxs-lookup"><span data-stu-id="72d38-124">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
