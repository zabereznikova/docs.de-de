---
ms.openlocfilehash: d69f619522c7abc3171f1c089e53cc2754899f93
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556175"
---
### <a name="uselegacyimages-compatibility-switch-not-supported"></a><span data-ttu-id="58b2f-101">Kompatibilitätsoption UseLegacyImages wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="58b2f-101">UseLegacyImages compatibility switch not supported</span></span>

<span data-ttu-id="58b2f-102">Der mit .NET Framework 4.8 eingeführte Kompatibilitätsswitch `Switch.System.Windows.Forms.UseLegacyImages` wird in Windows Forms unter .NET Core oder .NET 5.0 oder höher nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="58b2f-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.8, is not supported in Windows Forms on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="58b2f-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="58b2f-103">Change description</span></span>

<span data-ttu-id="58b2f-104">Ab .NET Framework 4.8 werden mit dem Kompatibilitätsswitch `Switch.System.Windows.Forms.UseLegacyImages` mögliche Bildskalierungsprobleme in ClickOnce-Szenarios in Umgebungen mit hohem DPI-Wert behoben.</span><span class="sxs-lookup"><span data-stu-id="58b2f-104">Starting with .NET Framework 4.8, the `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch addressed possible image scaling issues in ClickOnce scenarios in high DPI environments.</span></span> <span data-ttu-id="58b2f-105">Wenn der Switch auf `true` festgelegt wird, kann der Benutzer die Legacybildskalierung in Anzeigen mit hohem DPI-Wert wiederherstellen, deren Skalierung auf mehr als 100 % festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="58b2f-105">When set to `true`, the switch allows the user to restore legacy image scaling on high DPI displays whose scale is set to greater than 100%.</span></span> <span data-ttu-id="58b2f-106">Weitere Informationen finden Sie unter [Versionshinweise zu .NET Framework 4.8](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="58b2f-106">For more information, see [.NET Framework 4.8 Release Notes](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) on GitHub.</span></span>

<span data-ttu-id="58b2f-107">In .NET Core und .NET 5.0 oder höher wird der `Switch.System.Windows.Forms.UseLegacyImages`-Switch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="58b2f-107">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.UseLegacyImages` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="58b2f-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="58b2f-108">Version introduced</span></span>

<span data-ttu-id="58b2f-109">3.0</span><span class="sxs-lookup"><span data-stu-id="58b2f-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="58b2f-110">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="58b2f-110">Recommended action</span></span>

<span data-ttu-id="58b2f-111">Entfernen Sie den Switch.</span><span class="sxs-lookup"><span data-stu-id="58b2f-111">Remove the switch.</span></span> <span data-ttu-id="58b2f-112">Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.</span><span class="sxs-lookup"><span data-stu-id="58b2f-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="58b2f-113">Kategorie</span><span class="sxs-lookup"><span data-stu-id="58b2f-113">Category</span></span>

<span data-ttu-id="58b2f-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="58b2f-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="58b2f-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="58b2f-115">Affected APIs</span></span>

- <span data-ttu-id="58b2f-116">Keiner</span><span class="sxs-lookup"><span data-stu-id="58b2f-116">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
