---
title: Serialization1
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bebb27ac-9712-4196-9931-de19fc04dbac
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 14b2f596245eb7f9cdcb9b3e30eeb100180cd793
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="serialization"></a>Serialisierung
Serialisierung ist der Prozess der Konvertierung eines Objekts in ein Format, das unmittelbar persistent gespeichert und transportiert werden kann. Sie können z. B. ein Objekt serialisieren, transportieren, über das Internet mithilfe von HTTP und deserialisiert es auf dem Zielcomputer.  
  
 .NET Framework bietet drei wichtigsten Serialisierungstechnologien für verschiedene Serialisierungsszenarien optimiert. In der folgenden Tabelle werden diese Technologien und die zugehörigen Framework-Haupttypen für die jeweilige Technologie beschrieben.  
  
|**Technologiename**|**Haupttypen**|**Szenarien**|  
|-------------------------|--------------------|-------------------|  
|**Datenvertragsserialisierung**|<xref:System.Runtime.Serialization.DataContractAttribute> <br /> <xref:System.Runtime.Serialization.DataMemberAttribute> <br /> <xref:System.Runtime.Serialization.DataContractSerializer> <br /> <xref:System.Runtime.Serialization.NetDataContractSerializer> <br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <br /> <xref:System.Runtime.Serialization.ISerializable>|Allgemeine Persistenz<br />Webdienste<br />JSON|  
|**XML-Serialisierung**|<xref:System.Xml.Serialization.XmlSerializer>|XML-Format mit vollständiger Kontrolle über die XML-Form|  
|**Common Language Runtime-Serialisierung ("Binary" und "SOAP")**|<xref:System.SerializableAttribute> <br /> <xref:System.Runtime.Serialization.ISerializable> <br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|.NET-Remotezugriff|  
  
 **Führen Sie ✓** Frage Serialisierung, wenn Sie neue Typen entwerfen.  
  
## <a name="choosing-the-right-serialization-technology-to-support"></a>Auswählen einer geeigneten Serialisierungstechnologie, die unterstützt werden soll  
 **✓ GGF.** Datenvertragsserialisierung unterstützen, wenn Instanzen des Typs müssen möglicherweise beibehalten oder in Webdiensten verwendet werden.  
  
 **✓ GGF.** die XML-Serialisierung stattdessen oder zusätzlich Datenvertragsserialisierung unterstützen, wenn Sie mehr Kontrolle über das XML-Format benötigen, die erstellt wird, wenn der Typ serialisiert wird.  
  
 Dies kann in einigen Interoperabilität, die Szenarien, in denen Sie verwendet eine XML-Datei erstellen erforderlich sein, die nicht von Datenvertragsserialisierung, z. B. zum Generieren von XML-Attribute unterstützt wird.  
  
 **✓ GGF.** unterstützen die Serialisierung zur Laufzeit, wenn Instanzen des Typs .NET Remoting hinweg übertragen müssen.  
  
 **X vermeiden** Unterstützung der Serialisierung zur Laufzeit oder XML-Serialisierung nur für die allgemeine Persistenz Gründe. Verwenden Sie stattdessen Datenvertragsserialisierung.  
  
