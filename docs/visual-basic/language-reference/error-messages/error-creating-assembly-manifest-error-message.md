---
title: 'Fehler beim Erstellen des Assemblymanifests: &lt;Fehlermeldung&gt;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords: BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d846ef88f0c36b49e79b9d11252fcef419dfa0ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a><span data-ttu-id="97ad6-102">Fehler beim Erstellen des Assemblymanifests: &lt;Fehlermeldung&gt;</span><span class="sxs-lookup"><span data-stu-id="97ad6-102">Error creating assembly manifest: &lt;error message&gt;</span></span>
<span data-ttu-id="97ad6-103">Der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -Compiler ruft den Assemblylinker (Al.exe, auch bekannt als Alink) auf, um eine Assembly mit einem Manifest zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="97ad6-103">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="97ad6-104">Der Linker meldet einen Fehler in der Vorausgabestufe der Assemblyerstellung.</span><span class="sxs-lookup"><span data-stu-id="97ad6-104">The linker has reported an error in the pre-emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="97ad6-105">Zu diesem Fehler kann es kommen, wenn es Probleme mit der angegebenen Schlüsseldatei oder dem angegebenen Schlüsselcontainer gibt.</span><span class="sxs-lookup"><span data-stu-id="97ad6-105">This can occur if there are problems with the key file or the key container specified.</span></span> <span data-ttu-id="97ad6-106">Um eine Assembly vollständig zu signieren, müssen Sie eine gültige Schlüsseldatei bereitstellen, die Informationen zu den öffentlichen und privaten Schlüsseln enthält.</span><span class="sxs-lookup"><span data-stu-id="97ad6-106">To fully sign an assembly, you must provide a valid key file that contains information about the public and private keys.</span></span> <span data-ttu-id="97ad6-107">Um das Signieren einer Assembly zu verzögern, müssen Sie das Kontrollkästchen **Nur verzögerte Signierung** aktivieren und eine gültige Schlüsseldatei angeben, die Informationen zum öffentlichen Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="97ad6-107">To delay sign an assembly, you must select the **Delay sign only** check box and provide a valid key file that contains information about the public key information.</span></span> <span data-ttu-id="97ad6-108">Der private Schlüssel ist nicht erforderlich, wenn eine Assembly verzögert signiert wird.</span><span class="sxs-lookup"><span data-stu-id="97ad6-108">The private key is not necessary when an assembly is delay-signed.</span></span> <span data-ttu-id="97ad6-109">Weitere Informationen finden Sie unter [wie: Signieren einer Assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564).</span><span class="sxs-lookup"><span data-stu-id="97ad6-109">For more information, see [How to: Sign an Assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564).</span></span>  
  
 <span data-ttu-id="97ad6-110">**Fehler-ID:** BC30140</span><span class="sxs-lookup"><span data-stu-id="97ad6-110">**Error ID:** BC30140</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="97ad6-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="97ad6-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="97ad6-112">Überprüfen Sie die angegebene Fehlermeldung, und wenden Sie sich an das Thema [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) für Fehler AL1019 Weitere erläuterungen und Hinweise</span><span class="sxs-lookup"><span data-stu-id="97ad6-112">Examine the quoted error message and consult the topic [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) for error AL1019 further explanation and advice</span></span>  
  
2.  <span data-ttu-id="97ad6-113">Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="97ad6-113">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97ad6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97ad6-114">See Also</span></span>  
 [<span data-ttu-id="97ad6-115">How to: Sign an Assembly (Visual Studio) (Vorgehensweise: Signieren einer Assembly (Visual Studio))</span><span class="sxs-lookup"><span data-stu-id="97ad6-115">How to: Sign an Assembly (Visual Studio)</span></span>](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564)  
 [<span data-ttu-id="97ad6-116">Seite „Signierung“, Projekt-Designer</span><span class="sxs-lookup"><span data-stu-id="97ad6-116">Signing Page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)  
 [<span data-ttu-id="97ad6-117">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="97ad6-117">Al.exe (Assembly Linker)</span></span>](https://msdn.microsoft.com/library/c405shex)  
 [<span data-ttu-id="97ad6-118">Fehler und Warnungen Al.exe-Tools</span><span class="sxs-lookup"><span data-stu-id="97ad6-118">Al.exe Tool Errors and Warnings</span></span>](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)  
 [<span data-ttu-id="97ad6-119">Sprechen Sie mit uns</span><span class="sxs-lookup"><span data-stu-id="97ad6-119">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
