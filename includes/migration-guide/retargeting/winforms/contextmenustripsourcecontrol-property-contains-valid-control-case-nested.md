---
ms.openlocfilehash: 5529b8379c5cb9f1bc525e0c2340f6b885e35822
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606845"
---
### <a name="contextmenustripsourcecontrol-property-contains-a-valid-control-in-the-case-of-nested-toolstripmenuitems"></a><span data-ttu-id="2c353-101">„ContextMenuStrip.SourceControl“-Eigenschaft enthält im Fall geschachtelter „ToolStripMenuItems“ ein gültiges Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2c353-101">ContextMenuStrip.SourceControl property contains a valid control in the case of nested ToolStripMenuItems</span></span>

#### <a name="details"></a><span data-ttu-id="2c353-102">Details</span><span class="sxs-lookup"><span data-stu-id="2c353-102">Details</span></span>

<span data-ttu-id="2c353-103">In .NET Framework 4.7.1 und früheren Versionen gibt die <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>-Eigenschaft fälschlicherweise NULL zurück, wenn der Benutzer das Menü in geschachtelten <xref:System.Windows.Forms.ToolStripMenuItem>-Steuerelementen öffnet.</span><span class="sxs-lookup"><span data-stu-id="2c353-103">In the .NET Framework 4.7.1 and previous versions, the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> property incorrectly returns null when the user opens the menu from nested <xref:System.Windows.Forms.ToolStripMenuItem> controls.</span></span> <span data-ttu-id="2c353-104">In .NET Framework 4.7.2 und höher ist die <xref:System.Windows.Forms.ContextMenuStrip.SourceControl>-Eigenschaft immer auf das tatsächliche Quellsteuerelement festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2c353-104">In the .NET Framework 4.7.2 and later, <xref:System.Windows.Forms.ContextMenuStrip.SourceControl> property is always set to the actual source control.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2c353-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="2c353-105">Suggestion</span></span>

<span data-ttu-id="2c353-106">**Aktivieren oder Deaktivieren dieser Änderungen:** Damit eine Anwendung von diesen Änderungen profitieren kann, muss sie unter .NET Framework 4.7.2 oder höher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2c353-106">**How to opt in or out of these changes** In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="2c353-107">Die Anwendung kann von diesen Änderungen profitieren, wenn Sie Folgendes durchführen:</span><span class="sxs-lookup"><span data-stu-id="2c353-107">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="2c353-108">Die Anwendung ist auf .NET Framework 4.7.2 ausgelegt.</span><span class="sxs-lookup"><span data-stu-id="2c353-108">It targets the .NET Framework 4.7.2.</span></span> <span data-ttu-id="2c353-109">Diese Änderung wird standardmäßig für Windows Forms-Anwendungen aktiviert, die auf .NET Framework 4.7.2 oder höher ausgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="2c353-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="2c353-110">Die Anwendung ist auf .NET Framework 4.7.1 oder eine frühere Version ausgelegt und deaktiviert veraltete Verhaltensweisen der Barrierefreiheit, indem wie im folgenden Beispiel dargestellt folgender [AppContext-Schalter](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) zum Abschnitt `<runtime>` der Datei „app.config“ hinzugefügt und auf `false` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="2c353-110">It targets the .NET Framework 4.7.1 or an earlier version and opts out of the legacy accessibility behaviors by adding the following [AppContext Switch](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the `<runtime>` section of the app.config file and setting it to `false`, as the following example shows.</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue=false"/>
</runtime>
```

<span data-ttu-id="2c353-111">Bei Anwendungen, die auf .NET Framework 4.7.2 oder höher ausgelegt sind und das veraltete Barrierefreiheitsverhalten beibehalten sollen, können Sie die Verwendung des veralteten Quellcodeverwaltungswerts aktivieren, indem Sie den „AppContext“-Schalter auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="2c353-111">Applications that target the .NET Framework 4.7.2 or later, and want to preserve the legacy behavior can opt in to the use of the legacy source control value by explicitly setting this AppContext switch to `true`.</span></span>

| <span data-ttu-id="2c353-112">name</span><span class="sxs-lookup"><span data-stu-id="2c353-112">Name</span></span>    | <span data-ttu-id="2c353-113">Wert</span><span class="sxs-lookup"><span data-stu-id="2c353-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2c353-114">Bereich</span><span class="sxs-lookup"><span data-stu-id="2c353-114">Scope</span></span>   | <span data-ttu-id="2c353-115">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2c353-115">Edge</span></span>        |
| <span data-ttu-id="2c353-116">Version</span><span class="sxs-lookup"><span data-stu-id="2c353-116">Version</span></span> | <span data-ttu-id="2c353-117">4.7.2</span><span class="sxs-lookup"><span data-stu-id="2c353-117">4.7.2</span></span>       |
| <span data-ttu-id="2c353-118">Typ</span><span class="sxs-lookup"><span data-stu-id="2c353-118">Type</span></span>    | <span data-ttu-id="2c353-119">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="2c353-119">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="2c353-120">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="2c353-120">Affected APIs</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>
