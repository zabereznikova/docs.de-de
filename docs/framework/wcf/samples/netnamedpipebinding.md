---
title: "NetNamedPipeBinding | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Net-Profil – Benannte Pipe"
ms.assetid: e78e845f-c325-46e2-927d-81616f97f7d5
caps.latest.revision: 34
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 34
---
# NetNamedPipeBinding
In diesem Beispiel wird die `netNamedPipeBinding`\-Bindung, die prozessübergreifende Kommunikation auf dem gleichen Computer bereitstellt, veranschaulicht.  Benannte Pipes funktionieren nicht computerübergreifend.  Dieses Beispiel beruht auf dem [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md)\-Rechnerdienst.  
  
 In diesem Beispiel ist der Dienst selbst gehostet.  Sowohl der Client als auch der Dienst sind Konsolenanwendungen.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Die Bindung wird in den Konfigurationsdateien für den Client und Dienst angegeben.  Der Bindungstyp wird mit dem `binding`\-Attribut des [\<endpoint\>](http://msdn.microsoft.com/de-de/13aa23b7-2f08-4add-8dbf-a99f8127c017)\-Elements angegeben \(siehe folgende Beispielkonfiguration\).  
  
```  
<endpoint address="net.pipe://localhost/ServiceModelSamples/service"  
          binding="netNamedPipeBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 Im vorigen Beispiel wird gezeigt, wie ein Endpunkt für die Verwendung der `netNamedPipeBinding`\-Bindung mit den Standardeinstellungen konfiguriert wird.  Wenn Sie die`netNamedPipeBinding`\-Bindung konfigurieren und einige der Einstellungen ändern möchten, müssen Sie eine Bindungskonfiguration definieren.  Der Endpunkt muss auf die Bindungskonfiguration mithilfe des `bindingConfiguration`\-Attributs mit einem Namen verweisen.  
  
```  
<endpoint address="net.pipe://localhost/ServiceModelSamples/service"  
          binding="netNamedPipeBinding"  
          bindingConfiguration="Binding1"   
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 In diesem Beispiel heißt die Bindungskonfiguration `Binding1` und ist wie folgt definiert:  
  
```  
<bindings>  
  <!--   
        Following is the expanded configuration section for a NetNamedPipeBinding.  
        Each property is configured with the default value.  
     -->  
  <netNamedPipeBinding>  
    <binding name="Binding1"   
             closeTimeout="00:01:00"  
             openTimeout="00:01:00"   
             receiveTimeout="00:10:00"   
             sendTimeout="00:01:00"  
             transactionFlow="false"   
             transferMode="Buffered"   
             transactionProtocol="OleTransactions"  
             hostNameComparisonMode="StrongWildcard"   
             maxBufferPoolSize="524288"  
             maxBufferSize="65536"   
             maxConnections="10"   
             maxReceivedMessageSize="65536">  
      <security mode="Transport">  
        <transport protectionLevel="EncryptAndSign" />  
      </security>  
    </binding>  
  </netNamedPipeBinding>  
</bindings>  
  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.  Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```  
  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Zum Erstellen der C\#\- oder Visual Basic .NET\-Edition der Projektmappe befolgen Sie die unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md) aufgeführten Anweisungen.  
  
3.  Wenn Sie das Beispiel in einer Konfiguration mit einem einzigen Computer ausführen möchten, befolgen Sie die in [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md) aufgeführten Anweisungen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.  Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.  Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples\WCF\Basic\Binding\Net\NamedPipe`  
  
## Siehe auch