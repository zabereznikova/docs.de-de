---
ms.openlocfilehash: 76425ca03c98cd6a23b8366257f9e0d53b486edb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496774"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a><span data-ttu-id="84748-101">Für das Freigeben des Sitzungszustands mit Asp.Net StateServer müssen alle Server in der Webfarm dieselbe .NET Framework-Version verwenden</span><span class="sxs-lookup"><span data-stu-id="84748-101">Sharing session state with Asp.Net StateServer requires all servers in the web farm to use the same .NET Framework version</span></span>

#### <a name="details"></a><span data-ttu-id="84748-102">Details</span><span class="sxs-lookup"><span data-stu-id="84748-102">Details</span></span>

<span data-ttu-id="84748-103">Wenn ein <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName>-Sitzungszustand aktiviert wird, müssen alle Server in der jeweiligen Webfarm dieselbe Version von .NET Framework verwenden, damit der Zustand ohne Probleme freigegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="84748-103">When enabling <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> session state, all of the servers in the given web farm must use the same version of the .NET Framework in order for state to be properly shared.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="84748-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="84748-104">Suggestion</span></span>

<span data-ttu-id="84748-105">Führen Sie für alle .NET Framework-Versionen auf Webservern, für die ein Zustand freigegeben wird, gleichzeitig ein Upgrade aus.</span><span class="sxs-lookup"><span data-stu-id="84748-105">Be sure to upgrade .NET Framework versions on web servers that share state at the same time.</span></span>

| <span data-ttu-id="84748-106">name</span><span class="sxs-lookup"><span data-stu-id="84748-106">Name</span></span>    | <span data-ttu-id="84748-107">Wert</span><span class="sxs-lookup"><span data-stu-id="84748-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="84748-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="84748-108">Scope</span></span>   |<span data-ttu-id="84748-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="84748-109">Edge</span></span>|
|<span data-ttu-id="84748-110">Version</span><span class="sxs-lookup"><span data-stu-id="84748-110">Version</span></span>|<span data-ttu-id="84748-111">4.5</span><span class="sxs-lookup"><span data-stu-id="84748-111">4.5</span></span>|
|<span data-ttu-id="84748-112">Typ</span><span class="sxs-lookup"><span data-stu-id="84748-112">Type</span></span>|<span data-ttu-id="84748-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="84748-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="84748-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="84748-114">Affected APIs</span></span>

- <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType>

<!--

#### Affected APIs

- `F:System.Web.SessionState.SessionStateMode.StateServer`

-->
