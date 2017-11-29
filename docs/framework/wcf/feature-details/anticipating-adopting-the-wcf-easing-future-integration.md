---
title: "Vorbereitungen für Windows Communication Foundation: Einfachere Integration in der Zukunft"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8f60b2566895acfd7d2b749729fab9c3f5deb20c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a>Vorbereitungen für Windows Communication Foundation: Einfachere Integration in der Zukunft
Wenn Sie heute ASP.NET verwenden und vorhaben, zukünftig [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zu verwenden, bietet dieses Thema Tipps, die gewährleisten, dass neue ASP.NET-Webdienste mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendungen ordnungsgemäß zusammenwirken.  
  
## <a name="general-recommendations"></a>Allgemeine Empfehlungen  
 Übernehmen Sie ASP.NET 2.0 auch für neue Dienste. Dadurch stellen Sie den Zugriff auf die Verbesserungen und Erweiterungen der neuen Version bereit. Sie erhalten so auch die Möglichkeit, ASP.NET 2.0-Komponenten zusammen mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Komponenten in derselben Anwendung zu verwenden.  
  
## <a name="protocols"></a>Protokolle  
 Verwenden Sie die neue Funktion von ASP.NET 2.0 zum Überprüfen der Konformität mit WS-I Basic Profile 1.1:  
  
```  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 ASP.NET-Webdienste, die mit WS-I Basic Profile 1.1 übereinstimmen, sind mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients interoperabel, wenn die von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] vordefinierte <xref:System.ServiceModel.BasicHttpBinding>-Bindung verwendet wird.  
  
## <a name="service-development"></a>Dienstentwicklung  
 Verwenden Sie das <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute>-Attribut nicht, um Nachrichten basierend auf dem voll qualifizierten Namen des Textelements der SOAP-Nachricht anstatt des SOAPAction HTTP-Headers an Methoden weiterzuleiten. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet den SOAPAction-HTTP-Header zum Weiterleiten von Nachrichten.  
  
## <a name="data-representation"></a>Datendarstellung  
 Die XML, in die <xref:System.Xml.Serialization.XmlSerializer> standardmäßig einen Typ serialisiert, ist semantisch identisch mit der XML, in die <xref:System.Runtime.Serialization.DataContractSerializer> einen Typ serialisiert, vorausgesetzt, der Namespace ist für die XML explizit definiert. Wenn ein Datentyp für die Verwendung mit ASP.NET-Webdiensten in Antizipation einer zukünftigen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Integration definiert wird, gehen Sie wie folgt vor:  
  
1.  Definieren Sie den Typ mit .NET Framework-Klassen und nicht mit dem XML-Schema.  
  
2.  Fügen Sie der Klasse lediglich <xref:System.SerializableAttribute> und <xref:System.Xml.Serialization.XmlRootAttribute> hinzu, wobei Sie mit dem zweiten Attribut den Namespace für den Typ explizit definieren. Fügen Sie keine zusätzlichen Attribute aus dem <xref:System.Xml.Serialization>-Namespace hinzu, um zu steuern, wie die .NET Framework-Klasse in XML übersetzt wird.  
  
 Wenn Sie diese Vorgehensweise wählen, sollte es später kein Problem darstellen, die .NET-Klassen in Datenverträge umzuwandeln, indem Sie <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> hinzufügen, ohne die XML erheblich zu ändern, in die die Klassen für die Übertragung serialisiert werden. Die von den ASP.NET-Webdiensten verwendeten Typen können von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] als Datenverträge verarbeitet werden, was u.&#160;a. zu einer höheren Leistung der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendungen führt.  
  
## <a name="security"></a>Sicherheit  
 Vermeiden Sie die Verwendung der von den Internetinformationsdiensten (IIS) bereitgestellten Authentifizierungsoptionen. Diese werden von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients nicht unterstützt. Falls ein Dienst gesichert werden muss, verwenden Sie die von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bereitgestellten Optionen, da diese Optionen leistungsstärker sind und auf Standardprotokollen basieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorbereitungen für Windows Communication Foundation: Einfachere Migration in der Zukunft](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)
