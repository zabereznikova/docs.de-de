---
title: Serialization
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: bebb27ac-9712-4196-9931-de19fc04dbac
ms.openlocfilehash: d29a7bc9f304b8d19e8af593166b8d847117424f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743636"
---
# <a name="serialization"></a>Serialization
Serialisierung ist der Prozess, bei dem ein Objekt in ein Format umgewandelt wird, das leicht persistent gespeichert oder transportiert werden kann. Beispielsweise können Sie ein Objekt serialisieren, über das Internet mithilfe von http transportieren und auf dem Zielcomputer deserialisieren.

 Der .NET Framework bietet drei wichtige Serialisierungstechnologien, die für verschiedene Serialisierungsszenarien optimiert sind. In der folgenden Tabelle werden diese Technologien und die zugehörigen Framework-Haupttypen für die jeweilige Technologie beschrieben.

|**Technologie Name**|**Haupttypen**|**SS**|
|-------------------------|--------------------|-------------------|
|**Datenvertragsserialisierung**|<xref:System.Runtime.Serialization.DataContractAttribute> <br /> <xref:System.Runtime.Serialization.DataMemberAttribute> <br /> <xref:System.Runtime.Serialization.DataContractSerializer> <br /> <xref:System.Runtime.Serialization.NetDataContractSerializer> <br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <br /> <xref:System.Runtime.Serialization.ISerializable>|Allgemeine Persistenz<br />Webdienste<br />JSON|
|**XML-Serialisierung**|<xref:System.Xml.Serialization.XmlSerializer>|XML-Format mit vollständiger Kontrolle über die Form des XML-Codes|
|**Laufzeitserialisierung (Binary und SOAP)**|<xref:System.SerializableAttribute> <br /> <xref:System.Runtime.Serialization.ISerializable> <br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|.NET-Remotezugriff|

 Wenn Sie neue Typen entwerfen, ✔️ bei der Serialisierung nachzudenken.

## <a name="choosing-the-right-serialization-technology-to-support"></a>Auswählen einer geeigneten Serialisierungstechnologie, die unterstützt werden soll
 ✔️ in Erwägung ziehen, die Datenvertragsserialisierung zu unterstützen, wenn Instanzen des Typs möglicherweise persistent gespeichert oder in Webdiensten verwendet werden müssen.

 ✔️ sollten die XML-Serialisierung anstelle von oder zusätzlich zur Datenvertragsserialisierung unterstützen, wenn Sie mehr Kontrolle über das XML-Format benötigen, das bei der Serialisierung des Typs erzeugt wird.

 Dies kann in einigen Interoperabilitäts Szenarien notwendig sein, bei denen Sie ein XML-Konstrukt verwenden müssen, das von der Datenvertragsserialisierung nicht unterstützt wird, z. b. um XML-Attribute zu erzeugen

 ✔️ sollten die Laufzeitserialisierung unterstützen, wenn Instanzen des Typs über .NET-Remoting-Grenzen hinweg übertragen werden müssen.

 ❌ vermeiden der Unterstützung der Laufzeitserialisierung oder XML-Serialisierung nur aus Gründen der allgemeinen Persistenz. Bevorzugen Sie stattdessen die Datenvertragsserialisierung.

