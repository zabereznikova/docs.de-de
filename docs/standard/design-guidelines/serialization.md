---
title: Serialization
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: bebb27ac-9712-4196-9931-de19fc04dbac
ms.openlocfilehash: fb5d714e2452f1b9c1dcc79cc179b35a2dd48fec
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709074"
---
# <a name="serialization"></a>Serialization
Serialisierung ist der Prozess, bei dem ein Objekt in ein Format umgewandelt wird, das leicht persistent gespeichert oder transportiert werden kann. Beispielsweise können Sie ein Objekt serialisieren, über das Internet mithilfe von http transportieren und auf dem Zielcomputer deserialisieren.  
  
 Der .NET Framework bietet drei wichtige Serialisierungstechnologien, die für verschiedene Serialisierungsszenarien optimiert sind. In der folgenden Tabelle werden diese Technologien und die zugehörigen Framework-Haupttypen für die jeweilige Technologie beschrieben.  
  
|**Technologie Name**|**Haupttypen**|**Szenarien**|  
|-------------------------|--------------------|-------------------|  
|**Datenvertragsserialisierung**|<xref:System.Runtime.Serialization.DataContractAttribute> <br /> <xref:System.Runtime.Serialization.DataMemberAttribute> <br /> <xref:System.Runtime.Serialization.DataContractSerializer> <br /> <xref:System.Runtime.Serialization.NetDataContractSerializer> <br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <br /> <xref:System.Runtime.Serialization.ISerializable>|Allgemeine Persistenz<br />Webdienste<br />JSON|  
|**XML-Serialisierung**|<xref:System.Xml.Serialization.XmlSerializer>|XML-Format mit vollständiger Kontrolle über die Form des XML-Codes|  
|**Laufzeitserialisierung (Binary und SOAP)**|<xref:System.SerializableAttribute> <br /> <xref:System.Runtime.Serialization.ISerializable> <br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|.NET-Remotezugriff|  
  
 **✓ DO** Frage Serialisierung, wenn Sie neue Typen entwerfen.  
  
## <a name="choosing-the-right-serialization-technology-to-support"></a>Auswählen einer geeigneten Serialisierungstechnologie, die unterstützt werden soll  
 **✓ CONSIDER** Datenvertragsserialisierung unterstützen, wenn Instanzen des Typs müssen möglicherweise beibehalten oder in Webdiensten verwendet werden.  
  
 **✓ CONSIDER** die XML-Serialisierung stattdessen oder zusätzlich Datenvertragsserialisierung unterstützen, wenn Sie mehr Kontrolle über das XML-Format benötigen, die erstellt wird, wenn der Typ serialisiert wird.  
  
 Dies kann in einigen Interoperabilitäts Szenarien notwendig sein, bei denen Sie ein XML-Konstrukt verwenden müssen, das von der Datenvertragsserialisierung nicht unterstützt wird, z. b. um XML-Attribute zu erzeugen  
  
 **✓ CONSIDER** unterstützen die Serialisierung zur Laufzeit, wenn Instanzen des Typs .NET Remoting hinweg übertragen müssen.  
  
 **X AVOID** Unterstützung der Serialisierung zur Laufzeit oder XML-Serialisierung nur für die allgemeine Persistenz Gründe. Bevorzugen Sie stattdessen die Datenvertragsserialisierung.  
  
