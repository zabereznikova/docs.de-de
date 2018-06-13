---
title: Anforderung-Antwort-Korrelation
ms.date: 03/30/2017
ms.assetid: cf4379bf-2d08-43f3-9584-dfa30ffcb1f6
ms.openlocfilehash: c38854ad42ad4dddce5171482f3ddcfe5bd16b61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497203"
---
# <a name="request-reply-correlation"></a><span data-ttu-id="b867c-102">Anforderung-Antwort-Korrelation</span><span class="sxs-lookup"><span data-stu-id="b867c-102">Request-Reply Correlation</span></span>
<span data-ttu-id="b867c-103">Anforderung-Antwort-Korrelation wird verwendet, mit einem <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> -Paar, das einen bidirektionalen Vorgang in einem Workflowdienst und mit implementieren eine <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> -Paar, das einen bidirektionalen in eine andere Web Vorgang -Dienst.</span><span class="sxs-lookup"><span data-stu-id="b867c-103">Request-reply correlation is used with a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair to implement a two-way operation in a workflow service and with a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair that invokes a two-way operation in another Web service.</span></span> <span data-ttu-id="b867c-104">Beim Aufrufen der eines bidirektionalen Vorgangs in einem WCF-Dienst der Dienst kann entweder eine herkömmliche imperative codebasierte Windows Communication Foundation (WCF)-Dienst, oder es kann ein Workflowdienst sein.</span><span class="sxs-lookup"><span data-stu-id="b867c-104">When invoking a two-way operation in a WCF service, the service can be either a traditional imperative code-based Windows Communication Foundation (WCF) service or it can be a workflow service.</span></span> <span data-ttu-id="b867c-105">Zum Verwenden der Anforderung-Antwort-Korrelation muss eine bidirektionale Bindung wie <xref:System.ServiceModel.BasicHttpBinding> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b867c-105">To use request-reply correlation a two-way binding must be used, such as <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="b867c-106">Die Schritte zum Initialisieren der Korrelation sind für das Aufrufen und Implementieren eines bidirektionalen Vorgangs gleich und werden in diesem Abschnitt behandelt.</span><span class="sxs-lookup"><span data-stu-id="b867c-106">Whether invoking or implementing a two-way operation, the correlation initialization steps are similar and are covered in this section.</span></span>  
  
## <a name="using-correlation-in-a-two-way-operation-with-receivesendreply"></a><span data-ttu-id="b867c-107">Verwenden der Korrelation in einem bidirektionalen Vorgang mit Receive/SendReply</span><span class="sxs-lookup"><span data-stu-id="b867c-107">Using Correlation in a Two-Way Operation with Receive/SendReply</span></span>  
 <span data-ttu-id="b867c-108">Ein <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> Paar wird verwendet, um einen bidirektionalen Vorgang in einem Workflowdienst zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="b867c-108">A <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is used to implement a two-way operation in a workflow service.</span></span> <span data-ttu-id="b867c-109">Die Laufzeit verwendet die Anforderung-Antwort-Korrelation, um sicherzustellen, dass die Antwort an den richtigen Aufrufer weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="b867c-109">The runtime uses request-reply correlation to ensure that the reply is dispatched to the correct caller.</span></span> <span data-ttu-id="b867c-110">Wenn ein Workflow dann mit <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostet wird, beispielsweise Workflowdienste, ist die standardmäßige Korrelationsinitialisierung ausreichend.</span><span class="sxs-lookup"><span data-stu-id="b867c-110">When a workflow is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>, which is the case for workflow services, then the default correlation initialization is sufficient.</span></span> <span data-ttu-id="b867c-111">In diesem Szenario eine <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> -Paar von einem Workflow verwendet wird, und es ist keine spezielle korrelationskonfiguration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b867c-111">In this scenario, a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is used by a workflow, and no specific correlation configuration is required.</span></span>  
  
