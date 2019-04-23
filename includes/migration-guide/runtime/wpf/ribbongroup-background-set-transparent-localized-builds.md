---
ms.openlocfilehash: 921baed7381fad363cc832c6b6af69068c2c8f43
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236047"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="d07ef-101">In lokalisierten Builds ist der RibbonGroup-Hintergrund auf transparent festgelegt</span><span class="sxs-lookup"><span data-stu-id="d07ef-101">RibbonGroup background is set to transparent in localized builds</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d07ef-102">Details</span><span class="sxs-lookup"><span data-stu-id="d07ef-102">Details</span></span>|<xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> <span data-ttu-id="d07ef-103">-Hintergrund wurde in lokalisierten Builds stets mit einem Pinsel für Transparenzeffekte gezeichnet, was zu einer wenig ansprechenden Benutzeroberfläche führte.</span><span class="sxs-lookup"><span data-stu-id="d07ef-103">background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="d07ef-104">Dieses Problem wurde in der .NET Framework 4.7 WPF-Fehlerbehebung behoben, indem die lokalisierten Ressourcen für <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> aktualisiert wurden, wodurch sichergestellt wird, dass der richtige Pinsel ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="d07ef-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, which in turn ensures that the correct brush is selected.</span></span>|
|<span data-ttu-id="d07ef-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="d07ef-105">Suggestion</span></span>|<span data-ttu-id="d07ef-106">Upgrade auf .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="d07ef-106">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="d07ef-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="d07ef-107">Scope</span></span>|<span data-ttu-id="d07ef-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d07ef-108">Edge</span></span>|
|<span data-ttu-id="d07ef-109">Version</span><span class="sxs-lookup"><span data-stu-id="d07ef-109">Version</span></span>|<span data-ttu-id="d07ef-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="d07ef-110">4.6.2</span></span>|
|<span data-ttu-id="d07ef-111">Typ</span><span class="sxs-lookup"><span data-stu-id="d07ef-111">Type</span></span>|<span data-ttu-id="d07ef-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="d07ef-112">Runtime</span></span>|
