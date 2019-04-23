---
title: Diese Einzelinstanzanwendung konnte keine Verbindung zur ursprünglichen Instanz herstellen.
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_SingleInstanceCantConnect
ms.assetid: 7c2c0cee-02a1-4157-be03-39d18e18408f
ms.openlocfilehash: 7ffa9b185e16cfdf8223ce84e77d1a0e1fa67f65
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322653"
---
# <a name="this-single-instance-application-could-not-connect-to-the-original-instance"></a><span data-ttu-id="32e07-102">Diese Einzelinstanzanwendung konnte keine Verbindung zur ursprünglichen Instanz herstellen.</span><span class="sxs-lookup"><span data-stu-id="32e07-102">This single-instance application could not connect to the original instance</span></span>
<span data-ttu-id="32e07-103">Diese Einzelinstanzanwendung konnte keine Verbindung zur ursprünglichen Instanz herstellen.</span><span class="sxs-lookup"><span data-stu-id="32e07-103">This single-instance application could not connect to the original instance.</span></span> <span data-ttu-id="32e07-104">Mögliche Ursachen für dieses Problem:</span><span class="sxs-lookup"><span data-stu-id="32e07-104">Some of the possible causes for this problem are as follows:</span></span>  
  
-   <span data-ttu-id="32e07-105">Die ursprüngliche Instanz reagiert nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="32e07-105">The original instance stopped responding.</span></span>  
  
-   <span data-ttu-id="32e07-106">Die Anwendung verfügt nicht über die Berechtigungen, Kernelobjekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="32e07-106">The application does not have permissions to create kernel objects.</span></span> <span data-ttu-id="32e07-107">Weitere Informationen zu Kernelobjekten finden Sie unter [Mutexe](../../standard/threading/mutexes.md).</span><span class="sxs-lookup"><span data-stu-id="32e07-107">For more information about kernel objects, see [Mutexes](../../standard/threading/mutexes.md).</span></span>  
  
     <span data-ttu-id="32e07-108">Der Basisname des Kernelobjekts wird gebildet, indem GUID, Hauptversionsnummer und Nebenversionsnummer der Assembly aneinander gehängt werden.</span><span class="sxs-lookup"><span data-stu-id="32e07-108">The base name for the kernel objects comes from concatenating the assembly's GUID, major version number, and minor version number.</span></span> <span data-ttu-id="32e07-109">Der Basisname könnte beispielsweise `3639f15d-9547-43da-8145-60da347829915.1`lauten.</span><span class="sxs-lookup"><span data-stu-id="32e07-109">For example, the base name could be `3639f15d-9547-43da-8145-60da347829915.1`.</span></span>  
  
## <a name="to-correct-this-error-when-developing-the-application"></a><span data-ttu-id="32e07-110">So beheben Sie diesen Fehler beim Entwickeln der Anwendung</span><span class="sxs-lookup"><span data-stu-id="32e07-110">To correct this error when developing the application</span></span>  
  
1. <span data-ttu-id="32e07-111">Stellen Sie sicher, dass die Anwendung nicht in einen nicht reagierenden Zustand versetzt wird.</span><span class="sxs-lookup"><span data-stu-id="32e07-111">Check that the application does not go into an unresponsive state.</span></span>  
  
2. <span data-ttu-id="32e07-112">Stellen Sie sicher, dass die Anwendung über ausreichende Berechtigungen verfügt, um Kernelobjekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="32e07-112">Check that the application has sufficient permissions to create kernel objects.</span></span>  
  
3. <span data-ttu-id="32e07-113">Starten Sie die ursprüngliche Instanz der Anwendung neu.</span><span class="sxs-lookup"><span data-stu-id="32e07-113">Restart the original instance of the application.</span></span>  
  
4. <span data-ttu-id="32e07-114">Starten Sie den Computer neu, um alle Prozesse zu beenden, die möglicherweise die Ressource verwenden, die für eine Verbindung zur ursprünglichen Instanzanwendung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="32e07-114">Restart the computer to clear any process that may be using the resource that is required to connect to the original instance application.</span></span>  
  
5. <span data-ttu-id="32e07-115">Notieren Sie sich die Umstände, unter denen der Fehler aufgetreten ist, und wenden Sie sich an den Produktsupport von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="32e07-115">Note the circumstances under which the error occurred, and telephone Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32e07-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32e07-116">See also</span></span>

- [<span data-ttu-id="32e07-117">Debugger – Grundlagen</span><span class="sxs-lookup"><span data-stu-id="32e07-117">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)
