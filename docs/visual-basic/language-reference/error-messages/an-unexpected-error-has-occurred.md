---
title: "Ein unerwarteter Fehler ist aufgetreten, da eine Betriebssystemressource zum Start einer einzelnen Instanz übernommen werden kann | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrAppModel_CantGetMemoryMappedFile
dev_langs:
- VB
ms.assetid: 0d9f2a30-ff72-4355-8060-744f22339359
caps.latest.revision: 10
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
ms.openlocfilehash: 03ab2d1c746fbc28c0c6f3e59371cc6bbd4050cd
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="an-unexpected-error-has-occurred-because-an-operating-system-resource-required-for-single-instance-startup-cannot-be-acquired"></a><span data-ttu-id="df549-102">Unerwarteter Fehler. Eine Betriebssystemressource, die für den Start einer einzelnen Instanz benötigt wird, ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="df549-102">An unexpected error has occurred because an operating system resource required for single instance startup cannot be acquired</span></span>
<span data-ttu-id="df549-103">Die Anwendung konnte eine erforderliche Betriebssystemressource nicht abrufen.</span><span class="sxs-lookup"><span data-stu-id="df549-103">The application could not acquire a necessary operating system resource.</span></span> <span data-ttu-id="df549-104">Mögliche Ursachen für dieses Problem:</span><span class="sxs-lookup"><span data-stu-id="df549-104">Some of the possible causes for this problem are:</span></span>  
  
-   <span data-ttu-id="df549-105">Die Anwendung verfügt nicht über die Berechtigungen, benannte Betriebssystemobjekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="df549-105">The application does not have permissions to create named operating-system objects.</span></span>  
  
-   <span data-ttu-id="df549-106">Die Common Language Runtime verfügt nicht über die Berechtigungen, speicherzugeordnete Dateien zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="df549-106">The common language runtime does not have permissions to create memory-mapped files.</span></span>  
  
-   <span data-ttu-id="df549-107">Die Anwendung muss auf ein Betriebssystemobjekt zugreifen, das jedoch in einem anderen Prozess verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="df549-107">The application needs to access an operating-system object, but another process is using it.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="df549-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="df549-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="df549-109">Stellen Sie sicher, dass die Anwendung über ausreichende Berechtigungen verfügt, um benannte Betriebssystemobjekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="df549-109">Check that the application has sufficient permissions to create named operating-system objects.</span></span>  
  
2.  <span data-ttu-id="df549-110">Stellen Sie sicher, dass die Common Language Runtime über ausreichende Berechtigungen verfügt, um speicherzugeordnete Dateien zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="df549-110">Check that the common language runtime has sufficient permissions to create memory-mapped files.</span></span>  
  
3.  <span data-ttu-id="df549-111">Starten Sie den Computer neu, um alle Prozesse zu beenden, die erforderlich sind, um eine Verbindung zur ursprünglichen Instanzanwendung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="df549-111">Restart the computer to clear any process that may be using the resource needed to connect to the original instance application.</span></span>  
  
4.  <span data-ttu-id="df549-112">Notieren Sie sich die Umstände, unter denen der Fehler aufgetreten ist, und wenden Sie sich an den Produktsupport von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="df549-112">Note the circumstances under which the error occurred, and call Microsoft Product Support Services</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df549-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df549-113">See Also</span></span>  
 <span data-ttu-id="df549-114">[Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic) </span><span class="sxs-lookup"><span data-stu-id="df549-114">[Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic) </span></span>  
<span data-ttu-id="df549-115"> [Debugger-Grundlagen](https://docs.microsoft.com/visualstudio/debugger/debugger-basics) </span><span class="sxs-lookup"><span data-stu-id="df549-115"> [Debugger Basics](https://docs.microsoft.com/visualstudio/debugger/debugger-basics) </span></span>  
<span data-ttu-id="df549-116"> [Sprechen Sie mit uns](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span><span class="sxs-lookup"><span data-stu-id="df549-116"> [Talk to Us](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span></span>
