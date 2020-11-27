---
title: Mehrere Verträge
ms.date: 03/30/2017
ms.assetid: 2bef319b-fe9c-4d49-ac6c-dfb23eb35099
ms.openlocfilehash: 516867a2fd7d6ba0ca1eb6cc3b51c68769b46aba
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96260201"
---
# <a name="multiple-contracts"></a>Mehrere Verträge

Das Beispiel zu mehreren Verträgen zeigt, wie mehr als ein Vertrag für einen Dienst implementiert wird und wie Endpunkte zur Kommunikation mit den einzelnen implementierten Verträgen konfiguriert werden. Dieses Beispiel basiert [auf den ersten](getting-started-sample.md)Schritten. Der Dienst wurde so geändert, dass zwei Verträge definiert sind – der `ICalculator`-Vertrag und der `ICalculatorSession`-Vertrag.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
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
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\MultipleContracts`  
