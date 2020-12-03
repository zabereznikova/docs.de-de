---
title: 'Breaking Change: Statusleisten-Steuerelement wurde entfernt'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, wegen dem einige Windows Forms-Steuerelemente nicht mehr verfügbar sind.
ms.date: 07/18/2020
ms.openlocfilehash: 70aaa20f3fee1f4c342c4d9e547b0658aaf533b1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759510"
---
# <a name="removed-status-bar-controls"></a><span data-ttu-id="04042-103">Statusleisten-Steuerelement wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="04042-103">Removed status bar controls</span></span>

<span data-ttu-id="04042-104">Ab .NET 5.0 sind einige Windows Forms-Steuerelemente nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="04042-104">Starting in .NET 5.0, some Windows Forms controls are no longer available.</span></span>

## <a name="change-description"></a><span data-ttu-id="04042-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="04042-105">Change description</span></span>

<span data-ttu-id="04042-106">Ab .NET 5.0 sind einige Windows Forms-Steuerelemente für Statusleistenfunktionen nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="04042-106">Starting with .NET 5.0, some of the status bar-related Windows Forms controls are no longer available.</span></span> <span data-ttu-id="04042-107">Ersatzsteuerelemente, die ein besseres Design und eine umfassendere Unterstützung bieten, wurden in .NET Framework 2.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="04042-107">Replacement controls that have better design and support were introduced in .NET Framework 2.0.</span></span> <span data-ttu-id="04042-108">Die veralteten Steuerelemente wurden zwar bereits aus den Designer-Toolboxen entfernt, konnten aber weiterhin verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="04042-108">The deprecated controls were previously removed from designer toolboxes but were still available to be used.</span></span> <span data-ttu-id="04042-109">Nun wurden sie vollständig entfernt.</span><span class="sxs-lookup"><span data-stu-id="04042-109">Now, they have been completely removed.</span></span>

<span data-ttu-id="04042-110">Die folgenden Typen stehen nicht mehr länger zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="04042-110">The following types are no longer available:</span></span>

* `StatusBar`
* `StatusBarDrawItemEventArgs`
* `StatusBarDrawItemEventHandler`
* `StatusBarPanel`
* `StatusBarPanelAutoSize`
* `StatusBarPanelBorderStyle`
* `StatusBarPanelClickEventArgs`
* `StatusBarPanelClickEventHandler`
* `StatusBarPanelStyle`

## <a name="version-introduced"></a><span data-ttu-id="04042-111">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="04042-111">Version introduced</span></span>

<span data-ttu-id="04042-112">5.0</span><span class="sxs-lookup"><span data-stu-id="04042-112">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="04042-113">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="04042-113">Recommended action</span></span>

<span data-ttu-id="04042-114">Wechseln Sie zu den Ersetzungs-APIs für diese Steuerelemente und ihre Szenarios:</span><span class="sxs-lookup"><span data-stu-id="04042-114">Move to the replacement APIs for these controls and their scenarios:</span></span>

| <span data-ttu-id="04042-115">Altes Steuerelement (API)</span><span class="sxs-lookup"><span data-stu-id="04042-115">Old Control (API)</span></span> | <span data-ttu-id="04042-116">Empfohlener Ersatz</span><span class="sxs-lookup"><span data-stu-id="04042-116">Recommended Replacement</span></span>                          |
|-------------------|--------------------------------------------------|
| <span data-ttu-id="04042-117">StatusBar</span><span class="sxs-lookup"><span data-stu-id="04042-117">StatusBar</span></span>         | <xref:System.Windows.Forms.StatusStrip>          |
| <span data-ttu-id="04042-118">StatusBarPanel</span><span class="sxs-lookup"><span data-stu-id="04042-118">StatusBarPanel</span></span>    | <xref:System.Windows.Forms.ToolStripStatusLabel> |

## <a name="affected-apis"></a><span data-ttu-id="04042-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="04042-119">Affected APIs</span></span>

- <xref:System.Windows.Forms.StatusBar?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarDrawItemEventArgs?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarDrawItemEventHandler?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanel?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelAutoSize?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelBorderStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelClickEventArgs?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelClickEventHandler?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelStyle?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Windows.Forms.StatusBar`
- `T:System.Windows.Forms.StatusBarDrawItemEventArgs`
- `T:System.Windows.Forms.StatusBarDrawItemEventHandler`
- `T:System.Windows.Forms.StatusBarPanel`
- `T:System.Windows.Forms.StatusBarPanelAutoSize`
- `T:System.Windows.Forms.StatusBarPanelBorderStyle`
- `T:System.Windows.Forms.StatusBarPanelClickEventArgs`
- `T:System.Windows.Forms.StatusBarPanelClickEventHandler`
- `T:System.Windows.Forms.StatusBarPanelStyle`

### Category

Windows Forms

-->
