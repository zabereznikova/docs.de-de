---
title: Serialization1
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: bebb27ac-9712-4196-9931-de19fc04dbac
author: KrzysztofCwalina
ms.openlocfilehash: f0ef8ab378fb3898f2d2e134f0b38668f6794ef3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650153"
---
# <a name="serialization"></a>Serialisierung
Serialisierung ist der Prozess der Konvertierung eines Objekts in ein Format, das sofort erhalten oder transportiert werden kann. Sie können z. B. ein Objekt serialisieren, über das Internet mithilfe von HTTP und deserialisiert, es auf dem Zielcomputer transportieren.  
  
 .NET Framework bietet drei wichtige Serialisierungstechnologien, die für verschiedene serialisierungsszenarios optimiert. In der folgenden Tabelle werden diese Technologien und die zugehörigen Framework-Haupttypen für die jeweilige Technologie beschrieben.  
  
|**Technology Name**|**Haupttypen**|**Szenarien**|  
|-------------------------|--------------------|-------------------|  
|**Datenvertragsserialisierung**|<xref:System.Runtime.Serialization.DataContractAttribute> <br /> <xref:System.Runtime.Serialization.DataMemberAttribute> <br /> <xref:System.Runtime.Serialization.DataContractSerializer> <br /> <xref:System.Runtime.Serialization.NetDataContractSerializer> <br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <br /> <xref:System.Runtime.Serialization.ISerializable>|Allgemeine Persistenz<br />Webdienste<br />JSON|  
|**XML-Serialisierung**|<xref:System.Xml.Serialization.XmlSerializer>|XML-Format mit vollständiger Kontrolle über die XML-Form|  
|**Laufzeitserialisierung (binär und SOAP)**|<xref:System.SerializableAttribute> <br /> <xref:System.Runtime.Serialization.ISerializable> <br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|.NET-Remotezugriff|  
  
 **✓ DO** Frage Serialisierung, wenn Sie neue Typen entwerfen.  
  
## <a name="choosing-the-right-serialization-technology-to-support"></a>Auswählen einer geeigneten Serialisierungstechnologie, die unterstützt werden soll  
 **✓ CONSIDER** Datenvertragsserialisierung unterstützen, wenn Instanzen des Typs müssen möglicherweise beibehalten oder in Webdiensten verwendet werden.  
  
 **✓ CONSIDER** die XML-Serialisierung stattdessen oder zusätzlich Datenvertragsserialisierung unterstützen, wenn Sie mehr Kontrolle über das XML-Format benötigen, die erstellt wird, wenn der Typ serialisiert wird.  
  
 Dies kann in einigen Interoperabilität, Erstellen von Szenarios Sie in XML müssen, erforderlich sein, die nicht von der Datenvertragsserialisierung, z. B. unterstützt wird um XML-Attribute zu erzeugen.  
  
 **✓ CONSIDER** unterstützen die Serialisierung zur Laufzeit, wenn Instanzen des Typs .NET Remoting hinweg übertragen müssen.  
  
 **X AVOID** Unterstützung der Serialisierung zur Laufzeit oder XML-Serialisierung nur für die allgemeine Persistenz Gründe. Bevorzugen Sie stattdessen Datenvertragsserialisierung.  
  