```csharp  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
### <a name="explicitly-initializing-request-reply-correlation"></a><span data-ttu-id="b867c-112">Explizites Initialisieren der Anforderung-Antwort-Korrelation</span><span class="sxs-lookup"><span data-stu-id="b867c-112">Explicitly Initializing Request-Reply Correlation</span></span>  
 <span data-ttu-id="b867c-113">Wenn andere bidirektionale Vorgänge parallel laufen, sollte die Korrelation explizit konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="b867c-113">If other two-way operations are in parallel, then correlation should be explicitly configured.</span></span> <span data-ttu-id="b867c-114">Dies kann geschehen, indem Sie angeben einer <xref:System.ServiceModel.Activities.CorrelationHandle> und <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>, oder durch Platzieren der <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> innerhalb von einer <xref:System.ServiceModel.Activities.CorrelationScope>.</span><span class="sxs-lookup"><span data-stu-id="b867c-114">This can be done by specifying a <xref:System.ServiceModel.Activities.CorrelationHandle> and <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>, or by placing the <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> inside of a <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span> <span data-ttu-id="b867c-115">In diesem Beispiel wird auf Anforderung-Antwort-Korrelation konfiguriert eine <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> Paar.</span><span class="sxs-lookup"><span data-stu-id="b867c-115">In this example, request-reply correlation is configured on a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair.</span></span>  
  
```csharp  
Variable<CorrelationHandle> RRHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder",  
    CorrelationInitializers =  
    {  
        new RequestReplyCorrelationInitializer  
        {  
            CorrelationHandle = RRHandle  
        }  
    }  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
 <span data-ttu-id="b867c-116">Anstatt die Korrelation explizit zu konfigurieren, können Sie auch eine <xref:System.ServiceModel.Activities.CorrelationScope>-Aktivität verwenden.</span><span class="sxs-lookup"><span data-stu-id="b867c-116">Instead of explicitly configuring the correlation, a <xref:System.ServiceModel.Activities.CorrelationScope> activity can be used.</span></span> <span data-ttu-id="b867c-117"><xref:System.ServiceModel.Activities.CorrelationScope> stellt ein implizites <xref:System.ServiceModel.Activities.CorrelationHandle>-Objekt für die darin enthaltenen Messagingaktivitäten bereit.</span><span class="sxs-lookup"><span data-stu-id="b867c-117"><xref:System.ServiceModel.Activities.CorrelationScope> provides an implicit <xref:System.ServiceModel.Activities.CorrelationHandle> to the messaging activities that it contains.</span></span> <span data-ttu-id="b867c-118">In diesem Beispiel wird eine <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> Paar befindet sich innerhalb einer <xref:System.ServiceModel.Activities.CorrelationScope>.</span><span class="sxs-lookup"><span data-stu-id="b867c-118">In this example, a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is contained inside a <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span> <span data-ttu-id="b867c-119">Es ist keine explizite Korrelationskonfiguration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b867c-119">No explicit correlation configuration is required.</span></span>  
  
```csharp  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
CorrelationScope s = new CorrelationScope  
{  
    Body = new Sequence  
    {  
        Activities =   
        {  
            StartOrder,  
            // Activities that create the reply.  
            ReplyToStartOrder  
        }  
    }  
};  
  
// Construct a workflow using the CorrelationScope.  
```  
  
 <span data-ttu-id="b867c-120">Falls zusätzliche Korrelationen erforderlich sind, können diese mit der <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A>-Eigenschaft der jeweiligen Messagingaktivitäten konfiguriert werden, indem die gewünschten `CorrelationInitializer`-Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b867c-120">If additional correlations are required then they can be configured using the <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> property of the respective messaging activities using the desired `CorrelationInitializer` types.</span></span>  
  
## <a name="using-correlation-in-a-two-way-operation-with-sendreceivereply"></a><span data-ttu-id="b867c-121">Verwenden der Korrelation in einem bidirektionalen Vorgang mit Send/ReceiveReply</span><span class="sxs-lookup"><span data-stu-id="b867c-121">Using Correlation in a Two-Way Operation with Send/ReceiveReply</span></span>  
 <span data-ttu-id="b867c-122">Während der <xref:System.ServiceModel.Activities.Receive> Aktivität kann nur verwendet werden, in einem von gehosteten Workflowdienst <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.ServiceModel.Activities.Send> und <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> Paar in einem Workflow, der eine Methode für einen Webdienst aufrufen muss verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b867c-122">While the <xref:System.ServiceModel.Activities.Receive> activity can only be used in a workflow service hosted by <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.ServiceModel.Activities.Send> and the <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair can be used in any workflow that must invoke a method on a Web service.</span></span> <span data-ttu-id="b867c-123">Wenn der Workflow mit <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostet wird, gilt die im vorherigen Abschnitt beschriebene Standardkorrelation. Falls nicht, muss die Korrelation entweder explizit mit den gewünschten Objekten <xref:System.ServiceModel.Activities.CorrelationInitializer> und <xref:System.ServiceModel.Activities.CorrelationHandle> oder per impliziter Handleverwaltung von <xref:System.ServiceModel.Activities.CorrelationScope> konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="b867c-123">If the workflow is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost> then the default correlation described in the previous section applies, but if not, then correlation must be configured either explicitly using the desired <xref:System.ServiceModel.Activities.CorrelationInitializer> and <xref:System.ServiceModel.Activities.CorrelationHandle>, or by using the implicit handle management of the <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span>  
  
 <span data-ttu-id="b867c-124">Bei Verwendung **Hinzufügen eines Dienstverweises** für einen Dienst mit bidirektionalen Vorgängen, werden Aktivitäten generiert, Wrap eine <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> -paaraktivität intern mit der Anforderung/Antwort-Korrelation explizit angegeben.</span><span class="sxs-lookup"><span data-stu-id="b867c-124">When using **Add Service Reference** on a service with two-way operations, activities are generated that wrap a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair activity internally with the Request/Reply correlation explicitly specified.</span></span>