## <a name="supporting-data-contract-serialization"></a>Unterstützen der Datenvertragsserialisierung  
 Typen können die Datenvertragsserialisierung unterstützen, indem Sie die <xref:System.Runtime.Serialization.DataContractAttribute> auf den Typ anwenden und die <xref:System.Runtime.Serialization.DataMemberAttribute> auf die Member (Felder und Eigenschaften) des Typs anwenden.  
  
 **✓ CONSIDER** Datenmember eines Ihrer öffentlichen Typs markieren, wenn der Typ in teilweiser Vertrauenswürdigkeit verwendet werden kann.  
  
 Bei voller Vertrauenswürdigkeit können Datenvertragsserialisierer nicht öffentliche Typen und Member serialisieren und deserialisieren. in teilweiser Vertrauenswürdigkeit können jedoch nur öffentliche Member serialisiert und deserialisiert werden.  
  
 **✓ DO** implementieren Sie bei allen Eigenschaften, die über einen Getter und Setter <xref:System.Runtime.Serialization.DataMemberAttribute>. Datenvertragsserialisierer erfordern, dass sowohl der Getter als auch der Setter für den Typ als serialisierbar eingestuft werden. (In .NET Framework 3,5 SP1 können einige Sammlungs Eigenschaften nur "Get-only" sein.) Wenn der Typ bei teilweiser Vertrauenswürdigkeit nicht verwendet wird, kann einer oder beide der Eigenschaftenaccessoren nicht öffentlich sein.  
  
 **✓ CONSIDER** die serialisierungsrückrufe für die Initialisierung der deserialisierte Instanzen verwenden.  
  
 Konstruktoren werden beim Deserialisieren von Objekten nicht aufgerufen. (Es gibt Ausnahmen für die Regel. Konstruktoren von Auflistungen, die mit <xref:System.Runtime.Serialization.CollectionDataContractAttribute> gekennzeichnet sind, werden während der Deserialisierung aufgerufen.) Daher muss jede Logik, die während der normalen Erstellung ausgeführt wird, als eine der Serialisierungsrückrufe implementiert werden.  
  
 `OnDeserializedAttribute` ist das am häufigsten verwendete Rückruf Attribut. Weitere Attribute in der Familie sind <xref:System.Runtime.Serialization.OnDeserializingAttribute>, <xref:System.Runtime.Serialization.OnSerializingAttribute> und <xref:System.Runtime.Serialization.OnSerializedAttribute>. Mit ihnen können Rückrufe gekennzeichnet werden, die entsprechend vor der Deserialisierung, vor der Serialisierung oder nach der Serialisierung ausgeführt werden.  
  
 **✓ CONSIDER** mithilfe der <xref:System.Runtime.Serialization.KnownTypeAttribute> auf konkrete Typen anzugeben, die verwendet werden soll, wenn eine komplexe Objektdiagramm deserialisieren.  
  
 **✓ DO** rückwärts und Vorwärts-Kompatibilität beim Erstellen oder Ändern von serialisierbaren Typen zu berücksichtigen.  
  
 Beachten Sie, dass serialisierte Streams von zukünftigen Versionen des Typs in die aktuelle Version des Typs deserialisiert werden können und umgekehrt.  
  
 Stellen Sie sicher, dass auch private und interne Datenmember ihre Namen, Typen oder sogar deren Reihenfolge in zukünftigen Versionen des Typs nicht ändern können, es sei denn, es muss besonders sorgfältig vorgegangen werden, um den Vertrag mithilfe expliziter Parameter für die Daten Vertrags Attribute beizubehalten. .  
  
 Testen Sie die Kompatibilität der Serialisierung, wenn Sie Änderungen an serialisierbaren Typen vornehmen. Versuchen Sie eine Deserialisierung der neuen Version in eine alte Version und umgekehrt.  
  
 **✓ CONSIDER** implementieren <xref:System.Runtime.Serialization.IExtensibleDataObject> um Roundtrips zwischen verschiedenen Versionen des Typs zu ermöglichen.  
  
 Über die Schnittstelle kann das Serialisierungsprogramm sicherstellen, dass bei der wiederholten Umwandlung keine Daten verloren gehen. Die <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A?displayProperty=nameWithType>-Eigenschaft wird zum Speichern von Daten aus der zukünftigen Version des Typs verwendet, der in der aktuellen Version unbekannt ist, und kann daher nicht in ihren Datenmembern gespeichert werden. Wenn die aktuelle Version anschließend serialisiert und in eine zukünftige Version deserialisiert wird, sind die zusätzlichen Daten im serialisierten Stream verfügbar.  
  
