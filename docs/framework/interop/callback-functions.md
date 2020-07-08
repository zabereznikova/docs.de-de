---
title: Rückruffunktionen
description: Eine Rückruffunktion ist Code innerhalb einer verwalteten Anwendung, mit dem eine nicht verwaltete DLL-Funktion eine Aufgabe ausführen kann.
ms.date: 03/30/2017
helpviewer_keywords:
- callback function
- platform invoke, calling unmanaged functions
ms.assetid: c0aa8533-3b3b-42e8-9f60-84919793098c
ms.openlocfilehash: e28756b5ed935aff83363b38d6f33982e87718b2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621716"
---
# <a name="callback-functions"></a><span data-ttu-id="1cc04-103">Rückruffunktionen</span><span class="sxs-lookup"><span data-stu-id="1cc04-103">Callback Functions</span></span>
<span data-ttu-id="1cc04-104">Eine Rückruffunktion ist ein Code innerhalb einer verwalteten Anwendung, mit dem eine nicht verwaltete DLL-Funktion eine Aufgabe ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="1cc04-104">A callback function is code within a managed application that helps an unmanaged DLL function complete a task.</span></span> <span data-ttu-id="1cc04-105">Aufrufe einer Rückruffunktion werden indirekt von einer verwalteten Anwendung über eine DLL-Funktion und zurück an die verwaltete Implementierung übergeben.</span><span class="sxs-lookup"><span data-stu-id="1cc04-105">Calls to a callback function pass indirectly from a managed application, through a DLL function, and back to the managed implementation.</span></span> <span data-ttu-id="1cc04-106">Einige der vielen DLL-Funktionen, die mit dem Plattformaufruf aufgerufen werden, erfordern eine Rückruffunktion in verwaltetem Code zur ordnungsgemäßen Ausführung.</span><span class="sxs-lookup"><span data-stu-id="1cc04-106">Some of the many DLL functions called with platform invoke require a callback function in managed code to run properly.</span></span>  
  
 <span data-ttu-id="1cc04-107">Um die meisten DLL-Funktionen aus verwaltetem Code aufzurufen, erstellen Sie eine verwaltete Definition der Funktion, und rufen Sie sie dann auf.</span><span class="sxs-lookup"><span data-stu-id="1cc04-107">To call most DLL functions from managed code, you create a managed definition of the function and then call it.</span></span> <span data-ttu-id="1cc04-108">Der Vorgang ist einfach.</span><span class="sxs-lookup"><span data-stu-id="1cc04-108">The process is straightforward.</span></span>  
  
 <span data-ttu-id="1cc04-109">Die Verwendung einer DLL-Funktion, die eine Rückruffunktion benötigt, erfordert einige zusätzliche Schritte.</span><span class="sxs-lookup"><span data-stu-id="1cc04-109">Using a DLL function that requires a callback function has some additional steps.</span></span> <span data-ttu-id="1cc04-110">Zunächst müssen Sie durch einen Blick auf die Dokumentation der Funktion ermitteln, ob die Funktion einen Rückruf erfordert.</span><span class="sxs-lookup"><span data-stu-id="1cc04-110">First, you must determine whether the function requires a callback by looking at the documentation for the function.</span></span> <span data-ttu-id="1cc04-111">Als Nächstes müssen Sie die Rückruffunktion in einer verwalteten Anwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="1cc04-111">Next, you have to create the callback function in your managed application.</span></span> <span data-ttu-id="1cc04-112">Zum Schluss rufen Sie die DLL-Funktion auf, indem Sie als Argument einen Zeiger an die Rückruffunktion übergeben.</span><span class="sxs-lookup"><span data-stu-id="1cc04-112">Finally, you call the DLL function, passing a pointer to the callback function as an argument.</span></span>

 <span data-ttu-id="1cc04-113">In der folgenden Abbildung sind die Rückruffunktion und die Implementierungsschritte zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="1cc04-113">The following illustration summarizes the callback function and implementation steps:</span></span>  
  
 ![Diagramm mit dem Plattformaufruf der Rückruffunktion](./media/callback-functions/platform-invoke-callback-process.gif)  
  
 <span data-ttu-id="1cc04-115">Rückruffunktionen eignen sich ideal für die Verwendung in Situationen, in denen eine Aufgabe wiederholt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1cc04-115">Callback functions are ideal for use in situations in which a task is performed repeatedly.</span></span> <span data-ttu-id="1cc04-116">Eine weitere gängige Verwendungsmöglichkeit ist die Nutzung von Enumerationsfunktionen, wie z.B. **EnumFontFamilies**, **EnumPrinters** und **EnumWindows** in der Windows-API.</span><span class="sxs-lookup"><span data-stu-id="1cc04-116">Another common usage is with enumeration functions, such as **EnumFontFamilies**, **EnumPrinters**, and **EnumWindows** in the Windows API.</span></span> <span data-ttu-id="1cc04-117">Die **EnumWindows**-Funktion durchläuft alle vorhandenen Fenster auf Ihrem Computer und ruft die Rückruffunktion auf, die einen Task für jedes Fenster durchführt.</span><span class="sxs-lookup"><span data-stu-id="1cc04-117">The **EnumWindows** function enumerates through all existing windows on your computer, calling the callback function to perform a task on each window.</span></span> <span data-ttu-id="1cc04-118">Anweisungen und ein Beispiel finden Sie unter [Vorgehensweise: Implementieren von Rückruffunktionen](how-to-implement-callback-functions.md).</span><span class="sxs-lookup"><span data-stu-id="1cc04-118">For instructions and an example, see [How to: Implement Callback Functions](how-to-implement-callback-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cc04-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1cc04-119">See also</span></span>

- [<span data-ttu-id="1cc04-120">How to: Implementieren von Rückruffunktionen</span><span class="sxs-lookup"><span data-stu-id="1cc04-120">How to: Implement Callback Functions</span></span>](how-to-implement-callback-functions.md)
- [<span data-ttu-id="1cc04-121">Calling a DLL Function (Aufrufen einer DLL-Funktion)</span><span class="sxs-lookup"><span data-stu-id="1cc04-121">Calling a DLL Function</span></span>](calling-a-dll-function.md)
