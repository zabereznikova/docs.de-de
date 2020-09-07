---
ms.openlocfilehash: d6405573e476ce18513938b500041adefbeeef1b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497542"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="4a3db-101">In lokalisierten Builds ist der RibbonGroup-Hintergrund auf transparent festgelegt</span><span class="sxs-lookup"><span data-stu-id="4a3db-101">RibbonGroup background is set to transparent in localized builds</span></span>

#### <a name="details"></a><span data-ttu-id="4a3db-102">Details</span><span class="sxs-lookup"><span data-stu-id="4a3db-102">Details</span></span>

<span data-ttu-id="4a3db-103">Der <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>-Hintergrund wurde in lokalisierten Builds stets mit einem Pinsel für Transparenzeffekte gezeichnet, was zu einer wenig ansprechenden Benutzeroberfläche führte.</span><span class="sxs-lookup"><span data-stu-id="4a3db-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="4a3db-104">Dieses Problem wurde in der .NET Framework 4.7 WPF-Fehlerbehebung behoben, indem die lokalisierten Ressourcen für <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> aktualisiert wurden, wodurch sichergestellt wird, dass der richtige Pinsel ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="4a3db-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>, which in turn ensures that the correct brush is selected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4a3db-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="4a3db-105">Suggestion</span></span>

<span data-ttu-id="4a3db-106">Upgrade auf .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="4a3db-106">Upgrade to .NET Framework 4.7</span></span>

| <span data-ttu-id="4a3db-107">name</span><span class="sxs-lookup"><span data-stu-id="4a3db-107">Name</span></span>    | <span data-ttu-id="4a3db-108">Wert</span><span class="sxs-lookup"><span data-stu-id="4a3db-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4a3db-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="4a3db-109">Scope</span></span>   |<span data-ttu-id="4a3db-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="4a3db-110">Edge</span></span>|
|<span data-ttu-id="4a3db-111">Version</span><span class="sxs-lookup"><span data-stu-id="4a3db-111">Version</span></span>|<span data-ttu-id="4a3db-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="4a3db-112">4.6.2</span></span>|
|<span data-ttu-id="4a3db-113">Typ</span><span class="sxs-lookup"><span data-stu-id="4a3db-113">Type</span></span>|<span data-ttu-id="4a3db-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="4a3db-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="4a3db-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="4a3db-115">Affected APIs</span></span>

<span data-ttu-id="4a3db-116">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="4a3db-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
