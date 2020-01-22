---
ms.openlocfilehash: 7e76c32ddeb50eaf1ee93d7cf3cac7469187cc41
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937111"
---
### <a name="allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a><span data-ttu-id="572e3-101">Kompatibilitätsoption AllowUpdateChildControlIndexForTabControls wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="572e3-101">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>

<span data-ttu-id="572e3-102">Der Kompatibilitätsswitch `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` wird in Windows Forms unter .NET Framework 4.6 und höheren Versionen unterstützt. In Windows Forms ab .NET Core 3.0 gibt es diese Unterstützung jedoch nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="572e3-102">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch is supported in Windows Forms on .NET Framework 4.6 and later versions but is not supported in Windows Forms starting with .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="572e3-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="572e3-103">Change description</span></span>

<span data-ttu-id="572e3-104">Wenn in .NET Framework 4.6 und höheren Versionen eine Registerkarte ausgewählt wird, wird die Steuerelementauflistung neu sortiert.</span><span class="sxs-lookup"><span data-stu-id="572e3-104">In .NET Framework 4.6 and later versions, selecting a tab reorders its control collection.</span></span> <span data-ttu-id="572e3-105">Mit dem Kompatibilitätsswitch `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` kann eine Anwendung diese Neusortierung überspringen, sofern dieses Verhalten unerwünscht ist.</span><span class="sxs-lookup"><span data-stu-id="572e3-105">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch allows an application to skip this reordering when this behavior is undesirable.</span></span>

<span data-ttu-id="572e3-106">In .NET Core wird der Switch `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="572e3-106">In .NET Core, the `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="572e3-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="572e3-107">Version introduced</span></span>

<span data-ttu-id="572e3-108">3.0 Vorschau 9</span><span class="sxs-lookup"><span data-stu-id="572e3-108">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="572e3-109">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="572e3-109">Recommended action</span></span>

<span data-ttu-id="572e3-110">Entfernen Sie den Switch.</span><span class="sxs-lookup"><span data-stu-id="572e3-110">Remove the switch.</span></span> <span data-ttu-id="572e3-111">Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.</span><span class="sxs-lookup"><span data-stu-id="572e3-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="572e3-112">Kategorie</span><span class="sxs-lookup"><span data-stu-id="572e3-112">Category</span></span>

<span data-ttu-id="572e3-113">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="572e3-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="572e3-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="572e3-114">Affected APIs</span></span>

- <span data-ttu-id="572e3-115">Keine</span><span class="sxs-lookup"><span data-stu-id="572e3-115">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
