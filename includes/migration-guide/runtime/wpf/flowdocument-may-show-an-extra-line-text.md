---
ms.openlocfilehash: 0470cefc05fb5da6a6195ee0a96f04feef01fd10
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620435"
---
### <a name="flowdocument-may-show-an-extra-line-of-text"></a>„FlowDocument“ zeigt möglicherweise eine zusätzliche Textzeile an

#### <a name="details"></a>Details

In einigen Fälle zeigt ein <xref:System.Windows.Documents.FlowDocument>-Element, das unter .NET Framework 4.5 ausgeführt wird, im Gegensatz zu .NET Framework 4.0 eine zusätzliche Textzeile an. Es gibt keine bekannten Fälle, dass durch die Änderung ein Text schlecht oder unleserlich dargestellt wird. Es kann jedoch vorkommen, dass Text angezeigt wird, der zuvor aus der Anzeige von <xref:System.Windows.Documents.FlowDocument> entfernt wurde.

#### <a name="suggestion"></a>Vorschlag

In einigen Fällen kann das Verringern der PageHeight-Eigenschaft des Anzeigeelements um 1 (eins) die Anzahl der zuvor angezeigten Zeilen wiederherstellen.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Windows.Documents.FlowDocument.%23ctor></li><li><xref:System.Windows.Documents.FlowDocument.%23ctor(System.Windows.Documents.Block)></li><li><xref:System.Windows.Controls.FlowDocumentReader.%23ctor></li><li><xref:System.Windows.Controls.FlowDocumentPageViewer.%23ctor></li><li><xref:System.Windows.Controls.Primitives.DocumentPageView.%23ctor></li></ul>|
