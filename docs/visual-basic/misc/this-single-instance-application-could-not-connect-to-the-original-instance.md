---
title: Diese Einzelinstanzanwendung konnte keine Verbindung zur ursprünglichen Instanz herstellen.
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_SingleInstanceCantConnect
ms.assetid: 7c2c0cee-02a1-4157-be03-39d18e18408f
ms.openlocfilehash: 04ceec4839d07ba959c39af8c4f582c7abfe7d6b
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198124"
---
# <a name="this-single-instance-application-could-not-connect-to-the-original-instance"></a><span data-ttu-id="d64df-102">Diese Einzelinstanzanwendung konnte keine Verbindung zur ursprünglichen Instanz herstellen.</span><span class="sxs-lookup"><span data-stu-id="d64df-102">This single-instance application could not connect to the original instance</span></span>
<span data-ttu-id="d64df-103">Diese Einzelinstanzanwendung konnte keine Verbindung zur ursprünglichen Instanz herstellen.</span><span class="sxs-lookup"><span data-stu-id="d64df-103">This single-instance application could not connect to the original instance.</span></span> <span data-ttu-id="d64df-104">Mögliche Ursachen für dieses Problem:</span><span class="sxs-lookup"><span data-stu-id="d64df-104">Some of the possible causes for this problem are as follows:</span></span>  
  
- <span data-ttu-id="d64df-105">Die ursprüngliche Instanz reagiert nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="d64df-105">The original instance stopped responding.</span></span>  
  
- <span data-ttu-id="d64df-106">Die Anwendung verfügt nicht über die Berechtigungen, Kernelobjekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d64df-106">The application does not have permissions to create kernel objects.</span></span> <span data-ttu-id="d64df-107">Weitere Informationen zu Kernel Objekten finden Sie unter [Mutexes](../../standard/threading/mutexes.md).</span><span class="sxs-lookup"><span data-stu-id="d64df-107">For more information about kernel objects, see [Mutexes](../../standard/threading/mutexes.md).</span></span>  
  
     <span data-ttu-id="d64df-108">Der Basisname des Kernelobjekts wird gebildet, indem GUID, Hauptversionsnummer und Nebenversionsnummer der Assembly aneinander gehängt werden.</span><span class="sxs-lookup"><span data-stu-id="d64df-108">The base name for the kernel objects comes from concatenating the assembly's GUID, major version number, and minor version number.</span></span> <span data-ttu-id="d64df-109">Der Basisname könnte beispielsweise `3639f15d-9547-43da-8145-60da347829915.1`lauten.</span><span class="sxs-lookup"><span data-stu-id="d64df-109">For example, the base name could be `3639f15d-9547-43da-8145-60da347829915.1`.</span></span>  
  
## <a name="to-correct-this-error-when-developing-the-application"></a><span data-ttu-id="d64df-110">So beheben Sie diesen Fehler beim Entwickeln der Anwendung</span><span class="sxs-lookup"><span data-stu-id="d64df-110">To correct this error when developing the application</span></span>  
  
1. <span data-ttu-id="d64df-111">Stellen Sie sicher, dass die Anwendung nicht in einen nicht reagierenden Zustand versetzt wird.</span><span class="sxs-lookup"><span data-stu-id="d64df-111">Check that the application does not go into an unresponsive state.</span></span>  
  
2. <span data-ttu-id="d64df-112">Stellen Sie sicher, dass die Anwendung über ausreichende Berechtigungen verfügt, um Kernelobjekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d64df-112">Check that the application has sufficient permissions to create kernel objects.</span></span>  
  
3. <span data-ttu-id="d64df-113">Starten Sie die ursprüngliche Instanz der Anwendung neu.</span><span class="sxs-lookup"><span data-stu-id="d64df-113">Restart the original instance of the application.</span></span>  
  
4. <span data-ttu-id="d64df-114">Starten Sie den Computer neu, um alle Prozesse zu beenden, die möglicherweise die Ressource verwenden, die für eine Verbindung zur ursprünglichen Instanzanwendung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d64df-114">Restart the computer to clear any process that may be using the resource that is required to connect to the original instance application.</span></span>  
  
5. <span data-ttu-id="d64df-115">Notieren Sie sich die Umstände, unter denen der Fehler aufgetreten ist, und wenden Sie sich an den Produktsupport von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d64df-115">Note the circumstances under which the error occurred, and telephone Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d64df-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d64df-116">See also</span></span>

- [<span data-ttu-id="d64df-117">Debugger – Grundlagen</span><span class="sxs-lookup"><span data-stu-id="d64df-117">Debugger Basics</span></span>](/visualstudio/debugger/debugger-feature-tour)
