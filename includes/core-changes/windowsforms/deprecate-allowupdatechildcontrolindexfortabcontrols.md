---
ms.openlocfilehash: 1d01de4b978309e05a6036953f2a6909628a2480
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "71181707"
---
### <a name="switchsystemwindowsformsallowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a><span data-ttu-id="63e56-101">Kompatibilitätsswitch „Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls“ wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="63e56-101">Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>

<span data-ttu-id="63e56-102">Der Kompatibilitätsswitch `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` wird in Windows Forms unter .NET Framework 4.6 und höheren Versionen unterstützt. In Windows Forms ab .NET Core 3.0 gibt es diese Unterstützung jedoch nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="63e56-102">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch is supported in Windows Forms on .NET Framework 4.6 and later versions but is not supported in Windows Forms starting with .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="63e56-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="63e56-103">Change description</span></span>

<span data-ttu-id="63e56-104">Wenn in .NET Framework 4.6 und höheren Versionen eine Registerkarte ausgewählt wird, wird die Steuerelementauflistung neu sortiert.</span><span class="sxs-lookup"><span data-stu-id="63e56-104">In .NET Framework 4.6 and later versions, selecting a tab reorders its control collection.</span></span> <span data-ttu-id="63e56-105">Mit dem Kompatibilitätsswitch `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` kann eine Anwendung diese Neusortierung überspringen, sofern dieses Verhalten unerwünscht ist.</span><span class="sxs-lookup"><span data-stu-id="63e56-105">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch allows an application to skip this reordering when this behavior is undesirable.</span></span>

<span data-ttu-id="63e56-106">In .NET Core wird der Switch `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="63e56-106">In .NET Core, the `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="63e56-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="63e56-107">Version introduced</span></span>

<span data-ttu-id="63e56-108">3.0 Vorschau 9</span><span class="sxs-lookup"><span data-stu-id="63e56-108">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="63e56-109">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="63e56-109">Recommended action</span></span>

<span data-ttu-id="63e56-110">Entfernen Sie den Switch.</span><span class="sxs-lookup"><span data-stu-id="63e56-110">Remove the switch.</span></span> <span data-ttu-id="63e56-111">Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.</span><span class="sxs-lookup"><span data-stu-id="63e56-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="63e56-112">Kategorie</span><span class="sxs-lookup"><span data-stu-id="63e56-112">Category</span></span>

<span data-ttu-id="63e56-113">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="63e56-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="63e56-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="63e56-114">Affected APIs</span></span>

- <span data-ttu-id="63e56-115">Keine</span><span class="sxs-lookup"><span data-stu-id="63e56-115">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
