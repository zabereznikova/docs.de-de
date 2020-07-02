---
ms.openlocfilehash: a3ba42868577ac20ea2e082f90fc4973a1bfe108
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622356"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="7f6f3-101">In lokalisierten Builds ist der RibbonGroup-Hintergrund auf transparent festgelegt</span><span class="sxs-lookup"><span data-stu-id="7f6f3-101">RibbonGroup background is set to transparent in localized builds</span></span>

#### <a name="details"></a><span data-ttu-id="7f6f3-102">Details</span><span class="sxs-lookup"><span data-stu-id="7f6f3-102">Details</span></span>

<span data-ttu-id="7f6f3-103">Der <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>-Hintergrund wurde in lokalisierten Builds stets mit einem Pinsel für Transparenzeffekte gezeichnet, was zu einer wenig ansprechenden Benutzeroberfläche führte.</span><span class="sxs-lookup"><span data-stu-id="7f6f3-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="7f6f3-104">Dieses Problem wurde in der .NET Framework 4.7 WPF-Fehlerbehebung behoben, indem die lokalisierten Ressourcen für <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> aktualisiert wurden, wodurch sichergestellt wird, dass der richtige Pinsel ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="7f6f3-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>, which in turn ensures that the correct brush is selected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7f6f3-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="7f6f3-105">Suggestion</span></span>

<span data-ttu-id="7f6f3-106">Upgrade auf .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="7f6f3-106">Upgrade to .NET Framework 4.7</span></span>

| <span data-ttu-id="7f6f3-107">Name</span><span class="sxs-lookup"><span data-stu-id="7f6f3-107">Name</span></span>    | <span data-ttu-id="7f6f3-108">Wert</span><span class="sxs-lookup"><span data-stu-id="7f6f3-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7f6f3-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="7f6f3-109">Scope</span></span>   |<span data-ttu-id="7f6f3-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7f6f3-110">Edge</span></span>|
|<span data-ttu-id="7f6f3-111">Version</span><span class="sxs-lookup"><span data-stu-id="7f6f3-111">Version</span></span>|<span data-ttu-id="7f6f3-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="7f6f3-112">4.6.2</span></span>|
|<span data-ttu-id="7f6f3-113">Typ</span><span class="sxs-lookup"><span data-stu-id="7f6f3-113">Type</span></span>|<span data-ttu-id="7f6f3-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="7f6f3-114">Runtime</span></span>|
