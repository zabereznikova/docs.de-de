---
title: Serialisierungsrichtlinien
description: Dieses Dokument enthält Richtlinien, die beim Entwerfen einer zu serialisierenden API zu beachten sind, sowie eine Zusammenfassung der drei wichtigsten Serialisierungstechnologien, die .NET bietet.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serialization, guidelines
- binary serialization, guidelines
ms.assetid: ebbeddff-179d-443f-bf08-9c373199a73a
ms.openlocfilehash: 110efce0bd7fae1a4f39f5d879496bf541ffe667
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722153"
---
# <a name="serialization-guidelines"></a>Serialisierungsrichtlinien

In diesem Artikel werden die Richtlinien beschrieben, die beim Entwurf einer API zu berücksichtigen sind, welche für die Serialisierung vorgesehen ist.

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

 .NET Framework bietet drei wichtige Serialisierungstechnologien, die für verschiedene Serialisierungsszenarios optimiert wurden. In der folgenden Tabelle werden diese Technologien und die zugehörigen .NET-Typen für die jeweilige Technologie beschrieben.

|Technologie|Relevante Klassen|Hinweise|
|----------------|----------------------|-----------|
|Datenvertragsserialisierung|<xref:System.Runtime.Serialization.DataContractAttribute><br /><br /> <xref:System.Runtime.Serialization.DataMemberAttribute><br /><br /> <xref:System.Runtime.Serialization.DataContractSerializer><br /><br /> <xref:System.Runtime.Serialization.NetDataContractSerializer><br /><br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer><br /><br /> <xref:System.Runtime.Serialization.ISerializable>|Allgemeine Persistenz<br /><br /> Webdienste<br /><br /> JSON|
|XML-Serialisierung|<xref:System.Xml.Serialization.XmlSerializer>|XML-Format <br />mit vollständiger Kontrolle|
|Laufzeitserialisierung (binär und SOAP)|<xref:System.SerializableAttribute><br /><br /> <xref:System.Runtime.Serialization.ISerializable><br /><br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|.NET-Remotezugriff|

 Wenn Sie neue Typen entwerfen, müssen Sie entscheiden, welche dieser Technologien, sofern erforderlich, von den Typen unterstützt werden sollen. In den folgenden Richtlinien wird beschrieben, wie Sie diese Entscheidung treffen können und die entsprechende Unterstützung bereitstellen. Die Richtlinien geben keine Hilfestellung dazu, welche Serialisierungstechnologie letztendlich am besten für die Implementierung einer Anwendung oder Bibliothek geeignet ist. Solche Entscheidungen sind nicht direkt abhängig vom API-Entwurf und werden daher in diesem Thema nicht behandelt.

## <a name="guidelines"></a>Richtlinien

- Denken Sie beim Entwurf neuer Typen auch an eine mögliche Serialisierung.

  Die Serialisierung spielt eine wichtige Rolle beim Entwurf von Typen, da Programme ggf. Instanzen eines Typs beibehalten oder übertragen müssen.

### <a name="choosing-the-right-serialization-technology-to-support"></a>Auswählen einer geeigneten Serialisierungstechnologie, die unterstützt werden soll

 Jeder Typ kann keine, eine oder mehrere Serialisierungstechnologien unterstützen.

- ERWÄGEN Sie eine Unterstützung der *Datenvertragsserialisierung*, falls Instanzen des Typs in Webdiensten verwendet oder beibehalten werden.

- ERWÄGEN Sie eine Unterstützung der *XML-Serialisierung* anstelle oder zusätzlich zur Datenvertragsserialisierung, wenn Sie eine größere Kontrolle über das bei der Serialisierung des Typs erstellte XML-Format benötigen.

     Dies kann in einigen Interoperabilitätsszenarien von Bedeutung sein, wenn ein XML-Konstrukt verwendet werden muss, das von der Datenvertragsserialisierung nicht unterstützt wird, beispielsweise um XML-Attribute zu erzeugen.

