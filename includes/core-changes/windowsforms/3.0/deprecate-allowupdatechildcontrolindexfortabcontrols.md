---
ms.openlocfilehash: 3db4b0b42a154c5bc9296889ae9dc4b7ecf1e58e
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556177"
---
### <a name="allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a><span data-ttu-id="eaeb6-101">Kompatibilitätsoption AllowUpdateChildControlIndexForTabControls wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="eaeb6-101">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>

<span data-ttu-id="eaeb6-102">Der Kompatibilitätsswitch `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` wird in Windows Forms unter .NET Framework 4.6 und höheren Versionen unterstützt. Er wird jedoch nicht unter .NET Core oder .NET 5.0 oder höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-102">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch is supported in Windows Forms on .NET Framework 4.6 and later versions but is not supported on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="eaeb6-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="eaeb6-103">Change description</span></span>

<span data-ttu-id="eaeb6-104">Wenn in .NET Framework 4.6 und höheren Versionen eine Registerkarte ausgewählt wird, wird die Steuerelementauflistung neu sortiert.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-104">In .NET Framework 4.6 and later versions, selecting a tab reorders its control collection.</span></span> <span data-ttu-id="eaeb6-105">Mit dem Kompatibilitätsswitch `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` kann eine Anwendung diese Neusortierung überspringen, sofern dieses Verhalten unerwünscht ist.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-105">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch allows an application to skip this reordering when this behavior is undesirable.</span></span>

<span data-ttu-id="eaeb6-106">In .NET Core und .NET 5.0 oder höher wird der `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls`-Switch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-106">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="eaeb6-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="eaeb6-107">Version introduced</span></span>

<span data-ttu-id="eaeb6-108">3.0</span><span class="sxs-lookup"><span data-stu-id="eaeb6-108">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="eaeb6-109">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="eaeb6-109">Recommended action</span></span>

<span data-ttu-id="eaeb6-110">Entfernen Sie den Switch.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-110">Remove the switch.</span></span> <span data-ttu-id="eaeb6-111">Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.</span><span class="sxs-lookup"><span data-stu-id="eaeb6-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="eaeb6-112">Kategorie</span><span class="sxs-lookup"><span data-stu-id="eaeb6-112">Category</span></span>

<span data-ttu-id="eaeb6-113">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eaeb6-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="eaeb6-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="eaeb6-114">Affected APIs</span></span>

- <span data-ttu-id="eaeb6-115">Keiner</span><span class="sxs-lookup"><span data-stu-id="eaeb6-115">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
