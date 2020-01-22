---
ms.openlocfilehash: 80fc75d0736e2ae17699073a025e79b52b340613
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937077"
---
### <a name="domainupdownuselegacyscrolling-compatibility-switch-not-supported"></a><span data-ttu-id="f9ec1-101">Kompatibilitätsoption DomainUpDown.UseLegacyScrolling wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="f9ec1-101">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>

<span data-ttu-id="f9ec1-102">Der mit .NET Framework 4.7.1 eingeführte Kompatibilitätsswitch `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` wird in Windows Forms unter .NET Core 3.0 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f9ec1-102">The `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` compatibility switch, which was introduced in .NET Framework 4.7.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f9ec1-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="f9ec1-103">Change description</span></span>

<span data-ttu-id="f9ec1-104">Ab .NET Framework 4.7.1 können Entwickler mit dem Kompatibilitätsswitch `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` die unabhängigen Aktionen <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> und <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> abstellen.</span><span class="sxs-lookup"><span data-stu-id="f9ec1-104">Starting with the .NET Framework 4.7.1, the `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` compatibility switch allowed developers to opt-out of independent <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> and <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> actions.</span></span> <span data-ttu-id="f9ec1-105">Mit dem Switch wird das Legacyverhalten wiederhergestellt, bei dem <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> ignoriert wird, wenn Kontexttext vorhanden ist, und der Entwickler wird gezwungen, die Aktion <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> vor der Aktion <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> auf das Steuerelement anwenden.</span><span class="sxs-lookup"><span data-stu-id="f9ec1-105">The switch restored the legacy behavior, in which the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> is ignored if context text is present, and the developer is required to use <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> action on the control before the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action.</span></span> <span data-ttu-id="f9ec1-106">Weitere Informationen finden Sie unter [\<AppContextSwitchOverrides>-Element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span><span class="sxs-lookup"><span data-stu-id="f9ec1-106">For more information, see [\<AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span></span>

<span data-ttu-id="f9ec1-107">In .NET Core wird der Switch `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f9ec1-107">In .NET Core, the `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f9ec1-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="f9ec1-108">Version introduced</span></span>

<span data-ttu-id="f9ec1-109">3.0 Vorschau 9</span><span class="sxs-lookup"><span data-stu-id="f9ec1-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f9ec1-110">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="f9ec1-110">Recommended action</span></span>

<span data-ttu-id="f9ec1-111">Entfernen Sie den Switch.</span><span class="sxs-lookup"><span data-stu-id="f9ec1-111">Remove the switch.</span></span> <span data-ttu-id="f9ec1-112">Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f9ec1-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="f9ec1-113">Kategorie</span><span class="sxs-lookup"><span data-stu-id="f9ec1-113">Category</span></span>

<span data-ttu-id="f9ec1-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f9ec1-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f9ec1-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="f9ec1-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.DomainUpDown.DownButton`
- `M:System.Windows.Forms.DomainUpDown.UpButton`

-->
