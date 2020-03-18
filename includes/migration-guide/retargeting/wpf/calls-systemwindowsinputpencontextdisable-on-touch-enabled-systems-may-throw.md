---
ms.openlocfilehash: 6bb8c87af66e744514fb43e628c6423487342ac2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "72887776"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="b5ed7-101">Aufrufe von System.Windows.Input.PenContext.Disable auf touchfähigen Systemen können eine ArgumentException auslösen</span><span class="sxs-lookup"><span data-stu-id="b5ed7-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b5ed7-102">Details</span><span class="sxs-lookup"><span data-stu-id="b5ed7-102">Details</span></span>|<span data-ttu-id="b5ed7-103">Unter bestimmten Umständen können Aufrufe der internen Methode **System.Windows.Intput.PenContext.Disable** auf touchfähigen Systemen eine nicht behandelte <code>T:System.ArgumentException</code> aufgrund von Eintrittsinvarianz auslösen.</span><span class="sxs-lookup"><span data-stu-id="b5ed7-103">Under some circumstances, calls to the internal **System.Windows.Intput.PenContext.Disable** method on touch-enabled systems may throw an unhandled <code>T:System.ArgumentException</code> because of reentrancy.</span></span>|
|<span data-ttu-id="b5ed7-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="b5ed7-104">Suggestion</span></span>|<span data-ttu-id="b5ed7-105">Dieses Problem wurde in .NET Framework 4.7 behoben.</span><span class="sxs-lookup"><span data-stu-id="b5ed7-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="b5ed7-106">Führen Sie ein Upgrade auf .NET Framework 4.7 oder höher aus, um diese Ausnahme zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="b5ed7-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>|
|<span data-ttu-id="b5ed7-107">`Scope`</span><span class="sxs-lookup"><span data-stu-id="b5ed7-107">Scope</span></span>|<span data-ttu-id="b5ed7-108">Edge</span><span class="sxs-lookup"><span data-stu-id="b5ed7-108">Edge</span></span>|
|<span data-ttu-id="b5ed7-109">Version</span><span class="sxs-lookup"><span data-stu-id="b5ed7-109">Version</span></span>|<span data-ttu-id="b5ed7-110">4.6.1</span><span class="sxs-lookup"><span data-stu-id="b5ed7-110">4.6.1</span></span>|
|<span data-ttu-id="b5ed7-111">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b5ed7-111">Type</span></span>|<span data-ttu-id="b5ed7-112">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="b5ed7-112">Retargeting</span></span>|
