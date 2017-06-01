---
title: "Benutzerdefiniertes Binden von zuverl&#228;ssigen Sitzungen &#252;ber HTTPS | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 16aaa80d-3ffe-47c4-8b16-ec65c4d25f8d
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Benutzerdefiniertes Binden von zuverl&#228;ssigen Sitzungen &#252;ber HTTPS
In diesem Beispiel wird die Verwendung der SSL\-Transportsicherheit mit zuverlässigen Sitzungen veranschaulicht.Zuverlässige Sitzungen implementieren das WS\-ReliableMessaging\-Protokoll.Durch das Erstellen von WS\-Sicherheit über zuverlässige Sitzungen können Sie eine sichere zuverlässige Sitzung erreichen.In einigen Fällen werden Sie jedoch die Verwendung der HTTP\-Transportsicherheit mit SSL vorziehen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\ReliableSessionOverHttps`  
  
## Beispieldetails  
 SSL stellt sicher, dass die Pakete selbst sicher sind.Beachten Sie unbedingt, dass dies sich vom Sichern der zuverlässigen Sitzung mit WS\-Secure Conversation unterscheidet.  
  
 Zum Verwenden einer zuverlässigen Sitzung über HTTPS müssen Sie eine benutzerdefinierte Bindung erstellen.Dieses Beispiel basiert auf dem [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md), das einen Rechnerdienst implementiert.Eine benutzerdefinierte Bindung wird mit dem Bindungselement für zuverlässige Sitzungen und [\<httpsTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) erstellt.Die folgende Konfiguration bezieht sich auf die benutzerdefinierte Bindung.  
  
```  
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
  
 Der Programmcode im Beispiel stimmt mit dem des Diensts in [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md) überein.Sie müssen ein Zertifikat erstellen und es mithilfe des Assistenten für Webserverzertifikate zuweisen, bevor Sie das Beispiel erstellen und ausführen.Durch die Endpunktdefinition und Bindungsdefinition in den Einstellungen der Konfigurationsdatei wird die Verwendung der benutzerdefinierten Bindung aktiviert, wie in der folgenden Beispielkonfiguration für den Client dargestellt.  
  
```  
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
  
 Für die angegebene Adresse wird das https:\/\/\-Schema verwendet.  
  
 Da das in diesem Beispiel verwendete Zertifikat ein mit Makecert.exe erstelltes Testzertifikat ist, wird eine Sicherheitswarnung angezeigt, wenn Sie versuchen, in Ihrem Browser auf eine https:\-Adresse wie https:\/\/localhost\/servicemodelsamples\/service.svc zuzugreifen.Damit der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Client mit einem vorhandenen Testzertifikat arbeiten kann, muss auf dem Client zusätzlicher Code hinzugefügt werden, um die Sicherheitswarnung zu unterdrücken.Dieser Code und die begleitende Klasse sind bei der Verwendung von Produktionszertifikaten nicht erforderlich.  
  
```  
// This code is required only for test certificates like those created by Makecert.exe.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
#### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Installieren Sie [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 mithilfe des folgenden Befehls.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
  
    ```  
  
2.  Vergewissern Sie sich, dass Sie [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
3.  Vergewissern Sie sich, dass Sie [Installationsanleitung für IIS\-Serverzertifikate \(Internetinformationsdienste\)](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md) ausgeführt haben.  
  
4.  Zum Erstellen der C\#\- oder Visual Basic .NET\-Edition der Lösung befolgen Sie die unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md) aufgeführten Anweisungen.  
  
5.  Wenn Sie das Beispiel in einer Konfiguration mit einem einzigen Computer oder computerübergreifend ausführen möchten, befolgen Sie die unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md) aufgeführten Anweisungen.  
  
## Siehe auch