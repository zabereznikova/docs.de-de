---
title: "Vorgehensweise: Konfigurieren eines WCF-Diensts für die Zusammenarbeit mit ASP.NET Webdienstclients"
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
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7ed4bf8e86e727505d48e85bb55a88452217c76b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-configure-wcf-service-to-interoperate-with-aspnet-web-service-clients"></a>Vorgehensweise: Konfigurieren eines WCF-Diensts für die Zusammenarbeit mit ASP.NET Webdienstclients
Verwenden Sie den Typ [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] als Bindungstyp für Ihren Dienstendpunkt, um einen [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Dienstendpunkt so zu konfigurieren, dass er mit <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>-Webdienstclients zusammenarbeitet.  
  
 Sie können für die Bindung auch Unterstützung für HTTPS und Clientauthentifizierung auf Transportebene aktivieren. [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Webdienstclients unterstützen keine MTOM-Nachrichtencodierung; daher sollte die Eigenschaft <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> ihren Standardwert, <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>, behalten. ASP.NET-Webdienstclients unterstützen WS-Sicherheit nicht; deshalb sollte  <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> auf <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> festgelegt werden.  
  
 Die Metadaten vornehmen, damit eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Dienst zur Verfügung [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web Service Proxy Generation Tools (d. h. [Web Services Description Language Tool (Wsdl.exe)](http://go.microsoft.com/fwlink/?LinkId=73833), [Web Services Discovery Tool ( DISCO.exe)](http://go.microsoft.com/fwlink/?LinkId=73834), und das Feature "Webverweis hinzufügen" in Visual Studio), Sie sollten einen HTTP/GET-Metadatenendpunkt verfügbar zu machen.  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-code"></a>So fügen Sie einen WCF-Endpunkt hinzu, der im Code mit ASP.NET-Webdienstclients kompatibel ist  
  
1.  Erstellen Sie eine neue <xref:System.ServiceModel.BasicHttpBinding>-Instanz.  
  
2.  Aktivieren Sie optional Transportsicherheit für diese Dienstendpunktbindung, indem Sie den Sicherheitsmodus für die Bindung auf <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> festlegen. Weitere Informationen finden Sie unter [Transportsicherheit](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3.  Fügen Sie dem Diensthost einen neuen Anwendungsendpunkt mit der Bindungsinstanz hinzu, die Sie soeben erstellt haben. Ausführliche Informationen zum Hinzufügen eines Dienstendpunkts im Code finden Sie unter der [Vorgehensweise: Erstellen eines Dienstendpunkts im Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).  
  
4.  Aktivieren Sie einen HTTP/GET-Metadatenendpunkt für Ihren Dienst. Weitere Informationen finden Sie [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe von Code](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-a-configuration-file"></a>So fügen Sie einen WCF-Endpunkt, der mit ASP.NET-Webdienstclients kompatibel ist, einer Konfigurationsdatei hinzu.  
  
1.  Erstellen Sie eine neue <xref:System.ServiceModel.BasicHttpBinding>-Bindungskonfiguration. Einzelheiten finden Sie in der [wie: Angeben einer Dienstbindung in einer Konfiguration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
2.  Aktivieren Sie optional Transportsicherheit für diese Dienstendpunkt-Bindungskonfiguration, indem Sie den Sicherheitsmodus für die Bindung auf <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> festlegen. Weitere Informationen finden Sie unter [Transportsicherheit](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3.  Konfigurieren Sie einen neuen Anwendungsendpunkt für Ihren Dienst, indem Sie die Bindungskonfiguration verwenden, die Sie gerade erstellt haben. Ausführliche Informationen zum Hinzufügen eines Dienstendpunkts in einer Konfigurationsdatei finden Sie unter der [Vorgehensweise: Erstellen eines Dienstendpunkts in der Konfiguration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).  
  
4.  Aktivieren Sie einen HTTP/GET-Metadatenendpunkt für Ihren Dienst. Weitere Informationen finden Sie die [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Beispielcode zeigt das Hinzufügen eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Endpunkts, der im Code und alternativ in den Konfigurationsdateien kompatibel mit den [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Webdienstclients ist.  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)] 
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)] 
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]     
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Erstellen eines Dienstendpunkts im Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienstcode](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 [Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)  
 [Vorgehensweise: Erstellen eines Dienstendpunkts in der Konfiguration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [Transportsicherheit](../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [Mithilfe von Metadaten](../../../../docs/framework/wcf/feature-details/using-metadata.md)
