---
title: "Diese Einzelinstanzanwendung konnte keine Verbindung zur ursprünglichen Instanz herstellen."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrAppModel_SingleInstanceCantConnect
ms.assetid: 7c2c0cee-02a1-4157-be03-39d18e18408f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fbc8458231c36f3af9ca4de524e01e19a162ee47
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="this-single-instance-application-could-not-connect-to-the-original-instance"></a><span data-ttu-id="aa6dc-102">Diese Einzelinstanzanwendung konnte keine Verbindung zur ursprünglichen Instanz herstellen.</span><span class="sxs-lookup"><span data-stu-id="aa6dc-102">This single-instance application could not connect to the original instance</span></span>
<span data-ttu-id="aa6dc-103">Diese Einzelinstanzanwendung konnte keine Verbindung zur ursprünglichen Instanz herstellen.</span><span class="sxs-lookup"><span data-stu-id="aa6dc-103">This single-instance application could not connect to the original instance.</span></span> <span data-ttu-id="aa6dc-104">Mögliche Ursachen für dieses Problem:</span><span class="sxs-lookup"><span data-stu-id="aa6dc-104">Some of the possible causes for this problem are as follows:</span></span>  
  
-   <span data-ttu-id="aa6dc-105">Die ursprüngliche Instanz reagiert nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="aa6dc-105">The original instance stopped responding.</span></span>  
  
-   <span data-ttu-id="aa6dc-106">Die Anwendung verfügt nicht über die Berechtigungen, Kernelobjekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="aa6dc-106">The application does not have permissions to create kernel objects.</span></span> <span data-ttu-id="aa6dc-107">Weitere Informationen zu Kernelobjekten finden Sie unter [Mutexe](../../standard/threading/mutexes.md).</span><span class="sxs-lookup"><span data-stu-id="aa6dc-107">For more information about kernel objects, see [Mutexes](../../standard/threading/mutexes.md).</span></span>  
  
     <span data-ttu-id="aa6dc-108">Der Basisname des Kernelobjekts wird gebildet, indem GUID, Hauptversionsnummer und Nebenversionsnummer der Assembly aneinander gehängt werden.</span><span class="sxs-lookup"><span data-stu-id="aa6dc-108">The base name for the kernel objects comes from concatenating the assembly's GUID, major version number, and minor version number.</span></span> <span data-ttu-id="aa6dc-109">Der Basisname könnte beispielsweise `3639f15d-9547-43da-8145-60da347829915.1`lauten.</span><span class="sxs-lookup"><span data-stu-id="aa6dc-109">For example, the base name could be `3639f15d-9547-43da-8145-60da347829915.1`.</span></span>  
  
## <a name="to-correct-this-error-when-developing-the-application"></a><span data-ttu-id="aa6dc-110">So beheben Sie diesen Fehler beim Entwickeln der Anwendung</span><span class="sxs-lookup"><span data-stu-id="aa6dc-110">To correct this error when developing the application</span></span>  
  
1.  <span data-ttu-id="aa6dc-111">Stellen Sie sicher, dass die Anwendung nicht in einen nicht reagierenden Zustand versetzt wird.</span><span class="sxs-lookup"><span data-stu-id="aa6dc-111">Check that the application does not go into an unresponsive state.</span></span>  
  
2.  <span data-ttu-id="aa6dc-112">Stellen Sie sicher, dass die Anwendung über ausreichende Berechtigungen verfügt, um Kernelobjekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="aa6dc-112">Check that the application has sufficient permissions to create kernel objects.</span></span>  
  
3.  <span data-ttu-id="aa6dc-113">Starten Sie die ursprüngliche Instanz der Anwendung neu.</span><span class="sxs-lookup"><span data-stu-id="aa6dc-113">Restart the original instance of the application.</span></span>  
  
4.  <span data-ttu-id="aa6dc-114">Starten Sie den Computer neu, um alle Prozesse zu beenden, die möglicherweise die Ressource verwenden, die für eine Verbindung zur ursprünglichen Instanzanwendung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="aa6dc-114">Restart the computer to clear any process that may be using the resource that is required to connect to the original instance application.</span></span>  
  
5.  <span data-ttu-id="aa6dc-115">Notieren Sie sich die Umstände, unter denen der Fehler aufgetreten ist, und wenden Sie sich an den Produktsupport von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aa6dc-115">Note the circumstances under which the error occurred, and telephone Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa6dc-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa6dc-116">See Also</span></span>  
 [<span data-ttu-id="aa6dc-117">NIB: Vorgehensweise: Angeben des Instanziierungsverhaltens für eine Anwendung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa6dc-117">NIB: How to: Specify Instancing Behavior for an Application (Visual Basic)</span></span>](http://msdn.microsoft.com/en-us/48539ad8-d960-4210-beab-ee65f6c6dc6e)  
 [<span data-ttu-id="aa6dc-118">Debugger – Grundlagen</span><span class="sxs-lookup"><span data-stu-id="aa6dc-118">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)  
 [<span data-ttu-id="aa6dc-119">PAVEOVER Produktsupport und Barrierefreiheit</span><span class="sxs-lookup"><span data-stu-id="aa6dc-119">PAVEOVER Product Support and Accessibility</span></span>](http://msdn.microsoft.com/en-us/14e1d293-7b6d-40a6-bf3e-a92f8ee6c88c)
