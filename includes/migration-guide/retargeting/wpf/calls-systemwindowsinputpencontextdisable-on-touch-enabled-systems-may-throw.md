---
ms.openlocfilehash: 3cd5052dffcb059c240a310e0b89384f28409264
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234462"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="77ff0-101">Aufrufe von System.Windows.Input.PenContext.Disable auf touchfähigen Systemen können eine ArgumentException auslösen</span><span class="sxs-lookup"><span data-stu-id="77ff0-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="77ff0-102">Details</span><span class="sxs-lookup"><span data-stu-id="77ff0-102">Details</span></span>|<span data-ttu-id="77ff0-103">Unter bestimmten Umständen können Aufrufe der internen Methode <strong>System.Windows.Intput.PenContext.Disable</strong> auf touchfähigen Systemen eine nicht behandelte <code>T:System.ArgumentException</code> aufgrund von Eintrittsinvarianz auslösen.</span><span class="sxs-lookup"><span data-stu-id="77ff0-103">Under some circumstances, calls to the internal <strong>System.Windows.Intput.PenContext.Disable</strong> method on touch-enabled systems may throw an unhandled <code>T:System.ArgumentException</code> because of reentrancy.</span></span>|
|<span data-ttu-id="77ff0-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="77ff0-104">Suggestion</span></span>|<span data-ttu-id="77ff0-105">Dieses Problem wurde in .NET Framework 4.7 behoben.</span><span class="sxs-lookup"><span data-stu-id="77ff0-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="77ff0-106">Führen Sie ein Upgrade auf .NET Framework 4.7 oder höher aus, um diese Ausnahme zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="77ff0-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>|
|<span data-ttu-id="77ff0-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="77ff0-107">Scope</span></span>|<span data-ttu-id="77ff0-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="77ff0-108">Edge</span></span>|
|<span data-ttu-id="77ff0-109">Version</span><span class="sxs-lookup"><span data-stu-id="77ff0-109">Version</span></span>|<span data-ttu-id="77ff0-110">4.6.1</span><span class="sxs-lookup"><span data-stu-id="77ff0-110">4.6.1</span></span>|
|<span data-ttu-id="77ff0-111">Typ</span><span class="sxs-lookup"><span data-stu-id="77ff0-111">Type</span></span>|<span data-ttu-id="77ff0-112">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="77ff0-112">Retargeting</span></span>|
