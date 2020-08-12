---
ms.openlocfilehash: 196a26bd235e5e2556baa7fac979b3316ff81e1f
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556174"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="aeed1-101">Kompatibilitätsoption EnableVisualStyleValidation wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="aeed1-101">EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="aeed1-102">Der Kompatibilitätsswitch `Switch.System.Windows.Forms.EnableVisualStyleValidation` wird in Windows Forms unter .NET Core oder .NET 5.0 oder höher nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="aeed1-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="aeed1-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="aeed1-103">Change description</span></span>

<span data-ttu-id="aeed1-104">In .NET Framework ist es mit dem Kompatibilitätsswitch `Switch.System.Windows.Forms.EnableVisualStyleValidation` möglich, dass eine Anwendung die Prüfung von visuellen Elementen abstellt, die in einer numerischen Form bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="aeed1-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="aeed1-105">In .NET Core und .NET 5.0 oder höher wird der `Switch.System.Windows.Forms.EnableVisualStyleValidation`-Switch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="aeed1-105">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="aeed1-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="aeed1-106">Version introduced</span></span>

<span data-ttu-id="aeed1-107">3.0</span><span class="sxs-lookup"><span data-stu-id="aeed1-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="aeed1-108">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="aeed1-108">Recommended action</span></span>

<span data-ttu-id="aeed1-109">Entfernen Sie den Switch.</span><span class="sxs-lookup"><span data-stu-id="aeed1-109">Remove the switch.</span></span> <span data-ttu-id="aeed1-110">Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.</span><span class="sxs-lookup"><span data-stu-id="aeed1-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="aeed1-111">Kategorie</span><span class="sxs-lookup"><span data-stu-id="aeed1-111">Category</span></span>

<span data-ttu-id="aeed1-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="aeed1-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="aeed1-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="aeed1-113">Affected APIs</span></span>

- <span data-ttu-id="aeed1-114">Keiner</span><span class="sxs-lookup"><span data-stu-id="aeed1-114">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
