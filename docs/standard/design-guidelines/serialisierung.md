---
title: "Serialization1 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: bebb27ac-9712-4196-9931-de19fc04dbac
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
---
# Serialisierung
Serialisierung ist der Prozess der Konvertierung eines Objekts in einem Format, die leicht erhalten oder transportiert werden kann. Sie können z. B. ein Objekt serialisieren, transport über das Internet mithilfe von HTTP und deserialisiert es auf dem Zielcomputer.  
  
 .NET Framework bietet drei wichtige Serialisierungstechnologien, die für verschiedene Serialisierungsszenarien optimiert. In der folgenden Tabelle werden diese Technologien und die wichtigsten Framework\-Typen, die im Zusammenhang mit diesen Technologien.  
  
|**Technologiename**|**Haupttypen**|**Szenarien**|  
|-------------------------|--------------------|-------------------|  
|**Datenvertragsserialisierung**|<xref:System.Runtime.Serialization.DataContractAttribute> <br /> <xref:System.Runtime.Serialization.DataMemberAttribute> <br /> <xref:System.Runtime.Serialization.DataContractSerializer> <br /> <xref:System.Runtime.Serialization.NetDataContractSerializer> <br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <br /> <xref:System.Runtime.Serialization.ISerializable>|Allgemeine Persistenz<br />Webdienste<br />JSON|  
|**XML\-Serialisierung**|<xref:System.Xml.Serialization.XmlSerializer>|XML\-Format mit vollständiger Kontrolle über die XML\-Form|  
|**Laufzeitserialisierung \(binär und SOAP\)**|<xref:System.SerializableAttribute> <br /> <xref:System.Runtime.Serialization.ISerializable> <br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|.NET\-Remotezugriff|  
  
 **✓ führen** Denken Sie Serialisierung, wenn Sie neue Typen zu entwerfen.  
  
## Auswählen der geeigneten Serialisierungstechnologie, Unterstützung  
 **✓ ggf.** Datenvertragsserialisierung unterstützen, wenn Instanzen des Typs müssen möglicherweise in Webdiensten verwendet oder beibehalten werden.  
  
 **✓ ggf.** die XML\-Serialisierung anstelle von oder zusätzlich zur Datenvertragsserialisierung unterstützen, sollten Sie mehr Kontrolle über das XML\-Format, das erzeugt wird, wenn der Typ serialisiert wird.  
  
 Dies kann in einigen Szenarien Sie in XML müssen erstellen Interoperabilitätsprobleme erforderlich sein, die nicht von Datenvertragsserialisierung, z. B. unterstützt um XML\-Attribute zu erzeugen.  
  
 **✓ ggf.** unterstützen der Laufzeitserialisierung, wenn Instanzen des Typs über .NET Remoting Grenzen übertragen müssen.  
  
 **X vermeiden** Laufzeitserialisierung oder XML\-Serialisierung nur zum allgemeinen persistenzgründen unterstützen. Lieber Datenvertragsserialisierung.  
  
## Unterstützende Datenvertragsserialisierung  
 Typen unterstützen Datenvertragsserialisierung durch Anwenden der <xref:System.Runtime.Serialization.DataContractAttribute> auf den Typ und die <xref:System.Runtime.Serialization.DataMemberAttribute> auf die Member des Typs \(Felder und Eigenschaften\).  
  
 **✓ ggf.** Datenmember Ihre öffentlichen Typ markieren, wenn der Typ bei teilweiser Vertrauenswürdigkeit verwendet werden kann.  
  
 Mit voller Vertrauenswürdigkeit Datenvertrag\-Serialisierer können serialisieren und Deserialisieren von nicht öffentliche Typen und Member, aber nur öffentliche Member serialisiert und in teilweiser Vertrauenswürdigkeit deserialisiert werden können.  
  
 **✓ führen** implementieren Sie einen Getter und Setter für alle Eigenschaften mit <xref:System.Runtime.Serialization.DataMemberAttribute>. Datenvertragsserialisierungsprogramme verlangen sowohl der Getter und Setter\-Methode für den Typ als serialisierbar betrachtet wird. \(In .NET Framework 3.5 SP1, können einige Auflistungseigenschaften nur sein.\) Wenn der Typ bei teilweiser Vertrauenswürdigkeit verwendet wird, können eine oder beide Eigenschaftenaccessoren nicht öffentlich sein.  
  
 **✓ ggf.** Verwendung von serialisierungsrückrufen für die Initialisierung deserialisierter Instanzen.  
  
 Konstruktoren werden beim Deserialisieren von Objekten nicht aufgerufen. \(Es gibt Ausnahmen von der Regel. Konstruktoren von Sammlungen mit markiert <xref:System.Runtime.Serialization.CollectionDataContractAttribute> werden während der Deserialisierung aufgerufen.\) Daher muss jede Logik, die während der normalen Erstellung ausgeführt wird als eines der serialisierungsrückrufe implementiert werden.  
  
 `OnDeserializedAttribute` ist das am häufigsten verwendete Rückrufattribut. Die anderen Attribute in der Familie sind <xref:System.Runtime.Serialization.OnDeserializingAttribute>,  <xref:System.Runtime.Serialization.OnSerializingAttribute>, und <xref:System.Runtime.Serialization.OnSerializedAttribute>. Sie können verwendet werden, um Rückrufe zu markieren, die vor der Deserialisierung, vor der Serialisierung und schließlich nach der Serialisierung bzw. ausgeführt werden.  
  
 **✓ ggf.** mithilfe der <xref:System.Runtime.Serialization.KnownTypeAttribute> um konkrete Typen anzugeben, die beim Deserialisieren eines komplexen Objektdiagramms verwendet werden soll.  
  
 **✓ führen** rückwärts und Vorwärts\-Kompatibilität beim Erstellen oder Ändern von serialisierbaren Typen zu berücksichtigen.  
  
 Denken Sie daran, die Streams von zukünftigen Versionen des Typs serialisiert, die in die aktuelle Version des Typs deserialisiert werden kann und umgekehrt.  
  
 Stellen Sie sicher, dass Sie verstehen, dass Datenmember, auch private und interne, deren Namen, Typen oder die Reihenfolge in zukünftigen Versionen des Typs ändern können, es sei denn, Sie besonders darauf geachtet, den Vertrag, indem explizite Parameter für den datenvertragsattributen beizubehalten.  
  
 Testen Sie die Kompatibilität der Serialisierung, wenn Änderungen an den serialisierbaren Typen. Versuchen Sie, Deserialisieren die neue Version in eine alte Version und umgekehrt.  
  
 **✓ ggf.** implementieren <xref:System.Runtime.Serialization.IExtensibleDataObject> um Roundtrips zwischen verschiedenen Versionen des Typs zu ermöglichen.  
  
 Die Schnittstelle kann das Serialisierungsprogramm sicherstellen, dass bei der wiederholten Umwandlung keine Daten verloren gegangen sind. Die <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A?displayProperty=fullName> Eigenschaft wird zum Speichern von Daten aus der zukünftigen Version des Typs, der in der aktuellen Version unbekannt ist, und daher es nicht speichern es in seinen Datenmembern. Wenn die aktuelle Version anschließend serialisiert und in einer zukünftigen Version deserialisiert wird, werden die zusätzlichen Daten im serialisierten Stream verfügbar sein.  
  
