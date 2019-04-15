---
ms.openlocfilehash: 8b0617d8f021a9534289fd7ae8539cd054684862
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234684"
---
### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a><span data-ttu-id="6dfdc-101">WPF-TextBox.Text wird möglicherweise nicht mehr mit der Datenbindung synchronisiert</span><span class="sxs-lookup"><span data-stu-id="6dfdc-101">WPF TextBox.Text can be out-of-sync with databinding</span></span>

|   |   |
|---|---|
|<span data-ttu-id="6dfdc-102">Details</span><span class="sxs-lookup"><span data-stu-id="6dfdc-102">Details</span></span>|<span data-ttu-id="6dfdc-103">In einigen Fällen stellt die <xref:System.Windows.Controls.TextBox.Text>-Eigenschaft einen früheren Wert des datengebundenen Eigenschaftswerts dar, wenn die Eigenschaft während eines Datenbindungsschreibvorgangs geändert wird.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-103">In some cases, the <xref:System.Windows.Controls.TextBox.Text> property reflects a previous value of the databound property value if the property is modified during a databinding write operation.</span></span>|
|<span data-ttu-id="6dfdc-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="6dfdc-104">Suggestion</span></span>|<span data-ttu-id="6dfdc-105">Dies sollte keine negativen Auswirkungen haben.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-105">This should have no negative impact.</span></span> <span data-ttu-id="6dfdc-106">Sie können jedoch das vorherige Verhalten wiederherstellen, indem Sie die <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty>-Eigenschaft auf <code>false</code> festlegen.</span><span class="sxs-lookup"><span data-stu-id="6dfdc-106">However, you can restore the previous behavior by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> property to <code>false</code>.</span></span>|
|<span data-ttu-id="6dfdc-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="6dfdc-107">Scope</span></span>|<span data-ttu-id="6dfdc-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6dfdc-108">Edge</span></span>|
|<span data-ttu-id="6dfdc-109">Version</span><span class="sxs-lookup"><span data-stu-id="6dfdc-109">Version</span></span>|<span data-ttu-id="6dfdc-110">4.5</span><span class="sxs-lookup"><span data-stu-id="6dfdc-110">4.5</span></span>|
|<span data-ttu-id="6dfdc-111">Typ</span><span class="sxs-lookup"><span data-stu-id="6dfdc-111">Type</span></span>|<span data-ttu-id="6dfdc-112">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="6dfdc-112">Retargeting</span></span>|
|<span data-ttu-id="6dfdc-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="6dfdc-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType></li></ul>|
