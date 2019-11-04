---
ms.openlocfilehash: 84b6bfc32f5a73597b227098e5aee1e3450cf85b
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198436"
---
### <a name="switchsystemwindowsformsenablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="547d0-101">Kompatibilitätsswitch „Switch.System.Windows.Forms.EnableVisualStyleValidation“ wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="547d0-101">Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="547d0-102">Der Kompatibilitätsswitch `Switch.System.Windows.Forms.EnableVisualStyleValidation` wird in Windows Forms unter .NET Core 3.0 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="547d0-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="547d0-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="547d0-103">Change description</span></span>

<span data-ttu-id="547d0-104">In .NET Framework ist es mit dem Kompatibilitätsswitch `Switch.System.Windows.Forms.EnableVisualStyleValidation` möglich, dass eine Anwendung die Prüfung von visuellen Elementen abstellt, die in einer numerischen Form bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="547d0-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="547d0-105">In .NET Core wird der Switch `Switch.System.Windows.Forms.EnableVisualStyleValidation` nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="547d0-105">In .NET Core, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="547d0-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="547d0-106">Version introduced</span></span>

<span data-ttu-id="547d0-107">3.0 Vorschau 9</span><span class="sxs-lookup"><span data-stu-id="547d0-107">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="547d0-108">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="547d0-108">Recommended action</span></span>

<span data-ttu-id="547d0-109">Entfernen Sie den Switch.</span><span class="sxs-lookup"><span data-stu-id="547d0-109">Remove the switch.</span></span> <span data-ttu-id="547d0-110">Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.</span><span class="sxs-lookup"><span data-stu-id="547d0-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="547d0-111">Kategorie</span><span class="sxs-lookup"><span data-stu-id="547d0-111">Category</span></span>

<span data-ttu-id="547d0-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="547d0-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="547d0-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="547d0-113">Affected APIs</span></span>

- <span data-ttu-id="547d0-114">Keine</span><span class="sxs-lookup"><span data-stu-id="547d0-114">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
