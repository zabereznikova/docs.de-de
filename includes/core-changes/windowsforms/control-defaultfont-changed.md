---
ms.openlocfilehash: 02dbf5ccca97f5e7d2e1fada39bdf601cf37906f
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71119149"
---
### <a name="controldefaultfont-changed-to-segoe-ui-9pt"></a>`Control.DefaultFont` wurde in `Segoe UI 9pt` geändert 

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Framework wurde die <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType>-Eigenschaft auf `Microsoft Sans Serif 8pt` festgelegt. Die folgende Abbildung zeigt ein Fenster, in dem die Standardschriftart verwendet wird.

![Steuerelement-Standardschriftart in .NET Framework](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

In .NET Core (ab .NET Core 3.0) wird sie auf `Segoe UI 9pt` festgelegt (die gleiche Schriftart wie <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>). Infolge dieser Änderung werden Formulare und Steuerelemente etwa 27 % größer dimensioniert, um die größere Größe der neuen Standardschriftart zu berücksichtigen. Beispiel:

![Steuerelement-Standardschriftart in .NET Core](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

Diese Änderung wurde vorgenommen, um den [Leitfäfen für Windows-UX](https://docs.microsoft.com/windows/win32/uxguide/vis-fonts#fonts-and-colors) zu genügen.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Aufgrund der Änderung der Größe von Formularen und Steuerelementen sollten Sie sicherstellen, dass Ihre Anwendung richtig gerendert wird.

Wenn Sie die ursprüngliche Schriftart beibehalten möchten, legen Sie die Standardschriftart des Formulars auf `Microsoft Sans Serif 8pt` fest. Beispiel:

```csharp
public MyForm()
{
    InitializeComponent();
    Font = new Font(new FontFamily("Microsoft Sans Serif"), 8f);
}
```

#### <a name="category"></a>Category (Kategorie)

- Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

None (Keine):

<!--

### Affected APIs

- Not detectable via API analysis

-->