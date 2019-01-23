---
title: Unerwarteter Fehler. Eine Betriebssystemressource, die für den Start einer einzelnen Instanz benötigt wird, ist nicht verfügbar.
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_CantGetMemoryMappedFile
ms.assetid: 0d9f2a30-ff72-4355-8060-744f22339359
ms.openlocfilehash: e2d7f5d570e187393b76f4af6301a81dbb350f2c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518526"
---
# <a name="an-unexpected-error-has-occurred-because-an-operating-system-resource-required-for-single-instance-startup-cannot-be-acquired"></a><span data-ttu-id="d7322-102">Unerwarteter Fehler. Eine Betriebssystemressource, die für den Start einer einzelnen Instanz benötigt wird, ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d7322-102">An unexpected error has occurred because an operating system resource required for single instance startup cannot be acquired</span></span>
<span data-ttu-id="d7322-103">Die Anwendung konnte eine erforderliche Betriebssystemressource nicht abrufen.</span><span class="sxs-lookup"><span data-stu-id="d7322-103">The application could not acquire a necessary operating system resource.</span></span> <span data-ttu-id="d7322-104">Mögliche Ursachen für dieses Problem:</span><span class="sxs-lookup"><span data-stu-id="d7322-104">Some of the possible causes for this problem are:</span></span>  
  
-   <span data-ttu-id="d7322-105">Die Anwendung verfügt nicht über die Berechtigungen, benannte Betriebssystemobjekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d7322-105">The application does not have permissions to create named operating-system objects.</span></span>  
  
-   <span data-ttu-id="d7322-106">Die Common Language Runtime verfügt nicht über die Berechtigungen, speicherzugeordnete Dateien zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d7322-106">The common language runtime does not have permissions to create memory-mapped files.</span></span>  
  
-   <span data-ttu-id="d7322-107">Die Anwendung muss auf ein Betriebssystemobjekt zugreifen, das jedoch in einem anderen Prozess verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d7322-107">The application needs to access an operating-system object, but another process is using it.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d7322-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d7322-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="d7322-109">Stellen Sie sicher, dass die Anwendung über ausreichende Berechtigungen verfügt, um benannte Betriebssystemobjekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d7322-109">Check that the application has sufficient permissions to create named operating-system objects.</span></span>  
  
2.  <span data-ttu-id="d7322-110">Stellen Sie sicher, dass die Common Language Runtime über ausreichende Berechtigungen verfügt, um speicherzugeordnete Dateien zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d7322-110">Check that the common language runtime has sufficient permissions to create memory-mapped files.</span></span>  
  
3.  <span data-ttu-id="d7322-111">Starten Sie den Computer neu, um alle Prozesse zu beenden, die erforderlich sind, um eine Verbindung zur ursprünglichen Instanzanwendung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d7322-111">Restart the computer to clear any process that may be using the resource needed to connect to the original instance application.</span></span>  
  
4.  <span data-ttu-id="d7322-112">Notieren Sie sich die Umstände, unter denen der Fehler aufgetreten ist, und wenden Sie sich an den Produktsupport von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d7322-112">Note the circumstances under which the error occurred, and call Microsoft Product Support Services</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7322-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7322-113">See also</span></span>
- [<span data-ttu-id="d7322-114">Seite „Anwendung“, Projekt-Designer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d7322-114">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [<span data-ttu-id="d7322-115">Debugger – Grundlagen</span><span class="sxs-lookup"><span data-stu-id="d7322-115">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)
- [<span data-ttu-id="d7322-116">Sprechen Sie mit uns</span><span class="sxs-lookup"><span data-stu-id="d7322-116">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
