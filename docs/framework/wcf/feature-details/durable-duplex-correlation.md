---
title: Permanente Duplexkorrelation
ms.date: 03/30/2017
ms.assetid: 8eb0e49a-6d3b-4f7e-a054-0d4febee2ffb
ms.openlocfilehash: eb879c583b4454cd0062396d86e157a90db4652f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254232"
---
# <a name="durable-duplex-correlation"></a>Permanente Duplexkorrelation

Die permanente Duplexkorrelation, die auch als Rückrufkorrelation bezeichnet wird, ist nützlich, wenn für einen Workflowdienst eine Anforderung besteht, einen Rückruf an den ursprünglichen Aufrufer zu senden. Im Gegensatz zu WCF-Duplex kann der Rückruf jederzeit in der Zukunft geschehen und ist nicht an den gleichen Kanal bzw. die Kanallebensdauer gebunden. Die einzige Anforderung besteht darin, dass der Aufrufer über einen aktiven Endpunkt verfügt, der die Rückrufnachricht überwacht. Auf diese Weise können zwei Workflowdienste eine lange Konversation führen. Dieses Thema bietet eine Übersicht über die permanente Duplexkorrelation.  
  
## <a name="using-durable-duplex-correlation"></a>Verwenden der permanenten Duplexkorrelation  

 Um die permanente Duplexkorrelation zu verwenden, müssen die beiden Dienste eine kontextfähige Bindung verwenden, die bidirektionale Vorgänge unterstützt, z. B. <xref:System.ServiceModel.NetTcpContextBinding> oder <xref:System.ServiceModel.WSHttpContextBinding>. Der aufrufende Dienst registriert eine <xref:System.ServiceModel.WSHttpContextBinding.ClientCallbackAddress%2A> mit der gewünschten Bindung auf dem <xref:System.ServiceModel.Endpoint> des Clients. Der empfangende Dienst empfängt diese Daten mit dem ersten Aufruf und verwendet diese dann auf seinem eigenen <xref:System.ServiceModel.Endpoint> in der <xref:System.ServiceModel.Activities.Send>-Aktivität, die den Rückruf zum aufrufenden Dienst ausführt. In diesem Beispiel kommunizieren zwei Dienste miteinander. Der erste Dienst ruft eine Methode auf dem zweiten Dienst auf und wartet dann auf eine Antwort. Der zweite Dienst kennt den Namen der Rückrufmethode, aber der Endpunkt des Diensts, der diese Methode implementiert, ist zur Entwurfszeit nicht bekannt.  
  
> [!NOTE]
> Permanenter Duplex kann nur verwendet werden, wenn die <xref:System.ServiceModel.Channels.AddressingVersion> des Endpunkts mit <xref:System.ServiceModel.Channels.AddressingVersion.WSAddressing10%2A> konfiguriert wird. Wenn dies nicht der Fall ist, <xref:System.InvalidOperationException> wird eine Ausnahme mit der folgenden Meldung ausgelöst: "die Nachricht enthält einen Rückruf Kontext Header mit einem Endpunkt Verweis für [AddressingVersion](http://schemas.xmlsoap.org/ws/2004/08/addressing). Der Rückruf Kontext kann nur übertragen werden, wenn AddressingVersion mit "WSAddressing10" konfiguriert ist.
  
 Im folgenden Beispiel wird ein Workflowdienst gehostet, der mithilfe von <xref:System.ServiceModel.Endpoint> einen <xref:System.ServiceModel.WSHttpContextBinding> für den Rückruf erstellt.  
  
```csharp  
// Host WF Service 1.  
string baseAddress1 = "http://localhost:8080/Service1";  
WorkflowServiceHost host1 = new WorkflowServiceHost(GetWF1(), new Uri(baseAddress1));  
  
// Add the callback endpoint.  
WSHttpContextBinding Binding1 = new WSHttpContextBinding();  
host1.AddServiceEndpoint("ICallbackItemsReady", Binding1, "ItemsReady");  
  
// Add the service endpoint.  
host1.AddServiceEndpoint("IService1", Binding1, baseAddress1);  
  
// Open the first workflow service.  
host1.Open();  
Console.WriteLine("Service1 waiting at: {0}", baseAddress1);  
```  
  
 Der Workflow, der diesen Workflowdienst implementiert, initialisiert die Rückrufkorrelation mit seiner <xref:System.ServiceModel.Activities.Send>-Aktivität. Er verweist in der <xref:System.ServiceModel.Activities.Receive>-Aktivität, die mit <xref:System.ServiceModel.Activities.Send> korreliert, auf diesen Rückrufendpunkt. Im folgenden Beispiel ist der Workflow dargestellt, der von der `GetWF1`-Methode zurückgegeben wird.  
  
