---
title: 'Fehler beim Erstellen des Assemblymanifests: &lt;Fehlermeldung&gt; | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30140
- vbc30140
dev_langs:
- VB
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: 13
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
ms.openlocfilehash: 12e08feff09e901839c4e282d32a0a4e54e12576
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a><span data-ttu-id="a586b-102">Fehler beim Erstellen des Assemblymanifests: &lt;Fehlermeldung&gt;</span><span class="sxs-lookup"><span data-stu-id="a586b-102">Error creating assembly manifest: &lt;error message&gt;</span></span>
<span data-ttu-id="a586b-103">Der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]-Compiler ruft den Assemblylinker (Al.exe, auch bekannt als Alink) auf, um eine Assembly mit einem Manifest zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a586b-103">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="a586b-104">Der Linker meldet einen Fehler in der Vorausgabestufe der Assemblyerstellung.</span><span class="sxs-lookup"><span data-stu-id="a586b-104">The linker has reported an error in the pre-emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="a586b-105">Zu diesem Fehler kann es kommen, wenn es Probleme mit der angegebenen Schlüsseldatei oder dem angegebenen Schlüsselcontainer gibt.</span><span class="sxs-lookup"><span data-stu-id="a586b-105">This can occur if there are problems with the key file or the key container specified.</span></span> <span data-ttu-id="a586b-106">Um eine Assembly vollständig zu signieren, müssen Sie eine gültige Schlüsseldatei bereitstellen, die Informationen zu den öffentlichen und privaten Schlüsseln enthält.</span><span class="sxs-lookup"><span data-stu-id="a586b-106">To fully sign an assembly, you must provide a valid key file that contains information about the public and private keys.</span></span> <span data-ttu-id="a586b-107">Um eine Assembly verzögert signieren, wählen Sie die **nur verzögerte Signierung** und geben Sie eine gültige Schlüsseldatei, die Informationen zu den öffentlichen Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="a586b-107">To delay sign an assembly, you must select the **Delay sign only** check box and provide a valid key file that contains information about the public key information.</span></span> <span data-ttu-id="a586b-108">Der private Schlüssel ist nicht erforderlich, wenn eine Assembly verzögert signiert wird.</span><span class="sxs-lookup"><span data-stu-id="a586b-108">The private key is not necessary when an assembly is delay-signed.</span></span> <span data-ttu-id="a586b-109">Weitere Informationen finden Sie unter [Gewusst wie: Signieren einer Assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564).</span><span class="sxs-lookup"><span data-stu-id="a586b-109">For more information, see [How to: Sign an Assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564).</span></span>  
  
 <span data-ttu-id="a586b-110">**Fehler-ID:** BC30140</span><span class="sxs-lookup"><span data-stu-id="a586b-110">**Error ID:** BC30140</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a586b-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a586b-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="a586b-112">Überprüfen Sie die angezeigte Fehlermeldung an, und wenden Sie sich an das Thema [Al.exe Tool Fehler und Warnungen](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) für Fehler al1019, um weitere Erklärung und Hinweise</span><span class="sxs-lookup"><span data-stu-id="a586b-112">Examine the quoted error message and consult the topic [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) for error AL1019 further explanation and advice</span></span>  
  
2.  <span data-ttu-id="a586b-113">Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a586b-113">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a586b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a586b-114">See Also</span></span>  
 <span data-ttu-id="a586b-115">[Vorgehensweise: Signieren einer Assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564) </span><span class="sxs-lookup"><span data-stu-id="a586b-115">[How to: Sign an Assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564) </span></span>  
<span data-ttu-id="a586b-116"> [Seite „Signierung“, Projekt-Designer](https://docs.microsoft.com/visualstudio/ide/reference/signing-page-project-designer) </span><span class="sxs-lookup"><span data-stu-id="a586b-116"> [Signing Page, Project Designer](https://docs.microsoft.com/visualstudio/ide/reference/signing-page-project-designer) </span></span>  
<span data-ttu-id="a586b-117"> [Al.exe (Assemblylinker)](https://msdn.microsoft.com/library/c405shex) </span><span class="sxs-lookup"><span data-stu-id="a586b-117"> [Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) </span></span>  
<span data-ttu-id="a586b-118"> [Al.exe-Tools-Fehler und Warnungen](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) </span><span class="sxs-lookup"><span data-stu-id="a586b-118"> [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) </span></span>  
<span data-ttu-id="a586b-119"> [Sprechen Sie mit uns](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span><span class="sxs-lookup"><span data-stu-id="a586b-119"> [Talk to Us](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span></span>
