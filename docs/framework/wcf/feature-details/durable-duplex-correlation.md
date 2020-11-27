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
# <a name="durable-duplex-correlation"></a><span data-ttu-id="98b6e-102">Permanente Duplexkorrelation</span><span class="sxs-lookup"><span data-stu-id="98b6e-102">Durable Duplex Correlation</span></span>

<span data-ttu-id="98b6e-103">Die permanente Duplexkorrelation, die auch als Rückrufkorrelation bezeichnet wird, ist nützlich, wenn für einen Workflowdienst eine Anforderung besteht, einen Rückruf an den ursprünglichen Aufrufer zu senden.</span><span class="sxs-lookup"><span data-stu-id="98b6e-103">Durable duplex correlation, also known as callback correlation, is useful when a workflow service has a requirement to send a callback to the initial caller.</span></span> <span data-ttu-id="98b6e-104">Im Gegensatz zu WCF-Duplex kann der Rückruf jederzeit in der Zukunft geschehen und ist nicht an den gleichen Kanal bzw. die Kanallebensdauer gebunden. Die einzige Anforderung besteht darin, dass der Aufrufer über einen aktiven Endpunkt verfügt, der die Rückrufnachricht überwacht.</span><span class="sxs-lookup"><span data-stu-id="98b6e-104">Unlike WCF duplex, the callback can happen at any time in the future and is not tied to the same channel or the channel lifetime; the only requirement is that the caller have an active endpoint listening for the callback message.</span></span> <span data-ttu-id="98b6e-105">Auf diese Weise können zwei Workflowdienste eine lange Konversation führen.</span><span class="sxs-lookup"><span data-stu-id="98b6e-105">This allows two workflow services to communicate in a long-running conversation.</span></span> <span data-ttu-id="98b6e-106">Dieses Thema bietet eine Übersicht über die permanente Duplexkorrelation.</span><span class="sxs-lookup"><span data-stu-id="98b6e-106">This topic provides an overview of durable duplex correlation.</span></span>  
  
