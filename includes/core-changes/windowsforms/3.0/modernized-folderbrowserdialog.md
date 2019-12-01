---
ms.openlocfilehash: 24141f4b95cda2ae382a923da034e75c329b8555
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643856"
---
### <a name="modernization-of-the-folderbrowserdialog"></a><span data-ttu-id="6b7ec-101">Modernisierung von FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="6b7ec-101">Modernization of the FolderBrowserDialog</span></span>

<span data-ttu-id="6b7ec-102">Das <xref:System.Windows.Forms.FolderBrowserDialog>-Steuerelement wurde in Windows Forms-Anwendungen für .NET Core geändert.</span><span class="sxs-lookup"><span data-stu-id="6b7ec-102">The <xref:System.Windows.Forms.FolderBrowserDialog> control has changed in Windows Forms applications for .NET Core.</span></span>

#### <a name="change-description"></a><span data-ttu-id="6b7ec-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="6b7ec-103">Change description</span></span>

<span data-ttu-id="6b7ec-104">In .NET Framework verwendet Windows Forms das folgende Dialogfeld für das <xref:System.Windows.Forms.FolderBrowserDialog>-Steuerelement:</span><span class="sxs-lookup"><span data-stu-id="6b7ec-104">In the .NET Framework, Windows forms uses the following dialog for the <xref:System.Windows.Forms.FolderBrowserDialog> control:</span></span>

![FolderBrowserDialogControl in .NET Framework](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-framework.png)

<span data-ttu-id="6b7ec-106">In .NET Core 3.0 verwendet Windows Forms ein neueres COM-basiertes Steuerelement, das in Windows Vista eingeführt wurde:</span><span class="sxs-lookup"><span data-stu-id="6b7ec-106">In .NET Core 3.0, Windows Forms users a newer COM-based control that was introduced in Windows Vista:</span></span>

![FolderBrowserDialogControl in .NET Core](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-core.png)

#### <a name="version-introduced"></a><span data-ttu-id="6b7ec-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="6b7ec-108">Version introduced</span></span>

<span data-ttu-id="6b7ec-109">3.0</span><span class="sxs-lookup"><span data-stu-id="6b7ec-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6b7ec-110">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="6b7ec-110">Recommended action</span></span>

<span data-ttu-id="6b7ec-111">Das Dialogfeld wird automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="6b7ec-111">The dialog will be upgraded automatically.</span></span>

<span data-ttu-id="6b7ec-112">Wenn Sie das ursprüngliche Dialogfeld beibehalten möchten, legen Sie die <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType>-Eigenschaft auf `false` fest, bevor Sie das Dialogfeld anzeigen, wie im folgenden Codefragment veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="6b7ec-112">If you desire to retain the original dialog, set the <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> property to `false` before showing the dialog, as illustrated by the following code fragment:</span></span>

```csharp
var dialog = new FolderBrowserDialog();
dialog.AutoUpgradeEnabled = false;
dialog.ShowDialog();
```

#### <a name="category"></a><span data-ttu-id="6b7ec-113">Kategorie</span><span class="sxs-lookup"><span data-stu-id="6b7ec-113">Category</span></span>

<span data-ttu-id="6b7ec-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6b7ec-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6b7ec-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="6b7ec-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>

<!--

### Affected APIs

- `System.Windows.Forms.FolderBrowserDialog`

-->
