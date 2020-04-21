---
title: 'Vorgehensweise: Konfigurieren eines WCF-Diensts für die Zusammenarbeit mit ASP.NET-Webdienstclients'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
ms.openlocfilehash: ddd7e8c95701532010b54e5136a33d37d139f6a4
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739231"
---
# <a name="how-to-configure-wcf-service-to-interoperate-with-aspnet-web-service-clients"></a>Vorgehensweise: Konfigurieren eines WCF-Diensts für die Zusammenarbeit mit ASP.NET-Webdienstclients

Um einen WCF-Dienstendpunkt (Windows Communication Foundation) so zu konfigurieren, <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> dass er mit ASP.NET Webdienstclients interoperabel ist, verwenden Sie den Typ als Bindungstyp für Ihren Dienstendpunkt.  
  
 Sie können für die Bindung auch Unterstützung für HTTPS und Clientauthentifizierung auf Transportebene aktivieren. ASP.NET Webdienstclients unterstützen keine MTOM-Nachrichtencodierung, daher sollte die <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> Eigenschaft als <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>Standardwert belassen werden, d. h. . ASP.NET Web Dienstclients unterstützen WS-Security <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> nicht, daher <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>sollte die auf festgelegt werden.  
  
 Um die Metadaten für einen WCF-Dienst für ASP.NET Webdienstproxygenerierungstools (d. h. [Web Services Description Language Tool (Wsdl.exe),](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v%3dvs.100))Web Services Discovery Tool [(Disco.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs(v=vs.100))und das **Feature Webreferenz** hinzufügen in Visual Studio) verfügbar zu machen, sollten Sie einen HTTP/GET-Metadatenendpunkt verfügbar machen.  
  
## <a name="add-an-endpoint-in-code"></a>Hinzufügen eines Endpunkts im Code  
  
1. Erstellen Sie eine neue <xref:System.ServiceModel.BasicHttpBinding>-Instanz.  
  
2. Aktivieren Sie optional Transportsicherheit für diese Dienstendpunktbindung, indem Sie den Sicherheitsmodus für die Bindung auf <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> festlegen. Weitere Informationen finden Sie unter [Transportsicherheit](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3. Fügen Sie dem Diensthost einen neuen Anwendungsendpunkt mit der Bindungsinstanz hinzu, die Sie soeben erstellt haben. Weitere Informationen zum Hinzufügen eines Serviceendpunkts im Code finden Sie unter [Gewusst wie: Erstellen eines Serviceendpunkts im Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).  
  
4. Aktivieren Sie einen HTTP/GET-Metadatenendpunkt für Ihren Dienst. Weitere Informationen finden [Sie unter Gewusst wie: Veröffentlichen von Metadaten für einen Dienst mithilfe](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)von Code .  
  
## <a name="add-an-endpoint-in-a-configuration-file"></a>Hinzufügen eines Endpunkts in einer Konfigurationsdatei  
  
1. Erstellen Sie eine neue <xref:System.ServiceModel.BasicHttpBinding>-Bindungskonfiguration. Weitere Informationen finden Sie unter [Gewusst wie: Angeben einer Dienstbindung in Konfiguration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
2. Aktivieren Sie optional Transportsicherheit für diese Dienstendpunkt-Bindungskonfiguration, indem Sie den Sicherheitsmodus für die Bindung auf <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> festlegen. Weitere Informationen finden Sie unter [Transportsicherheit](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3. Konfigurieren Sie einen neuen Anwendungsendpunkt für Ihren Dienst, indem Sie die Bindungskonfiguration verwenden, die Sie gerade erstellt haben. Weitere Informationen zum Hinzufügen eines Dienstendpunkts in einer Konfigurationsdatei finden Sie unter [Gewusst wie: Erstellen eines Dienstendpunkts in Configuration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).  
  
4. Aktivieren Sie einen HTTP/GET-Metadatenendpunkt für Ihren Dienst. Weitere Informationen finden Sie unter [Gewusst wie: Veröffentlichen](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei .  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispielcode wird veranschaulicht, wie Sie einen WCF-Endpunkt hinzufügen, der mit ASP.NET Webdienstclients im Code und alternativ in Konfigurationsdateien kompatibel ist.  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen eines Dienstendpunkts im Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)
- [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst über den Code](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)
- [Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)
- [Vorgehensweise: Erstellen eines Dienstendpunkts in einer Konfiguration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
- [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Verkehrssicherheit](../../../../docs/framework/wcf/feature-details/transport-security.md)
- [Verwenden von Metadaten](../../../../docs/framework/wcf/feature-details/using-metadata.md)
