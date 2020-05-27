---
ms.openlocfilehash: 0b2d3c1383246d4259c6d906ecf9dab927f4bdb1
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721717"
---
### <a name="default-control-font-changed-to-segoe-ui-9-pt"></a>Standardschriftart für Steuerelemente in Segoe UI 9 pt geändert

#### <a name="change-description"></a>Änderungsbeschreibung

Im .NET Framework wurde die Eigenschaft <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> auf `Microsoft Sans Serif 8 pt` festgelegt. Die folgende Abbildung zeigt ein Fenster, in dem die Standardschriftart verwendet wird.

![Standardschriftart für Steuerelemente im .NET Framework](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

Ab .NET Core 3.0 ist die Standardschriftart auf `Segoe UI 9 pt` festgelegt (dieselbe Schriftart wie <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>). Infolge dieser Änderung werden Formulare und Steuerelemente etwa 27 % größer dimensioniert, um der größeren neuen Standardschriftart gerecht zu werden. Beispiel:

![Standardschriftart für Steuerelemente in .NET Core](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

Diese Änderung wurde entsprechend den [Leitfäden für Benutzeroberflächen unter Windows](/windows/win32/uxguide/vis-fonts#fonts-and-colors) vorgenommen.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="recommended-action"></a>Empfohlene Aktion

Aufgrund der Änderung der Größe von Formularen und Steuerelementen sollten Sie sicherstellen, dass Ihre Anwendung richtig gerendert wird.

Wenn Sie die ursprüngliche Schriftart beibehalten möchten, legen Sie die Standardschriftart des Formulars auf `Microsoft Sans Serif 8 pt` fest. Beispiel:

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

Keine.

<!--

#### Affected APIs

- Not detectable via API analysis

-->
