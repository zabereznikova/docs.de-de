---
ms.openlocfilehash: aade03c29ff16053a97683499cf719a98ae33f3f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616258"
---
### <a name="add-selectiontextbrush-public-property-to-textboxpasswordbox-non-adorner-selection"></a><span data-ttu-id="382a6-101">Hinzufügen der öffentlichen Eigenschaft „Add SelectionTextBrush“ zur nicht auf Adorner basierenden Auswahl von TextBox/PasswordBox</span><span class="sxs-lookup"><span data-stu-id="382a6-101">Add SelectionTextBrush public property to TextBox/PasswordBox non-adorner selection</span></span>

#### <a name="details"></a><span data-ttu-id="382a6-102">Details</span><span class="sxs-lookup"><span data-stu-id="382a6-102">Details</span></span>

<span data-ttu-id="382a6-103">In WPF-Anwendungen, die eine [nicht auf Adorner basierende Textauswahl](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-TextBox-PasswordBox-text-selection-does-not-follow-system-colors.md) für <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.PasswordBox> verwenden, können Entwickler nun die neu hinzugefügte „SelectionTextBrush“-Eigenschaft festlegen, um das Rendering des ausgewählten Texts zu ändern.</span><span class="sxs-lookup"><span data-stu-id="382a6-103">In WPF applications using [non-adorner based text selection](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-TextBox-PasswordBox-text-selection-does-not-follow-system-colors.md) for <xref:System.Windows.Controls.TextBox> and <xref:System.Windows.Controls.PasswordBox>, developers may now set the newly added SelectionTextBrush property in order to alter the rendering of the selected text.</span></span>  <span data-ttu-id="382a6-104">Diese Farbe ändert sich standardmäßig mit <xref:System.Windows.SystemColors.HighlightTextBrushKey>.</span><span class="sxs-lookup"><span data-stu-id="382a6-104">By default, this color changes with <xref:System.Windows.SystemColors.HighlightTextBrushKey>.</span></span>  <span data-ttu-id="382a6-105">Wenn die nicht auf Adorner basierende Textauswahl nicht aktiviert ist, hat diese Eigenschaft keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="382a6-105">If non-adorner based text selection is not enabled, this property does nothing.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="382a6-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="382a6-106">Suggestion</span></span>

<span data-ttu-id="382a6-107">Nach dem Aktivieren einer nicht auf Adorner basierenden Textauswahl können Sie die Eigenschaften <xref:System.Windows.Controls.PasswordBox.SelectionTextBrush?displayProperty=nameWithType> und <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush> verwenden, um die Darstellung des ausgewählten Texts zu ändern.</span><span class="sxs-lookup"><span data-stu-id="382a6-107">Once non-adorner based text selection is enabled, you can use the <xref:System.Windows.Controls.PasswordBox.SelectionTextBrush?displayProperty=nameWithType> and <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush> property to change the appearance of the selected text.</span></span> <span data-ttu-id="382a6-108">Dies kann mithilfe von XAML erreicht werden:</span><span class="sxs-lookup"><span data-stu-id="382a6-108">This can be achieved using XAML:</span></span>

<pre><code class="lang-xaml">&lt;TextBox SelectionBrush=&quot;Red&quot; SelectionTextBrush=&quot;White&quot;  SelectionOpacity=&quot;0.5&quot;&#13;&#10;Foreground=&quot;Blue&quot; CaretBrush=&quot;Blue&quot;&gt;&#13;&#10;This is some text.&#13;&#10;&lt;/TextBox&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="382a6-109">name</span><span class="sxs-lookup"><span data-stu-id="382a6-109">Name</span></span>    | <span data-ttu-id="382a6-110">Wert</span><span class="sxs-lookup"><span data-stu-id="382a6-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="382a6-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="382a6-111">Scope</span></span>   | <span data-ttu-id="382a6-112">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="382a6-112">Major</span></span>       |
| <span data-ttu-id="382a6-113">Version</span><span class="sxs-lookup"><span data-stu-id="382a6-113">Version</span></span> | <span data-ttu-id="382a6-114">4.8</span><span class="sxs-lookup"><span data-stu-id="382a6-114">4.8</span></span>         |
| <span data-ttu-id="382a6-115">Typ</span><span class="sxs-lookup"><span data-stu-id="382a6-115">Type</span></span>    | <span data-ttu-id="382a6-116">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="382a6-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="382a6-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="382a6-117">Affected APIs</span></span>

- <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrushProperty?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush?displayProperty=nameWithType>
- [<span data-ttu-id="382a6-118">System.Windows.Controls.TextBox</span><span class="sxs-lookup"><span data-stu-id="382a6-118">System.Windows.Controls.TextBox</span></span>](xref:System.Windows.Controls.TextBox)
- [<span data-ttu-id="382a6-119">System.Windows.Controls.PasswordBox</span><span class="sxs-lookup"><span data-stu-id="382a6-119">System.Windows.Controls.PasswordBox</span></span>](xref:System.Windows.Controls.PasswordBox)