## <a name="supporting-xml-serialization"></a>Unterstützen der XML-Serialisierung  
 Die Datenvertragsserialisierung ist die wichtigste (standardmäßige) serialisierungstechnologie im .NET Framework, aber es gibt Serialisierungsszenarien, die die Datenvertragsserialisierung nicht unterstützt Beispielsweise kann die Form des vom Serialisierungsprogramm erzeugten bzw. verarbeiteten XML nicht vollständig kontrolliert werden. Wenn eine solche feine Kontrolle erforderlich ist, muss die XML-Serialisierung verwendet werden, und Sie müssen die Typen für die Unterstützung dieser serialisierungstechnologie entwerfen.  
  
 **X AVOID** speziell für die XML-Serialisierung, Ihre Typen entwerfen, es sei denn, stehen Ihnen einen sehr starken Grund zum Steuern der Form des XML erzeugt. Diese Serialisierungstechnologie wurde durch die im vorherigen Abschnitt behandelte Datenvertragsserialisierung abgelöst.  
  
 **✓ CONSIDER** implementieren die <xref:System.Xml.Serialization.IXmlSerializable> Schnittstelle, wenn Sie möchten noch mehr Kontrolle über die Form des serialisierten XML als was durch Anwenden der XML-Serialisierungsattribute angeboten wird. Mit zwei Methoden der-Schnittstelle, <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> und <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>, können Sie den serialisierten XML-Stream vollständig steuern. Sie können auch das XML-Schema steuern, das für den Typ generiert wird, indem Sie die `XmlSchemaProviderAttribute`anwenden.  
  
## <a name="supporting-runtime-serialization"></a>Unterstützen der Laufzeitserialisierung  
 Die Laufzeitserialisierung ist eine von .NET-Remoting verwendete Technologie. Wenn Sie der Ansicht sind, dass Ihre Typen mithilfe von .NET-Remoting transportiert werden, müssen Sie sicherstellen, dass Sie die Laufzeitserialisierung unterstützen.  
  
 Die grundlegende Unterstützung für die Laufzeitserialisierung kann durch Anwenden der <xref:System.SerializableAttribute>bereitgestellt werden. komplexere Szenarien umfassen die Implementierung eines einfachen laufzeitserialisierungsmusters (Implementieren von <xref:System.Runtime.Serialization.ISerializable> und Bereitstellen eines Serialisierungskonstruktors).  
  
 **✓ CONSIDER** Serialisierung zur Laufzeit unterstützen, wenn die Typen mit .NET Remoting verwendet werden. Beispielsweise verwendet der <xref:System.AddIn?displayProperty=nameWithType>-Namespace .NET-Remoting, sodass alle zwischen `System.AddIn`-Add-ins ausgetauschten Typen die Laufzeitserialisierung unterstützen müssen.  
  
 **✓ CONSIDER** der serialisierbaren Common Language Runtime-Muster implementieren, wenn Sie vollständige Kontrolle über den Serialisierungsprozess möchten. Dies wäre z. B. der Fall, wenn Daten bei der Serialisierung oder Deserialisierung umgewandelt werden sollen.  
  
 Das Muster ist sehr einfach. Sie müssen lediglich die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle implementieren und einen speziellen Konstruktor bereitstellen, der beim Deserialisieren des Objekts verwendet wird.  
  
 **✓ DO** stellen den Serialisierungskonstruktor geschützt, und geben Sie zwei Parameter eingegeben und mit dem Namen genau wie im Beispiel hier dargestellt.  
  
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
  
 **✓ DO** implementieren die <xref:System.Runtime.Serialization.ISerializable> Member explizit.  
  
 **✓ DO** übernehmen einen Linkaufruf, <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> Implementierung. Dadurch wird sichergestellt, dass nur vollständig vertrauenswürdige Kerne und das laufzeitserialisierungsprogramm Zugriff auf den Member haben.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)
