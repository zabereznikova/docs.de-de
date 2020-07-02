---
ms.openlocfilehash: c3e39e49747be709977d7fba3c39b59f5575c40d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620507"
---
### <a name="xmlschemaexception-now-sets-line-positions-properly"></a>XmlSchemaException legt Zeilenpositionen jetzt ordnungsgemäß fest

#### <a name="details"></a>Details

Wenn der <xref:System.Xml.Linq.LoadOptions.SetLineInfo>-Wert an die Load-Methode übergeben wird und ein Validierungsfehler auftritt, enthalten die Eigenschaften <xref:System.Xml.Schema.XmlSchemaException.LineNumber> und <xref:System.Xml.Schema.XmlSchemaException.LinePosition> jetzt Zeileninformationen.

#### <a name="suggestion"></a>Vorschlag

Ausnahmebehandlungscode, der davon ausgeht, dass <xref:System.Xml.Schema.XmlSchemaException.LineNumber> und <xref:System.Xml.Schema.XmlSchemaException.LinePosition> nicht festgelegt werden, sollte aktualisiert werden, da diese Eigenschaften jetzt ordnungsgemäß festgelegt werden kann, wenn „SetLineInfo“ beim Laden von XML verwendet wird.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType></li></ul>|
