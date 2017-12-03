---
title: "Metadatenveröffentlichungsverhalten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service behaviors, metadata publishing sample
- Metadata Publishing Behaviors Sample [Windows Communication Foundation]
ms.assetid: 78c13633-d026-4814-910e-1c801cffdac7
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a92b41df3b2e9c556e61c08979290b12206f18aa
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="metadata-publishing-behavior"></a>Metadatenveröffentlichungsverhalten
Das Beispiel für das Metadatenveröffentlichungsverhalten verdeutlicht, wie die Metadatenveröffentlichungsfunktionen eines Diensts gesteuert werden. Um ein unbeabsichtigtes Veröffentlichen von möglicherweise vertraulichen Dienstmetadaten zu vermeiden, wird mit der Standardkonfiguration für [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienste die Metadatenveröffentlichung deaktiviert. Dieses Verhalten ist in der Standardeinstellung sicher, bedeutet aber auch, dass man den zum Aufrufen des Diensts erforderlichen Clientcode nicht mithilfe eines Tools zum Importieren von Metadaten (wie Svcutil.exe) generieren kann. Dies ist nur dann möglich, wenn das Verhalten des Diensts zum Veröffentlichen von Metadaten in der Konfiguration explizit aktiviert ist.  
  
> [!IMPORTANT]
>  Beachten Sie, dass in diesem Beispiel die Erstellung eines ungesicherten Metadaten-Veröffentlichungsendpunkts veranschaulicht wird. Solche Endpunkte können für anonyme, nicht authentifizierte Benutzer möglicherweise verfügbar sein. Daher muss beim Bereitstellen solcher Endpunkte sorgfältig darauf geachtet werden, dass das Öffentlichmachen von Metadaten eines Diensts sachgerecht erfolgt. Finden Sie unter der [benutzerdefinierter sicherer Metadatenendpunkt](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) Beispiel für ein Beispiel, das einen Metadatenendpunkt sichert.  
  
 Das Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md), implementiert die `ICalculator` Dienstvertrag. In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Damit ein Dienst Metadaten verfügbar macht, muss <xref:System.ServiceModel.Description.ServiceMetadataBehavior> für den Dienst konfiguriert werden. Wenn dieses Verhalten auftritt, können Sie Metadaten veröffentlichen, indem Sie einen Endpunkt so konfigurieren, dass er den <xref:System.ServiceModel.Description.IMetadataExchange>-Vertrag als Implementierung eines WS-MEX-(MetadataExchange-)Protokolls verfügbar macht. Zur besseren Benutzerfreundlichkeit hat dieser Vertrag den abgekürzten Konfigurationsnamen "IMetadataExchange" erhalten. In diesem Beispiel wird `mexHttpBinding` verwendet. Dies ist eine benutzerfreundliche Standardbindung, die `wsHttpBinding` mit dem Sicherheitsmodus auf `None` entspricht. Im Endpunkt wird eine relative Adresse von "mex" verwendet, die beim Auflösen der Dienstbasisadresse in einer Endpunktadresse von http://localhost/servicemodelsamples/service.svc/mex resultiert. Im Folgenden wird die Verhaltenskonfiguration gezeigt:  
  
```xml  
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
  
 Im Folgenden wird der MEX-Endpunkt gezeigt:  
  
```xml  
<!-- the MEX endpoint is exposed at   
     http://localhost/servicemodelsamples/service.svc/mex   
     To expose the IMetadataExchange contract, you   
     must enable the serviceMetadata behavior as demonstrated                           
     previously. -->  
<endpoint address="mex"  
          binding="mexHttpBinding"  
          contract="IMetadataExchange" />  
```  
  
 In diesem Beispiel wird die <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A>-Eigenschaft auf `true` festgelegt, wodurch auch die Metadaten der Dienste mit HTTP GET verfügbar gemacht werden. Um einen HTTP GET-Metadatenendpunkt zu aktivieren, muss der Dienst eine HTTP-Basisadresse haben. Die Abfragezeichenfolge `?wsdl` wird auf die Basisadresse des Diensts angewendet, um auf die Metadaten zuzugreifen. Wenn Sie beispielsweise die WSDL für den Dienst einem Webbrowser anzeigen möchten, verwenden Sie die Adresse http://localhost/servicemodelsamples/service.svc?wsdl. Alternativ können Sie dieses Verhalten verwenden, um Metadaten durch Festlegen von <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> auf `true` über HTTPS verfügbar zu machen. Dies erfordert eine HTTPS-Basisadresse.  
  
 Der Dienst MEX-Endpunkt verwendet den Zugriff auf die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
 `svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs`  
  
 Dadurch wird ein Client auf der Grundlage der Metadaten des Diensts generiert.  
  
 Greifen Sie mit HTTP GET auf die Metadaten des Diensts zu, indem Sie Ihren Browser auf http://localhost/servicemodelsamples/service.svc?wsdl verweisen.  
  
 Wenn Sie dieses Verhalten entfernen und versuchen, den Dienst zu öffnen, erhalten Sie einen Ausnahmefehler. Dieser Fehler tritt auf, da der mit dem `IMetadataExchange`-Vertrag konfigurierte Endpunkt ohne das Verhalten keine Implementierung hat.  
  
 Wenn Sie `HttpGetEnabled` auf `false` festlegen, wird anstelle der Metadaten des Diensts die CalculatorService-Hilfeseite angezeigt.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Metadata`  
  
## <a name="see-also"></a>Siehe auch
