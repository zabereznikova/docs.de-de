---
ms.openlocfilehash: 843007ac6467584fbe6350b6ea19ef67609d73e2
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643844"
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

#### <a name="category"></a>Kategorie

- Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!--

### Affected APIs

- Not detectable via API analysis

-->
