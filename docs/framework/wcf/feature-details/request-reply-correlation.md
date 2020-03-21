---
title: Anforderung-Antwort-Korrelation
ms.date: 03/30/2017
ms.assetid: cf4379bf-2d08-43f3-9584-dfa30ffcb1f6
ms.openlocfilehash: 34a41a149e740faf0f3816bba2c9bd9b47d4996e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184545"
---
# <a name="request-reply-correlation"></a>Anforderung-Antwort-Korrelation
Die Anforderungs-Antwort-Korrelation <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> wird mit einem Paar verwendet, um einen <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> zweiseitigen Vorgang in einem Workflowdienst zu implementieren, und mit einem Paar, das einen zweiseitigen Vorgang in einem anderen Webdienst aufruft. Beim Aufrufen eines zweiseitigen Vorgangs in einem WCF-Dienst kann es sich bei dem Dienst entweder um einen herkömmlichen, codebasierten Windows Communication Foundation-Dienst (Imperative Code Based WCF) oder um einen Workflowdienst erarbeiten. Zum Verwenden der Anforderung-Antwort-Korrelation muss eine bidirektionale Bindung wie <xref:System.ServiceModel.BasicHttpBinding> verwendet werden. Die Schritte zum Initialisieren der Korrelation sind für das Aufrufen und Implementieren eines bidirektionalen Vorgangs gleich und werden in diesem Abschnitt behandelt.  
  
## <a name="using-correlation-in-a-two-way-operation-with-receivesendreply"></a>Verwenden der Korrelation in einem bidirektionalen Vorgang mit Receive/SendReply  
 <xref:System.ServiceModel.Activities.Receive> / Ein <xref:System.ServiceModel.Activities.SendReply> Paar wird verwendet, um einen zweiseitigen Vorgang in einem Workflowdienst zu implementieren. Die Laufzeit verwendet die Anforderung-Antwort-Korrelation, um sicherzustellen, dass die Antwort an den richtigen Aufrufer weitergeleitet wird. Wenn ein Workflow dann mit <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostet wird, beispielsweise Workflowdienste, ist die standardmäßige Korrelationsinitialisierung ausreichend. In diesem Szenario <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> wird ein Paar von einem Workflow verwendet, und es ist keine spezifische Korrelationskonfiguration erforderlich.  
  
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
  
### <a name="explicitly-initializing-request-reply-correlation"></a>Explizites Initialisieren der Anforderung-Antwort-Korrelation  
 Wenn andere bidirektionale Vorgänge parallel laufen, sollte die Korrelation explizit konfiguriert werden. Dies kann durch Angeben <xref:System.ServiceModel.Activities.CorrelationHandle> <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>von und oder <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> durch <xref:System.ServiceModel.Activities.CorrelationScope>Platzieren der Innenseite einer erfolgen. In diesem Beispiel wird die Anforderungs-Antwort-Korrelation für ein <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> Paar konfiguriert.  
  
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
  
 Anstatt die Korrelation explizit zu konfigurieren, können Sie auch eine <xref:System.ServiceModel.Activities.CorrelationScope>-Aktivität verwenden. <xref:System.ServiceModel.Activities.CorrelationScope> stellt ein implizites <xref:System.ServiceModel.Activities.CorrelationHandle>-Objekt für die darin enthaltenen Messagingaktivitäten bereit. In diesem Beispiel <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> ist ein <xref:System.ServiceModel.Activities.CorrelationScope>Paar in einer enthalten. Es ist keine explizite Korrelationskonfiguration erforderlich.  
  
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
  
 Falls zusätzliche Korrelationen erforderlich sind, können diese mit der <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A>-Eigenschaft der jeweiligen Messagingaktivitäten konfiguriert werden, indem die gewünschten `CorrelationInitializer`-Typen verwendet werden.  
  
## <a name="using-correlation-in-a-two-way-operation-with-sendreceivereply"></a>Verwenden der Korrelation in einem bidirektionalen Vorgang mit Send/ReceiveReply  
 Während <xref:System.ServiceModel.Activities.Receive> die Aktivität nur in einem Workflowdienst <xref:System.ServiceModel.Activities.Send> verwendet <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> werden kann, der von <xref:System.ServiceModel.Activities.WorkflowServiceHost>gehostet wird, kann das Paar in jedem Workflow verwendet werden, der eine Methode in einem Webdienst aufrufen muss. Wenn der Workflow mit <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostet wird, gilt die im vorherigen Abschnitt beschriebene Standardkorrelation. Falls nicht, muss die Korrelation entweder explizit mit den gewünschten Objekten <xref:System.ServiceModel.Activities.CorrelationInitializer> und <xref:System.ServiceModel.Activities.CorrelationHandle> oder per impliziter Handleverwaltung von <xref:System.ServiceModel.Activities.CorrelationScope> konfiguriert werden.  
  
 Wenn Sie **Dienstreferenz hinzufügen** für einen Dienst mit zweiseitigen <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> Vorgängen verwenden, werden Aktivitäten generiert, die eine Paaraktivität intern mit der explizit angegebenen Anforderungs-/Antwortkorrelation umschließen.
