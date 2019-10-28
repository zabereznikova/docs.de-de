---
ms.openlocfilehash: 6bb8c87af66e744514fb43e628c6423487342ac2
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "72887776"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="42032-101">Aufrufe von System.Windows.Input.PenContext.Disable auf touchfähigen Systemen können eine ArgumentException auslösen</span><span class="sxs-lookup"><span data-stu-id="42032-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="42032-102">Details</span><span class="sxs-lookup"><span data-stu-id="42032-102">Details</span></span>|<span data-ttu-id="42032-103">Unter bestimmten Umständen können Aufrufe der internen Methode **System.Windows.Intput.PenContext.Disable** auf touchfähigen Systemen eine nicht behandelte <code>T:System.ArgumentException</code> aufgrund von Eintrittsinvarianz auslösen.</span><span class="sxs-lookup"><span data-stu-id="42032-103">Under some circumstances, calls to the internal **System.Windows.Intput.PenContext.Disable** method on touch-enabled systems may throw an unhandled <code>T:System.ArgumentException</code> because of reentrancy.</span></span>|
|<span data-ttu-id="42032-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="42032-104">Suggestion</span></span>|<span data-ttu-id="42032-105">Dieses Problem wurde in .NET Framework 4.7 behoben.</span><span class="sxs-lookup"><span data-stu-id="42032-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="42032-106">Führen Sie ein Upgrade auf .NET Framework 4.7 oder höher aus, um diese Ausnahme zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="42032-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>|
|<span data-ttu-id="42032-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="42032-107">Scope</span></span>|<span data-ttu-id="42032-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="42032-108">Edge</span></span>|
|<span data-ttu-id="42032-109">Version</span><span class="sxs-lookup"><span data-stu-id="42032-109">Version</span></span>|<span data-ttu-id="42032-110">4.6.1</span><span class="sxs-lookup"><span data-stu-id="42032-110">4.6.1</span></span>|
|<span data-ttu-id="42032-111">Typ</span><span class="sxs-lookup"><span data-stu-id="42032-111">Type</span></span>|<span data-ttu-id="42032-112">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="42032-112">Retargeting</span></span>|
