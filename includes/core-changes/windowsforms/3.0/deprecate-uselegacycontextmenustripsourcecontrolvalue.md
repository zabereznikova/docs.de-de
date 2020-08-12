---
ms.openlocfilehash: df6169289fb96df5f7daf8bd58ccaeebc33ad87c
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556178"
---
### <a name="uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a><span data-ttu-id="5f0a0-101">Kompatibilitätsoption UseLegacyContextMenuStripSourceControlValue wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="5f0a0-101">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>

<span data-ttu-id="5f0a0-102">Der mit .NET Framework 4.7.2 eingeführte Kompatibilitätsswitch `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` wird in Windows Forms unter .NET Core oder .NET 5.0 oder höher nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5f0a0-102">The `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` compatibility switch, which was introduced in .NET Framework 4.7.2, is not supported in Windows Forms on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="5f0a0-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="5f0a0-103">Change description</span></span>

<span data-ttu-id="5f0a0-104">Ab .NET Framework 4.7.2 kann der Entwickler mit dem Kompatibilitätsswitch `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` das neue Verhalten der <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>-Eigenschaft abstellen, mit dem nun ein Verweis an die Quellcodeverwaltung zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5f0a0-104">Starting with .NET Framework 4.7.2, the `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` compatibility switch allows the developer to opt out of the new behavior of the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> property, which now returns a reference to the source control.</span></span> <span data-ttu-id="5f0a0-105">Mit dem früheren Verhalten der Eigenschaft wurde `null` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5f0a0-105">The previous behavior of the property was to return `null`.</span></span> <span data-ttu-id="5f0a0-106">Weitere Informationen finden Sie unter [\<AppContextSwitchOverrides>-Element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span><span class="sxs-lookup"><span data-stu-id="5f0a0-106">For more information, see [\<AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span></span>

<span data-ttu-id="5f0a0-107">In .NET Core und .NET 5.0 oder höher wird der `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue`-Switch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5f0a0-107">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5f0a0-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="5f0a0-108">Version introduced</span></span>

<span data-ttu-id="5f0a0-109">3.0</span><span class="sxs-lookup"><span data-stu-id="5f0a0-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5f0a0-110">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="5f0a0-110">Recommended action</span></span>

<span data-ttu-id="5f0a0-111">Entfernen Sie den Switch.</span><span class="sxs-lookup"><span data-stu-id="5f0a0-111">Remove the switch.</span></span> <span data-ttu-id="5f0a0-112">Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5f0a0-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="5f0a0-113">Kategorie</span><span class="sxs-lookup"><span data-stu-id="5f0a0-113">Category</span></span>

<span data-ttu-id="5f0a0-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5f0a0-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5f0a0-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="5f0a0-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `P:System.Windows.Forms.ContextMenuStrip.SourceControl`

-->
