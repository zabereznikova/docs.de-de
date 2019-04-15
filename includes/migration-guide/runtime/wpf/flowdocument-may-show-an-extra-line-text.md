---
ms.openlocfilehash: 6c1740df66ead271afa5f97dc125587810946bc6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235235"
---
### <a name="flowdocument-may-show-an-extra-line-of-text"></a>„FlowDocument“ zeigt möglicherweise eine zusätzliche Textzeile an

|   |   |
|---|---|
|Details|In einigen Fälle zeigt ein <xref:System.Windows.Documents.FlowDocument>-Element, das unter .NET Framework 4.5 ausgeführt wird, im Gegensatz zu .NET Framework 4.0 eine zusätzliche Textzeile an. Es gibt keine bekannten Fälle, dass durch die Änderung ein Text schlecht oder unleserlich dargestellt wird. Es kann jedoch vorkommen, dass Text angezeigt wird, der zuvor aus der Anzeige von <xref:System.Windows.Documents.FlowDocument> entfernt wurde.|
|Vorschlag|In einigen Fällen kann das Verringern der PageHeight-Eigenschaft des Anzeigeelements um 1 (eins) die Anzahl der zuvor angezeigten Zeilen wiederherstellen.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Windows.Documents.FlowDocument.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Documents.FlowDocument.%23ctor(System.Windows.Documents.Block)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.FlowDocumentReader.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.FlowDocumentPageViewer.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.DocumentPageView.%23ctor?displayProperty=nameWithType></li></ul>|
