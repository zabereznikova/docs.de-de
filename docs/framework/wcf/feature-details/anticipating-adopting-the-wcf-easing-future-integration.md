---
title: 'Vorbereitungen für Windows Communication Foundation: Einfachere Integration in der Zukunft'
ms.date: 03/30/2017
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
ms.openlocfilehash: f81e158a5e7f897307c0c6d376dfe01dac127ead
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a>Vorbereitungen für Windows Communication Foundation: Einfachere Integration in der Zukunft
Dieses Thema enthält Anleitungen, um sicherzustellen, dass neue ASP.NET-Webdienste auch zusammen mit WCF-Anwendungen funktioniert, wenn Sie heute ASP.NET verwenden und mithilfe von WCF in der Zukunft erwarten.  
  
## <a name="general-recommendations"></a>Allgemeine Empfehlungen  
 Übernehmen Sie ASP.NET 2.0 auch für neue Dienste. Dadurch stellen Sie den Zugriff auf die Verbesserungen und Erweiterungen der neuen Version bereit. Jedoch wird auch die Möglichkeit der Verwendung von ASP.NET 2.0-Komponenten zusammen mit WCF-Komponenten in der gleichen Anwendung ermöglichen.  
  
## <a name="protocols"></a>Protokolle  
 Verwenden Sie die neue Funktion von ASP.NET 2.0 zum Überprüfen der Konformität mit WS-I Basic Profile 1.1:  
  
```  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 ASP.NET-Webdienste, die mit WS-I Basic Profile 1.1 übereinstimmen Interoperabilität mit WCF-Clients mithilfe von vordefinierten WCF binden, <xref:System.ServiceModel.BasicHttpBinding>.  
  
## <a name="service-development"></a>Dienstentwicklung  
 Verwenden Sie das <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute>-Attribut nicht, um Nachrichten basierend auf dem voll qualifizierten Namen des Textelements der SOAP-Nachricht anstatt des SOAPAction HTTP-Headers an Methoden weiterzuleiten. WCF verwendet den SOAPAction-HTTP-Header zum Weiterleiten von Nachrichten.  
  
## <a name="data-representation"></a>Datendarstellung  
 Die XML, in die <xref:System.Xml.Serialization.XmlSerializer> standardmäßig einen Typ serialisiert, ist semantisch identisch mit der XML, in die <xref:System.Runtime.Serialization.DataContractSerializer> einen Typ serialisiert, vorausgesetzt, der Namespace ist für die XML explizit definiert. Wenn Sie einen Datentyp für die Verwendung mit ASP.NET-Webdiensten in antizipation von allen WCF in Zukunft zu definieren, führen Sie folgende Schritte aus:  
  
1.  Definieren Sie den Typ mit .NET Framework-Klassen und nicht mit dem XML-Schema.  
  
2.  Fügen Sie der Klasse lediglich <xref:System.SerializableAttribute> und <xref:System.Xml.Serialization.XmlRootAttribute> hinzu, wobei Sie mit dem zweiten Attribut den Namespace für den Typ explizit definieren. Fügen Sie keine zusätzlichen Attribute aus dem <xref:System.Xml.Serialization>-Namespace hinzu, um zu steuern, wie die .NET Framework-Klasse in XML übersetzt wird.  
  
 Wenn Sie diese Vorgehensweise wählen, sollte es später kein Problem darstellen, die .NET-Klassen in Datenverträge umzuwandeln, indem Sie <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> hinzufügen, ohne die XML erheblich zu ändern, in die die Klassen für die Übertragung serialisiert werden. Die von den ASP.NET-Webdiensten verwendeten Typen werden können als Datenverträge verarbeitet werden, von WCF-Anwendungen was u. a. andere Vorteile, die eine bessere Leistung in WCF-Anwendungen.  
  
## <a name="security"></a>Sicherheit  
 Vermeiden Sie die Verwendung der von den Internetinformationsdiensten (IIS) bereitgestellten Authentifizierungsoptionen. WCF-Clients werden nicht unterstützt. Wenn ein Dienst gesichert werden muss, verwenden Sie die Optionen, die von WCF bereitgestellt werden, da diese Optionen leistungsstärker sind und auf Standardprotokollen basieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorbereitungen für Windows Communication Foundation: Einfachere Migration in der Zukunft](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)
