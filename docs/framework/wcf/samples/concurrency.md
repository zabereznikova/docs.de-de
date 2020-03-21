---
title: Parallelität
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, concurency sample
- Concurrency Sample [Windows Communication Foundation]
ms.assetid: f8dbdfb3-6858-4f95-abe3-3a1db7878926
ms.openlocfilehash: eb6140895bb922bd159f1abf536a0d0b12d4f96c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183930"
---
# <a name="concurrency"></a>Parallelität
Das Parallelitätsbeispiel veranschaulicht die Verwendung des <xref:System.ServiceModel.ServiceBehaviorAttribute> mit der <xref:System.ServiceModel.ConcurrencyMode>-Enumeration, die steuert, ob eine Instanz eines Diensts Nachrichten sequenziell oder parallel verarbeitet. Das Beispiel basiert auf dem [Ersten](../../../../docs/framework/wcf/samples/getting-started-sample.md)Schritte `ICalculator` , das den Servicevertrag implementiert. Dieses Beispiel definiert einen neuen Vertrag, `ICalculatorConcurrency`, der von `ICalculator` erbt und zwei zusätzliche Vorgänge für die Überwachung des Status der Dienstparallelität bereitstellt. Indem Sie die Einstellung für die Parallelität ändern, können Sie Änderungen im Verhalten beobachten, wenn Sie den Client ausführen.  
  
 In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Es stehen drei Parallelitätsmodi zur Verfügung:  
  
- `Single`: Jede Dienstinstanz verarbeitet jeweils nur eine Nachricht. Dies ist der Standardparallelitätsmodus.  
  
- `Multiple`: Jede Dienstinstanz verarbeitet mehrere Nachrichten gleichzeitig. Für diesen Parallelitätsmodus muss die Dienstimplementierung threadsicher sein.  
  
- `Reentrant`: Jede Dienstinstanz verarbeitet jeweils nur eine Nachricht, akzeptiert jedoch eintrittsvariante Aufrufe. Der Dienst akzeptiert diese Anrufe nur, wenn er ausruft. Reentrant wird im [Beispiel ConcurrencyMode.Reentrant](../../../../docs/framework/wcf/samples/concurrencymode-reentrant.md) demonstriert.  
  
 Die Parallelität steht mit dem Instanziierungsmodus in Beziehung. In der <xref:System.ServiceModel.InstanceContextMode.PerCall>-Instanziierung ist Parallelität nicht relevant, da jede Nachricht von einer neuen Dienstinstanz verarbeitet wird. In der <xref:System.ServiceModel.InstanceContextMode.Single>-Instanziierung ist entweder die <xref:System.ServiceModel.ConcurrencyMode.Single>- oder die <xref:System.ServiceModel.ConcurrencyMode.Multiple>-Parallelität relevant, je nachdem, ob die einzelne Instanz Nachrichten sequenziell oder parallel verarbeitet. In der <xref:System.ServiceModel.InstanceContextMode.PerSession>-Instanziierung sind möglicherweise alle Parallelitätsmodi relevant.  
  
 Die Dienstklasse gibt das Parallelitätsverhalten mit dem `[ServiceBehavior(ConcurrencyMode=<setting>)]`-Attribut an, wie im folgenden Beispielcode dargestellt. Durch wechselndes Auskommentieren der Zeilen können Sie mit den Parallelitätsmodi `Single` und `Multiple` experimentieren. Denken Sie daran, den Dienst nach dem Ändern des Parallelitätsmodus neu zu erstellen.  
  
```csharp
// Single allows a single message to be processed sequentially by each service instance.  
//[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, InstanceContextMode = InstanceContextMode.Single)]  
  
// Multiple allows concurrent processing of multiple messages by a service instance.  
// The service implementation should be thread-safe. This can be used to increase throughput.  
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple, InstanceContextMode = InstanceContextMode.Single)]  
  
// Uses Thread.Sleep to vary the execution time of each operation.  
public class CalculatorService : ICalculatorConcurrency  
{  
    int operationCount;  
  
    public double Add(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(180);  
        return n1 + n2;  
    }  
  
    public double Subtract(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(100);  
        return n1 - n2;  
    }  
  
    public double Multiply(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(150);  
        return n1 * n2;  
    }  
  
    public double Divide(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(120);  
        return n1 / n2;  
    }  
  
    public string GetConcurrencyMode()  
    {
        // Return the ConcurrencyMode of the service.  
        ServiceHost host = (ServiceHost)OperationContext.Current.Host;  
        ServiceBehaviorAttribute behavior = host.Description.Behaviors.Find<ServiceBehaviorAttribute>();  
        return behavior.ConcurrencyMode.ToString();  
    }  
  
    public int GetOperationCount()  
    {
        // Return the number of operations.  
        return operationCount;  
    }  
}  
```  
  
 Im Beispiel wird standardmäßig die <xref:System.ServiceModel.ConcurrencyMode.Multiple>-Parallelität mit der <xref:System.ServiceModel.InstanceContextMode.Single>-Instanziierung verwendet. Der Clientcode wurde geändert, um einen asynchronen Proxy zu verwenden. Auf diese Weise kann der Client mehrere Aufrufe an den Dienst ausführen, ohne zwischen den Aufrufen auf eine Antwort zu warten. Sie können das unterschiedliche Verhalten des Dienstparallelitätsmodus beobachten.  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Der vom Dienst ausgeführte Parallelitätsmodus wird angezeigt, jeder Vorgang wird aufgerufen, und anschließend wird die Anzahl der Vorgänge angezeigt. Beachten Sie, dass die Ergebnisse in einer anderen Reihenfolge als in der zurückgeben werden, in der sie aufgerufen wurden, wenn der Parallelitätsmodus `Multiple` ist, da der Dienst mehrere Nachrichten gleichzeitig verarbeitet. Wenn der Parallelitätsmodus zu `Single` geändert wird, werden die Ergebnisse in der Reihenfolge zurückgegeben, in der sie aufgerufen wurden, da alle Nachrichten sequenziell verarbeitet werden. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setupverfahren für die Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)durchgeführt haben.  
  
2. Wenn Sie Svcutil.exe zum Generieren des Proxyclients `/async` verwenden, stellen Sie sicher, dass Sie die Option einschließen.  
  
3. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
4. Um das Beispiel in einer Konfiguration mit einem oder einer maschinellen Konfiguration auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Concurrency`  
