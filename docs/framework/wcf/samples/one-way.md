---
title: Unidirektional
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74e3e03d-cd15-4191-a6a5-1efa2dcb9e73
caps.latest.revision: "26"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 05dbd465345f3b0cd9506f581f1a779f834c50fe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="one-way"></a>Unidirektional
In diesem Beispiel wird ein Dienstvertrag mit unidirektionalen Dienstvorgängen veranschaulicht. Der Client wartet nicht darauf, dass Dienstvorgänge abgeschlossen sind, wie es bei bidirektionalen Dienstvorgängen der Fall ist. Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) und verwendet die `wsHttpBinding` Bindung. Der Dienst ist in diesem Beispiel eine selbst gehostete Konsolenanwendung, sodass Sie den Dienst beobachten können, der Nachrichten empfängt und verarbeitet. Der Client ist auch eine Konsolenanwendung.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Wenn Sie einen unidirektionalen Dienstvertrag erstellen möchten, wenden Sie die <xref:System.ServiceModel.OperationContractAttribute>-Klasse auf alle Vorgänge an, und legen Sie <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> auf `true` fest, wie im folgenden Beispielcode dargestellt:  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOneWayCalculator  
{  
    [OperationContract(IsOneWay=true)]  
    void Add(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Subtract(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Multiply(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Divide(double n1, double n2);  
}  
```  
  
 Um zu veranschaulichen, dass der Client nicht auf das Abschließen von Dienstvorgängen wartet, implementiert der Dienstcode in diesem Beispiel eine Verzögerung von fünf Sekunden, wie im folgenden Beispielcode dargestellt:  
  
```  
/ This service class implements the service contract.  
// This code writes output to the console window.  
 [ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Multiple,  
    InstanceContextMode = InstanceContextMode.PerCall)]  
public class CalculatorService : IOneWayCalculator  
{  
    public void Add(double n1, double n2)  
    {  
        Console.WriteLine("Received Add({0},{1}) - sleeping", n1, n2);  
        System.Threading.Thread.Sleep(1000 * 5);  
        double result = n1 + n2;  
        Console.WriteLine("Processing Add({0},{1}) - result: {2}", n1, n2, result);  
    }  
    ...  
}  
```  
  
 Wenn der Client den Dienst aufruft, wird der Aufruf zurückgegeben, ohne auf das Abschließen des Dienstvorgangs zu warten.  
  
 Wenn Sie das Beispiel ausführen, werden die Client- und Dienstaktivitäten sowohl im Dienst- als auch im Clientkonsolenfenster angezeigt. Sie können sehen, wie der Dienst Nachrichten vom Client empfängt. Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.  
  
 Der Client wird vor dem Dienst beendet und veranschaulicht damit, dass ein Client nicht auf das Abschließen unidirektionaler Dienstvorgänge warten muss. Die Clientausgabe lautet wie folgt:  
  
```  
Add(100,15.99)  
Subtract(145,76.54)  
Multiply(9,81.25)  
Divide(22,7)  
  
Press <ENTER> to terminate client.  
```  
  
 Die folgende Dienstausgabe wird angezeigt:  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Received Add(100,15.99) - sleeping  
Received Subtract(145,76.54) - sleeping  
Received Multiply(9,81.25) - sleeping  
Received Divide(22,7) - sleeping  
Processing Add(100,15.99) - result: 115.99  
Processing Subtract(145,76.54) - result: 68.46  
Processing Multiply(9,81.25) - result: 731.25  
Processing Divide(22,7) - result: 3.14285714285714  
```  
  
> [!NOTE]
>  HTTP ist per Definition ein Anforderungs-/Antwortprotokoll: wenn eine Anforderung gestellt wird, wird eine Antwort zurückgegeben. Dies gilt sogar für einen unidirektionalen Dienstvorgang, der über HTTP verfügbar gemacht wird. Wenn der Vorgang aufgerufen wird, gibt der Dienst den HTTP-Statuscode 202 zurück, bevor der Dienstvorgang ausgeführt wird. Dieser Statuscode bedeutet, dass die Anforderung zur Verarbeitung akzeptiert, die Verarbeitung jedoch noch nicht abgeschlossen wurde. Der den Vorgang aufrufende Client wird so lange blockiert, bis er die 202-Antwort vom Dienst empfängt. Dadurch kann es zu unerwartetem Verhalten kommen, wenn mehrere unidirektionale Nachrichten mithilfe einer Bindung gesendet werden, die für die Verwendung von Sitzungen konfiguriert ist. Die in diesem Beispiel verwendete `wsHttpBinding`-Bindung wird so konfiguriert, dass standardmäßig Sitzungen verwendet werden, um einen Sicherheitskontext herzustellen. Standardmäßig treffen Nachrichten in einer Sitzung in der Reihenfolge ihres Versands ein. Aus diesem Grund wird die zweite Nachricht in einer Sitzung beim Senden erst nach dem Verarbeiten der ersten Nachricht verarbeitet. Das führt dazu, dass der Client erst dann die 202-Antwort für eine Nachricht empfängt, wenn die Verarbeitung der vorhergehenden Nachricht abgeschlossen wurde. Der Client scheint daher bei jedem nachfolgenden Vorgangsaufruf zu blockieren. Um dieses Verhalten zu vermeiden, wird in diesem Beispiel die Laufzeit so konfiguriert, dass Nachrichten gleichzeitig an unterschiedliche Instanzen zur Verarbeitung gesendet werden. Im Beispiel wird <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> auf `PerCall` festgelegt, sodass jede Nachricht von einer anderen Instanz verarbeitet werden kann. <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> ist auf `Multiple` festgelegt, damit mehrere Threads gleichzeitig Nachrichten senden können.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!NOTE]
>  Starten Sie den Dienst vor dem Client, und beenden Sie den Client vor dem Dienst. Dadurch wird eine Clientausnahme vermieden, wenn der Client die Sicherheitssitzung nicht ordnungsgemäß beenden kann, da der Dienst nicht mehr vorhanden ist.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Oneway`  
  
## <a name="see-also"></a>Siehe auch
