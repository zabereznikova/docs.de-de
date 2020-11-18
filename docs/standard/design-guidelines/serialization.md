---
title: Serialisierung
ms.date: 10/22/2008
ms.assetid: bebb27ac-9712-4196-9931-de19fc04dbac
ms.openlocfilehash: 85481e9d759a71346d83c66f67d9623fc32e76ec
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828672"
---
# <a name="serialization"></a>Serialisierung
Serialisierung ist der Prozess, bei dem ein Objekt in ein Format umgewandelt wird, das leicht persistent gespeichert oder transportiert werden kann. Beispielsweise können Sie ein Objekt serialisieren, über das Internet mithilfe von http transportieren und auf dem Zielcomputer deserialisieren.

 Der .NET Framework bietet drei wichtige Serialisierungstechnologien, die für verschiedene Serialisierungsszenarien optimiert sind. In der folgenden Tabelle werden diese Technologien und die zugehörigen Framework-Haupttypen für die jeweilige Technologie beschrieben.

|**Technologiename**|**Haupttypen**|**Szenarios**|
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

 ❌ Vermeiden Sie die Unterstützung der Laufzeitserialisierung oder XML-Serialisierung nur aus Gründen allgemeiner Persistenz. Bevorzugen Sie stattdessen die Datenvertragsserialisierung.

## <a name="supporting-data-contract-serialization"></a>Unterstützen der Datenvertragsserialisierung
 Typen können die Datenvertragsserialisierung unterstützen, indem <xref:System.Runtime.Serialization.DataContractAttribute> Sie auf den Typ und auf die Member <xref:System.Runtime.Serialization.DataMemberAttribute> (Felder und Eigenschaften) des Typs anwenden.

 ✔️ in Erwägung gezogen, Datenmember des Typs öffentlich zu markieren, wenn der Typ in teilweiser Vertrauenswürdigkeit verwendet werden kann.

 Bei voller Vertrauenswürdigkeit können Datenvertragsserialisierer nicht öffentliche Typen und Member serialisieren und deserialisieren. in teilweiser Vertrauenswürdigkeit können jedoch nur öffentliche Member serialisiert und deserialisiert werden.

 ✔️ Implementieren einen Getter und Setter für alle Eigenschaften, die über verfügen <xref:System.Runtime.Serialization.DataMemberAttribute> . Datenvertragsserialisierer erfordern, dass sowohl der Getter als auch der Setter für den Typ als serialisierbar eingestuft werden. (In .NET Framework 3,5 SP1 können einige Sammlungs Eigenschaften nur "Get-only" sein.) Wenn der Typ bei teilweiser Vertrauenswürdigkeit nicht verwendet wird, kann einer oder beide der Eigenschaftenaccessoren nicht öffentlich sein.

 ✔️ in Erwägung gezogen werden, die Serialisierungsrückrufe für die Initialisierung von deserialisierten Instanzen zu verwenden.

 Konstruktoren werden beim Deserialisieren von Objekten nicht aufgerufen. (Es gibt Ausnahmen für die Regel. Konstruktoren von mit markierten Sammlungen <xref:System.Runtime.Serialization.CollectionDataContractAttribute> werden während der Deserialisierung aufgerufen.) Daher muss jede Logik, die während der normalen Erstellung ausgeführt wird, als eine der Serialisierungsrückrufe implementiert werden.

 `OnDeserializedAttribute` ist das am häufigsten verwendete Rückruf Attribut. Weitere Attribute in der Familie sind <xref:System.Runtime.Serialization.OnDeserializingAttribute>, <xref:System.Runtime.Serialization.OnSerializingAttribute> und <xref:System.Runtime.Serialization.OnSerializedAttribute>. Mit ihnen können Rückrufe gekennzeichnet werden, die entsprechend vor der Deserialisierung, vor der Serialisierung oder nach der Serialisierung ausgeführt werden.

 ✔️ die Verwendung <xref:System.Runtime.Serialization.KnownTypeAttribute> von in Erwägung gezogen, um konkrete Typen anzugeben, die beim Deserialisieren eines komplexen Objekt Diagramms verwendet werden sollen.

 bei der Erstellung oder Änderung serialisierbarer Typen ✔️ eine abwärts-und Vorwärtskompatibilität in Erwägung gezogen.

 Beachten Sie, dass serialisierte Streams von zukünftigen Versionen des Typs in die aktuelle Version des Typs deserialisiert werden können und umgekehrt.

 Stellen Sie sicher, dass auch private und interne Datenmember ihre Namen, Typen oder sogar deren Reihenfolge in zukünftigen Versionen des Typs nicht ändern können, es sei denn, Sie müssen den Vertrag mithilfe expliziter Parameter für die Daten Vertrags Attribute beibehalten.

 Testen Sie die Kompatibilität der Serialisierung, wenn Sie Änderungen an serialisierbaren Typen vornehmen. Versuchen Sie eine Deserialisierung der neuen Version in eine alte Version und umgekehrt.

 ✔️ sollten <xref:System.Runtime.Serialization.IExtensibleDataObject> Sie implementieren, um das Roundtrip zwischen verschiedenen Versionen des Typs zuzulassen.

 Über die Schnittstelle kann das Serialisierungsprogramm sicherstellen, dass bei der wiederholten Umwandlung keine Daten verloren gehen. Die <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A?displayProperty=nameWithType> -Eigenschaft wird zum Speichern von Daten aus der zukünftigen Version des Typs verwendet, der in der aktuellen Version unbekannt ist, und kann daher nicht in den Datenmembern gespeichert werden. Wenn die aktuelle Version anschließend serialisiert und in eine zukünftige Version deserialisiert wird, sind die zusätzlichen Daten im serialisierten Stream verfügbar.

