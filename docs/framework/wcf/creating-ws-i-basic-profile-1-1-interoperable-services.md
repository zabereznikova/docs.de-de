---
title: "Erstellen von interoperablen WS-I Basic Profile 1.1-Diensten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Konfiguration [WCF], interoperable Dienste"
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Erstellen von interoperablen WS-I Basic Profile 1.1-Diensten
So konfigurieren Sie einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstendpunkt, sodass er mit [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]-Webdienstclients interoperabel ist:  
  
-   Verwenden der <xref:System.ServiceModel.BasicHttpBinding?displayProperty=fullName> Typ als Bindungstyp für den Dienstendpunkt.  
  
-   Verwenden Sie für den Dienstendpunkt keine Rückruf- und Sitzungsvertragsfunktionen oder Transaktionsverhalten.  
  
 Sie können für die Bindung auch Unterstützung für HTTPS und Clientauthentifizierung auf Transportebene aktivieren.  
  
 Die folgenden Funktionen von der <xref:System.ServiceModel.BasicHttpBinding> -Klasse erfordern Funktionalität jenseits von WS-I Basic Profile 1.1:  
  
-   Message Transmission Optimization Mechanism (MTOM)-nachrichtencodierung gesteuert, von der <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=fullName> Eigenschaft. Behalten Sie den Standardwert für diese Eigenschaft <xref:System.ServiceModel.WSMessageEncoding?displayProperty=fullName> MTOM nicht zu verwenden.  
  
-   Die nachrichtensicherheit gesteuert, indem die <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=fullName> Wert bietet WS-Security-Unterstützung, die kompatibel mit WS-I Basic Security Profile 1.0. Behalten Sie den Standardwert für diese Eigenschaft <xref:System.ServiceModel.SecurityMode?displayProperty=fullName> WS-Sicherheit nicht zu verwenden.  
  
 Zu den Metadaten für eine [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Dienst bereit, [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], verwenden Sie die Web Service-Generation-Clienttools: [Web Services Description Language Tool (Wsdl.exe)](http://msdn.microsoft.com/de-de/b9210348-8bc2-4367-8c91-d1a04b403e88), [Webdienste-Suchtool (Disco.exe)](http://msdn.microsoft.com/de-de/acd88078-c581-42bc-94ca-6633e2851979), und die `Add Web Reference` Funktion [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]; müssen Sie Metadatenveröffentlichung aktivieren. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Metadatenendpunkte veröffentlichen](../../../docs/framework/wcf/publishing-metadata-endpoints.md).  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Der folgende Beispielcode demonstriert das Hinzufügen eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Endpunkts, der kompatibel mit den [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]-Webdienstclients ist, im Code und alternativ in Konfigurationsdateien.  
  
### <a name="code"></a>Code  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
  
 <!-- TODO: review snippet reference [!code[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/common/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  -->  
  
## <a name="see-also"></a>Siehe auch  
 [Interoperabilität mit ASP.NET-Webdiensten](../../../docs/framework/wcf/feature-details/interop-with-aspnet-web-services.md)