## <a name="supporting-data-contract-serialization"></a>Unterstützen der Datenvertragsserialisierung
 Typen können die Datenvertragsserialisierung unterstützen, indem Sie die <xref:System.Runtime.Serialization.DataContractAttribute> auf den Typ anwenden und die <xref:System.Runtime.Serialization.DataMemberAttribute> auf die Member (Felder und Eigenschaften) des Typs anwenden.

 ✔️ in Erwägung gezogen, Datenmember des Typs öffentlich zu markieren, wenn der Typ in teilweiser Vertrauenswürdigkeit verwendet werden kann.

 Bei voller Vertrauenswürdigkeit können Datenvertragsserialisierer nicht öffentliche Typen und Member serialisieren und deserialisieren. in teilweiser Vertrauenswürdigkeit können jedoch nur öffentliche Member serialisiert und deserialisiert werden.

 ✔️ Implementieren einen Getter und Setter für alle Eigenschaften, die über <xref:System.Runtime.Serialization.DataMemberAttribute>verfügen. Datenvertragsserialisierer erfordern, dass sowohl der Getter als auch der Setter für den Typ als serialisierbar eingestuft werden. (In .NET Framework 3,5 SP1 können einige Sammlungs Eigenschaften nur "Get-only" sein.) Wenn der Typ bei teilweiser Vertrauenswürdigkeit nicht verwendet wird, kann einer oder beide der Eigenschaftenaccessoren nicht öffentlich sein.

 ✔️ in Erwägung gezogen werden, die Serialisierungsrückrufe für die Initialisierung von deserialisierten Instanzen zu verwenden.

 Konstruktoren werden beim Deserialisieren von Objekten nicht aufgerufen. (Es gibt Ausnahmen für die Regel. Konstruktoren von Auflistungen, die mit <xref:System.Runtime.Serialization.CollectionDataContractAttribute> gekennzeichnet sind, werden während der Deserialisierung aufgerufen.) Daher muss jede Logik, die während der normalen Erstellung ausgeführt wird, als eine der Serialisierungsrückrufe implementiert werden.

 `OnDeserializedAttribute` ist das am häufigsten verwendete Rückruf Attribut. Weitere Attribute in der Familie sind <xref:System.Runtime.Serialization.OnDeserializingAttribute>, <xref:System.Runtime.Serialization.OnSerializingAttribute> und <xref:System.Runtime.Serialization.OnSerializedAttribute>. Mit ihnen können Rückrufe gekennzeichnet werden, die entsprechend vor der Deserialisierung, vor der Serialisierung oder nach der Serialisierung ausgeführt werden.

 ✔️ sollten Sie die <xref:System.Runtime.Serialization.KnownTypeAttribute> verwenden, um konkrete Typen anzugeben, die beim Deserialisieren eines komplexen Objekt Diagramms verwendet werden sollen.

 bei der Erstellung oder Änderung serialisierbarer Typen ✔️ eine abwärts-und Vorwärtskompatibilität in Erwägung gezogen.

 Beachten Sie, dass serialisierte Streams von zukünftigen Versionen des Typs in die aktuelle Version des Typs deserialisiert werden können und umgekehrt.

 Stellen Sie sicher, dass auch private und interne Datenmember ihre Namen, Typen oder sogar deren Reihenfolge in zukünftigen Versionen des Typs nicht ändern können, es sei denn, es muss besonders sorgfältig vorgegangen werden, um den Vertrag mithilfe expliziter Parameter für die Daten Vertrags Attribute beizubehalten. .

 Testen Sie die Kompatibilität der Serialisierung, wenn Sie Änderungen an serialisierbaren Typen vornehmen. Versuchen Sie eine Deserialisierung der neuen Version in eine alte Version und umgekehrt.

 ✔️ sollten Sie <xref:System.Runtime.Serialization.IExtensibleDataObject> implementieren, um das Roundtrip zwischen verschiedenen Versionen des Typs zu ermöglichen.

 Über die Schnittstelle kann das Serialisierungsprogramm sicherstellen, dass bei der wiederholten Umwandlung keine Daten verloren gehen. Die <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A?displayProperty=nameWithType>-Eigenschaft wird zum Speichern von Daten aus der zukünftigen Version des Typs verwendet, der in der aktuellen Version unbekannt ist, und kann daher nicht in ihren Datenmembern gespeichert werden. Wenn die aktuelle Version anschließend serialisiert und in eine zukünftige Version deserialisiert wird, sind die zusätzlichen Daten im serialisierten Stream verfügbar.