```csharp  
Variable<CorrelationHandle> CallbackHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = "IService1",  
    OperationName = "StartOrder"  
};  
  
Send GetItems = new Send  
{  
    CorrelationInitializers =
    {  
        new CallbackCorrelationInitializer  
        {  
            CorrelationHandle = CallbackHandle  
        }  
    },  
    ServiceContractName = "IService2",  
    OperationName = "StartItems",  
    Endpoint = new Endpoint  
    {  
        AddressUri = new Uri("http://localhost:8081/Service2"),  
        Binding = new WSHttpContextBinding  
        {  
            ClientCallbackAddress = new Uri("http://localhost:8080/Service1/ItemsReady")
        }  
    }  
};  
  
Receive ItemsReady = new Receive  
{  
    ServiceContractName = "ICallbackItemsReady",  
    OperationName = "ItemsReady",  
    CorrelatesWith = CallbackHandle,  
};  
  
Activity wf = new Sequence  
{  
    Variables =  
    {  
        CallbackHandle  
    },  
    Activities =  
    {  
        StartOrder,  
        new WriteLine  
        {  
            Text = "WF1 - Started"  
        },  
        GetItems,  
        new WriteLine  
        {  
            Text = "WF1 - Request Submitted"  
        },  
        ItemsReady,  
        new WriteLine  
        {  
            Text = "WF1 - Items Received"  
        }  
     }  
};  
```  
  
 Der zweite Workflowdienst wird mit einer vom System bereitgestellten, kontextbasierten Bindung gehostet.  
  
```csharp  
// Host WF Service 2.  
string baseAddress2 = "http://localhost:8081/Service2";  
WorkflowServiceHost host2 = new WorkflowServiceHost(GetWF2(), new Uri(baseAddress2));  
  
// Add the service endpoint.  
WSHttpContextBinding Binding2 = new WSHttpContextBinding();  
host2.AddServiceEndpoint("IService2", Binding2, baseAddress2);  
  
// Open the second workflow service.  
host2.Open();  
Console.WriteLine("Service2 waiting at: {0}", baseAddress2);  
```  
  
 Der Workflow, der diesen Workflowdienst implementiert, beginnt mit einer <xref:System.ServiceModel.Activities.Receive>-Aktivität. Diese Empfangsaktivität initialisiert die Rückrufkorrelation für diesen Dienst, verwendet eine Verzögerung als Simulation eines längeren Arbeitsvorgangs und führt dann den Rückruf an den ersten Dienst aus. Dafür wird der Rückrufkontext verwendet, der beim ersten Aufruf an den Dienst übergeben wurde. Im folgenden Beispiel ist der Workflow dargestellt, der bei einem Aufruf der `GetWF2`-Methode zurückgegeben wird. Beachten Sie, dass die <xref:System.ServiceModel.Activities.Send>-Aktivität über die Platzhalteradresse `http://www.contoso.com` verfügt. Die zur Laufzeit verwendete tatsächliche Adresse ist die angegebene Rückrufadresse.  
  
```csharp  
Variable<CorrelationHandle> ItemsCallbackHandle = new Variable<CorrelationHandle>();  
  
Receive StartItems = new Receive  
{  
    CorrelationInitializers =
    {  
        new CallbackCorrelationInitializer  
        {  
            CorrelationHandle = ItemsCallbackHandle  
        }  
    },  
    CanCreateInstance = true,  
    ServiceContractName = "IService2",  
    OperationName = "StartItems"  
};  
  
Send ItemsReady = new Send  
{  
    CorrelatesWith = ItemsCallbackHandle,  
    Endpoint = new Endpoint  
    {  
        // The callback address on the binding is used  
        // instead of this placeholder address.  
        AddressUri = new Uri("http://www.contoso.com"),  
  
        Binding = new WSHttpContextBinding()  
    },  
    OperationName = "ItemsReady",  
    ServiceContractName = "ICallbackItemsReady"  
};  
  
Activity wf = new Sequence  
{  
    Variables =  
    {  
        ItemsCallbackHandle  
    },  
    Activities =  
    {  
        StartItems,  
        new WriteLine  
        {  
            Text = "WF2 - Request Received"  
        },  
        new Delay  
        {  
            Duration = TimeSpan.FromMinutes(90)  
        },  
        new WriteLine  
        {  
            Text = "WF2 - Sending items"  
        },  
        ItemsReady,  
        new WriteLine  
        {  
            Text = "WF2 - Items sent"  
        }  
     }  
};  
```  
  
 Wenn die `StartOrder`-Methode für den ersten Workflow aufgerufen wird, wird die folgende Ausgabe angezeigt. Die Ausgabe verdeutlicht den Ausführungsfluss durch die beiden Workflows.  
  
```output  
Service1 waiting at: http://localhost:8080/Service1  
Service2 waiting at: http://localhost:8081/Service2  
Press enter to exit.
WF1 - Started  
WF2 - Request Received  
WF1 - Request Submitted  
WF2 - Sending items  
WF2 - Items sent  
WF1 - Items Received  
```  
  
 In diesem Beispiel verwalten beide Workflows die Korrelation explizit mithilfe eines <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer>-Objekts. Da in diesen Beispielworkflows nur eine einzelne Korrelation vorhanden war, reicht die <xref:System.ServiceModel.Activities.CorrelationHandle>-Standardverwaltung in diesem Fall aus.
