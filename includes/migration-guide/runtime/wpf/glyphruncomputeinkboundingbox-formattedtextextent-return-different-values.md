---
ms.openlocfilehash: d9e1624bbeb91db63bc284b8eb52643938eb42e5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497693"
---
### <a name="glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-framework-45"></a><span data-ttu-id="65c53-101">„GlyphRun.ComputeInkBoundingBox()“ und „FormattedText.Extent“ geben ab .NET Framework 4.5 verschiedene Werte zurück</span><span class="sxs-lookup"><span data-stu-id="65c53-101">GlyphRun.ComputeInkBoundingBox() and FormattedText.Extent return different values beginning in .NET Framework 4.5</span></span>

#### <a name="details"></a><span data-ttu-id="65c53-102">Details</span><span class="sxs-lookup"><span data-stu-id="65c53-102">Details</span></span>

<span data-ttu-id="65c53-103">Es wurden in .NET Framework 4.5 Verbesserungen an <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> und <xref:System.Windows.Media.FormattedText.Extent> vorgenommen, um Probleme zu beheben, bei denen Felder für die darin enthaltenen Glyphen in .NET Framework 4.0 zu klein waren.</span><span class="sxs-lookup"><span data-stu-id="65c53-103">Improvements were made to <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> and <xref:System.Windows.Media.FormattedText.Extent> in the .NET Framework 4.5 to address issues where the boxes were too small for the contained glyphs in some cases in the .NET Framework 4.0.</span></span> <span data-ttu-id="65c53-104">Aus diesem Grund sind einige Begrenzungsrahmen in .NET Framework 4.5 größer, sodass sich geringfügige Unterschiede beim Layout der Benutzeroberfläche ergeben.</span><span class="sxs-lookup"><span data-stu-id="65c53-104">As a result of this, some bounding boxes will be larger beginning in the .NET Framework 4.5, resulting in subtle differences in UI layout.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="65c53-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="65c53-105">Suggestion</span></span>

<span data-ttu-id="65c53-106">Beachten Sie, dass einige Begrenzungsrahmen für Glyphen vergrößert wurden.</span><span class="sxs-lookup"><span data-stu-id="65c53-106">Be aware that some glyph bounding box sizes have increased.</span></span> <span data-ttu-id="65c53-107">Diese Änderungen verbessert in der Regel die Darstellung und das Testen von Feldtreffern, aber wenn das ältere Verhalten (vor .NET 4.5) gewünscht wird, kann es durch Hinzufügen des folgenden Eintrags zur Datei „app.config“ aktiviert werden:</span><span class="sxs-lookup"><span data-stu-id="65c53-107">These changes will usually improve presentation and hit box testing, but if the older (pre-.NET 4.5) behavior is desired, it can be opted into by adding the following entry to the app.config file:</span></span><pre><code class="lang-xml">&lt;appsettings&gt;&#13;&#10;&lt;add key=&quot;IncludeAllInkInBoundingBox&quot; value=&quot;false&quot;&gt;&#13;&#10;&lt;/appsettings&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="65c53-108">name</span><span class="sxs-lookup"><span data-stu-id="65c53-108">Name</span></span>    | <span data-ttu-id="65c53-109">Wert</span><span class="sxs-lookup"><span data-stu-id="65c53-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="65c53-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="65c53-110">Scope</span></span>   |<span data-ttu-id="65c53-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="65c53-111">Edge</span></span>|
|<span data-ttu-id="65c53-112">Version</span><span class="sxs-lookup"><span data-stu-id="65c53-112">Version</span></span>|<span data-ttu-id="65c53-113">4.5</span><span class="sxs-lookup"><span data-stu-id="65c53-113">4.5</span></span>|
|<span data-ttu-id="65c53-114">Typ</span><span class="sxs-lookup"><span data-stu-id="65c53-114">Type</span></span>|<span data-ttu-id="65c53-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="65c53-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="65c53-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="65c53-116">Affected APIs</span></span>

- <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=nameWithType>
- <xref:System.Windows.Media.FormattedText.Extent?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Media.GlyphRun.ComputeInkBoundingBox`
- `P:System.Windows.Media.FormattedText.Extent`

-->
