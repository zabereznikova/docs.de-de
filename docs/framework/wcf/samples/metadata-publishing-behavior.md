---
title: Metadatenveröffentlichungsverhalten
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, metadata publishing sample
- Metadata Publishing Behaviors Sample [Windows Communication Foundation]
ms.assetid: 78c13633-d026-4814-910e-1c801cffdac7
ms.openlocfilehash: dade6d1a53fd99b994fb3c027db4e51392bfdcda
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144395"
---
# <a name="metadata-publishing-behavior"></a>Metadatenveröffentlichungsverhalten
Das Beispiel für das Metadatenveröffentlichungsverhalten verdeutlicht, wie die Metadatenveröffentlichungsfeatures eines Diensts gesteuert werden. Um die unbeabsichtigte Offenlegung potenziell vertraulicher Dienstmetadaten zu verhindern, deaktiviert die Standardkonfiguration für Windows Communication Foundation (WCF)-Dienste die Metadatenveröffentlichung. Dieses Verhalten ist in der Standardeinstellung sicher, bedeutet aber auch, dass man den zum Aufrufen des Diensts erforderlichen Clientcode nicht mithilfe eines Tools zum Importieren von Metadaten (wie Svcutil.exe) generieren kann. Dies ist nur dann möglich, wenn das Verhalten des Diensts zum Veröffentlichen von Metadaten in der Konfiguration explizit aktiviert ist.  
  
> [!IMPORTANT]
> Beachten Sie, dass in diesem Beispiel die Erstellung eines ungesicherten Metadaten-Veröffentlichungsendpunkts veranschaulicht wird. Solche Endpunkte können für anonyme, nicht authentifizierte Benutzer möglicherweise verfügbar sein. Daher muss beim Bereitstellen solcher Endpunkte sorgfältig darauf geachtet werden, dass das Öffentlichmachen von Metadaten eines Diensts sachgerecht erfolgt. Ein Beispiel, das einen Metadatenendpunkt sichert, finden Sie im [Beispiel für benutzerdefinierte sichere Metadatenendpunkte.](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)  
  
 Das Beispiel basiert auf dem [Ersten](../../../../docs/framework/wcf/samples/getting-started-sample.md)Schritte `ICalculator` , das den Servicevertrag implementiert. In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Damit ein Dienst Metadaten verfügbar macht, muss <xref:System.ServiceModel.Description.ServiceMetadataBehavior> für den Dienst konfiguriert werden. Wenn dieses Verhalten auftritt, können Sie Metadaten veröffentlichen, indem Sie einen Endpunkt so konfigurieren, dass er den <xref:System.ServiceModel.Description.IMetadataExchange>-Vertrag als Implementierung eines WS-MEX-(MetadataExchange-)Protokolls verfügbar macht. Zur besseren Benutzerfreundlichkeit hat dieser Vertrag den abgekürzten Konfigurationsnamen "IMetadataExchange" erhalten. In diesem Beispiel wird `mexHttpBinding` verwendet. Dies ist eine benutzerfreundliche Standardbindung, die `wsHttpBinding` mit dem Sicherheitsmodus auf `None` entspricht. Eine relative Adresse von "mex" wird im Endpunkt verwendet, die, wenn sie `http://localhost/servicemodelsamples/service.svc/mex`für die Dienstbasisadresse aufgelöst wird, zu einer Endpunktadresse von führt. Im Folgenden wird die Verhaltenskonfiguration gezeigt:  
  
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
  
 In diesem Beispiel wird die <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A>-Eigenschaft auf `true` festgelegt, wodurch auch die Metadaten der Dienste mit HTTP GET verfügbar gemacht werden. Um einen HTTP GET-Metadatenendpunkt zu aktivieren, muss der Dienst eine HTTP-Basisadresse haben. Die Abfragezeichenfolge `?wsdl` wird auf die Basisadresse des Diensts angewendet, um auf die Metadaten zuzugreifen. Um beispielsweise die WSDL für den Dienst in einem Webbrowser `http://localhost/servicemodelsamples/service.svc?wsdl`anzuzeigen, verwenden Sie die Adresse . Alternativ können Sie dieses Verhalten verwenden, um Metadaten durch Festlegen von <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> auf `true` über HTTPS verfügbar zu machen. Dies erfordert eine HTTPS-Basisadresse.  
  
 Um auf den MEX-Endpunkt des Dienstes zuzugreifen, verwenden Sie das [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
 `svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs`  
  
 Dadurch wird ein Client auf der Grundlage der Metadaten des Diensts generiert.  
  
 Um über HTTP GET auf die Metadaten des `http://localhost/servicemodelsamples/service.svc?wsdl`Dienstes zuzugreifen, verweisen Sie Ihren Browser auf .  
  
 Wenn Sie dieses Verhalten entfernen und versuchen, den Dienst zu öffnen, erhalten Sie einen Ausnahmefehler. Dieser Fehler tritt auf, da der mit dem `IMetadataExchange`-Vertrag konfigurierte Endpunkt ohne das Verhalten keine Implementierung hat.  
  
 Wenn Sie `HttpGetEnabled` auf `false` festlegen, wird anstelle der Metadaten des Diensts die CalculatorService-Hilfeseite angezeigt.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setupverfahren für die Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)durchgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem oder einer maschinellen Konfiguration auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Metadata`  
