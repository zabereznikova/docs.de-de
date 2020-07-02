---
ms.openlocfilehash: 0fe07ac21effacffc56d37ccb46a121f443acd20
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620177"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a><span data-ttu-id="0c560-101">Für das Freigeben des Sitzungszustands mit Asp.Net StateServer müssen alle Server in der Webfarm dieselbe .NET Framework-Version verwenden</span><span class="sxs-lookup"><span data-stu-id="0c560-101">Sharing session state with Asp.Net StateServer requires all servers in the web farm to use the same .NET Framework version</span></span>

#### <a name="details"></a><span data-ttu-id="0c560-102">Details</span><span class="sxs-lookup"><span data-stu-id="0c560-102">Details</span></span>

<span data-ttu-id="0c560-103">Wenn ein <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName>-Sitzungszustand aktiviert wird, müssen alle Server in der jeweiligen Webfarm dieselbe Version von .NET Framework verwenden, damit der Zustand ohne Probleme freigegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="0c560-103">When enabling <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> session state, all of the servers in the given web farm must use the same version of the .NET Framework in order for state to be properly shared.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0c560-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="0c560-104">Suggestion</span></span>

<span data-ttu-id="0c560-105">Führen Sie für alle .NET Framework-Versionen auf Webservern, für die ein Zustand freigegeben wird, gleichzeitig ein Upgrade aus.</span><span class="sxs-lookup"><span data-stu-id="0c560-105">Be sure to upgrade .NET Framework versions on web servers that share state at the same time.</span></span>

| <span data-ttu-id="0c560-106">name</span><span class="sxs-lookup"><span data-stu-id="0c560-106">Name</span></span>    | <span data-ttu-id="0c560-107">Wert</span><span class="sxs-lookup"><span data-stu-id="0c560-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0c560-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="0c560-108">Scope</span></span>   |<span data-ttu-id="0c560-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0c560-109">Edge</span></span>|
|<span data-ttu-id="0c560-110">Version</span><span class="sxs-lookup"><span data-stu-id="0c560-110">Version</span></span>|<span data-ttu-id="0c560-111">4.5</span><span class="sxs-lookup"><span data-stu-id="0c560-111">4.5</span></span>|
|<span data-ttu-id="0c560-112">Typ</span><span class="sxs-lookup"><span data-stu-id="0c560-112">Type</span></span>|<span data-ttu-id="0c560-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="0c560-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0c560-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="0c560-114">Affected APIs</span></span>

-<xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType></li></ul>|