## <a name="supporting-data-contract-serialization"></a>Unterstützen der Datenvertragsserialisierung  
 Typen unterstützen Datenvertragsserialisierung durch Anwenden der <xref:System.Runtime.Serialization.DataContractAttribute> in den Typ und die <xref:System.Runtime.Serialization.DataMemberAttribute> auf die Member des Typs (Felder und Eigenschaften).  
  
 **✓ GGF.** Datenmember eines Ihrer öffentlichen Typs markieren, wenn der Typ in teilweiser Vertrauenswürdigkeit verwendet werden kann.  
  
 Mit voller Vertrauenswürdigkeit Datenvertrag-Serialisierer serialisieren und Deserialisieren nicht öffentliche Typen und Member können, aber nur öffentliche Member serialisiert und in teilweiser Vertrauenswürdigkeit nicht deserialisiert werden können.  
  
 **Führen Sie ✓** implementieren Sie bei allen Eigenschaften, die über einen Getter und Setter <xref:System.Runtime.Serialization.DataMemberAttribute>. Daten Vertrag Serialisierungsprogramme benötigen sowohl der Getter und Setter-Methode für den Typ serialisierbar berücksichtigt werden können. (In .NET Framework 3.5 SP1, können einige Auflistungseigenschaften nur Get-sein.) Wenn der Typ nicht bei teilweiser Vertrauenswürdigkeit verwendet wird, können einer oder beide Eigenschaftenaccessoren nicht öffentlich sein.  
  
 **✓ GGF.** die serialisierungsrückrufe für die Initialisierung der deserialisierte Instanzen verwenden.  
  
 Konstruktoren werden beim Deserialisieren von Objekten nicht aufgerufen. (Es sind Ausnahmen von der Regel. Konstruktoren von Auflistungen mit markiert <xref:System.Runtime.Serialization.CollectionDataContractAttribute> werden während der Deserialisierung aufgerufen.) Daher muss keine Logik, die während der normalen Erstellung ausgeführt wird als eines der serialisierungsrückrufe implementiert werden.  
  
 `OnDeserializedAttribute` ist das am häufigsten verwendeten Rückrufattribut. Weitere Attribute in der Familie sind <xref:System.Runtime.Serialization.OnDeserializingAttribute>, <xref:System.Runtime.Serialization.OnSerializingAttribute> und <xref:System.Runtime.Serialization.OnSerializedAttribute>. Mit ihnen können Rückrufe gekennzeichnet werden, die entsprechend vor der Deserialisierung, vor der Serialisierung oder nach der Serialisierung ausgeführt werden.  
  
 **✓ GGF.** mithilfe der <xref:System.Runtime.Serialization.KnownTypeAttribute> auf konkrete Typen anzugeben, die verwendet werden soll, wenn eine komplexe Objektdiagramm deserialisieren.  
  
 **Führen Sie ✓** rückwärts und Vorwärts-Kompatibilität beim Erstellen oder Ändern von serialisierbaren Typen zu berücksichtigen.  
  
 Beachten Sie, dass serialisierte Streams von zukünftigen Versionen des Typs in die aktuelle Version des Typs deserialisiert werden können und umgekehrt.  
  
 Stellen Sie sicher, dass Sie wissen, dass der Datenmember, sogar private und interne, deren Namen, Typen oder sogar deren Reihenfolge in zukünftigen Versionen des Typs nicht ändern können, wenn darauf geachtet wird, den Vertrag unter Verwendung expliziter Parameter für die datenvertragsattribute beibehalten .  
  
 Testen Sie die Kompatibilität der Serialisierung beim vornehmen von Änderungen auf der serialisierbaren Typen. Versuchen Sie eine Deserialisierung der neuen Version in eine alte Version und umgekehrt.  
  
 **✓ GGF.** implementieren <xref:System.Runtime.Serialization.IExtensibleDataObject> um Roundtrips zwischen verschiedenen Versionen des Typs zu ermöglichen.  
  
 Über die Schnittstelle kann das Serialisierungsprogramm sicherstellen, dass bei der wiederholten Umwandlung keine Daten verloren gehen. Die <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A?displayProperty=nameWithType> Eigenschaft dient zum Speichern von Daten aus einer zukünftigen Version des Typs, die von der aktuellen Version unbekannt ist, und daher es nicht möglich speichern es in seinen Datenmembern. Wenn die aktuelle Version ist anschließend serialisiert und in einer zukünftigen Version deserialisiert, werden die zusätzlichen Daten in einem serialisierten Datenstrom verfügbar sein.  
  
