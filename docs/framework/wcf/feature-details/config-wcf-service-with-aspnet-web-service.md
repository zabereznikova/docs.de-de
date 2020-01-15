---
title: 'Vorgehensweise: Konfigurieren eines WCF-Diensts für die Zusammenarbeit mit ASP.NET Webdienstclients'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
ms.openlocfilehash: 7e07e8d8781040d4ddc1d5643446f5a42354a557
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2020
ms.locfileid: "75963548"
---
# <a name="how-to-configure-wcf-service-to-interoperate-with-aspnet-web-service-clients"></a>Vorgehensweise: Konfigurieren eines WCF-Diensts für die Zusammenarbeit mit ASP.NET Webdienstclients
Wenn Sie einen Windows Communication Foundation (WCF)-Dienst Endpunkt so konfigurieren möchten, dass er mit ASP.NET-Webdienst Clients interoperabel ist, verwenden Sie den <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>-Typ als Bindungstyp für den Dienst Endpunkt.  
  
 Sie können für die Bindung auch Unterstützung für HTTPS und Clientauthentifizierung auf Transportebene aktivieren. ASP.NET-Webdienst Clients unterstützen die MTOM-Nachrichten Codierung nicht. Daher sollte die <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType>-Eigenschaft als Standardwert belassen werden, der <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>ist. ASP.NET-Webdienstclients unterstützen WS-Sicherheit nicht; deshalb sollte  <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> auf <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> festgelegt werden.  
  
 Um die Metadaten für einen WCF-Dienst für ASP.NET-Webdienst-Proxy Generierungs Tools (d. h. [Web Services Description Language Tool (WSDL. exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v%3dvs.100)), [Web Services Discovery-Tool (Disco. exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs(v=vs.100))und das Feature "Webverweis hinzufügen" in Visual Studio verfügbar zu machen, sollten Sie einen HTTP/GET-Metadatenendpunkt verfügbar machen.  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-code"></a>So fügen Sie einen WCF-Endpunkt hinzu, der im Code mit ASP.NET-Webdienstclients kompatibel ist  
  
1. Erstellen Sie eine neue <xref:System.ServiceModel.BasicHttpBinding>-Instanz.  
  
2. Aktivieren Sie optional Transportsicherheit für diese Dienstendpunktbindung, indem Sie den Sicherheitsmodus für die Bindung auf <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> festlegen. Weitere Informationen finden Sie unter [Transport Sicherheit](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3. Fügen Sie dem Diensthost einen neuen Anwendungsendpunkt mit der Bindungsinstanz hinzu, die Sie soeben erstellt haben. Ausführliche Informationen zum Hinzufügen eines Dienst Endpunkts im Code finden Sie unter Gewusst [wie: Erstellen eines Dienst Endpunkts im Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).  
  
4. Aktivieren Sie einen HTTP/GET-Metadatenendpunkt für Ihren Dienst. Weitere Informationen finden [Sie unter Gewusst wie: Veröffentlichen von Metadaten für einen Dienst mithilfe von Code](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-a-configuration-file"></a>So fügen Sie einen WCF-Endpunkt, der mit ASP.NET-Webdienstclients kompatibel ist, einer Konfigurationsdatei hinzu.  
  
1. Erstellen Sie eine neue <xref:System.ServiceModel.BasicHttpBinding>-Bindungskonfiguration. Weitere Informationen finden Sie unter Vorgehens [Weise: Angeben einer Dienst Bindung in der Konfiguration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
2. Aktivieren Sie optional Transportsicherheit für diese Dienstendpunkt-Bindungskonfiguration, indem Sie den Sicherheitsmodus für die Bindung auf <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> festlegen. Weitere Informationen finden Sie unter [Transport Sicherheit](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3. Konfigurieren Sie einen neuen Anwendungsendpunkt für Ihren Dienst, indem Sie die Bindungskonfiguration verwenden, die Sie gerade erstellt haben. Ausführliche Informationen zum Hinzufügen eines Dienst Endpunkts in einer Konfigurationsdatei finden Sie unter Vorgehens [Weise: Erstellen eines Dienst](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)Endpunkts in der Konfiguration.  
  
4. Aktivieren Sie einen HTTP/GET-Metadatenendpunkt für Ihren Dienst. Weitere Informationen finden Sie unter Gewusst [wie: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispielcode wird veranschaulicht, wie ein WCF-Endpunkt hinzugefügt wird, der mit ASP.NET-Webdienst Clients im Code und alternativ in Konfigurationsdateien kompatibel ist.  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)] 
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)] 
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]     
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen eines Dienstendpunkts im Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)
- [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst über Code](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)
- [Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)
- [Vorgehensweise: Erstellen eines Dienstendpunkts in einer Konfiguration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
- [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Transportsicherheit](../../../../docs/framework/wcf/feature-details/transport-security.md)
- [Verwenden von Metadaten](../../../../docs/framework/wcf/feature-details/using-metadata.md)
