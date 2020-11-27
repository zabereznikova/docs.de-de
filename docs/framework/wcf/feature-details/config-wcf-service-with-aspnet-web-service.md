---
title: 'Vorgehensweise: Konfigurieren eines WCF-Diensts für die Zusammenarbeit mit ASP.NET-Webdienstclients'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
ms.openlocfilehash: 9c241c06f153e4f85c70459ff3c50889057103f5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295040"
---
# <a name="how-to-configure-wcf-service-to-interoperate-with-aspnet-web-service-clients"></a>Vorgehensweise: Konfigurieren eines WCF-Diensts für die Zusammenarbeit mit ASP.NET-Webdienstclients

Um einen Windows Communication Foundation (WCF)-Dienst Endpunkt zu konfigurieren, der mit ASP.NET-Webdienst Clients interoperabel ist, verwenden Sie den- <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> Typ als Bindungstyp für den Dienst Endpunkt.  
  
 Sie können für die Bindung auch Unterstützung für HTTPS und Clientauthentifizierung auf Transportebene aktivieren. ASP.NET-Webdienst Clients unterstützen die MTOM-Nachrichten Codierung nicht <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> . Daher sollte die-Eigenschaft als Standardwert belassen werden, d <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> . h.. ASP.NET-Webdienst Clients unterstützen WS-Sicherheit nicht, daher <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> sollte auf festgelegt werden <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> .  
  
 Um die Metadaten für einen WCF-Dienst für ASP.NET-Webdienst-Proxy Generierungs Tools (d. h. [Web Services Description Language Tool (Wsdl.exe)](/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100)), [Web Services Discovery Tool (Disco.exe)](/previous-versions/dotnet/netframework-4.0/cy2a3ybs(v=vs.100))und das Feature " **Webverweis hinzufügen** " in Visual Studio verfügbar zu machen, sollten Sie einen HTTP/GET-Metadatenendpunkt verfügbar machen.  
  
## <a name="add-an-endpoint-in-code"></a>Hinzufügen eines Endpunkts im Code  
  
1. Erstellen Sie eine neue <xref:System.ServiceModel.BasicHttpBinding>-Instanz.  
  
2. Aktivieren Sie optional Transportsicherheit für diese Dienstendpunktbindung, indem Sie den Sicherheitsmodus für die Bindung auf <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> festlegen. Weitere Informationen finden Sie unter [Transport Sicherheit](transport-security.md).  
  
3. Fügen Sie dem Diensthost einen neuen Anwendungsendpunkt mit der Bindungsinstanz hinzu, die Sie soeben erstellt haben. Ausführliche Informationen zum Hinzufügen eines Dienst Endpunkts im Code finden Sie unter Gewusst [wie: Erstellen eines Dienst Endpunkts im Code](how-to-create-a-service-endpoint-in-code.md).  
  
4. Aktivieren Sie einen HTTP/GET-Metadatenendpunkt für Ihren Dienst. Weitere Informationen finden [Sie unter Gewusst wie: Veröffentlichen von Metadaten für einen Dienst mithilfe von Code](how-to-publish-metadata-for-a-service-using-code.md).  
  
## <a name="add-an-endpoint-in-a-configuration-file"></a>Hinzufügen eines Endpunkts in einer Konfigurationsdatei  
  
1. Erstellen Sie eine neue <xref:System.ServiceModel.BasicHttpBinding>-Bindungskonfiguration. Weitere Informationen finden Sie unter Vorgehens [Weise: Angeben einer Dienst Bindung in der Konfiguration](../how-to-specify-a-service-binding-in-configuration.md).  
  
2. Aktivieren Sie optional Transportsicherheit für diese Dienstendpunkt-Bindungskonfiguration, indem Sie den Sicherheitsmodus für die Bindung auf <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> festlegen. Weitere Informationen finden Sie unter [Transport Sicherheit](transport-security.md).  
  
3. Konfigurieren Sie einen neuen Anwendungsendpunkt für Ihren Dienst, indem Sie die Bindungskonfiguration verwenden, die Sie gerade erstellt haben. Ausführliche Informationen zum Hinzufügen eines Dienst Endpunkts in einer Konfigurationsdatei finden Sie unter Vorgehens [Weise: Erstellen eines Dienst](how-to-create-a-service-endpoint-in-configuration.md)Endpunkts in der Konfiguration.  
  
4. Aktivieren Sie einen HTTP/GET-Metadatenendpunkt für Ihren Dienst. Weitere Informationen finden Sie unter Gewusst [wie: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispielcode wird veranschaulicht, wie ein WCF-Endpunkt hinzugefügt wird, der mit ASP.NET-Webdienst Clients im Code und alternativ in Konfigurationsdateien kompatibel ist.  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Erstellen eines Dienstendpunkts im Code](how-to-create-a-service-endpoint-in-code.md)
- [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst über den Code](how-to-publish-metadata-for-a-service-using-code.md)
- [Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration](../how-to-specify-a-service-binding-in-configuration.md)
- [Vorgehensweise: Erstellen eines Dienstendpunkts in einer Konfiguration](how-to-create-a-service-endpoint-in-configuration.md)
- [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Transport Sicherheit](transport-security.md)
- [Verwenden von Metadaten](using-metadata.md)
