---
title: Adressierung
ms.date: 03/30/2017
ms.assetid: d438e6f2-d0f3-43aa-b259-b51b5bda2e64
ms.openlocfilehash: 2a737552ef5ea2a8e4544f9ec2c2f84b4b994a75
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715877"
---
# <a name="addressing"></a>Adressierung
Im Beispiel für die Adressierung werden verschiedene Aspekte und Features von Endpunktadressen veranschaulicht. Das Beispiel basiert auf den ersten [Schritten.](../../../../docs/framework/wcf/samples/getting-started-sample.md) In diesem Beispiel ist der Dienst selbst gehostet. Sowohl der Dienst als auch der Client sind Konsolenanwendungen. Der Dienst definiert mehrere Endpunkte mithilfe einer Kombination aus relativen und absoluten Endpunktadressen.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Die Dienstkonfigurationsdatei gibt eine Basisadresse und vier Endpunkte an. Die Basisadresse wird mit dem Hinzufügen-Element unter service/host/baseAddresses angegeben, wie im folgenden Beispiel dargestellt.  
  
```xml  
<service name="Microsoft.ServiceModel.Samples.CalculatorService"  
         behaviorConfiguration="CalculatorServiceBehavior">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />  
    </baseAddresses>  
  </host>  
</service>  
```  
  
 Die erste Endpunktdefinition, die in der folgenden Beispielkonfiguration gezeigt wird, gibt eine relative Adresse an. Dies bedeutet, dass die Endpunktadresse eine Kombination aus der Basisadresse und der relativen Adresse nach den Regeln der URI-Zusammensetzung ist.  
  
```xml
<!-- Empty relative address specified:   
     use the base address provided by the host. -->  
<!-- The endpoint address is  
     http://localhost:8000/ServiceModelSamples/service. -->  
<endpoint address=""  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 In diesem Fall ist die relative Adresse leer (""); folglich entspricht die Endpunktadresse der Basisadresse. Die tatsächliche Endpunkt Adresse ist `http://localhost:8000/servicemodelsamples/service`.
  
 Die zweite Endpunktdefinition gibt ebenfalls eine relative Adresse an, wie in der folgenden Beispielkonfiguration dargestellt.  
  
```xml  
<!-- The relative address specified: use the base address -->  
<!-- provided by the host + path. The endpoint address is -->  
<!-- http://localhost:8000/servicemodelsamples/service/test. -->  
<endpoint address="/test"  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 Die relative Adresse "test" ist an die Basisadresse angefügt. Die tatsächliche Endpunkt Adresse ist `http://localhost:8000/servicemodelsamples/service/test`.
  
 Die dritte Endpunktdefinition gibt eine absolute Adresse an, wie in der folgenden Beispielkonfiguration dargestellt.  
  
```xml  
<endpoint address="http://localhost:8001/hello/servicemodelsamples"  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 Die Basisadresse spielt bei der Adresse keine Rolle. Die tatsächliche Endpunkt Adresse ist `http://localhost:8001/hello/servicemodelsamples`.
  
 Die vierte Endpunktadresse gibt eine absolute Adresse und einen anderen Transport an, nämlich TCP. Die Basisadresse spielt bei der Adresse keine Rolle. Die tatsächliche Endpunkt Adresse ist `net.tcp://localhost:9000/servicemodelsamples/service`.
  
```xml  
<!-- The absolute address specified, different transport: -->  
<!-- use the specified address, and ignore the base address. -->  
<!-- The endpoint address is -->  
<!-- net.tcp://localhost:9000/servicemodelsamples/service. -->  
<endpoint address=  
          "net.tcp://localhost:9000/servicemodelsamples/service"  
          binding="netTcpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
</service>  
```  
  
 Der Client greift nur auf einen der vier Dienstendpunkte zu, aber alle vier sind in seiner Konfigurationsdatei definiert. Der Client wählt einen Endpunkt aus, wenn das `CalculatorProxy`-Objekt erstellt wird. Indem Sie den Konfigurationsnamen von `CalculatorEndpoint1` bis `CalculatorEndpoint4` ändern, können Sie jeden Endpunkt testen.  
  
 Bei der Durchführung des Beispiels listet der Dienst die Adresse, den Bindungsnamen und den Vertragsnamen für jeden Endpunkt auf. Der MEX-Endpunkt (Metadata Exchange) ist aus Sicht des ServiceHost nur ein weiterer Endpunkt und wird somit ebenfalls aufgelistet.  
  
```console  
Service endpoints:  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service/test  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8001/hello/servicemodelsamples  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  net.tcp://localhost:9000/servicemodelsamples/service  
           binding:  NetTcpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service/mex  
           binding:  MetadataExchangeHttpBinding  
           contract: IMetadataExchange  
  
The service is ready.  
Press <ENTER> to terminate service.  
```  
  
 Wenn Sie den Client ausführen, werden die Anforderungen und Antworten für den Vorgang im Dienst- und Clientkonsolenfenster angezeigt. Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
    > [!NOTE]
    > Wenn Sie zur Neugenerierung der Konfiguration für dieses Beispiel die Datei Svcutil.exe verwenden, müssen Sie den Endpunktnamen in der Clientkonfiguration so ändern, dass er mit dem Clientcode übereinstimmt.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Addressing`  
