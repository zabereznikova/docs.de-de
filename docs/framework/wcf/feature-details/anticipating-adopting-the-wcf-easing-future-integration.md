---
title: 'Vorbereitungen für Windows Communication Foundation: einfachere Migration in der Zukunft'
ms.date: 03/30/2017
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
ms.openlocfilehash: ead28354a3687bcca22a1a0eb5ccc9f15f0c69d2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266570"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a>Vorbereitungen für Windows Communication Foundation: einfachere Migration in der Zukunft

Wenn Sie heute ASP.NET verwenden und die Verwendung von WCF in Zukunft erwarten, bietet dieses Thema Anleitungen, um sicherzustellen, dass neue ASP.NET-Webdienste gemeinsam mit WCF-Anwendungen funktionieren.  
  
## <a name="general-recommendations"></a>Allgemeine Empfehlungen  

 Übernehmen Sie ASP.NET 2.0 auch für neue Dienste. Dadurch stellen Sie den Zugriff auf die Verbesserungen und Erweiterungen der neuen Version bereit. Allerdings ist es auch möglich, ASP.NET 2,0-Komponenten mit WCF-Komponenten in derselben Anwendung zu verwenden.  
  
## <a name="protocols"></a>Protokolle  

 Verwenden Sie die neue Funktion von ASP.NET 2.0 zum Überprüfen der Konformität mit WS-I Basic Profile 1.1:  
  
```csharp  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 ASP.NET-Webdienste, die dem WS-I Basic Profile 1,1 entsprechen, können mit WCF-Clients mithilfe der vordefinierten WCF-Bindung () interoperabel werden <xref:System.ServiceModel.BasicHttpBinding> .  
  
## <a name="service-development"></a>Dienstentwicklung  

 Verwenden Sie das <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute>-Attribut nicht, um Nachrichten basierend auf dem voll qualifizierten Namen des Textelements der SOAP-Nachricht anstatt des SOAPAction HTTP-Headers an Methoden weiterzuleiten. WCF verwendet den SOAPAction-HTTP-Header zum Weiterleiten von Nachrichten.  
  
## <a name="data-representation"></a>Datendarstellung  

 Die XML, in die <xref:System.Xml.Serialization.XmlSerializer> standardmäßig einen Typ serialisiert, ist semantisch identisch mit der XML, in die <xref:System.Runtime.Serialization.DataContractSerializer> einen Typ serialisiert, vorausgesetzt, der Namespace ist für die XML explizit definiert. Wenn Sie einen Datentyp für die Verwendung mit ASP.NET-Webdiensten in Erwartung der Einführung von WCF in Zukunft definieren, gehen Sie folgendermaßen vor:  
  
1. Definieren Sie den Typ mit .NET Framework-Klassen und nicht mit dem XML-Schema.  
  
2. Fügen Sie der Klasse lediglich <xref:System.SerializableAttribute> und <xref:System.Xml.Serialization.XmlRootAttribute> hinzu, wobei Sie mit dem zweiten Attribut den Namespace für den Typ explizit definieren. Fügen Sie keine zusätzlichen Attribute aus dem <xref:System.Xml.Serialization>-Namespace hinzu, um zu steuern, wie die .NET Framework-Klasse in XML übersetzt wird.  
  
 Wenn Sie diese Vorgehensweise wählen, sollte es später kein Problem darstellen, die .NET-Klassen in Datenverträge umzuwandeln, indem Sie <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> hinzufügen, ohne die XML erheblich zu ändern, in die die Klassen für die Übertragung serialisiert werden. Die in Nachrichten von ASP.NET-Webdiensten verwendeten Typen können von WCF-Anwendungen als Datenverträge verarbeitet werden, was zu anderen Vorteilen zu einer besseren Leistung in WCF-Anwendungen führt.  
  
## <a name="security"></a>Sicherheit  

 Vermeiden Sie die Verwendung der von den Internetinformationsdiensten (IIS) bereitgestellten Authentifizierungsoptionen. WCF-Clients unterstützen diese nicht. Wenn ein Dienst geschützt werden muss, verwenden Sie die von WCF bereitgestellten Optionen, da diese Optionen umfangreicher sind und auf Standardprotokollen basieren.  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorbereitungen für Windows Communication Foundation: einfachere Integration in der Zukunft](anticipating-adopting-wcf-migration.md)
