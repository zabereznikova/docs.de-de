---
title: Benutzerdefiniertes Binden von zuverlässigen Sitzungen über HTTPS
ms.date: 03/30/2017
ms.assetid: 16aaa80d-3ffe-47c4-8b16-ec65c4d25f8d
ms.openlocfilehash: 051e7f56662a2ca67018ae7dd29189ff50245fc8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183873"
---
# <a name="custom-binding-reliable-session-over-https"></a>Benutzerdefiniertes Binden von zuverlässigen Sitzungen über HTTPS
In diesem Beispiel wird die Verwendung der SSL-Transportsicherheit mit zuverlässigen Sitzungen veranschaulicht. Zuverlässige Sitzungen implementieren das WS-ReliableMessaging-Protokoll. Durch das Erstellen von WS-Sicherheit über zuverlässige Sitzungen können Sie eine sichere zuverlässige Sitzung erreichen. In einigen Fällen werden Sie jedoch die Verwendung der HTTP-Transportsicherheit mit SSL vorziehen.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\ReliableSessionOverHttps`  
  
## <a name="sample-details"></a>Beispieldetails  
 SSL stellt sicher, dass die Pakete selbst sicher sind. Beachten Sie unbedingt, dass dies sich vom Sichern der zuverlässigen Sitzung mit WS-Secure Conversation unterscheidet.  
  
 Zum Verwenden einer zuverlässigen Sitzung über HTTPS müssen Sie eine benutzerdefinierte Bindung erstellen. Dieses Beispiel basiert auf dem [Ersten Schritte,](../../../../docs/framework/wcf/samples/getting-started-sample.md) der einen Rechnerdienst implementiert. Eine benutzerdefinierte Bindung wird mit dem zuverlässigen Sitzungsbindungselement und dem [ \<httpsTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md)erstellt. Die folgende Konfiguration bezieht sich auf die benutzerdefinierte Bindung.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service
          name="Microsoft.ServiceModel.Samples.CalculatorService"  
          behaviorConfiguration="CalculatorServiceBehavior">  
        <!-- use base address provided by host -->  
        <endpoint address=""  
                  binding="customBinding"  
                  bindingConfiguration="reliableSessionOverHttps"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is exposed as http://localhost/servicemodelsamples/service.svc/mex-->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange"/>  
      </service>  
    </services>  
  
    <bindings>  
      <customBinding>  
        <binding name="reliableSessionOverHttps">  
          <reliableSession />  
          <httpsTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="true" />  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```  
  
 Der Programmcode im Beispiel ist identisch mit dem des [Ersten -Start-Dienstes.](../../../../docs/framework/wcf/samples/getting-started-sample.md) Sie müssen ein Zertifikat erstellen und es mithilfe des Assistenten für Webserverzertifikate zuweisen, bevor Sie das Beispiel erstellen und ausführen. Durch die Endpunktdefinition und Bindungsdefinition in den Einstellungen der Konfigurationsdatei wird die Verwendung der benutzerdefinierten Bindung aktiviert, wie in der folgenden Beispielkonfiguration für den Client dargestellt.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint name=""  
                address="https://localhost/servicemodelsamples/service.svc"
                binding="customBinding"
                bindingConfiguration="reliableSessionOverHttps"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </client>  
  
      <bindings>  
        <customBinding>  
          <binding name="reliableSessionOverHttps">  
            <reliableSession />  
            <httpsTransport />  
          </binding>  
        </customBinding>
    </bindings>  
  
  </system.serviceModel>  
  
</configuration>  
```  
  
 Für die angegebene Adresse wird das https://-Schema verwendet.  
  
 Da es sich bei dem in diesem Beispiel verwendeten Zertifikat um ein Testzertifikat handelt, das mit Makecert.exe erstellt wurde, wird eine Sicherheitswarnung angezeigt, wenn Sie versuchen, über Ihren Browser auf eine https:-Adresse, z. https://localhost/servicemodelsamples/service.svcB. , zuzugreifen. Damit der Windows Communication Foundation (WCF)-Client mit einem Testzertifikat arbeiten kann, wurde dem Client zusätzlicher Code hinzugefügt, um die Sicherheitswarnung zu unterdrücken. Dieser Code und die begleitende Klasse sind bei der Verwendung von Produktionszertifikaten nicht erforderlich.  

```csharp
// This code is required only for test certificates like those created by Makecert.exe.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```

 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Installieren Sie ASP.NET 4.0 mit dem folgenden Befehl.  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. Stellen Sie sicher, dass Sie das [einmalige Setupverfahren für die Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)durchgeführt haben.  
  
3. Stellen Sie sicher, dass Sie die Installationsanleitung für [Internetinformationsdienste (IIS)](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md)server Certificate Installation ausgeführt haben.  
  
4. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
5. Um das Beispiel in einer Konfiguration mit einem oder einer maschinellen Konfiguration auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