## <a name="using-durable-duplex-correlation"></a><span data-ttu-id="98b6e-107">Verwenden der permanenten Duplexkorrelation</span><span class="sxs-lookup"><span data-stu-id="98b6e-107">Using Durable Duplex Correlation</span></span>  

 <span data-ttu-id="98b6e-108">Um die permanente Duplexkorrelation zu verwenden, müssen die beiden Dienste eine kontextfähige Bindung verwenden, die bidirektionale Vorgänge unterstützt, z. B. <xref:System.ServiceModel.NetTcpContextBinding> oder <xref:System.ServiceModel.WSHttpContextBinding>.</span><span class="sxs-lookup"><span data-stu-id="98b6e-108">To use durable duplex correlation, the two services must use a context-enabled binding that supports two-way operations, such as <xref:System.ServiceModel.NetTcpContextBinding> or <xref:System.ServiceModel.WSHttpContextBinding>.</span></span> <span data-ttu-id="98b6e-109">Der aufrufende Dienst registriert eine <xref:System.ServiceModel.WSHttpContextBinding.ClientCallbackAddress%2A> mit der gewünschten Bindung auf dem <xref:System.ServiceModel.Endpoint> des Clients.</span><span class="sxs-lookup"><span data-stu-id="98b6e-109">The calling service registers a <xref:System.ServiceModel.WSHttpContextBinding.ClientCallbackAddress%2A> with the desired binding on their client <xref:System.ServiceModel.Endpoint>.</span></span> <span data-ttu-id="98b6e-110">Der empfangende Dienst empfängt diese Daten mit dem ersten Aufruf und verwendet diese dann auf seinem eigenen <xref:System.ServiceModel.Endpoint> in der <xref:System.ServiceModel.Activities.Send>-Aktivität, die den Rückruf zum aufrufenden Dienst ausführt.</span><span class="sxs-lookup"><span data-stu-id="98b6e-110">The receiving service receives this data in the initial call and then uses it on its own <xref:System.ServiceModel.Endpoint> in the <xref:System.ServiceModel.Activities.Send> activity that makes the call back to the calling service.</span></span> <span data-ttu-id="98b6e-111">In diesem Beispiel kommunizieren zwei Dienste miteinander.</span><span class="sxs-lookup"><span data-stu-id="98b6e-111">In this example, two services communicate with each other.</span></span> <span data-ttu-id="98b6e-112">Der erste Dienst ruft eine Methode auf dem zweiten Dienst auf und wartet dann auf eine Antwort.</span><span class="sxs-lookup"><span data-stu-id="98b6e-112">The first service invokes a method on the second service and then waits for a reply.</span></span> <span data-ttu-id="98b6e-113">Der zweite Dienst kennt den Namen der Rückrufmethode, aber der Endpunkt des Diensts, der diese Methode implementiert, ist zur Entwurfszeit nicht bekannt.</span><span class="sxs-lookup"><span data-stu-id="98b6e-113">The second service knows the name of the callback method, but the endpoint of the service that implements this method is not known at design time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="98b6e-114">Permanenter Duplex kann nur verwendet werden, wenn die <xref:System.ServiceModel.Channels.AddressingVersion> des Endpunkts mit <xref:System.ServiceModel.Channels.AddressingVersion.WSAddressing10%2A> konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="98b6e-114">Durable duplex can only be used when the <xref:System.ServiceModel.Channels.AddressingVersion> of the endpoint is configured with <xref:System.ServiceModel.Channels.AddressingVersion.WSAddressing10%2A>.</span></span> <span data-ttu-id="98b6e-115">Wenn dies nicht der Fall ist, <xref:System.InvalidOperationException> wird eine Ausnahme mit der folgenden Meldung ausgelöst: "die Nachricht enthält einen Rückruf Kontext Header mit einem Endpunkt Verweis für [AddressingVersion](http://schemas.xmlsoap.org/ws/2004/08/addressing).</span><span class="sxs-lookup"><span data-stu-id="98b6e-115">If it is not, then an <xref:System.InvalidOperationException> exception is thrown with the following message: "The message contains a callback context header with an endpoint reference for [AddressingVersion](http://schemas.xmlsoap.org/ws/2004/08/addressing).</span></span> <span data-ttu-id="98b6e-116">Der Rückruf Kontext kann nur übertragen werden, wenn AddressingVersion mit "WSAddressing10" konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="98b6e-116">Callback context can only be transmitted when the AddressingVersion is configured with 'WSAddressing10'.</span></span>
  
 <span data-ttu-id="98b6e-117">Im folgenden Beispiel wird ein Workflowdienst gehostet, der mithilfe von <xref:System.ServiceModel.Endpoint> einen <xref:System.ServiceModel.WSHttpContextBinding> für den Rückruf erstellt.</span><span class="sxs-lookup"><span data-stu-id="98b6e-117">In the following example, a workflow service is hosted that creates a callback <xref:System.ServiceModel.Endpoint> using <xref:System.ServiceModel.WSHttpContextBinding>.</span></span>  
  
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
  
 <span data-ttu-id="98b6e-118">Der Workflow, der diesen Workflowdienst implementiert, initialisiert die Rückrufkorrelation mit seiner <xref:System.ServiceModel.Activities.Send>-Aktivität. Er verweist in der <xref:System.ServiceModel.Activities.Receive>-Aktivität, die mit <xref:System.ServiceModel.Activities.Send> korreliert, auf diesen Rückrufendpunkt.</span><span class="sxs-lookup"><span data-stu-id="98b6e-118">The workflow that implements this workflow service initializes the callback correlation with its <xref:System.ServiceModel.Activities.Send> activity, and references this callback endpoint from the <xref:System.ServiceModel.Activities.Receive> activity that correlates with the <xref:System.ServiceModel.Activities.Send>.</span></span> <span data-ttu-id="98b6e-119">Im folgenden Beispiel ist der Workflow dargestellt, der von der `GetWF1`-Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="98b6e-119">The following example represents the workflow that is returned from the `GetWF1` method.</span></span>  
  
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
  
 <span data-ttu-id="98b6e-120">Der zweite Workflowdienst wird mit einer vom System bereitgestellten, kontextbasierten Bindung gehostet.</span><span class="sxs-lookup"><span data-stu-id="98b6e-120">The second workflow service is hosted using a system-provided, context-based binding.</span></span>  
  
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
  
 <span data-ttu-id="98b6e-121">Der Workflow, der diesen Workflowdienst implementiert, beginnt mit einer <xref:System.ServiceModel.Activities.Receive>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="98b6e-121">The workflow that implements this workflow service begins with a <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="98b6e-122">Diese Empfangsaktivität initialisiert die Rückrufkorrelation für diesen Dienst, verwendet eine Verzögerung als Simulation eines längeren Arbeitsvorgangs und führt dann den Rückruf an den ersten Dienst aus. Dafür wird der Rückrufkontext verwendet, der beim ersten Aufruf an den Dienst übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="98b6e-122">This receive activity initializes the callback correlation for this service, delays for a period of time to simulate long-running work, and then calls back into the first service using the callback context that was passed in the first call into the service.</span></span> <span data-ttu-id="98b6e-123">Im folgenden Beispiel ist der Workflow dargestellt, der bei einem Aufruf der `GetWF2`-Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="98b6e-123">The following example represents the workflow that is returned from a call to `GetWF2`.</span></span> <span data-ttu-id="98b6e-124">Beachten Sie, dass die <xref:System.ServiceModel.Activities.Send>-Aktivität über die Platzhalteradresse `http://www.contoso.com` verfügt. Die zur Laufzeit verwendete tatsächliche Adresse ist die angegebene Rückrufadresse.</span><span class="sxs-lookup"><span data-stu-id="98b6e-124">Note that the <xref:System.ServiceModel.Activities.Send> activity has a placeholder address of `http://www.contoso.com`; the actual address used at runtime is the supplied callback address.</span></span>  
  
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
  
 <span data-ttu-id="98b6e-125">Wenn die `StartOrder`-Methode für den ersten Workflow aufgerufen wird, wird die folgende Ausgabe angezeigt. Die Ausgabe verdeutlicht den Ausführungsfluss durch die beiden Workflows.</span><span class="sxs-lookup"><span data-stu-id="98b6e-125">When the `StartOrder` method is invoked on the first workflow, the following output is displayed, which shows the flow of execution through the two workflows.</span></span>  
  
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
  
 <span data-ttu-id="98b6e-126">In diesem Beispiel verwalten beide Workflows die Korrelation explizit mithilfe eines <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer>-Objekts.</span><span class="sxs-lookup"><span data-stu-id="98b6e-126">In this example, both workflows explicitly manage correlation using a <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer>.</span></span> <span data-ttu-id="98b6e-127">Da in diesen Beispielworkflows nur eine einzelne Korrelation vorhanden war, reicht die <xref:System.ServiceModel.Activities.CorrelationHandle>-Standardverwaltung in diesem Fall aus.</span><span class="sxs-lookup"><span data-stu-id="98b6e-127">Because there was only a single correlation in these sample workflows, the default <xref:System.ServiceModel.Activities.CorrelationHandle> management would have been sufficient.</span></span>
