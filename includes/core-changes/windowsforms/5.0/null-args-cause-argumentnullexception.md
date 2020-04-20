---
ms.openlocfilehash: fc0eec26073c299887b4748d0ad37e21c7294e84
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81275242"
---
### <a name="winforms-apis-now-throw-argumentnullexception"></a>WinForms-APIs lösen nun ArgumentNullException aus

Einige Windows Forms-Methoden lösen nun eine <xref:System.ArgumentNullException>-Ausnahme für NULL-Argumente aus, für die sie zuvor eine <xref:System.NullReferenceException>-Ausnahme ausgelöst haben.

#### <a name="change-description"></a>Änderungsbeschreibung

Zuvor haben bestimmte Windows Forms-Methoden eine <xref:System.NullReferenceException>-Ausnahme ausgelöst, wenn ein Argument mit dem Wert NULL übergeben wurde. Ab .NET 5.0 lösen diese Methoden stattdessen eine <xref:System.ArgumentNullException>-Ausnahme für NULL-Argumente aus.

Das Auslösen einer <xref:System.ArgumentNullException>-Ausnahme entspricht dem Verhalten der .NET Runtime. Außerdem wird die Debugfunktion verbessert, indem ausdrücklich kommuniziert wird, dass ein Argument den Wert NULL aufweist und welches Argument betroffen ist.

#### <a name="version-introduced"></a>Eingeführt in Version

.NET 5.0 Preview 1
.NET 5.0 Preview 2

#### <a name="recommended-action"></a>Empfohlene Aktion

Wenn Sie eine dieser Methoden aufrufen und Ihr Code <xref:System.NullReferenceException> für NULL-Argumente abfängt, sollte stattdessen <xref:System.ArgumentNullException> abgefangen werden. Außerdem sollten Sie ein Update für den Code in Betracht ziehen, um die Übergabe von NULL-Argumenten an die aufgeführten Methoden zu verhindern.

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

Ab .NET 5.0 Preview 1:

- <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)>
- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType>

Ab .NET 5.0 Preview 2:

- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> (nur für den <xref:System.IO.Stream>-Parameter)

<!-- 

### Affected APIs

- `M:System.Windows.Forms.Control.ControlCollection.#ctor(System.Windows.Forms.Control)`
- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.TableLayoutControlCollection.#ctor(System.Windows.Forms.TableLayoutPanel)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)`
- `M:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)`
- `M:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)`

-->
