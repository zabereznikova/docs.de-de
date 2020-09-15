---
ms.openlocfilehash: 97299ddb9bee89c792ddb3d2b9c37516180996f7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614570"
---
### <a name="contextmenustripsourcecontrol-property-contains-a-valid-control-in-the-case-of-nested-toolstripmenuitems"></a><span data-ttu-id="2f361-101">„ContextMenuStrip.SourceControl“-Eigenschaft enthält im Fall geschachtelter „ToolStripMenuItems“ ein gültiges Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2f361-101">ContextMenuStrip.SourceControl property contains a valid control in the case of nested ToolStripMenuItems</span></span>

#### <a name="details"></a><span data-ttu-id="2f361-102">Details</span><span class="sxs-lookup"><span data-stu-id="2f361-102">Details</span></span>

<span data-ttu-id="2f361-103">In .NET Framework 4.7.1 und früheren Versionen gibt die <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>-Eigenschaft fälschlicherweise NULL zurück, wenn der Benutzer das Menü in geschachtelten <xref:System.Windows.Forms.ToolStripMenuItem>-Steuerelementen öffnet.</span><span class="sxs-lookup"><span data-stu-id="2f361-103">In the .NET Framework 4.7.1 and previous versions, the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> property incorrectly returns null when the user opens the menu from nested <xref:System.Windows.Forms.ToolStripMenuItem> controls.</span></span> <span data-ttu-id="2f361-104">In .NET Framework 4.7.2 und höher ist die <xref:System.Windows.Forms.ContextMenuStrip.SourceControl>-Eigenschaft immer auf das tatsächliche Quellsteuerelement festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2f361-104">In the .NET Framework 4.7.2 and later, <xref:System.Windows.Forms.ContextMenuStrip.SourceControl> property is always set to the actual source control.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2f361-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="2f361-105">Suggestion</span></span>

<span data-ttu-id="2f361-106">**Aktivieren oder Deaktivieren dieser Änderungen:** Damit eine Anwendung von diesen Änderungen profitieren kann, muss sie unter .NET Framework 4.7.2 oder höher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2f361-106">**How to opt in or out of these changes** In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="2f361-107">Die Anwendung kann von diesen Änderungen profitieren, wenn Sie Folgendes durchführen:</span><span class="sxs-lookup"><span data-stu-id="2f361-107">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="2f361-108">Die Anwendung ist auf .NET Framework 4.7.2 ausgelegt.</span><span class="sxs-lookup"><span data-stu-id="2f361-108">It targets the .NET Framework 4.7.2.</span></span> <span data-ttu-id="2f361-109">Diese Änderung wird standardmäßig für Windows Forms-Anwendungen aktiviert, die auf .NET Framework 4.7.2 oder höher ausgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="2f361-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="2f361-110">Die Anwendung ist auf .NET Framework 4.7.1 oder eine frühere Version ausgelegt und deaktiviert veraltete Verhaltensweisen der Barrierefreiheit, indem wie im folgenden Beispiel dargestellt folgender [AppContext-Schalter](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) zum Abschnitt `<runtime>` der Datei „app.config“ hinzugefügt und auf `false` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="2f361-110">It targets the .NET Framework 4.7.1 or an earlier version and opts out of the legacy accessibility behaviors by adding the following [AppContext Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the `<runtime>` section of the app.config file and setting it to `false`, as the following example shows.</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue=false"/>
</runtime>
```

<span data-ttu-id="2f361-111">Bei Anwendungen, die auf .NET Framework 4.7.2 oder höher ausgelegt sind und das veraltete Barrierefreiheitsverhalten beibehalten sollen, können Sie die Verwendung des veralteten Quellcodeverwaltungswerts aktivieren, indem Sie den „AppContext“-Schalter auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="2f361-111">Applications that target the .NET Framework 4.7.2 or later, and want to preserve the legacy behavior can opt in to the use of the legacy source control value by explicitly setting this AppContext switch to `true`.</span></span>

| <span data-ttu-id="2f361-112">name</span><span class="sxs-lookup"><span data-stu-id="2f361-112">Name</span></span>    | <span data-ttu-id="2f361-113">Wert</span><span class="sxs-lookup"><span data-stu-id="2f361-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2f361-114">Bereich</span><span class="sxs-lookup"><span data-stu-id="2f361-114">Scope</span></span>   | <span data-ttu-id="2f361-115">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2f361-115">Edge</span></span>        |
| <span data-ttu-id="2f361-116">Version</span><span class="sxs-lookup"><span data-stu-id="2f361-116">Version</span></span> | <span data-ttu-id="2f361-117">4.7.2</span><span class="sxs-lookup"><span data-stu-id="2f361-117">4.7.2</span></span>       |
| <span data-ttu-id="2f361-118">Typ</span><span class="sxs-lookup"><span data-stu-id="2f361-118">Type</span></span>    | <span data-ttu-id="2f361-119">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="2f361-119">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="2f361-120">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="2f361-120">Affected APIs</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>
