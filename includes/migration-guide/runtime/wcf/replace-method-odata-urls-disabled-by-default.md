---
ms.openlocfilehash: fccf349517133245ec85ae3c25cedbfb27a7dd8b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497216"
---
### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a><span data-ttu-id="798d0-101">Die Replace-Methode in OData-URLs ist standardmäßig deaktiviert</span><span class="sxs-lookup"><span data-stu-id="798d0-101">The Replace method in OData URLs is disabled by default</span></span>

#### <a name="details"></a><span data-ttu-id="798d0-102">Details</span><span class="sxs-lookup"><span data-stu-id="798d0-102">Details</span></span>

<span data-ttu-id="798d0-103">Ab .NET Framework 4.5 ist die Replace-Methode in OData-URLs standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="798d0-103">Beginning in the .NET Framework 4.5, the Replace method in OData URLs is disabled by default.</span></span> <span data-ttu-id="798d0-104">Wenn „Replace“ für OData (jetzt standardmäßig) deaktiviert ist, schlagen alle Benutzeranforderungen fehl, einschließlich der Ersetzungsfunktionen (die nicht üblich sind).</span><span class="sxs-lookup"><span data-stu-id="798d0-104">When OData Replace is disabled (now by default), any user requests including replace functions (which are uncommon) will fail.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="798d0-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="798d0-105">Suggestion</span></span>

<span data-ttu-id="798d0-106">Wenn die Replace-Methode erforderlich ist (was nicht üblich ist), kann sie über die Konfigurationseinstellung <xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=fullName> erneut aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="798d0-106">If the replace method is required (which is uncommon), it can be re-enabled through a config settings (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=fullName>).</span></span> <span data-ttu-id="798d0-107">Eine aktivierte Replace-Methode kann jedoch Sicherheitslücken öffnen und sollte nur nach sorgfältiger Prüfung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="798d0-107">However, an enabled replace method can open security vulnerabilities and should only be used after careful review.</span></span>

| <span data-ttu-id="798d0-108">name</span><span class="sxs-lookup"><span data-stu-id="798d0-108">Name</span></span>    | <span data-ttu-id="798d0-109">Wert</span><span class="sxs-lookup"><span data-stu-id="798d0-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="798d0-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="798d0-110">Scope</span></span>   |<span data-ttu-id="798d0-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="798d0-111">Edge</span></span>|
|<span data-ttu-id="798d0-112">Version</span><span class="sxs-lookup"><span data-stu-id="798d0-112">Version</span></span>|<span data-ttu-id="798d0-113">4.5</span><span class="sxs-lookup"><span data-stu-id="798d0-113">4.5</span></span>|
|<span data-ttu-id="798d0-114">Typ</span><span class="sxs-lookup"><span data-stu-id="798d0-114">Type</span></span>|<span data-ttu-id="798d0-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="798d0-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="798d0-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="798d0-116">Affected APIs</span></span>

- <xref:System.Data.Services.DataService%601?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``T:System.Data.Services.DataService`1``

-->
