---
title: "Benutzerdefiniertes Binden von zuverlässigen Sitzungen über HTTPS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16aaa80d-3ffe-47c4-8b16-ec65c4d25f8d
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dfd417bc04bcbcabda70618aff9db3605556b068
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="custom-binding-reliable-session-over-https"></a>Benutzerdefiniertes Binden von zuverlässigen Sitzungen über HTTPS
In diesem Beispiel wird die Verwendung der SSL-Transportsicherheit mit zuverlässigen Sitzungen veranschaulicht. Zuverlässige Sitzungen implementieren das WS-ReliableMessaging-Protokoll. Durch das Erstellen von WS-Sicherheit über zuverlässige Sitzungen können Sie eine sichere zuverlässige Sitzung erreichen. In einigen Fällen werden Sie jedoch die Verwendung der HTTP-Transportsicherheit mit SSL vorziehen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\ReliableSessionOverHttps`  
  
## <a name="sample-details"></a>Beispieldetails  
 SSL stellt sicher, dass die Pakete selbst sicher sind. Beachten Sie unbedingt, dass dies sich vom Sichern der zuverlässigen Sitzung mit WS-Secure Conversation unterscheidet.  
  
 Zum Verwenden einer zuverlässigen Sitzung über HTTPS müssen Sie eine benutzerdefinierte Bindung erstellen. Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) , implementiert einen rechnerdienst. Eine benutzerdefinierte Bindung wird mit dem Bindungselement der zuverlässigen Sitzung erstellt und die [ \<HttpsTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md). Die folgende Konfiguration bezieht sich auf die benutzerdefinierte Bindung.  
  
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
  
 Die Programm-Codes in diesem Beispiel ist identisch mit der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) Dienst. Sie müssen ein Zertifikat erstellen und es mithilfe des Assistenten für Webserverzertifikate zuweisen, bevor Sie das Beispiel erstellen und ausführen. Durch die Endpunktdefinition und Bindungsdefinition in den Einstellungen der Konfigurationsdatei wird die Verwendung der benutzerdefinierten Bindung aktiviert, wie in der folgenden Beispielkonfiguration für den Client dargestellt.  
  
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
  
 Da das in diesem Beispiel verwendete Zertifikat ein mit Makecert.exe erstelltes Testzertifikat ist, wird eine Sicherheitswarnung angezeigt, wenn Sie versuchen, in Ihrem Browser auf eine https:-Adresse wie https://localhost/servicemodelsamples/service.svc zuzugreifen. Damit der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Client mit einem vorhandenen Testzertifikat arbeiten kann, muss auf dem Client zusätzlicher Code hinzugefügt werden, um die Sicherheitswarnung zu unterdrücken. Dieser Code und die begleitende Klasse sind bei der Verwendung von Produktionszertifikaten nicht erforderlich.  
  
```  
// This code is required only for test certificates like those created by Makecert.exe.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Installieren Sie [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 mithilfe des folgenden Befehls.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
3.  Stellen Sie sicher, dass Sie ausgeführt haben die [Installationsanweisungen für Internetinformationsdienste (Internet Information Services, IIS) Server Zertifikat](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).  
  
4.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
5.  Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>Siehe auch
