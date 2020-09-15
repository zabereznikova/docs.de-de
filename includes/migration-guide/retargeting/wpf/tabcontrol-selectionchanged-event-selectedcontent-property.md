---
ms.openlocfilehash: dfdb62e8dd6db67d4fd12aba93928f4615e3f284
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614608"
---
### <a name="tabcontrol-selectionchanged-event-and-selectedcontent-property"></a><span data-ttu-id="9e093-101">SelectionChanged-Ereignis und SelectedContent-Eigenschaft von „TabControl“</span><span class="sxs-lookup"><span data-stu-id="9e093-101">TabControl SelectionChanged event and SelectedContent property</span></span>

#### <a name="details"></a><span data-ttu-id="9e093-102">Details</span><span class="sxs-lookup"><span data-stu-id="9e093-102">Details</span></span>

<span data-ttu-id="9e093-103">Ab .NET Framework 4.7.1 aktualisiert <xref:System.Windows.Controls.TabControl> den Wert der <xref:System.Windows.Controls.TabControl.SelectedContent>-Eigenschaft, bevor das <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>-Ereignis ausgelöst wird, wenn die Auswahl geändert wird. In .NET Framework 4.7 und früher wurde das Update für „SelectedContent“ nach dem Ereignis durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="9e093-103">Starting with the .NET Framework 4.7.1, a <xref:System.Windows.Controls.TabControl> updates the value of its <xref:System.Windows.Controls.TabControl.SelectedContent> property before raising the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event, when its selection changes.In the .NET Framework 4.7 and earlier versions, the update to SelectedContent happened after the event.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9e093-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="9e093-104">Suggestion</span></span>

<span data-ttu-id="9e093-105">Für Apps mit der Zielplattform .NET Framework 4.7.1 oder höher kann diese Änderung deaktiviert und das Legacyverhalten verwendet werden, indem Sie dem Abschnitt `<runtime>` der Anwendungskonfigurationsdatei Folgendes hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="9e093-105">Apps that target the .NET Framework 4.7.1 or later can opt out of this change and use legacy behavior by adding the following to the `<runtime>` section of the application configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

<span data-ttu-id="9e093-106">Für Apps mit der Zielplattform .NET Framework 4.7 oder früheren Versionen, die unter .NET Framework 4.7.1 oder höher ausgeführt werden, kann das neue Verhalten aktiviert werden, indem Sie dem Abschnitt `<runtime>` der Anwendungskonfigurationsdatei die folgende Zeile hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="9e093-106">Apps that target the .NET Framework 4.7 or earlier but are running on the .NET Framework 4.7.1 or later can enable the new behavior by adding the following line to the `<runtime>` section of the application .configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="9e093-107">name</span><span class="sxs-lookup"><span data-stu-id="9e093-107">Name</span></span>    | <span data-ttu-id="9e093-108">Wert</span><span class="sxs-lookup"><span data-stu-id="9e093-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9e093-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="9e093-109">Scope</span></span>   | <span data-ttu-id="9e093-110">Gering</span><span class="sxs-lookup"><span data-stu-id="9e093-110">Minor</span></span>       |
| <span data-ttu-id="9e093-111">Version</span><span class="sxs-lookup"><span data-stu-id="9e093-111">Version</span></span> | <span data-ttu-id="9e093-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="9e093-112">4.7.1</span></span>       |
| <span data-ttu-id="9e093-113">Typ</span><span class="sxs-lookup"><span data-stu-id="9e093-113">Type</span></span>    | <span data-ttu-id="9e093-114">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="9e093-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="9e093-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="9e093-115">Affected APIs</span></span>

- <xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType>
