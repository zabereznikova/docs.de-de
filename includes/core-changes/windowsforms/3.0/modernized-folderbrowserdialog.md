---
ms.openlocfilehash: 645df8080abd21e4db95903a301a36b79a698858
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888118"
---
### <a name="modernization-of-the-folderbrowserdialog"></a><span data-ttu-id="6c806-101">Modernisierung von FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="6c806-101">Modernization of the FolderBrowserDialog</span></span>

<span data-ttu-id="6c806-102">Das <xref:System.Windows.Forms.FolderBrowserDialog>-Steuerelement wurde in Windows Forms-Anwendungen für .NET Core geändert.</span><span class="sxs-lookup"><span data-stu-id="6c806-102">The <xref:System.Windows.Forms.FolderBrowserDialog> control has changed in Windows Forms applications for .NET Core.</span></span>

#### <a name="change-description"></a><span data-ttu-id="6c806-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="6c806-103">Change description</span></span>

<span data-ttu-id="6c806-104">In .NET Framework verwendet Windows Forms das folgende Dialogfeld für das <xref:System.Windows.Forms.FolderBrowserDialog>-Steuerelement:</span><span class="sxs-lookup"><span data-stu-id="6c806-104">In the .NET Framework, Windows forms uses the following dialog for the <xref:System.Windows.Forms.FolderBrowserDialog> control:</span></span>

![FolderBrowserDialogControl in .NET Framework](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-framework.png)

<span data-ttu-id="6c806-106">In .NET Core 3.0 verwendet Windows Forms ein neueres COM-basiertes Steuerelement, das in Windows Vista eingeführt wurde:</span><span class="sxs-lookup"><span data-stu-id="6c806-106">In .NET Core 3.0, Windows Forms users a newer COM-based control that was introduced in Windows Vista:</span></span>

![FolderBrowserDialogControl in .NET Core](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-core.png)

#### <a name="version-introduced"></a><span data-ttu-id="6c806-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="6c806-108">Version introduced</span></span>

<span data-ttu-id="6c806-109">3.0</span><span class="sxs-lookup"><span data-stu-id="6c806-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6c806-110">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="6c806-110">Recommended action</span></span>

<span data-ttu-id="6c806-111">Das Dialogfeld wird automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="6c806-111">The dialog will be upgraded automatically.</span></span>

<span data-ttu-id="6c806-112">Wenn Sie das ursprüngliche Dialogfeld beibehalten möchten, legen Sie die <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType>-Eigenschaft auf `false` fest, bevor Sie das Dialogfeld anzeigen, wie im folgenden Codefragment veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="6c806-112">If you desire to retain the original dialog, set the <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> property to `false` before showing the dialog, as illustrated by the following code fragment:</span></span>

```csharp
var dialog = new FolderBrowserDialog();
dialog.AutoUpgradeEnabled = false;
dialog.ShowDialog();
```

#### <a name="category"></a><span data-ttu-id="6c806-113">Kategorie</span><span class="sxs-lookup"><span data-stu-id="6c806-113">Category</span></span>

<span data-ttu-id="6c806-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6c806-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6c806-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="6c806-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>

<!--

### Affected APIs

- `T:System.Windows.Forms.FolderBrowserDialog`

-->
