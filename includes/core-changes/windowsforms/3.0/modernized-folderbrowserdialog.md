---
ms.openlocfilehash: 24141f4b95cda2ae382a923da034e75c329b8555
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643856"
---
### <a name="modernization-of-the-folderbrowserdialog"></a>Modernisierung von FolderBrowserDialog

Das <xref:System.Windows.Forms.FolderBrowserDialog>-Steuerelement wurde in Windows Forms-Anwendungen für .NET Core geändert.

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Framework verwendet Windows Forms das folgende Dialogfeld für das <xref:System.Windows.Forms.FolderBrowserDialog>-Steuerelement:

![FolderBrowserDialogControl in .NET Framework](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-framework.png)

In .NET Core 3.0 verwendet Windows Forms ein neueres COM-basiertes Steuerelement, das in Windows Vista eingeführt wurde:

![FolderBrowserDialogControl in .NET Core](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-core.png)

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Das Dialogfeld wird automatisch aktualisiert.

Wenn Sie das ursprüngliche Dialogfeld beibehalten möchten, legen Sie die <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType>-Eigenschaft auf `false` fest, bevor Sie das Dialogfeld anzeigen, wie im folgenden Codefragment veranschaulicht:

```csharp
var dialog = new FolderBrowserDialog();
dialog.AutoUpgradeEnabled = false;
dialog.ShowDialog();
```

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Forms.FolderBrowserDialog>

<!--

### Affected APIs

- `System.Windows.Forms.FolderBrowserDialog`

-->
