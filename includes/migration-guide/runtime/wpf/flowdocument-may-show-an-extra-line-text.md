---
ms.openlocfilehash: 0470cefc05fb5da6a6195ee0a96f04feef01fd10
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620435"
---
### <a name="flowdocument-may-show-an-extra-line-of-text"></a><span data-ttu-id="67685-101">„FlowDocument“ zeigt möglicherweise eine zusätzliche Textzeile an</span><span class="sxs-lookup"><span data-stu-id="67685-101">FlowDocument may show an extra line of text</span></span>

#### <a name="details"></a><span data-ttu-id="67685-102">Details</span><span class="sxs-lookup"><span data-stu-id="67685-102">Details</span></span>

<span data-ttu-id="67685-103">In einigen Fälle zeigt ein <xref:System.Windows.Documents.FlowDocument>-Element, das unter .NET Framework 4.5 ausgeführt wird, im Gegensatz zu .NET Framework 4.0 eine zusätzliche Textzeile an.</span><span class="sxs-lookup"><span data-stu-id="67685-103">In some cases, a <xref:System.Windows.Documents.FlowDocument> element will display an extra line of text when running on the .NET Framework 4.5 compared to how it displayed when run on the .NET Framework 4.0.</span></span> <span data-ttu-id="67685-104">Es gibt keine bekannten Fälle, dass durch die Änderung ein Text schlecht oder unleserlich dargestellt wird. Es kann jedoch vorkommen, dass Text angezeigt wird, der zuvor aus der Anzeige von <xref:System.Windows.Documents.FlowDocument> entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="67685-104">There are no known cases of the change causing any text to be displayed poorly or illegibly, but it could cause text to appear that previously was omitted from a <xref:System.Windows.Documents.FlowDocument>'s view.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="67685-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="67685-105">Suggestion</span></span>

<span data-ttu-id="67685-106">In einigen Fällen kann das Verringern der PageHeight-Eigenschaft des Anzeigeelements um 1 (eins) die Anzahl der zuvor angezeigten Zeilen wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="67685-106">In some cases, decreasing the display element's PageHeight property by one can restore the previous number of displayed lines.</span></span>

| <span data-ttu-id="67685-107">name</span><span class="sxs-lookup"><span data-stu-id="67685-107">Name</span></span>    | <span data-ttu-id="67685-108">Wert</span><span class="sxs-lookup"><span data-stu-id="67685-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="67685-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="67685-109">Scope</span></span>   |<span data-ttu-id="67685-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="67685-110">Edge</span></span>|
|<span data-ttu-id="67685-111">Version</span><span class="sxs-lookup"><span data-stu-id="67685-111">Version</span></span>|<span data-ttu-id="67685-112">4.5</span><span class="sxs-lookup"><span data-stu-id="67685-112">4.5</span></span>|
|<span data-ttu-id="67685-113">Typ</span><span class="sxs-lookup"><span data-stu-id="67685-113">Type</span></span>|<span data-ttu-id="67685-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="67685-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="67685-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="67685-115">Affected APIs</span></span>

-<xref:System.Windows.Documents.FlowDocument.%23ctor></li><li><xref:System.Windows.Documents.FlowDocument.%23ctor(System.Windows.Documents.Block)></li><li><xref:System.Windows.Controls.FlowDocumentReader.%23ctor></li><li><xref:System.Windows.Controls.FlowDocumentPageViewer.%23ctor></li><li><xref:System.Windows.Controls.Primitives.DocumentPageView.%23ctor></li></ul>|