## Die XML\-Serialisierung unterstützen  
 Datenvertragsserialisierung ist \(Standard\) serialisierungstechnologie in .NET Framework, aber es gibt Serialisierungsszenarien, die Datenvertragsserialisierung nicht unterstützt. Beispielsweise ist es Ihnen nicht die vollständige Kontrolle über die Form des XML erzeugt oder verbraucht wurde vom Serialisierungsprogramm. Wenn eine präzise Kontrolle erforderlich ist, muss die XML\-Serialisierung verwendet werden, und Sie müssen die Typen zur Unterstützung dieser serialisierungstechnologie zu entwerfen.  
  
 **X vermeiden** Entwerfen von Typen speziell für die XML\-Serialisierung, sofern es einen sehr starken Grund zur Steuerung der XML\-Form erstellt. Diese serialisierungstechnologie wurde durch den im vorherigen Abschnitt behandelte Datenvertragsserialisierung abgelöst.  
  
 **✓ ggf.** implementieren die <xref:System.Xml.Serialization.IXmlSerializable> Schnittstelle, wenn Sie noch mehr Kontrolle über die Form des serialisierten XML als was angeboten wird, indem die XML\-Serialisierungsattribute angewendet werden soll. Zwei Methoden der Schnittstelle, <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> und <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>, können Sie den serialisierten XML\-Stream vollständig steuern. Sie können auch steuern, das XML\-Schema, die für den Typ wird durch Anwenden generiert der `XmlSchemaProviderAttribute`.  
  
## Unterstützung der Laufzeitserialisierung  
 Laufzeitserialisierung ist eine Technologie von .NET Remoting verwendet. Wenn Sie, dass die Typen mithilfe von .NET Remoting transportiert werden glauben, müssen Sie sicherstellen, dass die Laufzeitserialisierung unterstützen.  
  
 Die grundlegende Unterstützung für die Serialisierung zur Laufzeit kann angegeben werden, durch Anwenden der <xref:System.SerializableAttribute>, und komplexere Szenarien umfassen die Implementierung einer einfachen Laufzeitserialisierungsmusters \(implementieren <xref:System.Runtime.Serialization.ISerializable> und Serialisierungskonstruktor bereitstellen\).  
  
 **✓ ggf.** Laufzeitserialisierung unterstützen, wenn Ihre Typen mit .NET Remoting verwendet werden. Zum Beispiel die <xref:System.AddIn?displayProperty=fullName> Namespace verwendet .NET Remoting und alle Typen ausgetauschten `System.AddIn` \-add\-ins Laufzeitserialisierung unterstützen müssen.  
  
 **✓ ggf.** der Laufzeitserialisierungsmusters implementieren, wenn Sie vollständige Kontrolle über den Serialisierungsprozess möchten. Wenn Sie Daten als transformieren möchten ruft es z. B. serialisiert oder deserialisiert.  
  
 Das Muster ist sehr einfach. Sie müssen lediglich zu implementieren ist die <xref:System.Runtime.Serialization.ISerializable> Schnittstelle, und geben Sie einen speziellen Konstruktor, der verwendet wird, wenn das Objekt deserialisiert wird.  
  
 **✓ führen** stellen den Serialisierungskonstruktor geschützt, und geben Sie zwei Parameter typisiert und mit dem Namen genau wie im Beispiel hier dargestellt.  
  
```  
[Serializable]  
public class Person : ISerializable {  
    protected Person(SerializationInfo info, StreamingContext context) {  
        ...  
    }  
}  
```  
  
 **✓ führen** Implementieren der `ISerializable` Member explizit.  
  
 **✓ führen** übernehmen einen Linkaufruf auf <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> Implementierung. Dadurch wird sichergestellt, dass, der nur voll vertrauenswürdiger Core und das Laufzeitserialisierungsprogramm Zugriff auf den Member haben.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)