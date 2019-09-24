---
ms.openlocfilehash: 02dbf5ccca97f5e7d2e1fada39bdf601cf37906f
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71119149"
---
### <a name="controldefaultfont-changed-to-segoe-ui-9pt"></a><span data-ttu-id="9818a-101">`Control.DefaultFont` wurde in `Segoe UI 9pt` geändert</span><span class="sxs-lookup"><span data-stu-id="9818a-101">`Control.DefaultFont` changed to `Segoe UI 9pt`</span></span> 

#### <a name="change-description"></a><span data-ttu-id="9818a-102">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="9818a-102">Change description</span></span>

<span data-ttu-id="9818a-103">In .NET Framework wurde die <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType>-Eigenschaft auf `Microsoft Sans Serif 8pt` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9818a-103">In the .NET Framework, the <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> property was set to `Microsoft Sans Serif 8pt`.</span></span> <span data-ttu-id="9818a-104">Die folgende Abbildung zeigt ein Fenster, in dem die Standardschriftart verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9818a-104">The following figure shows a window that uses the default font.</span></span>

![Steuerelement-Standardschriftart in .NET Framework](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

<span data-ttu-id="9818a-106">In .NET Core (ab .NET Core 3.0) wird sie auf `Segoe UI 9pt` festgelegt (die gleiche Schriftart wie <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="9818a-106">In .NET Core starting with .NET Core 3.0, it is set to `Segoe UI 9pt` (the same font as <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>).</span></span> <span data-ttu-id="9818a-107">Infolge dieser Änderung werden Formulare und Steuerelemente etwa 27 % größer dimensioniert, um die größere Größe der neuen Standardschriftart zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="9818a-107">As a result of this change, forms and controls will be sized about 27% larger to account for the larger size of the new default font.</span></span> <span data-ttu-id="9818a-108">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9818a-108">For example:</span></span>

![Steuerelement-Standardschriftart in .NET Core](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

<span data-ttu-id="9818a-110">Diese Änderung wurde vorgenommen, um den [Leitfäfen für Windows-UX](https://docs.microsoft.com/windows/win32/uxguide/vis-fonts#fonts-and-colors) zu genügen.</span><span class="sxs-lookup"><span data-stu-id="9818a-110">This change was made to align with [Windows UX guidelines](https://docs.microsoft.com/windows/win32/uxguide/vis-fonts#fonts-and-colors).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9818a-111">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9818a-111">Version introduced</span></span>

<span data-ttu-id="9818a-112">3.0</span><span class="sxs-lookup"><span data-stu-id="9818a-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9818a-113">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="9818a-113">Recommended action</span></span>

<span data-ttu-id="9818a-114">Aufgrund der Änderung der Größe von Formularen und Steuerelementen sollten Sie sicherstellen, dass Ihre Anwendung richtig gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="9818a-114">Because of the change in the size of forms and controls, ensure that your application renders correctly.</span></span>

<span data-ttu-id="9818a-115">Wenn Sie die ursprüngliche Schriftart beibehalten möchten, legen Sie die Standardschriftart des Formulars auf `Microsoft Sans Serif 8pt` fest.</span><span class="sxs-lookup"><span data-stu-id="9818a-115">To retain the original font, set your form's default font to `Microsoft Sans Serif 8pt`.</span></span> <span data-ttu-id="9818a-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9818a-116">For example:</span></span>

```csharp
public MyForm()
{
    InitializeComponent();
    Font = new Font(new FontFamily("Microsoft Sans Serif"), 8f);
}
```

#### <a name="category"></a><span data-ttu-id="9818a-117">Category (Kategorie)</span><span class="sxs-lookup"><span data-stu-id="9818a-117">Category</span></span>

- <span data-ttu-id="9818a-118">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9818a-118">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9818a-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="9818a-119">Affected APIs</span></span>

<span data-ttu-id="9818a-120">None (Keine):</span><span class="sxs-lookup"><span data-stu-id="9818a-120">None.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->