---
ms.openlocfilehash: 5c1dc42a451d2c6a82e2c2429115db023c610334
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643904"
---
### <a name="switchsystemwindowsformsuselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a><span data-ttu-id="86827-101">Kompatibilitätsswitch „Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue“ wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="86827-101">Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>

<span data-ttu-id="86827-102">Der mit .NET Framework 4.7.2 eingeführte Kompatibilitätsswitch `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` wird in Windows Forms unter .NET Core 3.0 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="86827-102">The `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` compatibility switch, which was introduced in .NET Framework 4.7.2, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="86827-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="86827-103">Change description</span></span>

<span data-ttu-id="86827-104">Ab .NET Framework 4.7.2 kann der Entwickler mit dem Kompatibilitätsswitch `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` das neue Verhalten der <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>-Eigenschaft abstellen, mit dem nun ein Verweis an die Quellcodeverwaltung zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="86827-104">Starting with the .NET Framework 4.7.2, the `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` compatibility switch allows the developer to opt out of the new behavior of the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> property, which now returns a reference to the source control.</span></span> <span data-ttu-id="86827-105">Mit dem früheren Verhalten der Eigenschaft wurde `null` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="86827-105">The previous behavior of the property was to return `null`.</span></span> <span data-ttu-id="86827-106">Weitere Informationen finden Sie unter [\<AppContextSwitchOverrides>-Element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span><span class="sxs-lookup"><span data-stu-id="86827-106">For more information, see [\<AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span></span>

<span data-ttu-id="86827-107">In .NET Core wird der Switch `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="86827-107">In .NET Core, the `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="86827-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="86827-108">Version introduced</span></span>

<span data-ttu-id="86827-109">3.0 Vorschau 9</span><span class="sxs-lookup"><span data-stu-id="86827-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="86827-110">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="86827-110">Recommended action</span></span>

<span data-ttu-id="86827-111">Entfernen Sie den Switch.</span><span class="sxs-lookup"><span data-stu-id="86827-111">Remove the switch.</span></span> <span data-ttu-id="86827-112">Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.</span><span class="sxs-lookup"><span data-stu-id="86827-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="86827-113">Kategorie</span><span class="sxs-lookup"><span data-stu-id="86827-113">Category</span></span>

<span data-ttu-id="86827-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="86827-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="86827-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="86827-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `P:System.Windows.Forms.ContextMenuStrip.SourceControl`

-->
