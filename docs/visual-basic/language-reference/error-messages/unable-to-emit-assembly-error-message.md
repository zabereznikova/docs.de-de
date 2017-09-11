---
title: 'Assembly wurde nicht generiert: &lt;Fehlermeldung&gt; | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30145
- bc30145
dev_langs:
- VB
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d15981a1a2fb31ba377066fa421f5a9979d47a12
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a><span data-ttu-id="a8a08-102">Assembly wurde nicht generiert: &lt;Fehlermeldung&gt;</span><span class="sxs-lookup"><span data-stu-id="a8a08-102">Unable to emit assembly: &lt;error message&gt;</span></span>
<span data-ttu-id="a8a08-103">Der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]-Compiler ruft den Assemblylinker (Al.exe, auch bekannt als Alink) auf, um eine Assembly mit einem Manifest zu erstellen. Dabei meldet der Linker einen Fehler in der Ausgabephase der Assemblyerstellung.</span><span class="sxs-lookup"><span data-stu-id="a8a08-103">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest, with the linker reporting an error in the emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="a8a08-104">**Fehler-ID:** BC30145</span><span class="sxs-lookup"><span data-stu-id="a8a08-104">**Error ID:** BC30145</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a8a08-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a8a08-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="a8a08-106">Überprüfen Sie die angezeigte Fehlermeldung an, und wenden Sie sich an das Thema [Al.exe Tool Fehler und Warnungen](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) Weitere Hinweise und Tipps.</span><span class="sxs-lookup"><span data-stu-id="a8a08-106">Examine the quoted error message and consult the topic [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) for further explanation and advice.</span></span>  
  
2.  <span data-ttu-id="a8a08-107">Wiederholen Sie die Assembly manuell zu signieren, entweder mithilfe der [Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) oder [Sn.exe (Strong Name-Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span><span class="sxs-lookup"><span data-stu-id="a8a08-107">Try signing the assembly manually, using either the [Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) or the [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
3.  <span data-ttu-id="a8a08-108">Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a8a08-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="a8a08-109">So signieren Sie die Assembly manuell</span><span class="sxs-lookup"><span data-stu-id="a8a08-109">To sign the assembly manually</span></span>  
  
1.  <span data-ttu-id="a8a08-110">Verwenden der [Sn.exe (Strong Name-Tool)](https://msdn.microsoft.com/library/k5b5tt23) zum Erstellen einer Datei Schlüsselpaar aus öffentlichem und privatem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="a8a08-110">Use the [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) to create a public/private key pair file.</span></span>  
  
     <span data-ttu-id="a8a08-111">Die Dateierweiterung dieser Datei lautet .snk.</span><span class="sxs-lookup"><span data-stu-id="a8a08-111">This file has a .snk extension.</span></span>  
  
2.  <span data-ttu-id="a8a08-112">Löschen Sie den COM-Verweis, der für den Fehler verantwortlich ist, aus Ihrem Projekt.</span><span class="sxs-lookup"><span data-stu-id="a8a08-112">Delete the COM reference that is generating the error from your project.</span></span>  
  
3.  <span data-ttu-id="a8a08-113">Von der Windows **Start** auf **Programme**, zeigen Sie auf **Microsoft Visual Studio 2008**, zeigen Sie auf **Visual Studio-Tools**, und klicken Sie dann auf **Visual Studio 2008 Command Prompt**.</span><span class="sxs-lookup"><span data-stu-id="a8a08-113">From the Windows **Start** menu, point to **Programs**, point to **Microsoft Visual Studio 2008**, point to **Visual Studio Tools**, and then click **Visual Studio 2008 Command Prompt**.</span></span>  
  
4.  <span data-ttu-id="a8a08-114">Wechseln Sie in das Verzeichnis, in das Sie den Assemblywrapper platzieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a8a08-114">Move to the directory where you want to place your assembly wrapper.</span></span>  
  
5.  <span data-ttu-id="a8a08-115">Geben Sie den folgenden Code ein.</span><span class="sxs-lookup"><span data-stu-id="a8a08-115">Type the following code.</span></span>  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     <span data-ttu-id="a8a08-116">Im Folgenden finden Sie ein Beispiel für den von Ihnen eingegebenen Code.</span><span class="sxs-lookup"><span data-stu-id="a8a08-116">An example of the code you might enter would be the following.</span></span>  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     <span data-ttu-id="a8a08-117">Verwenden Sie doppelte Anführungszeichen ("), wenn ein Pfad oder eine Datei Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="a8a08-117">Use double quotation marks (") if a path or file contains spaces.</span></span>  
  
6.  <span data-ttu-id="a8a08-118">Fügen Sie in [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] einen .NET Assembly-Verweis auf die gerade von Ihnen erstellte Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="a8a08-118">In [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], add a .NET Assembly reference to the file you just created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8a08-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8a08-119">See Also</span></span>  
 <span data-ttu-id="a8a08-120">[Al.exe (Assemblylinker)](https://msdn.microsoft.com/library/c405shex) </span><span class="sxs-lookup"><span data-stu-id="a8a08-120">[Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) </span></span>  
<span data-ttu-id="a8a08-121"> [Al.exe-Tools-Fehler und Warnungen](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) </span><span class="sxs-lookup"><span data-stu-id="a8a08-121"> [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) </span></span>  
<span data-ttu-id="a8a08-122"> [Sn.exe (Strong Name-Tool)](https://msdn.microsoft.com/library/k5b5tt23) </span><span class="sxs-lookup"><span data-stu-id="a8a08-122"> [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) </span></span>  
<span data-ttu-id="a8a08-123"> [Vorgehensweise: Erstellen eines öffentlichen/privaten Schlüsselpaars](http://msdn.microsoft.com/library/05026813-f3bd-4d7c-9e0b-fc588eb3d114) </span><span class="sxs-lookup"><span data-stu-id="a8a08-123"> [How to: Create a Public-Private Key Pair](http://msdn.microsoft.com/library/05026813-f3bd-4d7c-9e0b-fc588eb3d114) </span></span>  
<span data-ttu-id="a8a08-124"> [Sprechen Sie mit uns](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span><span class="sxs-lookup"><span data-stu-id="a8a08-124"> [Talk to Us](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span></span>
