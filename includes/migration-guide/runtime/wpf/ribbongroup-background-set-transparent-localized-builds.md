---
ms.openlocfilehash: 921baed7381fad363cc832c6b6af69068c2c8f43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802495"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="9ef18-101">In lokalisierten Builds ist der RibbonGroup-Hintergrund auf transparent festgelegt</span><span class="sxs-lookup"><span data-stu-id="9ef18-101">RibbonGroup background is set to transparent in localized builds</span></span>

|   |   |
|---|---|
|<span data-ttu-id="9ef18-102">Details</span><span class="sxs-lookup"><span data-stu-id="9ef18-102">Details</span></span>|<span data-ttu-id="9ef18-103">Der <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>-Hintergrund wurde in lokalisierten Builds stets mit einem Pinsel für Transparenzeffekte gezeichnet, was zu einer wenig ansprechenden Benutzeroberfläche führte.</span><span class="sxs-lookup"><span data-stu-id="9ef18-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="9ef18-104">Dieses Problem wurde in der .NET Framework 4.7 WPF-Fehlerbehebung behoben, indem die lokalisierten Ressourcen für <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> aktualisiert wurden, wodurch sichergestellt wird, dass der richtige Pinsel ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="9ef18-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, which in turn ensures that the correct brush is selected.</span></span>|
|<span data-ttu-id="9ef18-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="9ef18-105">Suggestion</span></span>|<span data-ttu-id="9ef18-106">Upgrade auf .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="9ef18-106">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="9ef18-107">`Scope`</span><span class="sxs-lookup"><span data-stu-id="9ef18-107">Scope</span></span>|<span data-ttu-id="9ef18-108">Edge</span><span class="sxs-lookup"><span data-stu-id="9ef18-108">Edge</span></span>|
|<span data-ttu-id="9ef18-109">Version</span><span class="sxs-lookup"><span data-stu-id="9ef18-109">Version</span></span>|<span data-ttu-id="9ef18-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="9ef18-110">4.6.2</span></span>|
|<span data-ttu-id="9ef18-111">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9ef18-111">Type</span></span>|<span data-ttu-id="9ef18-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="9ef18-112">Runtime</span></span>|
