---
ms.openlocfilehash: e6bb1d53cbe1883b8faef75bd22942bd4f65a5e6
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "71181769"
---
### <a name="switchsystemwindowsformsenablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="d653a-101">Kompatibilitätsswitch „Switch.System.Windows.Forms.EnableVisualStyleValidation“ wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="d653a-101">Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="d653a-102">Der Kompatibilitätsswitch `Switch.System.Windows.Forms.EnableVisualStyleValidation` wird in Windows Forms unter .NET Core 3.0 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d653a-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d653a-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="d653a-103">Change description</span></span>

<span data-ttu-id="d653a-104">In .NET Framework ist es mit dem Kompatibilitätsswitch `Switch.System.Windows.Forms.EnableVisualStyleValidation` möglich, dass eine Anwendung die Prüfung von visuellen Elementen abstellt, die in einer numerischen Form bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d653a-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span> 

<span data-ttu-id="d653a-105">In .NET Core wird der Switch `Switch.System.Windows.Forms.EnableVisualStyleValidation` nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d653a-105">In .NET Core, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d653a-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d653a-106">Version introduced</span></span>

<span data-ttu-id="d653a-107">3.0 Vorschau 9</span><span class="sxs-lookup"><span data-stu-id="d653a-107">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d653a-108">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="d653a-108">Recommended action</span></span>

<span data-ttu-id="d653a-109">Entfernen Sie den Switch.</span><span class="sxs-lookup"><span data-stu-id="d653a-109">Remove the switch.</span></span> <span data-ttu-id="d653a-110">Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d653a-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="d653a-111">Kategorie</span><span class="sxs-lookup"><span data-stu-id="d653a-111">Category</span></span>

<span data-ttu-id="d653a-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d653a-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d653a-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="d653a-113">Affected APIs</span></span>

- <span data-ttu-id="d653a-114">Keine</span><span class="sxs-lookup"><span data-stu-id="d653a-114">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
