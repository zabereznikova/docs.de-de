---
ms.openlocfilehash: c980b0c0be9f4d6a529baa0743dec9ac16ca0d7f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721275"
---
### <a name="uselegacyimages-compatibility-switch-not-supported"></a><span data-ttu-id="e5fe2-101">Kompatibilitätsoption UseLegacyImages wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="e5fe2-101">UseLegacyImages compatibility switch not supported</span></span>

<span data-ttu-id="e5fe2-102">Der mit .NET Framework 4.8 eingeführte Kompatibilitätsswitch `Switch.System.Windows.Forms.UseLegacyImages` wird in Windows Forms unter .NET Core 3.0 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e5fe2-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.8, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e5fe2-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="e5fe2-103">Change description</span></span>

<span data-ttu-id="e5fe2-104">Ab .NET Framework 4.8 werden mit dem Kompatibilitätsswitch `Switch.System.Windows.Forms.UseLegacyImages` mögliche Bildskalierungsprobleme in ClickOnce-Szenarios in Umgebungen mit hohem DPI-Wert behoben.</span><span class="sxs-lookup"><span data-stu-id="e5fe2-104">Starting with the .NET Framework 4.8, the `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch addressed possible image scaling issues in ClickOnce scenarios in high DPI environments.</span></span> <span data-ttu-id="e5fe2-105">Wenn der Switch auf `true` festgelegt wird, kann der Benutzer die Legacybildskalierung in Anzeigen mit hohem DPI-Wert wiederherstellen, deren Skalierung auf mehr als 100 % festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e5fe2-105">When set to `true`, the switch allows the user to restore legacy image scaling on high DPI displays whose scale is set to greater than 100%.</span></span> <span data-ttu-id="e5fe2-106">Weitere Informationen finden Sie unter [Versionshinweise zu .NET Framework 4.8](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="e5fe2-106">For more information, see [.NET Framework 4.8 Release Notes](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) on GitHub.</span></span>

<span data-ttu-id="e5fe2-107">In .NET Core wird der Switch `Switch.System.Windows.Forms.UseLegacyImages` nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e5fe2-107">In .NET Core, the `Switch.System.Windows.Forms.UseLegacyImages` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e5fe2-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e5fe2-108">Version introduced</span></span>

<span data-ttu-id="e5fe2-109">3.0 Vorschau 9</span><span class="sxs-lookup"><span data-stu-id="e5fe2-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e5fe2-110">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="e5fe2-110">Recommended action</span></span>

<span data-ttu-id="e5fe2-111">Entfernen Sie den Switch.</span><span class="sxs-lookup"><span data-stu-id="e5fe2-111">Remove the switch.</span></span> <span data-ttu-id="e5fe2-112">Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e5fe2-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="e5fe2-113">Kategorie</span><span class="sxs-lookup"><span data-stu-id="e5fe2-113">Category</span></span>

<span data-ttu-id="e5fe2-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e5fe2-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e5fe2-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="e5fe2-115">Affected APIs</span></span>

- <span data-ttu-id="e5fe2-116">Keiner</span><span class="sxs-lookup"><span data-stu-id="e5fe2-116">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
