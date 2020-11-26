---
title: 'Vorgehensweise: Hosten eines WCF-Diensts in WAS'
ms.date: 03/30/2017
ms.assetid: 9e3e213e-2dce-4f98-81a3-f62f44caeb54
ms.openlocfilehash: 640cfdd7525fb9877c6f3551a1456fed29c99b8a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244404"
---
# <a name="how-to-host-a-wcf-service-in-was"></a>Vorgehensweise: Hosten eines WCF-Diensts in WAS

In diesem Thema werden die grundlegenden Schritte beschrieben, die zum Erstellen eines Windows-Prozess Aktivierungs Diensts (auch bekannt als was) Windows Communication Foundation gehostet werden müssen. WAS ist der neue Prozessaktivierungsdienst, der eine Generalisierung der Funktionen der Internetinformationsdienste (IIS) darstellt, die mit Nicht-HTTP-Transportprotokollen arbeiten. WCF kommuniziert mithilfe der Listeneradapter-Schnittstelle Aktivierungs Anforderungen, die über die von WCF unterstützten nicht-HTTP-Protokolle empfangen werden, wie z. b. TCP, Named Pipes und Message Queuing.  
  
 Diese Hostingoption erfordert, dass die WAS-Aktivierungskomponenten korrekt installiert und konfiguriert wurden. Es muss jedoch keinerlei Hostcode für die Anwendung geschrieben werden. Weitere Informationen zum Installieren und Konfigurieren von was finden Sie unter Gewusst [wie: Installieren und Konfigurieren von WCF-Aktivierungs Komponenten](how-to-install-and-configure-wcf-activation-components.md).  
  
> [!WARNING]
> Die WAS-Aktivierung wird nicht unterstützt, wenn die Anforderungsverarbeitungspipeline des Webservers auf den klassischen Modus festgelegt ist. Die Anforderungsverarbeitungspipeline des Webservers muss auf den integrierten Modus festgelegt sein, wenn die WAS-Aktivierung verwendet werden soll.  
  
 Wenn ein WCF-Dienst in was gehostet wird, werden die Standard Bindungen auf die übliche Weise verwendet. Werden jedoch <xref:System.ServiceModel.NetTcpBinding> und <xref:System.ServiceModel.NetNamedPipeBinding> verwendet, um einen WAS-gehosteten Dienst zu konfigurieren, muss eine Bedingung erfüllt sein. Wenn verschiedene Endpunkte denselben Transport verwenden, müssen die Bindungseinstellungen für die folgenden sieben Eigenschaften übereinstimmen:  
  
- ConnectionBufferSize  
  
- ChannelInitializationTimeout  
  
- MaxPendingConnections  
  
- MaxOutputDelay  
  
- MaxPendingAccepts  
  
- ConnectionPoolSettings.IdleTimeout  
  
- ConnectionPoolSettings.MaxOutboundConnectionsPerEndpoint  
  
 Andernfalls bestimmt der zuerst initialisierte Endpunkt die Werte dieser Eigenschaften, und später hinzugefügte Endpunkte lösen eine <xref:System.ServiceModel.ServiceActivationException> aus, wenn ihre Einstellungen diesen Einstellungen nicht entsprechen.  
  
 Die Quell Kopie dieses Beispiels finden Sie unter [TCP-Aktivierung](../samples/tcp-activation.md).  
  
### <a name="to-create-a-basic-service-hosted-by-was"></a>So erstellen Sie einen grundlegenden durch WAS gehosteten Dienst  
  
1. Definieren Sie einen Dienstvertrag für den Diensttyp.  
  
     [!code-csharp[C_HowTo_HostInWAS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/service.cs#1121)]  
  
2. Implementieren Sie den Dienstvertrag in einer Dienstklasse. Beachten Sie, dass die Adresse oder die Bindungsinformationen in der Implementierung des Diensts nicht angegeben werden. Es muss auch kein Code geschrieben werden, um Informationen aus der Konfigurationsdatei abzurufen.  
  
     [!code-csharp[C_HowTo_HostInWAS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/service.cs#1122)]  
  
3. Erstellen Sie eine „Web.config“-Datei, um die <xref:System.ServiceModel.NetTcpBinding>-Bindung zu definieren, die von den `CalculatorService`-Endpunkten verwendet wird.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <bindings>  
          <netTcpBinding>  
            <binding portSharingEnabled="true">  
              <security mode="None" />  
            </binding>  
          </netTcpBinding>  
        </bindings>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
4. Erstellen Sie eine Service.svc-Datei, die den folgenden Code enthält.  
  
   ```aspx-csharp
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```
  
5. Stellen Sie die Service.svc-Datei in das virtuelle IIS-Verzeichnis.  
  
### <a name="to-create-a-client-to-use-the-service"></a>So erstellen Sie einen Client, der den Dienst verwendet  
  
1. Verwenden Sie das [Service Model Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) von der Befehlszeile aus, um Code aus Dienst Metadaten zu generieren.  
  
    ```console
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
    ```  
  
2. Der generierte Client enthält die `ICalculator`-Schnittstelle, die den Dienstvertrag definiert, dem die Clientimplementierung entsprechen muss.  
  
     [!code-csharp[C_HowTo_HostInWAS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1221)]  
  
3. Die generierte Clientanwendung enthält außerdem die Implementierung von `ClientCalculator`. Beachten Sie, dass die Adresse und die Bindungsinformationen in der Implementierung des Diensts nirgendwo angegeben werden. Es muss auch kein Code geschrieben werden, um Informationen aus der Konfigurationsdatei abzurufen.  
  
     [!code-csharp[C_HowTo_HostInWAS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1222)]  
  
4. Svcutil.exe generiert auch die Konfiguration für den Client, der <xref:System.ServiceModel.NetTcpBinding> verwendet. Wenn Sie Visual&#160;Studio verwenden, sollte diese Datei in der Datei App.config genannt werden.  
  
     [!code-xml[C_HowTo_HostInWAS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/common/app.config#2211)]
  
5. Erstellen Sie eine Instanz von `ClientCalculator` in einer Anwendung, und rufen Sie dann die Dienstvorgänge auf.  
  
     [!code-csharp[C_HowTo_HostInWAS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1223)]  
  
6. Kompilieren Sie den Code, und führen Sie den Client aus.  
  
## <a name="see-also"></a>Weitere Informationen

- [TCP-Aktivierung](../samples/tcp-activation.md)
- [Windows Server AppFabric-Hostingfunktionen](/previous-versions/appfabric/ee677189(v=azure.10))
