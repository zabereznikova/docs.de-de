---
title: Selbst gehostete Dienste
ms.date: 03/30/2017
helpviewer_keywords:
- Self hosted service
- Self Host Sample [Windows Communication Foundation]
ms.assetid: 05e68661-1ddf-4abf-a899-9bb1b8272a5b
ms.openlocfilehash: 9b3e2a7bea7a0749707416e0fce7be25cf00c99e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135748"
---
# <a name="self-host"></a>Selbst gehostete Dienste
In diesem Beispiel wird das Implementieren eines selbst gehosteten Diensts in einer Konsolenanwendung veranschaulicht. Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md). Die Dienstkonfigurationsdatei wurde von "Web.config" in "App.config" umbenannt und so geändert, dass eine vom Host verwendete Basisadresse konfiguriert wird. Der Quellcode für den Dienst wurde so geändert, dass eine statische `Main`-Funktion implementiert wird. Diese erstellt und öffnet einen Diensthost, der die konfigurierte Basisadresse bereitstellt. Die Dienstimplementierung wurde geändert, sodass die Ausgabe für jeden Vorgang in der Konsole geschrieben wird. Der Client ist unverändert geblieben, er wurde nur mit der richtigen Endpunktadresse des Diensts konfiguriert.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Im Beispiel wird eine statische Hauptfunktion zum Erstellen eines <xref:System.ServiceModel.ServiceHost> für den gegebenen `CalculatorService`-Typ implementiert, wie im folgenden Beispielcode dargestellt.  
  
```csharp
// Host the service within this EXE console application.  
public static void Main()  
{  
    // Create a ServiceHost for the CalculatorService type.  
    using (ServiceHost serviceHost =   
           new ServiceHost(typeof(CalculatorService)))  
    {  
        // Open the ServiceHost to create listeners   
        // and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
    }  
}  
```  
  
 Wenn ein Dienst in Internetinformationsdienste (IIS) oder Windows Process Activation Service (WAS) gehostet wird, wird die Basisadresse des Diensts von der Hostumgebung bereitgestellt. Bei einem selbst gehosteten Dienst müssen Sie die Basisadresse selbst angeben. Dies erfolgt mithilfe der `add` -Element, untergeordnetes Element der [ \<BaseAddresses >](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md), untergeordnetes Element des [ \<Host >](../../../../docs/framework/configure-apps/file-schema/wcf/host.md), untergeordnetes Element des [ \<Dienst > ](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) wie in der folgenden Beispielkonfiguration gezeigt.  
  
```xml  
<service   
    name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
    </baseAddresses>  
  </host>  
  ...  
</service>  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Dienst- und Clientkonsolenfenster angezeigt. Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Folgen Sie den Anweisungen, um das Beispiel in einer Konfiguration für die einzelnen-Computer oder computerübergreifend auszuführen, [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\SelfHost`  
  
## <a name="see-also"></a>Siehe auch

- [AppFabric-Hosting- und -Persistenzbeispiele](https://go.microsoft.com/fwlink/?LinkId=193961)
