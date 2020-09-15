---
ms.openlocfilehash: a44458484ea09c566defeabc9b604bd55d994e93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617533"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="2bd1e-101">Aufrufe von System.Windows.Input.PenContext.Disable auf touchfähigen Systemen können eine ArgumentException auslösen</span><span class="sxs-lookup"><span data-stu-id="2bd1e-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

#### <a name="details"></a><span data-ttu-id="2bd1e-102">Details</span><span class="sxs-lookup"><span data-stu-id="2bd1e-102">Details</span></span>

<span data-ttu-id="2bd1e-103">Unter bestimmten Umständen können Aufrufe der internen Methode **System.Windows.Intput.PenContext.Disable** auf touchfähigen Systemen eine nicht behandelte `T:System.ArgumentException` aufgrund von Eintrittsinvarianz auslösen.</span><span class="sxs-lookup"><span data-stu-id="2bd1e-103">Under some circumstances, calls to the internal **System.Windows.Intput.PenContext.Disable** method on touch-enabled systems may throw an unhandled `T:System.ArgumentException` because of reentrancy.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2bd1e-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="2bd1e-104">Suggestion</span></span>

<span data-ttu-id="2bd1e-105">Dieses Problem wurde in .NET Framework 4.7 behoben.</span><span class="sxs-lookup"><span data-stu-id="2bd1e-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="2bd1e-106">Führen Sie ein Upgrade auf .NET Framework 4.7 oder höher aus, um diese Ausnahme zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="2bd1e-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>

| <span data-ttu-id="2bd1e-107">name</span><span class="sxs-lookup"><span data-stu-id="2bd1e-107">Name</span></span>    | <span data-ttu-id="2bd1e-108">Wert</span><span class="sxs-lookup"><span data-stu-id="2bd1e-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2bd1e-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="2bd1e-109">Scope</span></span>   | <span data-ttu-id="2bd1e-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2bd1e-110">Edge</span></span>        |
| <span data-ttu-id="2bd1e-111">Version</span><span class="sxs-lookup"><span data-stu-id="2bd1e-111">Version</span></span> | <span data-ttu-id="2bd1e-112">4.6.1</span><span class="sxs-lookup"><span data-stu-id="2bd1e-112">4.6.1</span></span>       |
| <span data-ttu-id="2bd1e-113">Typ</span><span class="sxs-lookup"><span data-stu-id="2bd1e-113">Type</span></span>    | <span data-ttu-id="2bd1e-114">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="2bd1e-114">Retargeting</span></span> |