## <a name="supporting-data-contract-serialization"></a>Unterstützen der Datenvertragsserialisierung  
 Typen unterstützen der Datenvertragsserialisierung durch Anwenden der <xref:System.Runtime.Serialization.DataContractAttribute> in den Typ und die <xref:System.Runtime.Serialization.DataMemberAttribute> auf die Member (Felder und Eigenschaften) des Typs.  
  
 **✓ CONSIDER** Datenmember eines Ihrer öffentlichen Typs markieren, wenn der Typ in teilweiser Vertrauenswürdigkeit verwendet werden kann.  
  
 Mit voller Vertrauenswürdigkeit Datenvertrag-Serialisierer können serialisieren und Deserialisieren von nicht öffentliche Typen und Member, aber nur öffentliche Member serialisiert und bei teilweiser Vertrauenswürdigkeit nicht deserialisiert werden können.  
  
 **✓ DO** implementieren Sie bei allen Eigenschaften, die über einen Getter und Setter <xref:System.Runtime.Serialization.DataMemberAttribute>. Datenvertragsserialisierungsprogramme verlangen sowohl einen Getter als auch der Setter für den Typ als serialisierbar betrachtet wird. (In .NET Framework 3.5 SP1, können einige Auflistungseigenschaften nur sein.) Wenn der Typ nicht bei teilweiser Vertrauenswürdigkeit verwendet wird, können einer oder beide Eigenschaftenaccessoren nicht öffentlich sein.  
  
 **✓ CONSIDER** die serialisierungsrückrufe für die Initialisierung der deserialisierte Instanzen verwenden.  
  
 Konstruktoren werden beim Deserialisieren von Objekten nicht aufgerufen. (Es gibt Ausnahmen, die für die Regel. Konstruktoren von Sammlungen mit markiert <xref:System.Runtime.Serialization.CollectionDataContractAttribute> während der Deserialisierung aufgerufen werden.) Aus diesem Grund muss jede Logik, die während der normalen Erstellung ausgeführt wird als eines der serialisierungsrückrufe implementiert werden.  
  
 `OnDeserializedAttribute` ist die am häufigsten verwendete Rückrufattribut. Weitere Attribute in der Familie sind <xref:System.Runtime.Serialization.OnDeserializingAttribute>, <xref:System.Runtime.Serialization.OnSerializingAttribute> und <xref:System.Runtime.Serialization.OnSerializedAttribute>. Mit ihnen können Rückrufe gekennzeichnet werden, die entsprechend vor der Deserialisierung, vor der Serialisierung oder nach der Serialisierung ausgeführt werden.  
  
 **✓ CONSIDER** mithilfe der <xref:System.Runtime.Serialization.KnownTypeAttribute> auf konkrete Typen anzugeben, die verwendet werden soll, wenn eine komplexe Objektdiagramm deserialisieren.  
  
 **✓ DO** rückwärts und Vorwärts-Kompatibilität beim Erstellen oder Ändern von serialisierbaren Typen zu berücksichtigen.  
  
 Beachten Sie, dass serialisierte Streams von zukünftigen Versionen des Typs in die aktuelle Version des Typs deserialisiert werden können und umgekehrt.  
  
 Stellen Sie sicher, dass Sie verstehen, dass Datenmember, auch private und interne, ihren Namen, Typen oder die Reihenfolge in zukünftigen Versionen des Typs ändern können, es sei denn, Sie besonders darauf geachtet, den Vertrag, indem explizite Parameter für die datenvertragsattribute beizubehalten. .  
  
 Testen Sie die Kompatibilität der Serialisierung, wenn Sie Änderungen an den serialisierbaren Typen vornehmen. Versuchen Sie eine Deserialisierung der neuen Version in eine alte Version und umgekehrt.  
  
 **✓ CONSIDER** implementieren <xref:System.Runtime.Serialization.IExtensibleDataObject> um Roundtrips zwischen verschiedenen Versionen des Typs zu ermöglichen.  
  
 Über die Schnittstelle kann das Serialisierungsprogramm sicherstellen, dass bei der wiederholten Umwandlung keine Daten verloren gehen. Die <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A?displayProperty=nameWithType> Eigenschaft wird verwendet, um alle Daten aus der zukünftigen Version des Typs zu speichern, die in der aktuellen Version unbekannt ist, und daher kann nicht speichern es in seinen Datenmembern. Wenn die aktuelle Version anschließend serialisiert und in eine zukünftige Version deserialisiert wird, werden die zusätzlichen Daten im serialisierten Stream verfügbar sein.  
  
## <a name="supporting-xml-serialization"></a>Unterstützen der XML-Serialisierung  
 Datenvertragsserialisierung ist die primäre (Standard) serialisierungstechnologie in .NET Framework, aber es gibt Serialisierungsszenarien,, die von der Datenvertragsserialisierung nicht unterstützt. Beispielsweise kann die Form des vom Serialisierungsprogramm erzeugten bzw. verarbeiteten XML nicht vollständig kontrolliert werden. Wenn eine präzise Kontrolle erforderlich ist, muss die XML-Serialisierung verwendet werden, und Entwurf die Typen zur Unterstützung dieser serialisierungstechnologie werden müssen.  
  
 **X AVOID** speziell für die XML-Serialisierung, Ihre Typen entwerfen, es sei denn, stehen Ihnen einen sehr starken Grund zum Steuern der Form des XML erzeugt. Diese Serialisierungstechnologie wurde durch die im vorherigen Abschnitt behandelte Datenvertragsserialisierung abgelöst.  
  
 **✓ CONSIDER** implementieren die <xref:System.Xml.Serialization.IXmlSerializable> Schnittstelle, wenn Sie möchten noch mehr Kontrolle über die Form des serialisierten XML als was durch Anwenden der XML-Serialisierungsattribute angeboten wird. Zwei Methoden der Schnittstelle <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> und <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>, können Sie den serialisierten XML-Stream vollständig zu steuern. Sie können auch steuern, das XML-Schema, das für den Typ, durch Anwenden generiert wird der `XmlSchemaProviderAttribute`.  
  
## <a name="supporting-runtime-serialization"></a>Unterstützen der Laufzeitserialisierung  
 Laufzeitserialisierung ist eine von .NET-Remotezugriff verwendete Technologie. Wenn Sie, dass die Typen mit .NET Remoting übertragen werden glauben, müssen Sie sicherstellen, dass die Laufzeitserialisierung unterstützen.  
  
 Die grundlegende Unterstützung für die Serialisierung zur Laufzeit kann bereitgestellt werden, durch Anwenden der <xref:System.SerializableAttribute>, und komplexere Szenarien umfassen die Implementierung einer einfachen Laufzeitserialisierungsmusters (implementieren <xref:System.Runtime.Serialization.ISerializable> und Bereitstellen Serialisierungskonstruktors).  
  
 **✓ CONSIDER** Serialisierung zur Laufzeit unterstützen, wenn die Typen mit .NET Remoting verwendet werden. Z. B. die <xref:System.AddIn?displayProperty=nameWithType> Namespace verwendet, und alle Typen ausgetauscht werden, zwischen `System.AddIn` -add-ins Laufzeitserialisierung unterstützen müssen.  
  
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
  
 **✓ DO** übernehmen einen Linkaufruf, <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> Implementierung. Dadurch wird sichergestellt, dass ausschließlich vollständig vertrauenswürdige, dass Core und das Laufzeitserialisierungsprogramm Zugriff auf den Member haben.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)
