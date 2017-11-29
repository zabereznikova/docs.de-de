---
title: 'Assembly kann nicht ausgegeben: &lt;Fehlermeldung&gt;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords: BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9dcf3d4bec379faa5783ca17847b91f9739df598
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a><span data-ttu-id="a0fd2-102">Assembly kann nicht ausgegeben: &lt;Fehlermeldung&gt;</span><span class="sxs-lookup"><span data-stu-id="a0fd2-102">Unable to emit assembly: &lt;error message&gt;</span></span>
<span data-ttu-id="a0fd2-103">Der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]-Compiler ruft den Assemblylinker (Al.exe, auch bekannt als Alink) auf, um eine Assembly mit einem Manifest zu erstellen. Dabei meldet der Linker einen Fehler in der Ausgabephase der Assemblyerstellung.</span><span class="sxs-lookup"><span data-stu-id="a0fd2-103">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest, with the linker reporting an error in the emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="a0fd2-104">**Fehler-ID:** BC30145</span><span class="sxs-lookup"><span data-stu-id="a0fd2-104">**Error ID:** BC30145</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a0fd2-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a0fd2-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="a0fd2-106">Überprüfen Sie die angegebene Fehlermeldung, und gehen Sie zum Thema [Fehler und Warnungen des Al.exe-Tools](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) , um weitere Erläuterungen und Hinweise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a0fd2-106">Examine the quoted error message and consult the topic [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) for further explanation and advice.</span></span>  
  
2.  <span data-ttu-id="a0fd2-107">Wiederholen Sie die Assembly manuell zu signieren, entweder die [Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) oder [Sn.exe (Strong Name-Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span><span class="sxs-lookup"><span data-stu-id="a0fd2-107">Try signing the assembly manually, using either the [Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) or the [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
3.  <span data-ttu-id="a0fd2-108">Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a0fd2-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="a0fd2-109">So signieren Sie die Assembly manuell</span><span class="sxs-lookup"><span data-stu-id="a0fd2-109">To sign the assembly manually</span></span>  
  
1.  <span data-ttu-id="a0fd2-110">Verwenden der [Sn.exe (Strong Name-Tool)](https://msdn.microsoft.com/library/k5b5tt23) So erstellen Sie eine öffentliches/privates Schlüsselpaar-Datei.</span><span class="sxs-lookup"><span data-stu-id="a0fd2-110">Use the [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) to create a public/private key pair file.</span></span>  
  
     <span data-ttu-id="a0fd2-111">Die Dateierweiterung dieser Datei lautet .snk.</span><span class="sxs-lookup"><span data-stu-id="a0fd2-111">This file has a .snk extension.</span></span>  
  
2.  <span data-ttu-id="a0fd2-112">Löschen Sie den COM-Verweis, der für den Fehler verantwortlich ist, aus Ihrem Projekt.</span><span class="sxs-lookup"><span data-stu-id="a0fd2-112">Delete the COM reference that is generating the error from your project.</span></span>  
  
3.  <span data-ttu-id="a0fd2-113">Vom Windows **starten** Sie im Menü **Programme**, zeigen Sie auf **Microsoft Visual Studio 2008**, zeigen Sie auf **Visual Studio-Tools**, und Klicken Sie dann auf **Visual Studio 2008-Eingabeaufforderung**.</span><span class="sxs-lookup"><span data-stu-id="a0fd2-113">From the Windows **Start** menu, point to **Programs**, point to **Microsoft Visual Studio 2008**, point to **Visual Studio Tools**, and then click **Visual Studio 2008 Command Prompt**.</span></span>  
  
4.  <span data-ttu-id="a0fd2-114">Wechseln Sie in das Verzeichnis, in das Sie den Assemblywrapper platzieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a0fd2-114">Move to the directory where you want to place your assembly wrapper.</span></span>  
  
5.  <span data-ttu-id="a0fd2-115">Geben Sie den folgenden Code ein.</span><span class="sxs-lookup"><span data-stu-id="a0fd2-115">Type the following code.</span></span>  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     <span data-ttu-id="a0fd2-116">Im Folgenden finden Sie ein Beispiel für den von Ihnen eingegebenen Code.</span><span class="sxs-lookup"><span data-stu-id="a0fd2-116">An example of the code you might enter would be the following.</span></span>  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     <span data-ttu-id="a0fd2-117">Verwenden Sie doppelte Anführungszeichen ("), wenn ein Pfad oder eine Datei Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="a0fd2-117">Use double quotation marks (") if a path or file contains spaces.</span></span>  
  
6.  <span data-ttu-id="a0fd2-118">Fügen Sie in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] einen .NET Assembly-Verweis auf die gerade von Ihnen erstellte Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="a0fd2-118">In [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], add a .NET Assembly reference to the file you just created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0fd2-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0fd2-119">See Also</span></span>  
 [<span data-ttu-id="a0fd2-120">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="a0fd2-120">Al.exe (Assembly Linker)</span></span>](https://msdn.microsoft.com/library/c405shex)  
 [<span data-ttu-id="a0fd2-121">Fehler und Warnungen Al.exe-Tools</span><span class="sxs-lookup"><span data-stu-id="a0fd2-121">Al.exe Tool Errors and Warnings</span></span>](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)  
 [<span data-ttu-id="a0fd2-122">Sn.exe (Strong Name-Tool)</span><span class="sxs-lookup"><span data-stu-id="a0fd2-122">Sn.exe (Strong Name Tool)</span></span>](https://msdn.microsoft.com/library/k5b5tt23)  
 [<span data-ttu-id="a0fd2-123">Vorgehensweise: Erstellen eines öffentlichen/privaten Schlüsselpaars</span><span class="sxs-lookup"><span data-stu-id="a0fd2-123">How to: Create a Public-Private Key Pair</span></span>](http://msdn.microsoft.com/library/05026813-f3bd-4d7c-9e0b-fc588eb3d114)  
 [<span data-ttu-id="a0fd2-124">Sprechen Sie mit uns</span><span class="sxs-lookup"><span data-stu-id="a0fd2-124">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
