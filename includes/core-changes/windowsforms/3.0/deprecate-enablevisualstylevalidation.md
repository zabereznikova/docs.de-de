---
ms.openlocfilehash: 97e38685777c7c418c0ccd91f4c433501ecf3aaa
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721561"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="ab3a5-101">Kompatibilitätsoption EnableVisualStyleValidation wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="ab3a5-101">EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="ab3a5-102">Der Kompatibilitätsswitch `Switch.System.Windows.Forms.EnableVisualStyleValidation` wird in Windows Forms unter .NET Core 3.0 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ab3a5-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="ab3a5-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="ab3a5-103">Change description</span></span>

<span data-ttu-id="ab3a5-104">In .NET Framework ist es mit dem Kompatibilitätsswitch `Switch.System.Windows.Forms.EnableVisualStyleValidation` möglich, dass eine Anwendung die Prüfung von visuellen Elementen abstellt, die in einer numerischen Form bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ab3a5-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="ab3a5-105">In .NET Core wird der Switch `Switch.System.Windows.Forms.EnableVisualStyleValidation` nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ab3a5-105">In .NET Core, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ab3a5-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="ab3a5-106">Version introduced</span></span>

<span data-ttu-id="ab3a5-107">3.0 Vorschau 9</span><span class="sxs-lookup"><span data-stu-id="ab3a5-107">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ab3a5-108">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="ab3a5-108">Recommended action</span></span>

<span data-ttu-id="ab3a5-109">Entfernen Sie den Switch.</span><span class="sxs-lookup"><span data-stu-id="ab3a5-109">Remove the switch.</span></span> <span data-ttu-id="ab3a5-110">Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ab3a5-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="ab3a5-111">Kategorie</span><span class="sxs-lookup"><span data-stu-id="ab3a5-111">Category</span></span>

<span data-ttu-id="ab3a5-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ab3a5-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ab3a5-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="ab3a5-113">Affected APIs</span></span>

- <span data-ttu-id="ab3a5-114">Keiner</span><span class="sxs-lookup"><span data-stu-id="ab3a5-114">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
