---
ms.openlocfilehash: 0ef39d67cd4335658658f5772b5bce49d827cad0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614600"
---
### <a name="selector-selectionchanged-event-and-selectedvalue-property"></a><span data-ttu-id="cea10-101">Selector-Klasse – SelectionChanged-Ereignis und SelectedValue-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="cea10-101">Selector SelectionChanged event and SelectedValue property</span></span>

#### <a name="details"></a><span data-ttu-id="cea10-102">Details</span><span class="sxs-lookup"><span data-stu-id="cea10-102">Details</span></span>

<span data-ttu-id="cea10-103">Ab .NET Framework 4.7.1 aktualisiert ein <xref:System.Windows.Controls.Primitives.Selector>-Objekt immer den Wert der zugehörigen <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>-Eigenschaft, bevor das Ereignis <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> ausgelöst wird, wenn die Auswahl geändert wird.</span><span class="sxs-lookup"><span data-stu-id="cea10-103">Starting with the .NET Framework 4.7.1, a <xref:System.Windows.Controls.Primitives.Selector> always updates the value of its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property before raising the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event, when its selection changes.</span></span> <span data-ttu-id="cea10-104">Dadurch wird die „SelectedValue“-Eigenschaft mit den anderen Auswahleigenschaften (<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A> und <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>) in Einklang gebracht, die vor dem Auslösen des Ereignisses aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="cea10-104">This makes the SelectedValue property consistent with the other selection properties (<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A> and <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>), which are updated before raising the event.</span></span><p/><span data-ttu-id="cea10-105">In .NET Framework 4.7 und früheren Versionen wurde „SelectValue“ in den meisten Fällen vor der Auslösung des Ereignisses aktualisiert. Wenn die Änderung der Auswahl durch Ändern der <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>-Eigenschaft ausgelöst wurde, fand die Aktualisierung jedoch nach dem Auslösen des Ereignisses statt.</span><span class="sxs-lookup"><span data-stu-id="cea10-105">In the .NET Framework 4.7 and earlier versions, the update to SelectedValue happened before the event in most cases, but it happened after the event if the selection change was caused by changing the <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="cea10-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="cea10-106">Suggestion</span></span>

<span data-ttu-id="cea10-107">Für Apps mit der Zielplattform .NET Framework 4.7.1 oder höher kann diese Änderung deaktiviert und das Legacyverhalten verwendet werden, indem Sie dem Abschnitt `<runtime>` der Anwendungskonfigurationsdatei Folgendes hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="cea10-107">Apps that target the .NET Framework 4.7.1 or later can opt out of this change and use legacy behavior by adding the following to the `<runtime>` section of the application configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

<span data-ttu-id="cea10-108">Für Apps mit der Zielplattform .NET Framework 4.7 oder früheren Versionen, die unter .NET Framework 4.7.1 oder höher ausgeführt werden, kann das neue Verhalten aktiviert werden, indem Sie dem Abschnitt `<runtime>` der Anwendungskonfigurationsdatei die folgende Zeile hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="cea10-108">Apps that target the .NET Framework 4.7 or earlier but are running on the .NET Framework 4.7.1 or later can enable the new behavior by adding the following line to the `<runtime>` section of the application .configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="cea10-109">name</span><span class="sxs-lookup"><span data-stu-id="cea10-109">Name</span></span>    | <span data-ttu-id="cea10-110">Wert</span><span class="sxs-lookup"><span data-stu-id="cea10-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="cea10-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="cea10-111">Scope</span></span>   | <span data-ttu-id="cea10-112">Gering</span><span class="sxs-lookup"><span data-stu-id="cea10-112">Minor</span></span>       |
| <span data-ttu-id="cea10-113">Version</span><span class="sxs-lookup"><span data-stu-id="cea10-113">Version</span></span> | <span data-ttu-id="cea10-114">4.7.1</span><span class="sxs-lookup"><span data-stu-id="cea10-114">4.7.1</span></span>       |
| <span data-ttu-id="cea10-115">Typ</span><span class="sxs-lookup"><span data-stu-id="cea10-115">Type</span></span>    | <span data-ttu-id="cea10-116">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="cea10-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="cea10-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="cea10-117">Affected APIs</span></span>

- <xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType>
