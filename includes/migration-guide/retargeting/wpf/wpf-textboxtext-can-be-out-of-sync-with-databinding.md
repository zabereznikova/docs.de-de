---
ms.openlocfilehash: 8b0617d8f021a9534289fd7ae8539cd054684862
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774338"
---
### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a><span data-ttu-id="c98ae-101">WPF-TextBox.Text wird möglicherweise nicht mehr mit der Datenbindung synchronisiert</span><span class="sxs-lookup"><span data-stu-id="c98ae-101">WPF TextBox.Text can be out-of-sync with databinding</span></span>

|   |   |
|---|---|
|<span data-ttu-id="c98ae-102">Details</span><span class="sxs-lookup"><span data-stu-id="c98ae-102">Details</span></span>|<span data-ttu-id="c98ae-103">In einigen Fällen stellt die <xref:System.Windows.Controls.TextBox.Text>-Eigenschaft einen früheren Wert des datengebundenen Eigenschaftswerts dar, wenn die Eigenschaft während eines Datenbindungsschreibvorgangs geändert wird.</span><span class="sxs-lookup"><span data-stu-id="c98ae-103">In some cases, the <xref:System.Windows.Controls.TextBox.Text> property reflects a previous value of the databound property value if the property is modified during a databinding write operation.</span></span>|
|<span data-ttu-id="c98ae-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="c98ae-104">Suggestion</span></span>|<span data-ttu-id="c98ae-105">Dies sollte keine negativen Auswirkungen haben.</span><span class="sxs-lookup"><span data-stu-id="c98ae-105">This should have no negative impact.</span></span> <span data-ttu-id="c98ae-106">Sie können jedoch das vorherige Verhalten wiederherstellen, indem Sie die <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty>-Eigenschaft auf <code>false</code> festlegen.</span><span class="sxs-lookup"><span data-stu-id="c98ae-106">However, you can restore the previous behavior by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> property to <code>false</code>.</span></span>|
|<span data-ttu-id="c98ae-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="c98ae-107">Scope</span></span>|<span data-ttu-id="c98ae-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c98ae-108">Edge</span></span>|
|<span data-ttu-id="c98ae-109">Version</span><span class="sxs-lookup"><span data-stu-id="c98ae-109">Version</span></span>|<span data-ttu-id="c98ae-110">4.5</span><span class="sxs-lookup"><span data-stu-id="c98ae-110">4.5</span></span>|
|<span data-ttu-id="c98ae-111">Typ</span><span class="sxs-lookup"><span data-stu-id="c98ae-111">Type</span></span>|<span data-ttu-id="c98ae-112">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="c98ae-112">Retargeting</span></span>|
|<span data-ttu-id="c98ae-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="c98ae-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType></li></ul>|
