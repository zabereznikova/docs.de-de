---
title: Mehrere Verträge
ms.date: 03/30/2017
ms.assetid: 2bef319b-fe9c-4d49-ac6c-dfb23eb35099
ms.openlocfilehash: 5e52c83d69c15ca5c407240a8971248205fef832
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818336"
---
# <a name="multiple-contracts"></a>Mehrere Verträge
Das Beispiel zu mehreren Verträgen zeigt, wie mehr als ein Vertrag für einen Dienst implementiert wird und wie Endpunkte zur Kommunikation mit den einzelnen implementierten Verträgen konfiguriert werden. Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md). Der Dienst wurde so geändert, dass zwei Verträge definiert sind – der `ICalculator`-Vertrag und der `ICalculatorSession`-Vertrag.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Die Dienstklasse implementiert sowohl den `ICalculator`-Vertrag als auch den `ICalculatorSession`-Vertrag. Da für einen der Verträge eine Sitzung erforderlich ist, verwendet der Dienst den <xref:System.ServiceModel.InstanceContextMode.PerSession>-Instanzmodus, um den Status während der Lebensdauer der Sitzung zu verwalten.  
  
 Die Dienstkonfiguration wurde so geändert, dass nun zwei Endpunkte definiert sind, um jeden der beiden Verträge zugänglich zu machen. Der `ICalculator`-Endpunkt wird an der Basisadresse mit einer `basicHttpBinding` verfügbar gemacht. Der `ICalculatorSession`-Endpunkt wird an der Basisadresse/in der Sitzung mit einer `wsHttpBinding` verfügbar gemacht, wobei für das `bindingConfiguration`-Attribut `BindingWithSession` festgelegt ist, wie in der folgenden Beispielkonfiguration gezeigt.  
  
```xml  
<service   
    name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">  
  <!-- ICalculator endpoint is exposed using BasicBinding at the base  
       address provided by host:   
       http://localhost/servicemodelsamples/service.svc  -->  
  <endpoint address=""  
            binding="basicHttpBinding"  
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  <!-- ICalculatorSession endpoint is exposed using BindingWithSession  
       at {baseaddress}/session:  
       http://localhost/servicemodelsamples/service.svc/session -->  
  <endpoint address="session"  
            binding="wsHttpBinding"  
            bindingConfiguration="BindingWithSession"   
           contract="Microsoft.ServiceModel.Samples.ICalculatorSession" />  
  ...  
</service>  
```  
  
 Der generierte Clientcode enthält nun eine Clientklasse für den ursprünglichen `ICalculator`-Vertrag und für den neuen `ICalculatorSession`-Vertrag. Die Clientkonfiguration und der Code wurden geändert, um mit jedem Vertrag am entsprechenden Dienstendpunkt zu kommunizieren.  
  
 Der Client ist eine Konsolen-Windows-Anwendung (.exe). Der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.  
  
 Das Clientkonsolenfenster zeigt die an jeden Endpunkt gesendeten Vorgänge an (zuerst den Basisendpunkt, dann den sicheren Endpunkt).  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\MultipleContracts`  
  