## <a name="supporting-xml-serialization"></a>Unterstützen der XML-Serialisierung
 Die Datenvertragsserialisierung ist die wichtigste (standardmäßige) serialisierungstechnologie im .NET Framework, aber es gibt Serialisierungsszenarien, die die Datenvertragsserialisierung nicht unterstützt Beispielsweise kann die Form des vom Serialisierungsprogramm erzeugten bzw. verarbeiteten XML nicht vollständig kontrolliert werden. Wenn eine solche feine Kontrolle erforderlich ist, muss die XML-Serialisierung verwendet werden, und Sie müssen die Typen für die Unterstützung dieser serialisierungstechnologie entwerfen.

 ❌ Vermeiden Sie das Entwerfen von Typen speziell für die XML-Serialisierung, es sei denn, Sie haben einen sehr starken Grund, die Form des erzeugten XML zu steuern. Diese Serialisierungstechnologie wurde durch die im vorherigen Abschnitt behandelte Datenvertragsserialisierung abgelöst.

 ✔️ sollten Sie die Implementierung der- <xref:System.Xml.Serialization.IXmlSerializable> Schnittstelle in Erwägung nehmen, wenn Sie die Form des serialisierten XML-Codes noch besser steuern möchten, als durch Anwenden der XML-Serialisierungsattribute. Die beiden Methoden <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> und <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> der Schnittstelle erlauben eine vollständige Kontrolle des serialisierten XML-Streams. Sie können auch das XML-Schema steuern, das für den Typ generiert wird, indem Sie das Anwenden `XmlSchemaProviderAttribute` .

## <a name="supporting-runtime-serialization"></a>Unterstützen der Laufzeitserialisierung
 Die Laufzeitserialisierung ist eine von .NET-Remoting verwendete Technologie. Wenn Sie der Ansicht sind, dass Ihre Typen mithilfe von .NET-Remoting transportiert werden, müssen Sie sicherstellen, dass Sie die Laufzeitserialisierung unterstützen.

 Die grundlegende Unterstützung für die Laufzeitserialisierung kann durch Anwenden von bereitgestellt werden <xref:System.SerializableAttribute> . Erweiterte Szenarien umfassen die Implementierung eines einfachen laufzeitserialisierbaren Musters (implementieren <xref:System.Runtime.Serialization.ISerializable> und Bereitstellen des Serialisierungskonstruktors).

 ✔️ sollten die Laufzeitserialisierung unterstützen, wenn Ihre Typen mit .NET-Remoting verwendet werden. Beispielsweise verwendet der <xref:System.AddIn?displayProperty=nameWithType> Namespace .NET-Remoting, sodass alle zwischen den Add-ins ausgetauschten Typen die `System.AddIn` Laufzeitserialisierung unterstützen müssen.

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

 ✔️ die Elemente <xref:System.Runtime.Serialization.ISerializable> explizit implementieren.

 ✔️ wenden Sie einen Link Aufruf auf die <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> Implementierung an. Dadurch wird sichergestellt, dass nur vollständig vertrauenswürdige Kerne und das laufzeitserialisierungsprogramm Zugriff auf den Member haben.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Framework-Entwurfs Richtlinien](index.md)
- [Verwendungs Richtlinien](usage-guidelines.md)
