---
ms.openlocfilehash: aade03c29ff16053a97683499cf719a98ae33f3f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616258"
---
### <a name="add-selectiontextbrush-public-property-to-textboxpasswordbox-non-adorner-selection"></a>Hinzufügen der öffentlichen Eigenschaft „Add SelectionTextBrush“ zur nicht auf Adorner basierenden Auswahl von TextBox/PasswordBox

#### <a name="details"></a>Details

In WPF-Anwendungen, die eine [nicht auf Adorner basierende Textauswahl](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-TextBox-PasswordBox-text-selection-does-not-follow-system-colors.md) für <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.PasswordBox> verwenden, können Entwickler nun die neu hinzugefügte „SelectionTextBrush“-Eigenschaft festlegen, um das Rendering des ausgewählten Texts zu ändern.  Diese Farbe ändert sich standardmäßig mit <xref:System.Windows.SystemColors.HighlightTextBrushKey>.  Wenn die nicht auf Adorner basierende Textauswahl nicht aktiviert ist, hat diese Eigenschaft keine Auswirkungen.

#### <a name="suggestion"></a>Vorschlag

Nach dem Aktivieren einer nicht auf Adorner basierenden Textauswahl können Sie die Eigenschaften <xref:System.Windows.Controls.PasswordBox.SelectionTextBrush?displayProperty=nameWithType> und <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush> verwenden, um die Darstellung des ausgewählten Texts zu ändern. Dies kann mithilfe von XAML erreicht werden:

<pre><code class="lang-xaml">&lt;TextBox SelectionBrush=&quot;Red&quot; SelectionTextBrush=&quot;White&quot;  SelectionOpacity=&quot;0.5&quot;&#13;&#10;Foreground=&quot;Blue&quot; CaretBrush=&quot;Blue&quot;&gt;&#13;&#10;This is some text.&#13;&#10;&lt;/TextBox&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   | Hauptversion       |
| Version | 4.8         |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrushProperty?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush?displayProperty=nameWithType>
- [System.Windows.Controls.TextBox](xref:System.Windows.Controls.TextBox)
- [System.Windows.Controls.PasswordBox](xref:System.Windows.Controls.PasswordBox)
