---
ms.openlocfilehash: 0778285ef1b5702bd79743038a1bd21ba04612d6
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804314"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="6fb0a-101">Aufrufe von System.Windows.Input.PenContext.Disable auf touchfähigen Systemen können eine ArgumentException auslösen</span><span class="sxs-lookup"><span data-stu-id="6fb0a-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="6fb0a-102">Details</span><span class="sxs-lookup"><span data-stu-id="6fb0a-102">Details</span></span>|<span data-ttu-id="6fb0a-103">Unter bestimmten Umständen können Aufrufe der internen Methode <strong>System.Windows.Intput.PenContext.Disable</strong> auf touchfähigen Systemen eine nicht behandelte <code>T:System.ArgumentException</code> aufgrund von Eintrittsinvarianz auslösen.</span><span class="sxs-lookup"><span data-stu-id="6fb0a-103">Under some circumstances, calls to the internal <strong>System.Windows.Intput.PenContext.Disable</strong> method on touch-enabled systems may throw an unhandled <code>T:System.ArgumentException</code> because of reentrancy.</span></span>|
|<span data-ttu-id="6fb0a-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="6fb0a-104">Suggestion</span></span>|<span data-ttu-id="6fb0a-105">Dieses Problem wurde in .NET Framework 4.7 behoben.</span><span class="sxs-lookup"><span data-stu-id="6fb0a-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="6fb0a-106">Führen Sie ein Upgrade auf .NET Framework 4.7 oder höher aus, um diese Ausnahme zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="6fb0a-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>|
|<span data-ttu-id="6fb0a-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="6fb0a-107">Scope</span></span>|<span data-ttu-id="6fb0a-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6fb0a-108">Edge</span></span>|
|<span data-ttu-id="6fb0a-109">Version</span><span class="sxs-lookup"><span data-stu-id="6fb0a-109">Version</span></span>|<span data-ttu-id="6fb0a-110">4.6.1</span><span class="sxs-lookup"><span data-stu-id="6fb0a-110">4.6.1</span></span>|
|<span data-ttu-id="6fb0a-111">Typ</span><span class="sxs-lookup"><span data-stu-id="6fb0a-111">Type</span></span>|<span data-ttu-id="6fb0a-112">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="6fb0a-112">Retargeting</span></span>|

