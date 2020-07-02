---
ms.openlocfilehash: eafbdd2d42977381fb4d77748a3c9a2595ff2936
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620373"
---
### <a name="xmlserializer-fails-while-serializing-a-type-that-hides-an-accessible-member-with-an-inaccessible-one"></a>„XmlSerializer“ schlägt während der Serialisierung eines Typs fehl, der einen verfügbaren Member mit einem nicht verfügbaren überdeckt

#### <a name="details"></a>Details

Bei der Serialisierung eines abgeleiteten Typs kann <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> fehlschlagen, wenn der Typ einen verfügbaren Member oder eine Eigenschaft enthält, die ein Feld oder eine Eigenschaft mit dem gleichen Namen ausblendet (durch das Schlüsselwort „new“), das bzw. die zuvor im Basistyp verfügbar (z.B. „public“) war.

#### <a name="suggestion"></a>Vorschlag

Dieses Problem kann gelöst werden, indem der neue, ausgeblendete Member für <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> zur Verfügung gestellt wird, indem es z.B. als „public“ gekennzeichnet wird. Alternativ kann das Verhalten von <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> unter 4.0 mithilfe von folgenden Konfigurationseinstellungen wiederhergestellt und das Problem somit behoben werden:<pre><code class="lang-xml">&lt;system.xml.serialization&gt;&#13;&#10;&lt;xmlSerializer useLegacySerializerGeneration=&quot;true&quot; /&gt;&#13;&#10;&lt;/system.xml.serialization&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter,System.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Object,System.Xml.Serialization.XmlSerializationWriter)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces,System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces,System.String,System.String)?displayProperty=nameWithType></li></ul>|
