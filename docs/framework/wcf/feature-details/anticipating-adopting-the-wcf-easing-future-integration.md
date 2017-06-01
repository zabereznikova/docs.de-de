---
title: "Vorbereitungen f&#252;r Windows Communication Foundation: Einfachere Integration in der Zukunft | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Vorbereitungen f&#252;r Windows Communication Foundation: Einfachere Integration in der Zukunft
Wenn Sie heute ASP.NET verwenden und vorhaben, zukünftig [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zu verwenden, bietet dieses Thema Tipps, die gewährleisten, dass neue ASP.NET\-Webdienste mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Anwendungen ordnungsgemäß zusammenwirken.  
  
## Allgemeine Empfehlungen  
 Übernehmen Sie ASP.NET 2.0 auch für neue Dienste.Dadurch stellen Sie den Zugriff auf die Verbesserungen und Erweiterungen der neuen Version bereit.Sie erhalten so auch die Möglichkeit, ASP.NET 2.0\-Komponenten zusammen mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Komponenten in derselben Anwendung zu verwenden.  
  
## Protokolle  
 Verwenden Sie die neue Funktion von ASP.NET 2.0 zum Überprüfen der Konformität mit WS\-I Basic Profile 1.1:  
  
```  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
  
```  
  
 ASP.NET\-Webdienste, die mit WS\-I Basic Profile 1.1 übereinstimmen, sind mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clients interoperabel, wenn die von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] vordefinierte <xref:System.ServiceModel.BasicHttpBinding>\-Bindung verwendet wird.  
  
## Dienstentwicklung  
 Verwenden Sie das <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute>\-Attribut nicht, um Nachrichten basierend auf dem voll qualifizierten Namen des Textelements der SOAP\-Nachricht anstatt des SOAPAction HTTP\-Headers an Methoden weiterzuleiten.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet den SOAPAction\-HTTP\-Header zum Weiterleiten von Nachrichten.  
  
## Datendarstellung  
 Die XML, in die <xref:System.Xml.Serialization.XmlSerializer> standardmäßig einen Typ serialisiert, ist semantisch identisch mit der XML, in die <xref:System.Runtime.Serialization.DataContractSerializer> einen Typ serialisiert, vorausgesetzt, der Namespace für die XML wurde explizit definiert.Wenn ein Datentyp für die Verwendung mit ASP.NET\-Webdiensten in Antizipation einer zukünftigen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Integration definiert wird, gehen Sie wie folgt vor:  
  
1.  Definieren Sie den Typ mit .NET Framework\-Klassen und nicht mit dem XML\-Schema.  
  
2.  Fügen Sie der Klasse lediglich <xref:System.SerializableAttribute> und <xref:System.Xml.Serialization.XmlRootAttribute> hinzu, wobei Sie letzteres zur expliziten Definition des Namespace für den Typ verwenden.Fügen Sie keine zusätzlichen Attribute aus dem <xref:System.Xml.Serialization>\-Namespace hinzu, um zu steuern, wie die .NET Framework\-Klasse in XML übersetzt wird.  
  
 Wenn Sie diese Methode wählen, sollte es später kein Problem darstellen, die .NET\-Klassen in Datenverträge umzuwandeln, indem Sie <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> hinzufügen, ohne die XML erheblich zu ändern, in die die Klassen für die Übertragung serialisiert werden.Die von den ASP.NET\-Webdiensten verwendeten Typen können von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] als Datenverträge verarbeitet werden, was u. a. zu einer höheren Leistung der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Anwendungen führt.  
  
## Sicherheit  
 Vermeiden Sie die Verwendung der von den Internetinformationsdiensten \(IIS\) bereitgestellten Authentifizierungsoptionen.Diese werden von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clients nicht unterstützt.Falls ein Dienst gesichert werden muss, verwenden Sie die von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bereitgestellten Optionen, da diese Optionen leistungsstärker sind und auf Standardprotokollen basieren.  
  
## Siehe auch  
 [Vorbereitungen für Windows Communication Foundation: Einfachere Migration in der Zukunft](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)