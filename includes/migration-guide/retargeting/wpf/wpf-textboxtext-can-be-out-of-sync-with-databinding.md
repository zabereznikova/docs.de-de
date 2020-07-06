---
ms.openlocfilehash: d0de1a262d57c67dd4dfb258d5ac013af5d8783d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617230"
---
### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a><span data-ttu-id="2a3ac-101">WPF-TextBox.Text wird möglicherweise nicht mehr mit der Datenbindung synchronisiert</span><span class="sxs-lookup"><span data-stu-id="2a3ac-101">WPF TextBox.Text can be out-of-sync with databinding</span></span>

#### <a name="details"></a><span data-ttu-id="2a3ac-102">Details</span><span class="sxs-lookup"><span data-stu-id="2a3ac-102">Details</span></span>

<span data-ttu-id="2a3ac-103">In einigen Fällen stellt die <xref:System.Windows.Controls.TextBox.Text>-Eigenschaft einen früheren Wert des datengebundenen Eigenschaftswerts dar, wenn die Eigenschaft während eines Datenbindungsschreibvorgangs geändert wird.</span><span class="sxs-lookup"><span data-stu-id="2a3ac-103">In some cases, the <xref:System.Windows.Controls.TextBox.Text> property reflects a previous value of the databound property value if the property is modified during a databinding write operation.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2a3ac-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="2a3ac-104">Suggestion</span></span>

<span data-ttu-id="2a3ac-105">Dies sollte keine negativen Auswirkungen haben.</span><span class="sxs-lookup"><span data-stu-id="2a3ac-105">This should have no negative impact.</span></span> <span data-ttu-id="2a3ac-106">Sie können jedoch das vorherige Verhalten wiederherstellen, indem Sie die <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty>-Eigenschaft auf `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="2a3ac-106">However, you can restore the previous behavior by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> property to `false`.</span></span>

| <span data-ttu-id="2a3ac-107">name</span><span class="sxs-lookup"><span data-stu-id="2a3ac-107">Name</span></span>    | <span data-ttu-id="2a3ac-108">Wert</span><span class="sxs-lookup"><span data-stu-id="2a3ac-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2a3ac-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="2a3ac-109">Scope</span></span>   | <span data-ttu-id="2a3ac-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2a3ac-110">Edge</span></span>        |
| <span data-ttu-id="2a3ac-111">Version</span><span class="sxs-lookup"><span data-stu-id="2a3ac-111">Version</span></span> | <span data-ttu-id="2a3ac-112">4.5</span><span class="sxs-lookup"><span data-stu-id="2a3ac-112">4.5</span></span>         |
|<span data-ttu-id="2a3ac-113">Typ</span><span class="sxs-lookup"><span data-stu-id="2a3ac-113">Type</span></span>|<span data-ttu-id="2a3ac-114">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="2a3ac-114">Retargeting</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2a3ac-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="2a3ac-115">Affected APIs</span></span>

- <xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType>
