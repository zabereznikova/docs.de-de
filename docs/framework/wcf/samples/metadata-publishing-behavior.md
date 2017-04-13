---
title: "Metadatenver&#246;ffentlichungsverhalten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Metadatenveröffentlichungsverhalten-Beispiel [Windows Communication Foundation]"
  - "Dienstverhalten, Metadatenveröffentlichungs-Beispiel"
ms.assetid: 78c13633-d026-4814-910e-1c801cffdac7
caps.latest.revision: 23
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 23
---
# Metadatenver&#246;ffentlichungsverhalten
Das Beispiel für das Metadatenveröffentlichungsverhalten verdeutlicht, wie die Metadatenveröffentlichungsfeatures eines Diensts gesteuert werden.Um zu verhindern, dass potenziell vertrauliche Dienstmetadaten versehentlich offengelegt werden, wird das Veröffentlichen von Metadaten in der Standardkonfiguration für [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Dienste deaktiviert.Dieses Verhalten ist in der Standardeinstellung sicher, bedeutet aber auch, dass man den zum Aufrufen des Diensts erforderlichen Clientcode nicht mithilfe eines Tools zum Importieren von Metadaten \(wie Svcutil.exe\) generieren kann. Dies ist nur dann möglich, wenn das Verhalten des Diensts zum Veröffentlichen von Metadaten in der Konfiguration explizit aktiviert ist.  
  
> [!IMPORTANT]
>  Beachten Sie, dass in diesem Beispiel die Erstellung eines ungesicherten Metadaten\-Veröffentlichungsendpunkts veranschaulicht wird.Solche Endpunkte können für anonyme, nicht authentifizierte Benutzer möglicherweise verfügbar sein. Daher muss beim Bereitstellen solcher Endpunkte sorgfältig darauf geachtet werden, dass das Öffentlichmachen von Metadaten eines Diensts sachgerecht erfolgt.Ein Beispiel zum Absichern eines Metadatenendpunkts finden Sie im Beispiel [Benutzerdefinierter sicherer Metadatenendpunkt](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).  
  
 Das Beispiel basiert auf dem [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md), das den `ICalculator`\-Dienstvertrag implementiert.In diesem Beispiel ist der Client eine Konsolenanwendung \(.exe\), und der Dienst wird von IIS \(Internet Information Services, Internetinformationsdienste\) gehostet.  
  
> [!NOTE]
>  Die Setupprozedur und die Erstellungsanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Damit ein Dienst Metadaten verfügbar macht, muss <xref:System.ServiceModel.Description.ServiceMetadataBehavior> für den Dienst konfiguriert werden.Wenn dieses Verhalten auftritt, können Sie Metadaten veröffentlichen, indem Sie einen Endpunkt so konfigurieren, dass er den <xref:System.ServiceModel.Description.IMetadataExchange>\-Vertrag als Implementierung eines WS\-MEX\-\(MetadataExchange\-\)Protokolls verfügbar macht.Zur besseren Benutzerfreundlichkeit hat dieser Vertrag den abgekürzten Konfigurationsnamen "IMetadataExchange" erhalten.In diesem Beispiel wird `mexHttpBinding` verwendet. Dies ist eine benutzerfreundliche Standardbindung, die `wsHttpBinding` mit dem Sicherheitsmodus auf `None` entspricht.Im Endpunkt wird eine relative Adresse von "mex" verwendet, die beim Auflösen der Dienstbasisadresse in einer Endpunktadresse von http:\/\/localhost\/servicemodelsamples\/service.svc\/mex resultiert.Im Folgenden wird die Verhaltenskonfiguration gezeigt:  
  
```  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <!-- The serviceMetadata behavior publishes metadata through   
           the IMetadataExchange contract. When this behavior is   
           present, you can expose this contract through an endpoint   
           as shown below. Setting httpGetEnabled to true publishes   
           the service's WSDL at the <baseaddress>?wsdl, for example,  
           http://localhost/servicemodelsamples/service.svc?wsdl -->  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Im Folgenden wird der MEX\-Endpunkt gezeigt:  
  
```  
<!-- the MEX endpoint is exposed at   
     http://localhost/servicemodelsamples/service.svc/mex   
     To expose the IMetadataExchange contract, you   
     must enable the serviceMetadata behavior as demonstrated                           
     previously. -->  
<endpoint address="mex"  
          binding="mexHttpBinding"  
          contract="IMetadataExchange" />  
```  
  
 In diesem Beispiel wird die <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A>\-Eigenschaft auf `true` festgelegt, wodurch auch die Metadaten der Dienste mit HTTP GET verfügbar gemacht werden.Um einen HTTP GET\-Metadatenendpunkt zu aktivieren, muss der Dienst eine HTTP\-Basisadresse haben.Die Abfragezeichenfolge `?wsdl` wird auf die Basisadresse des Diensts angewendet, um auf die Metadaten zuzugreifen.Wenn Sie beispielsweise die WSDL für den Dienst einem Webbrowser anzeigen möchten, verwenden Sie die Adresse http:\/\/localhost\/servicemodelsamples\/service.svc?wsdl.Alternativ können Sie dieses Verhalten verwenden, um Metadaten durch Festlegen von <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> auf `true` über HTTPS verfügbar zu machen.Dies erfordert eine HTTPS\-Basisadresse.  
  
 Verwenden Sie das [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), um auf den MEX\-Endpunkt des Diensts zuzugreifen.  
  
 `svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs`  
  
 Dadurch wird ein Client auf der Grundlage der Metadaten des Diensts generiert.  
  
 Greifen Sie mit HTTP GET auf die Metadaten des Diensts zu, indem Sie Ihren Browser auf http:\/\/localhost\/servicemodelsamples\/service.svc?wsdl verweisen.  
  
 Wenn Sie dieses Verhalten entfernen und versuchen, den Dienst zu öffnen, erhalten Sie einen Ausnahmefehler.Dieser Fehler tritt auf, da der mit dem `IMetadataExchange`\-Vertrag konfigurierte Endpunkt ohne das Verhalten keine Implementierung hat.  
  
 Wenn Sie `HttpGetEnabled` auf `false` festlegen, wird anstelle der Metadaten des Diensts die CalculatorService\-Hilfeseite angezeigt.  
  
### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Vergewissern Sie sich, dass Sie [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Folgen Sie zum Erstellen der C\#\- bzw. Visual Basic .NET\-Version der Projektmappe den Anweisungen unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Um das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend auszuführen, befolgen Sie die Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Metadata`  
  
## Siehe auch