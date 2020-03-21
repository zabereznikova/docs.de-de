---
title: Rückruffunktionen
ms.date: 03/30/2017
helpviewer_keywords:
- callback function
- platform invoke, calling unmanaged functions
ms.assetid: c0aa8533-3b3b-42e8-9f60-84919793098c
ms.openlocfilehash: 8b8bb4dff4f73247282060c0b4fd778ae0169b1f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181516"
---
# <a name="callback-functions"></a><span data-ttu-id="73e1c-102">Rückruffunktionen</span><span class="sxs-lookup"><span data-stu-id="73e1c-102">Callback Functions</span></span>
<span data-ttu-id="73e1c-103">Eine Rückruffunktion ist ein Code innerhalb einer verwalteten Anwendung, mit dem eine nicht verwaltete DLL-Funktion eine Aufgabe ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="73e1c-103">A callback function is code within a managed application that helps an unmanaged DLL function complete a task.</span></span> <span data-ttu-id="73e1c-104">Aufrufe einer Rückruffunktion werden indirekt von einer verwalteten Anwendung über eine DLL-Funktion und zurück an die verwaltete Implementierung übergeben.</span><span class="sxs-lookup"><span data-stu-id="73e1c-104">Calls to a callback function pass indirectly from a managed application, through a DLL function, and back to the managed implementation.</span></span> <span data-ttu-id="73e1c-105">Einige der vielen DLL-Funktionen, die mit dem Plattformaufruf aufgerufen werden, erfordern eine Rückruffunktion in verwaltetem Code zur ordnungsgemäßen Ausführung.</span><span class="sxs-lookup"><span data-stu-id="73e1c-105">Some of the many DLL functions called with platform invoke require a callback function in managed code to run properly.</span></span>  
  
 <span data-ttu-id="73e1c-106">Um die meisten DLL-Funktionen aus verwaltetem Code aufzurufen, erstellen Sie eine verwaltete Definition der Funktion, und rufen Sie sie dann auf.</span><span class="sxs-lookup"><span data-stu-id="73e1c-106">To call most DLL functions from managed code, you create a managed definition of the function and then call it.</span></span> <span data-ttu-id="73e1c-107">Der Vorgang ist einfach.</span><span class="sxs-lookup"><span data-stu-id="73e1c-107">The process is straightforward.</span></span>  
  
 <span data-ttu-id="73e1c-108">Die Verwendung einer DLL-Funktion, die eine Rückruffunktion benötigt, erfordert einige zusätzliche Schritte.</span><span class="sxs-lookup"><span data-stu-id="73e1c-108">Using a DLL function that requires a callback function has some additional steps.</span></span> <span data-ttu-id="73e1c-109">Zunächst müssen Sie durch einen Blick auf die Dokumentation der Funktion ermitteln, ob die Funktion einen Rückruf erfordert.</span><span class="sxs-lookup"><span data-stu-id="73e1c-109">First, you must determine whether the function requires a callback by looking at the documentation for the function.</span></span> <span data-ttu-id="73e1c-110">Als Nächstes müssen Sie die Rückruffunktion in einer verwalteten Anwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="73e1c-110">Next, you have to create the callback function in your managed application.</span></span> <span data-ttu-id="73e1c-111">Zum Schluss rufen Sie die DLL-Funktion auf, indem Sie als Argument einen Zeiger an die Rückruffunktion übergeben.</span><span class="sxs-lookup"><span data-stu-id="73e1c-111">Finally, you call the DLL function, passing a pointer to the callback function as an argument.</span></span>

 <span data-ttu-id="73e1c-112">In der folgenden Abbildung sind die Rückruffunktion und die Implementierungsschritte zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="73e1c-112">The following illustration summarizes the callback function and implementation steps:</span></span>  
  
 ![Diagramm mit dem Plattformaufruf der Rückruffunktion](./media/callback-functions/platform-invoke-callback-process.gif)  
  
 <span data-ttu-id="73e1c-114">Rückruffunktionen eignen sich ideal für die Verwendung in Situationen, in denen eine Aufgabe wiederholt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="73e1c-114">Callback functions are ideal for use in situations in which a task is performed repeatedly.</span></span> <span data-ttu-id="73e1c-115">Eine weitere gängige Verwendungsmöglichkeit ist die Nutzung von Enumerationsfunktionen, wie z.B. **EnumFontFamilies**, **EnumPrinters** und **EnumWindows** in der Windows-API.</span><span class="sxs-lookup"><span data-stu-id="73e1c-115">Another common usage is with enumeration functions, such as **EnumFontFamilies**, **EnumPrinters**, and **EnumWindows** in the Windows API.</span></span> <span data-ttu-id="73e1c-116">Die **EnumWindows**-Funktion durchläuft alle vorhandenen Fenster auf Ihrem Computer und ruft die Rückruffunktion auf, die einen Task für jedes Fenster durchführt.</span><span class="sxs-lookup"><span data-stu-id="73e1c-116">The **EnumWindows** function enumerates through all existing windows on your computer, calling the callback function to perform a task on each window.</span></span> <span data-ttu-id="73e1c-117">Anweisungen und ein Beispiel finden Sie unter [Vorgehensweise: Implementieren von Rückruffunktionen](how-to-implement-callback-functions.md).</span><span class="sxs-lookup"><span data-stu-id="73e1c-117">For instructions and an example, see [How to: Implement Callback Functions](how-to-implement-callback-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73e1c-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="73e1c-118">See also</span></span>

- [<span data-ttu-id="73e1c-119">Gewusst wie: Implementieren von Rückruffunktionen</span><span class="sxs-lookup"><span data-stu-id="73e1c-119">How to: Implement Callback Functions</span></span>](how-to-implement-callback-functions.md)
- [<span data-ttu-id="73e1c-120">Aufrufen einer DLL-Funktion</span><span class="sxs-lookup"><span data-stu-id="73e1c-120">Calling a DLL Function</span></span>](calling-a-dll-function.md)