- ERWÄGEN Sie eine Unterstützung der *Laufzeitserialisierung*, wenn Instanzen des Typs über .NET-Remotegrenzen übertragen werden müssen.

- Vermeiden Sie eine Unterstützung der Laufzeitserialisierung oder der XML-Serialisierung, wenn diese Unterstützung lediglich aus allgemeinen Persistenzgründen implementiert wird. In solchen Fällen sollten Sie die Datenvertragsserialisierung bevorzugen.

#### <a name="data-contract-serialization"></a>Datenvertragsserialisierung

 Um die Datenvertragsserialisierung für einen Typ zu unterstützen, wenden Sie <xref:System.Runtime.Serialization.DataContractAttribute> auf den Typ und <xref:System.Runtime.Serialization.DataMemberAttribute> auf die Member (Felder und Eigenschaften) des Typs an.

 [!code-csharp[SerializationGuidelines#1](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#1)]
 [!code-vb[SerializationGuidelines#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#1)]

1. Erwägen Sie, die Datenmember des Typs als öffentlich zu kennzeichnen, wenn der Typ bei teilweiser Vertrauenswürdigkeit verwendet werden kann. Bei voller Vertrauenswürdigkeit können Datenvertragsserialisierungsprogramme nicht öffentliche Typen und Member serialisieren und deserialisieren, bei teilweiser Vertrauenswürdigkeit hingegen können ausschließlich öffentliche Member serialisiert und deserialisiert werden.

2. Implementieren Sie einen Getter und einen Setter für alle Eigenschaften, die über ein Data-MemberAttribute verfügen. Datenvertragsserialisierungsprogramme verlangen sowohl einen Getter als auch einen Setter, damit der Typ als serialisierbar betrachtet wird. Wenn der Typ nicht bei teilweiser Vertrauenswürdigkeit verwendet wird, können einer oder beide Methoden für den Zugriff auf Eigenschaften nicht öffentlich sein.

     [!code-csharp[SerializationGuidelines#2](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#2)]
     [!code-vb[SerializationGuidelines#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#2)]

3. Erwägen Sie die Verwendung von Serialisierungsrückrufen für die Initialisierung deserialisierter Instanzen.

     Konstruktoren werden beim Deserialisieren von Objekten nicht aufgerufen. Daher muss jede Logik, die während der normalen Erstellung ausgeführt wird, als einer der *Serialisierungsrückrufe* implementiert werden.

     [!code-csharp[SerializationGuidelines#3](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#3)]
     [!code-vb[SerializationGuidelines#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#3)]

     Das <xref:System.Runtime.Serialization.OnDeserializedAttribute>-Attribut ist das am häufigsten verwendete Rückrufattribut. Weitere Attribute in der Familie sind <xref:System.Runtime.Serialization.OnDeserializingAttribute>, <xref:System.Runtime.Serialization.OnSerializingAttribute> und <xref:System.Runtime.Serialization.OnSerializedAttribute>. Mit ihnen können Rückrufe gekennzeichnet werden, die entsprechend vor der Deserialisierung, vor der Serialisierung oder nach der Serialisierung ausgeführt werden.

4. Erwägen Sie die Verwendung des <xref:System.Runtime.Serialization.KnownTypeAttribute>, um konkrete Typen anzugeben, die beim Deserialisieren eines komplexen Objektdiagramms verwendet werden sollen.

     Wenn ein Typ eines deserialisierten Datenmembers z.B. durch eine abstrakte Klasse dargestellt wird, benötigt das Serialisierungsprogramm die Informationen zum *bekannten Typ*, um zu entscheiden, welcher konkrete Typ instanziiert und dem Member zugewiesen werden soll. Wenn der bekannte Typ nicht mithilfe des Attributs angegeben wird, muss er explizit an das Serialisierungsprogramm übergeben werden (durch Übergabe der bekannten Typen an den Konstruktor des Serialisierungsprogramms) oder in der Konfigurationsdatei angegeben sein.

     [!code-csharp[SerializationGuidelines#4](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#4)]
     [!code-vb[SerializationGuidelines#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#4)]

     In Fällen, in denen die Liste der bekannten Typen nicht statisch ist (wenn die **Person**-Klasse kompiliert wird), kann **KnownTypeAttribute** auch auf eine Methode zeigen, die zur Laufzeit eine Liste bekannter Typen zurückgibt.

5. Berücksichtigen Sie die Abwärts- und Aufwärtskompatibilität, wenn Sie serialisierbare Typen erstellen oder ändern.

     Beachten Sie, dass serialisierte Streams von zukünftigen Versionen des Typs in die aktuelle Version des Typs deserialisiert werden können und umgekehrt. Berücksichtigen Sie bei allen Überlegungen, dass Datenmember, auch private und interne, ihren Namen, ihren Typ und die Reihenfolge in zukünftigen Versionen des Typs nicht mehr ändern können, es sei denn, es wird besonders darauf geachtet, dass der Vertrag erhalten bleibt, indem explizite Parameter für die Datenvertragsattribute verwendet werden. Testen Sie die Kompatibilität der Serialisierung, wenn Sie Änderungen an den serialisierbaren Typen vornehmen. Versuchen Sie eine Deserialisierung der neuen Version in eine alte Version und umgekehrt.

6. Erwägen Sie die Implementierung der <xref:System.Runtime.Serialization.IExtensibleDataObject>-Schnittstelle, um wiederholte Umwandlungen zwischen verschiedenen Versionen des Typs zu gestatten.

     Über die Schnittstelle kann das Serialisierungsprogramm sicherstellen, dass bei der wiederholten Umwandlung keine Daten verloren gehen. In der <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>-Eigenschaft werden alle Daten aus der zukünftigen Version des Typs gespeichert, die in der aktuellen Version unbekannt sind. Wenn die aktuelle Version anschließend serialisiert und in eine zukünftige Version deserialisiert wird, sind die zusätzlichen Daten im serialisierten Stream über den Wert der **ExtensionData**-Eigenschaft verfügbar.

     [!code-csharp[SerializationGuidelines#5](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#5)]
     [!code-vb[SerializationGuidelines#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#5)]

     Weitere Informationen finden Sie unter [Aufwärtskompatible Datenverträge](../../framework/wcf/feature-details/forward-compatible-data-contracts.md).

#### <a name="xml-serialization"></a>XML-Serialisierung

 Die Datenvertragsserialisierung ist die primäre (standardmäßige) Serialisierungstechnologie in .NET Framework. Es gibt jedoch einige Serialisierungsszenarien, die von der Datenvertragsserialisierung nicht unterstützt werden. Beispielsweise kann die Form des vom Serialisierungsprogramm erzeugten bzw. verarbeiteten XML nicht vollständig kontrolliert werden. Wenn eine präzise Kontrolle erforderlich ist, muss die *XML-Serialisierung* verwendet werden, und der Entwurf der Typen muss eine Unterstützung dieser Serialisierungstechnologie enthalten.

1. Vermeiden Sie es, Typen speziell für die XML-Serialisierung zu entwerfen, sofern es keinen eindeutigen Grund gibt, die Form des erzeugten XML zu kontrollieren. Diese Serialisierungstechnologie wurde durch die im vorherigen Abschnitt behandelte Datenvertragsserialisierung abgelöst.

     Mit anderen Worten, wenden Sie keine Attribute aus dem <xref:System.Xml.Serialization>-Namespace auf neue Typen an, es sei denn, Sie wissen, dass für den Typ eine XML-Serialisierung verwendet werden soll. Anhand des folgenden Beispiels wird dargestellt, wie die Form des erzeugten XML mit **System.Xml.Serialization** kontrolliert werden kann.

     [!code-csharp[SerializationGuidelines#6](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#6)]
     [!code-vb[SerializationGuidelines#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#6)]

2. Erwägen Sie eine Implementierung der <xref:System.Xml.Serialization.IXmlSerializable>-Schnittstelle, wenn Sie eine noch präzisere Kontrolle über die Form des serialisierten XML erreichen möchten, als mit den XML-Serialisierungsattributen möglich ist. Die beiden Methoden <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> und <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> der Schnittstelle erlauben eine vollständige Kontrolle des serialisierten XML-Streams. Sie können auch das XML-Schema kontrollieren, das für den Typ generiert wird, indem Sie das <xref:System.Xml.Serialization.XmlSchemaProviderAttribute>-Attribut anwenden.

#### <a name="runtime-serialization"></a>Laufzeitserialisierung

 Die *Laufzeitserialisierung* ist eine von .NET-Remoting verwendete Technologie. Wenn eine Übertragung der Typen mit .NET-Remoting vorgesehen ist, müssen Sie gewährleisten, dass die Typen die Laufzeitserialisierung unterstützen.

 Eine grundlegende Unterstützung der *Laufzeitserialisierung* kann durch Anwenden des <xref:System.SerializableAttribute>-Attributs bereitgestellt werden. Komplexere Szenarios umfassen die Implementierung eines einfachen *Laufzeitserialisierungsmusters* (durch Implementieren von <xref:System.Runtime.Serialization.ISerializable> und Bereitstellen eines Serialisierungskonstruktors).

1. Erwägen Sie eine Unterstützung der Laufzeitserialisierung, wenn die Typen zusammen mit .NET-Remotezugriff verwendet werden sollen. Der <xref:System.AddIn>-Namespace verwendet z.B. .NET-Remotezugriff, sodass alle zwischen **System.AddIn**-Add-Ins ausgetauschten Typen die Laufzeitserialisierung unterstützen müssen.

     [!code-csharp[SerializationGuidelines#7](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#7)]
     [!code-vb[SerializationGuidelines#7](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#7)]

2. ERWÄGEN Sie die Implementierung des *Laufzeitserialisierungsmusters*, wenn Sie den Serialisierungsprozess vollständig kontrollieren möchten. Dies wäre z. B. der Fall, wenn Daten bei der Serialisierung oder Deserialisierung umgewandelt werden sollen.

     Das Muster ist sehr einfach. Sie müssen lediglich die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle implementieren und einen speziellen Konstruktor bereitstellen, der beim Deserialisieren des Objekts verwendet wird.

     [!code-csharp[SerializationGuidelines#8](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#8)]
     [!code-vb[SerializationGuidelines#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#8)]

3. Definieren Sie den Serialisierungskonstruktor als geschützt, und stellen Sie zwei Parameter mit denselben Typen und Namen wie im hier gezeigten Beispiel bereit.

     [!code-csharp[SerializationGuidelines#9](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#9)]
     [!code-vb[SerializationGuidelines#9](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#9)]

4. Implementieren Sie die ISerializable-Member explizit.

     [!code-csharp[SerializationGuidelines#10](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#10)]
     [!code-vb[SerializationGuidelines#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#10)]

5. WENDEN Sie einen Linkaufruf auf die **ISerializable.GetObjectData**-Implementierung an. Dadurch wird gewährleistet, dass ausschließlich vollständig vertrauenswürdige Kernkomponenten und das Laufzeitserialisierungsprogramm Zugriff auf den Member haben.

     [!code-csharp[SerializationGuidelines#11](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#11)]
     [!code-vb[SerializationGuidelines#11](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#11)]

## <a name="see-also"></a>Siehe auch

- [Verwenden von Datenverträgen](../../framework/wcf/feature-details/using-data-contracts.md)
- [Datenvertragsserialisierer](../../framework/wcf/feature-details/data-contract-serializer.md)
- [Vom Datenvertragsserialisierer unterstützte Typen](../../framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md)
- [Binäre Serialisierung](binary-serialization.md)
- [.NET-Remotezugriff](/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))
- [XML- und SOAP-Serialisierung](xml-and-soap-serialization.md)
- [Sicherheit und Serialisierung](../../framework/misc/security-and-serialization.md)
