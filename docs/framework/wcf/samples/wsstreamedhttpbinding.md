---
title: WSStreamedHttpBinding
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97ce4d3d-ca6f-45fa-b33b-2429bb84e65b
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 94df68732622c45605479cc62f600258b54a95c0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="wsstreamedhttpbinding"></a>WSStreamedHttpBinding
Das Beispiel veranschaulicht, wie eine Bindung erstellt wird, die Streamingszenarios unterstützt, wenn HTTP-Transport verwendet wird.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Binding\WSStreamedHttpBinding`  
  
 Zum Erstellen und Konfigurieren einer neuen Standardbindung müssen folgende Schritte ausgeführt werden.  
  
1.  Erstellen einer neuen Standardbindung  
  
     Die Standardbindungen in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], z.&#160;B. basicHttpBinding und netTcpBinding, konfigurieren die zugrunde liegenden Transporte und Kanalstapel für bestimmte Anforderungen. In diesem Beispiel konfiguriert `WSStreamedHttpBinding` den Kanalstapel, um Streaming zu unterstützen. Standardmäßig werden WS-Sicherheit und zuverlässiges Messaging nicht zum Kanalstapel hinzugefügt, da beide Features nicht vom Streaming unterstützt werden. Die neue Bindung wird in die Klasse `WSStreamedHttpBinding` implementiert, die von <xref:System.ServiceModel.Channels.Binding> abgeleitet ist. `WSStreamedHttpBinding` enthält die folgenden Bindungselemente: <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>, <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> und <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>. Die Klasse stellt eine `CreateBindingElements()`-Methode bereit, um den resultierenden Bindungsstapel zu konfigurieren, wie im folgenden Codebeispiel gezeigt.  
  
    ```  
    public override BindingElementCollection CreateBindingElements()  
    {  
         // return collection of BindingElements  
         BindingElementCollection bindingElements = new BindingElementCollection();  
  
        // the order of binding elements within the collection is important: layered channels are applied in the order included, followed by  
        // the message encoder, and finally the transport at the end  
        if (flowTransactions)  
        {  
            bindingElements.Add(transactionFlow);  
        }  
        bindingElements.Add(textEncoding);  
  
        // add transport (http or https)  
        bindingElements.Add(transport);  
        return bindingElements.Clone();  
    }  
    ```  
  
2.  Hinzufügen von Konfigurationsunterstützung  
  
     Im Beispiel werden zwei weitere Klassen – `WSStreamedHttpBindingConfigurationElement` und `WSStreamedHttpBindingSection` – implementiert, um den Transport durch Konfiguration verfügbar zu machen. Die Klasse `WSStreamedHttpBindingSection` ist ein <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602>, das die `WSStreamedHttpBinding` für das [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Konfigurationssystem verfügbar macht. Der Großteil der Implementierung wird dem `WSStreamedHttpBindingConfigurationElement` übertragen, das von <xref:System.ServiceModel.Configuration.StandardBindingElement> abgeleitet wird. Die Klasse `WSStreamedHttpBindingConfigurationElement` verfügt über Eigenschaften, die mit den Eigenschaften von `WSStreamedHttpBinding` übereinstimmen, sowie über Funktionen, um jedes Konfigurationselement einer Bindung zuzuordnen.  
  
     Registrieren Sie den Handler mit dem Konfigurationssystem, indem Sie den folgenden Abschnitt zur Konfigurationsdatei des Diensts hinzufügen.  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <extensions>  
          <bindingExtensions>  
            <add name="wsStreamedHttpBinding" type="Microsoft.ServiceModel.Samples.WSStreamedHttpBindingCollectionElement, WSStreamedHttpBinding, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null" />  
          </bindingExtensions>  
        </extensions>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     Auf den Handler kann vom serviceModel-Konfigurationsabschnitt aus verwiesen werden.  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint  
                    address="https://localhost/servicemodelsamples/service.svc"  
                    bindingConfiguration="Binding"  
                    binding="wsStreamedHttpBinding"  
                    contract="Microsoft.ServiceModel.Samples.IStreamedEchoService"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Installieren Sie [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 mithilfe des folgenden Befehls.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  Stellen Sie sicher, dass Sie die Schritte unter ausgeführt haben [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
3.  Stellen Sie sicher, dass Sie ausgeführt haben die [Installationsanweisungen für Internetinformationsdienste (Internet Information Services, IIS) Server Zertifikat](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).  
  
4.  Führen Sie zum Erstellen der Projektmappe die Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
5.  Um das Beispiel in einer computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
6.  Wenn das Clientfenster angezeigt wird, geben Sie "Sample.txt" ein. In Ihrem Verzeichnis sollte sich eine Datei "Copy of Sample.txt" befinden.  
  
## <a name="the-wsstreamedhttpbinding-sample-service"></a>Der WSStreamedHttpBinding-Beispieldienst  
 Der Beispieldienst, der die `WSStreamedHttpBinding` verwendet, befindet sich im Dienstunterverzeichnis. Die Implementierung von `OperationContract` verwendet einen `MemoryStream`, um zuerst alle Daten vom eingehenden Stream abzurufen, bevor der `MemoryStream` zurückgegeben wird. Der Beispieldienst wird von Internetinformationsdiensten (IIS) gehostet.  
  
```  
[ServiceContract]  
public interface IStreamedEchoService  
{  
    [OperationContract]  
    Stream Echo(Stream data);  
}  
  
public class StreamedEchoService : IStreamedEchoService  
{  
    public Stream Echo(Stream data)  
    {  
        MemoryStream dataStorage = new MemoryStream();  
        byte[] byteArray = new byte[8192];  
        int bytesRead = data.Read(byteArray, 0, 8192);  
        while (bytesRead > 0)  
        {  
            dataStorage.Write(byteArray, 0, bytesRead);  
            bytesRead = data.Read(byteArray, 0, 8192);  
        }  
        data.Close();  
        dataStorage.Seek(0, SeekOrigin.Begin);  
  
        return dataStorage;  
    }  
}  
```  
  
## <a name="the-wsstreamedhttpbinding-sample-client"></a>Der WSStreamedHttpBinding-Beispielclient  
 Der Client, der für die Interaktion mit dem Dienst über `WSStreamedHttpBinding` verwendet wird, befindet sich im Clientunterverzeichnis. Da das in diesem Beispiel verwendete Zertifikat ein mit Makecert.exe erstelltes Testzertifikat ist, wird eine Sicherheitswarnung angezeigt, wenn Sie versuchen, in Ihrem Browser auf eine HTTPS-Adresse wie https://localhost/servicemodelsamples/service.svc zuzugreifen. Damit der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client mit einem vorhandenen Testzertifikat arbeiten kann, muss auf dem Client zusätzlicher Code hinzugefügt werden, um die Sicherheitswarnung zu unterdrücken. Der Code und die begleitende Klasse sind bei der Verwendung von Produktionszertifikaten nicht erforderlich.  
  
```  
// WARNING: This code is only required for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
## <a name="see-also"></a>Siehe auch
