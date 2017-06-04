---
title: "Instanziierung | Microsoft Docs"
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
  - "Beispiel zur Instanziierung [Windows Communication Foundation]"
  - "Dienstverhalten, Beispiel zur Instanziierung"
ms.assetid: c290fa54-f6ae-45a1-9186-d9504ebc6ee6
caps.latest.revision: 40
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 40
---
# Instanziierung
Im Beispiel zur Instanziierung wird die Einstellung zum Instanziierungsverhalten veranschaulicht, die steuert, wie Instanzen einer Dienstklasse als Reaktion auf Clientanforderungen erstellt werden.  Das Beispiel basiert auf dem [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md), das den `ICalculator`\-Dienstvertrag implementiert.  In diesem Beispiel wird ein neuer Vertrag \(`ICalculatorInstance`\) definiert, der von `ICalculator` erbt.  Der von `ICalculatorInstance` angegebene Vertrag stellt drei zusätzliche Vorgänge zum Überprüfen des Zustands der Dienstinstanz bereit.  Indem Sie die Einstellung für die Instanziierung ändern, können Sie Änderungen im Verhalten beobachten, wenn Sie den Client ausführen.  
  
 In diesem Beispiel ist der Client eine Konsolenanwendung \(.exe\), und der Dienst wird von IIS \(Internet Information Services, Internetinformationsdienste\) gehostet.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Es stehen die folgenden Instanziierungsmodi zur Verfügung:  
  
-   <xref:System.ServiceModel.InstanceContextMode>: Für jede Clientanforderung wird eine neue Instanz erstellt.  
  
-   <xref:System.ServiceModel.InstanceContextMode>: Für jede neue Clientsitzung wird eine neue Instanz erstellt und für die Lebensdauer dieser Sitzung aufrechterhalten. Hierfür ist eine Bindung erforderlich, die Sitzungen unterstützt.  
  
-   <xref:System.ServiceModel.InstanceContextMode>: Alle Clientanforderungen werden während der Lebensdauer der Anwendung von einer Instanz der Dienstklasse verarbeitet.  
  
 Die Dienstklasse gibt das Instanziierungsverhalten mit dem `[ServiceBehavior(InstanceContextMode=<setting>)]`\-Attribut an, wie im folgenden Beispielcode dargestellt.  Indem Sie unterschiedliche Zeilen auskommentieren, können Sie das Verhalten der einzelnen Instanzmodi beobachten.  Denken Sie daran, den Dienst nach dem Ändern des Instanziierungsmodus neu zu erstellen.  Es gibt keine Einstellungen in Bezug auf die Instanziierung, die auf dem Client angegeben werden.  
  
```  
// Enable one of the following instance modes to compare instancing behaviors.  
 [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
  
// PerCall creates a new instance for each operation.  
//[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerCall)]  
  
// Singleton creates a single instance for application lifetime.  
//[ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
public class CalculatorService : ICalculatorInstance  
{  
    static Object syncObject = new object();  
    static int instanceCount;  
    int instanceId;  
    int operationCount;  
  
    public CalculatorService()  
    {  
        lock (syncObject)  
        {  
            instanceCount++;  
            instanceId = instanceCount;  
        }  
    }  
  
    public double Add(double n1, double n2)  
    {  
        operationCount++;  
        return n1 + n2;  
    }  
  
    public double Subtract(double n1, double n2)  
    {  
        Interlocked.Increment(ref operationCount);  
        return n1 - n2;  
    }  
  
    public double Multiply(double n1, double n2)  
    {  
        Interlocked.Increment(ref operationCount);  
        return n1 * n2;  
    }  
  
    public double Divide(double n1, double n2)  
    {  
        Interlocked.Increment(ref operationCount);  
        return n1 / n2;  
    }  
  
    public string GetInstanceContextMode()  
    {   // Return the InstanceContextMode of the service  
        ServiceHost host = (ServiceHost)OperationContext.Current.Host;  
        ServiceBehaviorAttribute behavior = host.Description.Behaviors.Find<ServiceBehaviorAttribute>();  
        return behavior.InstanceContextMode.ToString();  
    }  
  
    public int GetInstanceId()  
    {   // Return the id for this instance  
        return instanceId;  
    }  
  
    public int GetOperationCount()  
    {   // Return the number of ICalculator operations performed   
        // on this instance  
        lock (syncObject)  
        {  
            return operationCount;  
        }  
    }  
}  
  
static void Main()  
{  
    // Create a client.  
    CalculatorInstanceClient client = new CalculatorInstanceClient();  
    string instanceMode = client.GetInstanceContextMode();  
    Console.WriteLine("InstanceContextMode: {0}", instanceMode);  
    DoCalculations(client);  
  
    // Create a second client.  
    CalculatorInstanceClient client2 = new CalculatorInstanceClient();  
  
    DoCalculations(client2);  
  
    Console.WriteLine();  
    Console.WriteLine("Press <ENTER> to terminate client.");  
    Console.ReadLine();  
}  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.  Es wird der Instanzmodus angezeigt, unter dem der Dienst ausgeführt wird.  Nach jedem Vorgang werden die Instanz\-ID und die Vorgangsanzahl angezeigt, um das Verhalten des Instanziierungsmodus darzustellen.  Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
### So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Zum Erstellen der C\#\- oder Visual Basic .NET\-Edition der Projektmappe befolgen Sie die unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md) aufgeführten Anweisungen.  
  
3.  Um das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend auszuführen, befolgen Sie die Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.  Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.  Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Instancing`  
  
## Siehe auch