## <a name="supporting-xml-serialization"></a>Unterstützen der XML-Serialisierung
 Die Datenvertragsserialisierung ist die wichtigste (standardmäßige) serialisierungstechnologie im .NET Framework, aber es gibt Serialisierungsszenarien, die die Datenvertragsserialisierung nicht unterstützt Beispielsweise kann die Form des vom Serialisierungsprogramm erzeugten bzw. verarbeiteten XML nicht vollständig kontrolliert werden. Wenn eine solche feine Kontrolle erforderlich ist, muss die XML-Serialisierung verwendet werden, und Sie müssen die Typen für die Unterstützung dieser serialisierungstechnologie entwerfen.

 ❌ vermeiden Sie das Entwerfen von Typen speziell für die XML-Serialisierung, es sei denn, Sie haben einen sehr starken Grund, die Form der erstellten XML zu steuern. Diese Serialisierungstechnologie wurde durch die im vorherigen Abschnitt behandelte Datenvertragsserialisierung abgelöst.

 ✔️ sollten Sie die <xref:System.Xml.Serialization.IXmlSerializable>-Schnittstelle implementieren, wenn Sie die Form des serialisierten XML-Codes noch besser steuern möchten, als durch Anwenden der XML-Serialisierungsattribute. Mit zwei Methoden der-Schnittstelle, <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> und <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>, können Sie den serialisierten XML-Stream vollständig steuern. Sie können auch das XML-Schema steuern, das für den Typ generiert wird, indem Sie die `XmlSchemaProviderAttribute`anwenden.

## <a name="supporting-runtime-serialization"></a>Unterstützen der Laufzeitserialisierung
 Die Laufzeitserialisierung ist eine von .NET-Remoting verwendete Technologie. Wenn Sie der Ansicht sind, dass Ihre Typen mithilfe von .NET-Remoting transportiert werden, müssen Sie sicherstellen, dass Sie die Laufzeitserialisierung unterstützen.

 Die grundlegende Unterstützung für die Laufzeitserialisierung kann durch Anwenden der <xref:System.SerializableAttribute>bereitgestellt werden. komplexere Szenarien umfassen die Implementierung eines einfachen laufzeitserialisierungsmusters (Implementieren von <xref:System.Runtime.Serialization.ISerializable> und Bereitstellen eines Serialisierungskonstruktors).

 ✔️ sollten die Laufzeitserialisierung unterstützen, wenn Ihre Typen mit .NET-Remoting verwendet werden. Beispielsweise verwendet der <xref:System.AddIn?displayProperty=nameWithType>-Namespace .NET-Remoting, sodass alle zwischen `System.AddIn`-Add-ins ausgetauschten Typen die Laufzeitserialisierung unterstützen müssen.

 ✔️ sollten das serialisierbare Lauf Zeitmuster implementieren, wenn Sie die gesamte Kontrolle über den Serialisierungsprozess haben möchten. Dies wäre z. B. der Fall, wenn Daten bei der Serialisierung oder Deserialisierung umgewandelt werden sollen.

 Das Muster ist sehr einfach. Sie müssen lediglich die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle implementieren und einen speziellen Konstruktor bereitstellen, der beim Deserialisieren des Objekts verwendet wird.

 mit ✔️ wird der Serialisierungskonstruktor geschützt, und es werden zwei Parameter eingegeben, die genau wie im Beispiel hier dargestellt eingegeben und benannt werden.

```csharp
[Serializable]
public class Person : ISerializable
{
    protected Person(SerializationInfo info, StreamingContext context)
    {
        // ...
    }
}
```

 ✔️ die <xref:System.Runtime.Serialization.ISerializable> Member explizit implementieren.

 ✔️ wenden Sie einen Link Aufruf auf <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> Implementierung an. Dadurch wird sichergestellt, dass nur vollständig vertrauenswürdige Kerne und das laufzeitserialisierungsprogramm Zugriff auf den Member haben.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)
