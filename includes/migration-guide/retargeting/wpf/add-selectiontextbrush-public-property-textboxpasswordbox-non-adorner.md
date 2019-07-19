---
ms.openlocfilehash: 01bbc49cb0febc5a29dafc7c311b848387a4094a
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803566"
---
### <a name="add-selectiontextbrush-public-property-to-textboxpasswordbox-non-adorner-selection"></a>Hinzufügen der öffentlichen Eigenschaft „Add SelectionTextBrush“ zur nicht auf Adorner basierenden Auswahl von TextBox/PasswordBox

|   |   |
|---|---|
|Details|In WPF-Anwendungen, die eine [nicht auf Adorner basierende Textauswahl](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-TextBox-PasswordBox-text-selection-does-not-follow-system-colors.md) für <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.PasswordBox> verwenden, können Entwickler nun die neu hinzugefügte „SelectionTextBrush“-Eigenschaft festlegen, um das Rendering des ausgewählten Texts zu ändern.  Diese Farbe ändert sich standardmäßig mit <xref:System.Windows.SystemColors.HighlightTextBrushKey>.  Wenn die nicht auf Adorner basierende Textauswahl nicht aktiviert ist, hat diese Eigenschaft keine Auswirkungen.|
|Vorschlag|Nach dem Aktivieren einer nicht auf Adorner basierenden Textauswahl können Sie die Eigenschaften <xref:System.Windows.Controls.PasswordBox.SelectionTextBrush?displayProperty=nameWithType> und <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush> verwenden, um die Darstellung des ausgewählten Texts zu ändern. Dies kann mithilfe von XAML erreicht werden:<pre><code class="lang-xaml">&lt;TextBox SelectionBrush=&quot;Red&quot; SelectionTextBrush=&quot;White&quot;  SelectionOpacity=&quot;0.5&quot;&#13;&#10;Foreground=&quot;Blue&quot; CaretBrush=&quot;Blue&quot;&gt;&#13;&#10;This is some text.&#13;&#10;&lt;/TextBox&gt;&#13;&#10;</code></pre>|
|Bereich|Hauptversion|
|Version|4.8|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrushProperty?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush?displayProperty=nameWithType></li><li>[System.Windows.Controls.TextBox](xref:System.Windows.Controls.TextBox)</li><li>[System.Windows.Controls.PasswordBox](xref:System.Windows.Controls.PasswordBox)</li></ul>|