## <a name="supporting-xml-serialization"></a>Unterstützen der XML-Serialisierung  
 Datenvertragsserialisierung ist (Standard) serialisierungstechnologie in .NET Framework, aber es gibt Serialisierungsszenarien,, die Datenvertragsserialisierung nicht unterstützt. Beispielsweise kann die Form des vom Serialisierungsprogramm erzeugten bzw. verarbeiteten XML nicht vollständig kontrolliert werden. Wenn solche genaue Steuerung erforderlich ist, XML-Serialisierung besitzt, die verwendet werden, und Sie müssen zum Entwerfen Ihrer Typen zur Unterstützung dieser serialisierungstechnologie zu verwenden.  
  
 **X vermeiden** speziell für die XML-Serialisierung, Ihre Typen entwerfen, es sei denn, stehen Ihnen einen sehr starken Grund zum Steuern der Form des XML erzeugt. Diese Serialisierungstechnologie wurde durch die im vorherigen Abschnitt behandelte Datenvertragsserialisierung abgelöst.  
  
 **✓ GGF.** implementieren die <xref:System.Xml.Serialization.IXmlSerializable> Schnittstelle, wenn Sie möchten noch mehr Kontrolle über die Form des serialisierten XML als was durch Anwenden der XML-Serialisierungsattribute angeboten wird. Zwei Methoden der Schnittstelle <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> und <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>, können Sie den serialisierten XML-Stream vollständig zu steuern. Sie können auch steuern, das XML-Schema, die für den Typ wird durch Anwenden generiert der `XmlSchemaProviderAttribute`.  
  
## <a name="supporting-runtime-serialization"></a>Unterstützen der Laufzeitserialisierung  
 Common Language Runtime-Serialisierung ist eine Technologie, die von .NET Remoting verwendet. Wenn Sie, dass die Typen mit .NET-Remoting transportiert werden glauben, müssen Sie sicherstellen, dass sie die Common Language Runtime-Serialisierung unterstützen.  
  
 Die grundlegende Unterstützung für die Serialisierung der Common Language Runtime kann bereitgestellt werden, durch Anwenden der <xref:System.SerializableAttribute>, und komplexere Szenarien umfassen das Implementieren einer einfachen serialisierbar Common Language Runtime-Musters (implementieren <xref:System.Runtime.Serialization.ISerializable> und Bereitstellen des Serialisierungskonstruktors).  
  
 **✓ GGF.** Serialisierung zur Laufzeit unterstützen, wenn die Typen mit .NET Remoting verwendet werden. Z. B. die <xref:System.AddIn?displayProperty=nameWithType> Namespace verwendet .NET Remoting und daher sind alle Typen ausgetauscht werden, zwischen `System.AddIn` -add-ins Serialisierung zur Laufzeit unterstützt werden müssen.  
  
 **✓ GGF.** der serialisierbaren Common Language Runtime-Muster implementieren, wenn Sie vollständige Kontrolle über den Serialisierungsprozess möchten. Dies wäre z. B. der Fall, wenn Daten bei der Serialisierung oder Deserialisierung umgewandelt werden sollen.  
  
 Das Muster ist sehr einfach. Sie müssen lediglich die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle implementieren und einen speziellen Konstruktor bereitstellen, der beim Deserialisieren des Objekts verwendet wird.  
  
 **Führen Sie ✓** stellen den Serialisierungskonstruktor geschützt, und geben Sie zwei Parameter eingegeben und mit dem Namen genau wie im Beispiel hier dargestellt.  
  
```  
[Serializable]  
public class Person : ISerializable {  
    protected Person(SerializationInfo info, StreamingContext context) {  
        ...  
    }  
}  
```  
  
 **Führen Sie ✓** implementieren die `ISerializable` Member explizit.  
  
 **Führen Sie ✓** übernehmen einen Linkaufruf, <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> Implementierung. Dadurch wird sichergestellt, dass die Kern- und die Common Language Runtime-Serialisierungsprogramm haben Zugriff auf das Element nur vollständig vertrauenswürdige.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)
