---
title: 'Vorgehensweise: Konfigurieren eines WCF-Diensts für die Zusammenarbeit mit ASP.NET-Webdienstclients'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
ms.openlocfilehash: 84762d8917609b84a049ea665b575acfa6e5fecf
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59325188"
---
# <a name="how-to-configure-wcf-service-to-interoperate-with-aspnet-web-service-clients"></a>Vorgehensweise: Konfigurieren eines WCF-Diensts für die Zusammenarbeit mit ASP.NET-Webdienstclients
So konfigurieren Sie einen Windows Communication Foundation (WCF)-Dienstendpunkt, um Interoperabilität mit [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Webdienstclients, verwenden Sie die <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> Typ als Bindungstyp für den Dienstendpunkt.  
  
 Sie können für die Bindung auch Unterstützung für HTTPS und Clientauthentifizierung auf Transportebene aktivieren. [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Webdienstclients unterstützen keine MTOM-nachrichtencodierung, sodass die <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> Eigenschaft sollte als den Standardwert zurück, d.h. bleiben <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>. ASP.NET-Webdienstclients unterstützen WS-Sicherheit nicht; deshalb sollte  <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> auf <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> festgelegt werden.  
  
 Um die Metadaten für einen WCF-Dienst verfügbar zu machen [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web Service Proxy-Generation-Tools (d. h. [Web Services Description Language Tool (Wsdl.exe)](https://go.microsoft.com/fwlink/?LinkId=73833), [Web Services Discovery Tool (Disco.exe)](https://go.microsoft.com/fwlink/?LinkId=73834), und die Funktion "Webverweis hinzufügen" in Visual Studio), Sie sollten einen HTTP/GET-Metadatenendpunkt verfügbar zu machen.  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-code"></a>So fügen Sie einen WCF-Endpunkt hinzu, der im Code mit ASP.NET-Webdienstclients kompatibel ist  
  
1. Erstellen Sie eine neue <xref:System.ServiceModel.BasicHttpBinding>-Instanz.  
  
2. Aktivieren Sie optional Transportsicherheit für diese Dienstendpunktbindung, indem Sie den Sicherheitsmodus für die Bindung auf <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> festlegen. Weitere Informationen finden Sie unter [Transportsicherheit](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3. Fügen Sie dem Diensthost einen neuen Anwendungsendpunkt mit der Bindungsinstanz hinzu, die Sie soeben erstellt haben. Ausführliche Informationen zum Hinzufügen eines Dienstendpunkts im Code finden Sie unter den [Vorgehensweise: Erstellen eines Dienstendpunkts im Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).  
  
4. Aktivieren Sie einen HTTP/GET-Metadatenendpunkt für Ihren Dienst. Weitere Informationen finden Sie [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienstcode](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-a-configuration-file"></a>So fügen Sie einen WCF-Endpunkt, der mit ASP.NET-Webdienstclients kompatibel ist, einer Konfigurationsdatei hinzu.  
  
1. Erstellen Sie eine neue <xref:System.ServiceModel.BasicHttpBinding>-Bindungskonfiguration. Weitere Informationen finden Sie unter den [Vorgehensweise: Angeben eine Dienstbindung in einer Konfiguration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
2. Aktivieren Sie optional Transportsicherheit für diese Dienstendpunkt-Bindungskonfiguration, indem Sie den Sicherheitsmodus für die Bindung auf <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> festlegen. Weitere Informationen finden Sie unter [Transportsicherheit](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3. Konfigurieren Sie einen neuen Anwendungsendpunkt für Ihren Dienst, indem Sie die Bindungskonfiguration verwenden, die Sie gerade erstellt haben. Ausführliche Informationen zum Hinzufügen eines Dienstendpunkts in einer Konfigurationsdatei finden Sie unter den [Vorgehensweise: Erstellen eines Dienstendpunkts in der Konfiguration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).  
  
4. Aktivieren Sie einen HTTP/GET-Metadatenendpunkt für Ihren Dienst. Weitere Informationen finden Sie die [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Beispielcode veranschaulicht, wie einen WCF-Endpunkt hinzufügen, die kompatibel mit [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Webdienstclients im Code und Alternativ in Konfigurationsdateien.  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)] 
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)] 
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]     
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen eines Dienstendpunkts im Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)
- [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst über den Code](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)
- [Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)
- [Vorgehensweise: Erstellen eines Dienstendpunkts in einer Konfiguration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
- [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Transportsicherheit](../../../../docs/framework/wcf/feature-details/transport-security.md)
- [Verwenden von Metadaten](../../../../docs/framework/wcf/feature-details/using-metadata.md)
