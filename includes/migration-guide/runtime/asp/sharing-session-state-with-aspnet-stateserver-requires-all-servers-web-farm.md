---
ms.openlocfilehash: e450c53008e7562e37518fdfd6872ff9b63b6ac3
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609132"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a><span data-ttu-id="a0fb2-101">Für das Freigeben des Sitzungszustands mit ASP.NET StateServer müssen alle Server in der Webfarm dieselbe .NET Framework-Version verwenden</span><span class="sxs-lookup"><span data-stu-id="a0fb2-101">Sharing session state with ASP.NET StateServer requires all servers in the web farm to use the same .NET Framework version</span></span>

#### <a name="details"></a><span data-ttu-id="a0fb2-102">Details</span><span class="sxs-lookup"><span data-stu-id="a0fb2-102">Details</span></span>

<span data-ttu-id="a0fb2-103">Wenn ein <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName>-Sitzungszustand aktiviert wird, müssen alle Server in der jeweiligen Webfarm dieselbe Version von .NET Framework verwenden, damit der Zustand ohne Probleme freigegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-103">When enabling <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> session state, all of the servers in the given web farm must use the same version of the .NET Framework in order for state to be properly shared.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a0fb2-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="a0fb2-104">Suggestion</span></span>

<span data-ttu-id="a0fb2-105">Führen Sie für alle .NET Framework-Versionen auf Webservern, für die ein Zustand freigegeben wird, gleichzeitig ein Upgrade aus.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-105">Be sure to upgrade .NET Framework versions on web servers that share state at the same time.</span></span>

| <span data-ttu-id="a0fb2-106">name</span><span class="sxs-lookup"><span data-stu-id="a0fb2-106">Name</span></span>    | <span data-ttu-id="a0fb2-107">Wert</span><span class="sxs-lookup"><span data-stu-id="a0fb2-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a0fb2-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="a0fb2-108">Scope</span></span>   |<span data-ttu-id="a0fb2-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a0fb2-109">Edge</span></span>|
|<span data-ttu-id="a0fb2-110">Version</span><span class="sxs-lookup"><span data-stu-id="a0fb2-110">Version</span></span>|<span data-ttu-id="a0fb2-111">4.5</span><span class="sxs-lookup"><span data-stu-id="a0fb2-111">4.5</span></span>|
|<span data-ttu-id="a0fb2-112">Typ</span><span class="sxs-lookup"><span data-stu-id="a0fb2-112">Type</span></span>|<span data-ttu-id="a0fb2-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a0fb2-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a0fb2-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a0fb2-114">Affected APIs</span></span>

- <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType>

<!--

#### Affected APIs

- `F:System.Web.SessionState.SessionStateMode.StateServer`

-->
