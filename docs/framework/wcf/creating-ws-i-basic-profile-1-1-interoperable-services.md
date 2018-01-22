---
title: Erstellen von interoperablen WS-I Basic Profile 1.1-Diensten
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d6bef68c8ba433e902cfd50e59a3b343e3af08cd
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a>Erstellen von interoperablen WS-I Basic Profile 1.1-Diensten
So konfigurieren Sie einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstendpunkt, sodass er mit [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]-Webdienstclients interoperabel ist:  
  
-   Verwenden Sie den <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>-Typ als Bindungstyp für den Dienstendpunkt.  
  
-   Verwenden Sie für den Dienstendpunkt keine Rückruf- und Sitzungsvertragsfunktionen oder Transaktionsverhalten.  
  
 Sie können für die Bindung auch Unterstützung für HTTPS und Clientauthentifizierung auf Transportebene aktivieren.  
  
 Die folgenden Funktionen der <xref:System.ServiceModel.BasicHttpBinding>-Klasse erfordern Funktionalität jenseits von WS-I Basic Profiles 1.1:  
  
-   MTOM-Meldungscodierung (Message Transmission Optimization Mechanism), die von der <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType>-Eigenschaft gesteuert wird. Behalten Sie für diese Eigenschaft den Standardwert bei, der <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> ist, was bedeutet, dass kein MTOM verwendet wird.  
  
-   Meldungssicherheit, die vom <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType>-Wert gesteuert wird, stellt WS-Sicherheit bereit, die mit WS-I Basic Security Profile 1.0 kompatibel ist. Behalten Sie für diese Eigenschaft den Standardwert <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> bei, d. h. es wird keine WS-Sicherheit verwendet.  
  
 Die Metadaten vornehmen, damit eine [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Dienst zur Verfügung [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], verwenden Sie die Web-Dienst-Clienttools: [Web Services Description Language Tool (Wsdl.exe)](http://msdn.microsoft.com/library/b9210348-8bc2-4367-8c91-d1a04b403e88), [(Web Services Discovery Tool DISCO.exe)](http://msdn.microsoft.com/library/acd88078-c581-42bc-94ca-6633e2851979), und die `Add Web Reference` feature [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]; müssen Sie die Veröffentlichung von Metadaten aktivieren. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Metadatenendpunkte veröffentlichen](../../../docs/framework/wcf/publishing-metadata-endpoints.md).  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Der folgende Beispielcode veranschaulicht das Hinzufügen einer [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Endpunkt, der kompatibel mit [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] -Webdienstclients im Code und Alternativ in einer Konfigurationsdatei.  
  
### <a name="code"></a>Code  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a>Siehe auch  
 [Interoperabilität mit ASP.NET-Webdiensten](../../../docs/framework/wcf/feature-details/interop-with-aspnet-web-services.md)
