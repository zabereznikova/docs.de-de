---
title: Unerwarteter Fehler. Eine Betriebssystemressource, die für den Start einer einzelnen Instanz benötigt wird, ist nicht verfügbar.
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrAppModel_CantGetMemoryMappedFile
ms.assetid: 0d9f2a30-ff72-4355-8060-744f22339359
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8969303d66e946d5579c6cca592b5701c4ebd632
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="an-unexpected-error-has-occurred-because-an-operating-system-resource-required-for-single-instance-startup-cannot-be-acquired"></a><span data-ttu-id="d97f9-102">Unerwarteter Fehler. Eine Betriebssystemressource, die für den Start einer einzelnen Instanz benötigt wird, ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d97f9-102">An unexpected error has occurred because an operating system resource required for single instance startup cannot be acquired</span></span>
<span data-ttu-id="d97f9-103">Die Anwendung konnte eine erforderliche Betriebssystemressource nicht abrufen.</span><span class="sxs-lookup"><span data-stu-id="d97f9-103">The application could not acquire a necessary operating system resource.</span></span> <span data-ttu-id="d97f9-104">Mögliche Ursachen für dieses Problem:</span><span class="sxs-lookup"><span data-stu-id="d97f9-104">Some of the possible causes for this problem are:</span></span>  
  
-   <span data-ttu-id="d97f9-105">Die Anwendung verfügt nicht über die Berechtigungen, benannte Betriebssystemobjekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d97f9-105">The application does not have permissions to create named operating-system objects.</span></span>  
  
-   <span data-ttu-id="d97f9-106">Die Common Language Runtime verfügt nicht über die Berechtigungen, speicherzugeordnete Dateien zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d97f9-106">The common language runtime does not have permissions to create memory-mapped files.</span></span>  
  
-   <span data-ttu-id="d97f9-107">Die Anwendung muss auf ein Betriebssystemobjekt zugreifen, das jedoch in einem anderen Prozess verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d97f9-107">The application needs to access an operating-system object, but another process is using it.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d97f9-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d97f9-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="d97f9-109">Stellen Sie sicher, dass die Anwendung über ausreichende Berechtigungen verfügt, um benannte Betriebssystemobjekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d97f9-109">Check that the application has sufficient permissions to create named operating-system objects.</span></span>  
  
2.  <span data-ttu-id="d97f9-110">Stellen Sie sicher, dass die Common Language Runtime über ausreichende Berechtigungen verfügt, um speicherzugeordnete Dateien zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d97f9-110">Check that the common language runtime has sufficient permissions to create memory-mapped files.</span></span>  
  
3.  <span data-ttu-id="d97f9-111">Starten Sie den Computer neu, um alle Prozesse zu beenden, die erforderlich sind, um eine Verbindung zur ursprünglichen Instanzanwendung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d97f9-111">Restart the computer to clear any process that may be using the resource needed to connect to the original instance application.</span></span>  
  
4.  <span data-ttu-id="d97f9-112">Notieren Sie sich die Umstände, unter denen der Fehler aufgetreten ist, und wenden Sie sich an den Produktsupport von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d97f9-112">Note the circumstances under which the error occurred, and call Microsoft Product Support Services</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d97f9-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d97f9-113">See Also</span></span>  
 [<span data-ttu-id="d97f9-114">Seite „Anwendung“, Projekt-Designer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d97f9-114">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)  
 [<span data-ttu-id="d97f9-115">Debugger – Grundlagen</span><span class="sxs-lookup"><span data-stu-id="d97f9-115">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)  
 [<span data-ttu-id="d97f9-116">Sprechen Sie mit uns</span><span class="sxs-lookup"><span data-stu-id="d97f9-116">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
