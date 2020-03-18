---
ms.openlocfilehash: b0c4e9617677cf95e3a059b57f3d50ddfb072f4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937016"
---
### <a name="default-control-font-changed-to-segoe-ui-9-pt"></a><span data-ttu-id="a9360-101">Standardschriftart für Steuerelemente in Segoe UI 9 pt geändert</span><span class="sxs-lookup"><span data-stu-id="a9360-101">Default control font changed to Segoe UI 9 pt</span></span>

#### <a name="change-description"></a><span data-ttu-id="a9360-102">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="a9360-102">Change description</span></span>

<span data-ttu-id="a9360-103">Im .NET Framework wurde die Eigenschaft <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> auf `Microsoft Sans Serif 8 pt` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a9360-103">In .NET Framework, the <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> property was set to `Microsoft Sans Serif 8 pt`.</span></span> <span data-ttu-id="a9360-104">Die folgende Abbildung zeigt ein Fenster, in dem die Standardschriftart verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a9360-104">The following image shows a window that uses the default font.</span></span>

![Standardschriftart für Steuerelemente im .NET Framework](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

<span data-ttu-id="a9360-106">Ab .NET Core 3.0 ist die Standardschriftart auf `Segoe UI 9 pt` festgelegt (dieselbe Schriftart wie <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="a9360-106">Starting in .NET Core 3.0, the default font is set to `Segoe UI 9 pt` (the same font as <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>).</span></span> <span data-ttu-id="a9360-107">Infolge dieser Änderung werden Formulare und Steuerelemente etwa 27 % größer dimensioniert, um der größeren neuen Standardschriftart gerecht zu werden.</span><span class="sxs-lookup"><span data-stu-id="a9360-107">As a result of this change, forms and controls are sized about 27% larger to account for the larger size of the new default font.</span></span> <span data-ttu-id="a9360-108">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a9360-108">For example:</span></span>

![Standardschriftart für Steuerelemente in .NET Core](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

<span data-ttu-id="a9360-110">Diese Änderung wurde entsprechend den [Leitfäden für Benutzeroberflächen unter Windows](/windows/win32/uxguide/vis-fonts#fonts-and-colors) vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="a9360-110">This change was made to align with [Windows user experience (UX) guidelines](/windows/win32/uxguide/vis-fonts#fonts-and-colors).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a9360-111">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="a9360-111">Version introduced</span></span>

<span data-ttu-id="a9360-112">3.0</span><span class="sxs-lookup"><span data-stu-id="a9360-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a9360-113">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="a9360-113">Recommended action</span></span>

<span data-ttu-id="a9360-114">Aufgrund der Änderung der Größe von Formularen und Steuerelementen sollten Sie sicherstellen, dass Ihre Anwendung richtig gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="a9360-114">Because of the change in the size of forms and controls, ensure that your application renders correctly.</span></span>

<span data-ttu-id="a9360-115">Wenn Sie die ursprüngliche Schriftart beibehalten möchten, legen Sie die Standardschriftart des Formulars auf `Microsoft Sans Serif 8 pt` fest.</span><span class="sxs-lookup"><span data-stu-id="a9360-115">To retain the original font, set your form's default font to `Microsoft Sans Serif 8 pt`.</span></span> <span data-ttu-id="a9360-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a9360-116">For example:</span></span>

```csharp
public MyForm()
{
    InitializeComponent();
    Font = new Font(new FontFamily("Microsoft Sans Serif"), 8f);
}
```

#### <a name="category"></a><span data-ttu-id="a9360-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="a9360-117">Category</span></span>

- <span data-ttu-id="a9360-118">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a9360-118">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a9360-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a9360-119">Affected APIs</span></span>

<span data-ttu-id="a9360-120">Keine.</span><span class="sxs-lookup"><span data-stu-id="a9360-120">None.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
