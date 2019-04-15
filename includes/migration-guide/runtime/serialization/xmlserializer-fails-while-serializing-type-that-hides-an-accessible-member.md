---
ms.openlocfilehash: 9b8f5e210c21bc516e7965f1a092cc6ff1371b8c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235779"
---
### <a name="xmlserializer-fails-while-serializing-a-type-that-hides-an-accessible-member-with-an-inaccessible-one"></a>„XmlSerializer“ schlägt während der Serialisierung eines Typs fehl, der einen verfügbaren Member mit einem nicht verfügbaren überdeckt

|   |   |
|---|---|
|Details|Bei der Serialisierung eines abgeleiteten Typs kann <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> fehlschlagen, wenn der Typ einen verfügbaren Member oder eine Eigenschaft enthält, die ein Feld oder eine Eigenschaft mit dem gleichen Namen ausblendet (durch das Schlüsselwort „new“), das bzw. die zuvor im Basistyp verfügbar (z.B. „public“) war.|
|Vorschlag|Dieses Problem kann gelöst werden, indem der neue, ausgeblendete Member für <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> zur Verfügung gestellt wird, indem es z.B. als „public“ gekennzeichnet wird. Alternativ kann das Verhalten von <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> unter 4.0 mithilfe von folgenden Konfigurationseinstellungen wiederhergestellt und das Problem somit behoben werden:<pre><code class="lang-xml">&lt;system.xml.serialization&gt;&#13;&#10;&lt;xmlSerializer useLegacySerializerGeneration=&quot;true&quot; /&gt;&#13;&#10;&lt;/system.xml.serialization&gt;&#13;&#10;</code></pre>|
|Bereich|Gering|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter,System.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Object,System.Xml.Serialization.XmlSerializationWriter)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces,System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces,System.String,System.String)?displayProperty=nameWithType></li></ul>|
