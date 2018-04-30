---
title: Kontextaustauschkorrelation
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e2852be-3601-45ae-b507-ccc465d45c60
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bf84dfce2b2164d78bf07f840d66d6089a16ff23
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="context-exchange-correlation"></a><span data-ttu-id="0dcc9-102">Kontextaustauschkorrelation</span><span class="sxs-lookup"><span data-stu-id="0dcc9-102">Context Exchange Correlation</span></span>
<span data-ttu-id="0dcc9-103">Kontextkorrelation basiert auf dem kontextaustauschmechanismus, der gemäß der [.NET Context Exchange Protocol Specification](http://go.microsoft.com/fwlink/?LinkId=166059).</span><span class="sxs-lookup"><span data-stu-id="0dcc9-103">Context correlation is based on the context exchange mechanism described in the [.NET Context Exchange Protocol Specification](http://go.microsoft.com/fwlink/?LinkId=166059).</span></span> <span data-ttu-id="0dcc9-104">Bei der Kontextkorrelation wird ein bekannter Kontextheader oder ein Cookie verwendet, um Nachrichten der richtigen Instanz zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="0dcc9-104">Context correlation uses a well-known context header or cookie to relate messages to the correct instance.</span></span> <span data-ttu-id="0dcc9-105">Zur Durchführung der Kontextkorrelation muss eine kontextbasierte Bindung wie <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> oder <xref:System.ServiceModel.NetTcpContextBinding> auf dem Endpunkt verwendet werden, der für <xref:System.ServiceModel.Activities.WorkflowServiceHost> bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0dcc9-105">To use context correlation, a context-based binding such as <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding>, or <xref:System.ServiceModel.NetTcpContextBinding> must be used on the endpoint provided to the <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="0dcc9-106">In diesem Thema wird erläutert, wie die Kontextkorrelation mit Messagingaktivitäten in einem Workflowdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0dcc9-106">This topic explains how to use context correlation with messaging activities in a workflow service.</span></span>  
  
## <a name="using-context-correlation"></a><span data-ttu-id="0dcc9-107">Verwenden der Kontextkorrelation</span><span class="sxs-lookup"><span data-stu-id="0dcc9-107">Using Context Correlation</span></span>  
 <span data-ttu-id="0dcc9-108">Die Kontextkorrelation wird verwendet, wenn ein Client häufig Aufrufe an einen Workflowdienst durchführen muss und der Dienst mit einer der Kontextbindungen gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="0dcc9-108">Context correlation is used when a client must make repeated calls into a workflow service and the service is hosted using one of the context bindings.</span></span> <span data-ttu-id="0dcc9-109">Diese Art der Korrelation wird initialisiert, indem eine <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> -Paar im Workflow Service.</span><span class="sxs-lookup"><span data-stu-id="0dcc9-109">This type of correlation is initialized by a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair in the workflow service.</span></span> <span data-ttu-id="0dcc9-110">Der Kontext wird zusammen mit der Antwort an den Client zurückgesendet, und der Client fügt diesen Kontext dann an nachfolgende Aufrufe des Diensts an.</span><span class="sxs-lookup"><span data-stu-id="0dcc9-110">The context is sent back to the client together with the reply, and then the client attaches this context on subsequent calls to the service.</span></span>  
  
### <a name="configuring-context-correlation-in-a-workflow-service"></a><span data-ttu-id="0dcc9-111">Konfigurieren der Kontextkorrelation in einem Workflowdienst</span><span class="sxs-lookup"><span data-stu-id="0dcc9-111">Configuring Context Correlation in a Workflow Service</span></span>  
 <span data-ttu-id="0dcc9-112">Die Kontextkorrelation wird mit einem <xref:System.ServiceModel.Activities.ContextCorrelationInitializer> initialisiert, der der <xref:System.ServiceModel.Activities.SendReply>-Aktivität zugeordnet ist. Diese Aktivität antwortet auf die ursprüngliche eingehende Nachricht.</span><span class="sxs-lookup"><span data-stu-id="0dcc9-112">Context correlation is initialized by using a <xref:System.ServiceModel.Activities.ContextCorrelationInitializer> that is associated with the <xref:System.ServiceModel.Activities.SendReply> activity that replies to the initial incoming message.</span></span> <span data-ttu-id="0dcc9-113">Im folgenden Beispiel wird <xref:System.ServiceModel.Activities.SendReply> konfiguriert, um eine Kontextkorrelation zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="0dcc9-113">In the following example, the <xref:System.ServiceModel.Activities.SendReply> is configured to initialize a context correlation.</span></span>  
  
```csharp  
Variable<string> Item = new Variable<string>();  
Variable<CorrelationHandle> OrderHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = "IOrderService",  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    CorrelationInitializers =  
    {  
        new ContextCorrelationInitializer  
        {  
            CorrelationHandle = OrderHandle  
        }  
    }  
};  
```  
  
> [!NOTE]
>  <span data-ttu-id="0dcc9-114">In diesem Beispiel werden zwei Korrelationstypen verwendet: die Kontextkorrelation und die Anforderung-Antwort-Korrelation.</span><span class="sxs-lookup"><span data-stu-id="0dcc9-114">In this example, there are actually two types of correlation being used: context correlation and request-reply correlation.</span></span> <span data-ttu-id="0dcc9-115">Die Kontextkorrelation wird verwendet, damit Aufrufe von Clients an die richtige Instanz weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="0dcc9-115">The context correlation is used so that calls from clients are routed to the correct instance.</span></span> <span data-ttu-id="0dcc9-116">Die Anforderung-Antwort-Korrelation wird von den <xref:System.ServiceModel.Activities.Receive>-Aktivitäten und den <xref:System.ServiceModel.Activities.SendReply>-Aktivitäten gemeinsam verwendet, um den von diesen Aktivitäten modellierten bidirektionalen Vorgang zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="0dcc9-116">The request-reply correlation is used by the <xref:System.ServiceModel.Activities.Receive> and the <xref:System.ServiceModel.Activities.SendReply> activities together to implement the two-way operation modeled by these activities.</span></span> <span data-ttu-id="0dcc9-117">In diesem Beispiel nur die kontextkorrelation explizit konfiguriert ist, und die <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> -Paar verwendet die standardmäßige Anforderung / Antwort-Korrelation, die über die implizite bereitgestellt wird <xref:System.ServiceModel.Activities.CorrelationHandle> Verwaltung von <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="0dcc9-117">In this example, only the context correlation is explicitly configured, and the <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is using the default request-reply correlation that is provided by the implicit <xref:System.ServiceModel.Activities.CorrelationHandle> management of <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="0dcc9-118">Bei Verwendung der **ReceiveAndSendReply** -Aktivitätsvorlage im Workflow-Designer, Anforderung / Antwort-Korrelation explizit konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="0dcc9-118">When using the **ReceiveAndSendReply** activity template in the workflow designer, request-reply correlation is explicitly configured.</span></span> <span data-ttu-id="0dcc9-119">Weitere Informationen zur Anforderung / Antwort-Korrelation und implizite korrelationshandleverwaltung finden Sie unter [Anforderung / Antwort-](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md) und [Übersicht über die Korrelation](../../../../docs/framework/wcf/feature-details/correlation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0dcc9-119">For more information about request-reply correlation and implicit correlation handle management, see [Request-Reply](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md) and [Correlation Overview](../../../../docs/framework/wcf/feature-details/correlation-overview.md).</span></span> <span data-ttu-id="0dcc9-120">Weitere Informationen zu den **ReceiveAndSendReply** Aktivitätsvorlage, finden Sie unter [ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer).</span><span class="sxs-lookup"><span data-stu-id="0dcc9-120">For more information about the **ReceiveAndSendReply** activity template, see [ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer).</span></span>  
  
 <span data-ttu-id="0dcc9-121">In den nachfolgenden <xref:System.ServiceModel.Activities.Receive>-Aktivitäten im Workflowdienst können auf das <xref:System.ServiceModel.Activities.CorrelationHandle>-Objekt verweisen, das im vorherigen Beispiel von <xref:System.ServiceModel.Activities.SendReply> initialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="0dcc9-121">Subsequent <xref:System.ServiceModel.Activities.Receive> activities in the workflow service can reference the <xref:System.ServiceModel.Activities.CorrelationHandle> that was initialized by the <xref:System.ServiceModel.Activities.SendReply> in the previous example.</span></span>  
  
```csharp  
Receive AddItem = new Receive  
{  
    ServiceContractName = "IOrderService",  
    OperationName = "AddItem",  
    CorrelatesWith = OrderHandle  
};  
```  
  
 <span data-ttu-id="0dcc9-122">Der Endpunkt wird dann auf dem <xref:System.ServiceModel.Activities.WorkflowServiceHost> konfiguriert, um eine kontextbasierte Bindung zu verwenden, z. B. <xref:System.ServiceModel.BasicHttpContextBinding>.</span><span class="sxs-lookup"><span data-stu-id="0dcc9-122">The endpoint is then configured on the <xref:System.ServiceModel.Activities.WorkflowServiceHost> to use a context-based binding, such as <xref:System.ServiceModel.BasicHttpContextBinding>.</span></span>  
  
```xml  
<endpoint  
  contract="IOrderContract"  
  binding = "basicHttpContextBinding"  
  address="http://localhost:8080/OrderService" />  
```  
  
### <a name="configuring-context-correlation-in-a-workflow-client"></a><span data-ttu-id="0dcc9-123">Konfigurieren der Kontextkorrelation in einem Workflowclient</span><span class="sxs-lookup"><span data-stu-id="0dcc9-123">Configuring Context Correlation in a Workflow Client</span></span>  
 <span data-ttu-id="0dcc9-124">Wenn der Client ein anderer Workflow ist, muss die Kontextkorrelation auch auf dem Client konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="0dcc9-124">When the client is another workflow, context correlation must be configured on the client as well.</span></span> <span data-ttu-id="0dcc9-125">Im clientworkflow der <xref:System.ServiceModel.Activities.ReceiveReply> von der <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> -Paar, den erste Aufruf an den Workflowdienst besteht, muss konfiguriert sein, mit einer <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>.</span><span class="sxs-lookup"><span data-stu-id="0dcc9-125">On the client workflow, the <xref:System.ServiceModel.Activities.ReceiveReply> of the <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair that makes the initial call to the workflow service must be configured with a <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>.</span></span>  
  
```csharp  
Variable<CorrelationHandle> cchandle = new Variable<CorrelationHandle>();  
Send request = new Send  
{  
    // Activity configuration omitted.  
};  
  
ReceiveReply reply = new ReceiveReply  
{  
    Request = request,  
    CorrelationInitializers =   
    {  
        new ContextCorrelationInitializer  
        {  
            CorrelationHandle = cchandle  
        }  
    }  
};  
```  
  
 <span data-ttu-id="0dcc9-126">Nachdem die Korrelation initialisiert wurde, können nachfolgende <xref:System.ServiceModel.Activities.Send>-Aktivitäten das <xref:System.ServiceModel.Activities.CorrelationHandle>-Objekt verwenden, um Methoden auf der gleichen Dienstinstanz aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="0dcc9-126">After the correlation is initialized, subsequent <xref:System.ServiceModel.Activities.Send> activities can use the <xref:System.ServiceModel.Activities.CorrelationHandle> to invoke methods on the same service instance.</span></span>  
  
```csharp  
Send request2 = new Send  
{  
    CorrelatesWith = cchandle,  
    // Remaining activity configuration omitted.  
};  
```  
  
 <span data-ttu-id="0dcc9-127">Beachten Sie, dass die Kontextkorrelation in diesen Beispielen explizit konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="0dcc9-127">Note that in these examples, the context correlation has been explicitly configured.</span></span> <span data-ttu-id="0dcc9-128">Wenn der Clientworkflow nicht auch in einem <xref:System.ServiceModel.Activities.WorkflowServiceHost>-Objekt gehostet wird, muss die Korrelation explizit konfiguriert werden, es sei denn, die Aktivitäten sind in einer <xref:System.ServiceModel.Activities.CorrelationScope>-Aktivität enthalten.</span><span class="sxs-lookup"><span data-stu-id="0dcc9-128">If the client workflow is not also hosted in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>, then correlation must be explicitly configured, unless the activities are contained within a <xref:System.ServiceModel.Activities.CorrelationScope> activity.</span></span> <span data-ttu-id="0dcc9-129">Weitere Informationen zu kontextkorrelation, finden Sie unter der [NetContextExchangeCorrelation](http://msdn.microsoft.com/library/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="0dcc9-129">For more information about context correlation, see the [NetContextExchangeCorrelation](http://msdn.microsoft.com/library/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf) sample.</span></span>  
  
 <span data-ttu-id="0dcc9-130">Wenn der Client, der die Aufrufe an den Workflowdienst durchführt, kein Workflow ist, kann er trotzdem wiederholte Aufrufe ausführen. Es muss nur gewährleistet sein, dass er den explizit den Kontext übergibt, den der erste Aufruf an den Workflowdienst zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0dcc9-130">If the client that is making calls to the workflow service is not a workflow, then it can still make repeated calls as long as it explicitly passes back the context that is returned from the first call to the workflow service.</span></span> <span data-ttu-id="0dcc9-131">Proxys, die durch das Hinzufügen eines Dienstverweises in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] generiert werden, speichern und übergeben diesen Kontext standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="0dcc9-131">Proxies generated by adding a service reference in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] store and pass this context by default.</span></span>
