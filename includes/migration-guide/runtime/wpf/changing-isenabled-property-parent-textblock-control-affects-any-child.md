---
ms.openlocfilehash: 12a26030a9a336d887ae9d53994a9daf13356618
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497371"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a><span data-ttu-id="01233-101">Das Ändern der IsEnabled-Eigenschaft des übergeordneten Elements eines TextBlock-Steuerelements wirkt sich auf alle untergeordneten Steuerelemente aus</span><span class="sxs-lookup"><span data-stu-id="01233-101">Changing the IsEnabled property of the parent of a TextBlock control affects any child controls</span></span>

#### <a name="details"></a><span data-ttu-id="01233-102">Details</span><span class="sxs-lookup"><span data-stu-id="01233-102">Details</span></span>

<span data-ttu-id="01233-103">Ab .NET Framework 4.6.2 wirkt sich das Ändern der <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName>-Eigenschaft eines übergeordneten Elements eines <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>-Steuerelements auf alle untergeordneten Steuerelemente (z.B. Links und Schaltflächen) des <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>-Steuerelements aus. In .NET Framework 4.6.1 und früher zeigten Steuerelemente innerhalb von <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> nicht immer den Status der <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName>-Eigenschaft des übergeordneten <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>-Elements an.</span><span class="sxs-lookup"><span data-stu-id="01233-103">Starting with the .NET Framework 4.6.2, changing the <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> property of the parent of a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control affects any child controls (such as hyperlinks and buttons) of the <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control.In the .NET Framework 4.6.1 and earlier versions, controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> did not always reflect the state of the <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> property of the <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> parent.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="01233-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="01233-104">Suggestion</span></span>

<span data-ttu-id="01233-105">Keine.</span><span class="sxs-lookup"><span data-stu-id="01233-105">None.</span></span> <span data-ttu-id="01233-106">Diese Änderung entspricht dem erwarteten Verhalten für Steuerelemente innerhalb eines <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>-Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="01233-106">This change conforms to the expected behavior for controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control.</span></span>

| <span data-ttu-id="01233-107">Name</span><span class="sxs-lookup"><span data-stu-id="01233-107">Name</span></span>    | <span data-ttu-id="01233-108">Wert</span><span class="sxs-lookup"><span data-stu-id="01233-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="01233-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="01233-109">Scope</span></span>   |<span data-ttu-id="01233-110">Gering</span><span class="sxs-lookup"><span data-stu-id="01233-110">Minor</span></span>|
|<span data-ttu-id="01233-111">Version</span><span class="sxs-lookup"><span data-stu-id="01233-111">Version</span></span>|<span data-ttu-id="01233-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="01233-112">4.6.2</span></span>|
|<span data-ttu-id="01233-113">Typ</span><span class="sxs-lookup"><span data-stu-id="01233-113">Type</span></span>|<span data-ttu-id="01233-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="01233-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="01233-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="01233-115">Affected APIs</span></span>

- <xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.UIElement.IsEnabled`

-->
