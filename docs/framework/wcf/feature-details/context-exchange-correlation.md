---
title: "Kontextaustauschkorrelation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1e2852be-3601-45ae-b507-ccc465d45c60
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# Kontextaustauschkorrelation
Die Kontextkorrelation basiert auf dem Kontextaustauschmechanismus, der unter [.NET Context Exchange Protocol Specification](http://go.microsoft.com/fwlink/?LinkId=166059) beschrieben wird.Bei der Kontextkorrelation wird ein bekannter Kontextheader oder ein Cookie verwendet, um Nachrichten der richtigen Instanz zuzuordnen.Zur Durchführung der Kontextkorrelation muss eine kontextbasierte Bindung wie <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> oder <xref:System.ServiceModel.NetTcpContextBinding> auf dem Endpunkt verwendet werden, der für <xref:System.ServiceModel.Activities.WorkflowServiceHost> bereitgestellt wird.In diesem Thema wird erläutert, wie die Kontextkorrelation mit Messagingaktivitäten in einem Workflowdienst verwendet wird.  
  
## Verwenden der Kontextkorrelation  
 Die Kontextkorrelation wird verwendet, wenn ein Client häufig Aufrufe an einen Workflowdienst durchführen muss und der Dienst mit einer der Kontextbindungen gehostet wird.Dieser Typ der Korrelation wird von einem <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply>\-Paar im Workflowdienst initialisiert.Der Kontext wird zusammen mit der Antwort an den Client zurückgesendet, und der Client fügt diesen Kontext dann an nachfolgende Aufrufe des Diensts an.  
  
### Konfigurieren der Kontextkorrelation in einem Workflowdienst  
 Die Kontextkorrelation wird mit einem <xref:System.ServiceModel.Activities.ContextCorrelationInitializer> initialisiert, der der <xref:System.ServiceModel.Activities.SendReply>\-Aktivität zugeordnet ist. Diese Aktivität antwortet auf die ursprüngliche eingehende Nachricht.Im folgenden Beispiel wird <xref:System.ServiceModel.Activities.SendReply> konfiguriert, um eine Kontextkorrelation zu initialisieren.  
  
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
>  In diesem Beispiel werden zwei Korrelationstypen verwendet: die Kontextkorrelation und die Anforderung\-Antwort\-Korrelation.Die Kontextkorrelation wird verwendet, damit Aufrufe von Clients an die richtige Instanz weitergeleitet werden.Die Anforderung\-Antwort\-Korrelation wird von den <xref:System.ServiceModel.Activities.Receive>\-Aktivitäten und den <xref:System.ServiceModel.Activities.SendReply>\-Aktivitäten gemeinsam verwendet, um den von diesen Aktivitäten modellierten bidirektionalen Vorgang zu implementieren.In diesem Beispiel wird nur die Kontextkorrelation explizit konfiguriert, und das <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply>\-Paar verwendet die standardmäßige Anforderung\-Antwort\-Korrelation, die über die implizite <xref:System.ServiceModel.Activities.CorrelationHandle>\-Verwaltung von <xref:System.ServiceModel.Activities.WorkflowServiceHost> bereitgestellt wird.Bei Verwendung der **ReceiveAndSendReply**\-Aktivitätsvorlage im Workflow\-Designer wird die Anforderung\-Antwort\-Korrelation explizit konfiguriert.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Anforderung\-Antwort\-Korrelation und die implizite Korrelationshandleverwaltung finden Sie unter [Anforderung\-Antwort](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md) und [Übersicht über die Korrelation](../../../../docs/framework/wcf/feature-details/correlation-overview.md).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur **ReceiveAndSendReply**\-Aktivitätsvorlage finden Sie unter [ReceiveAndSendReply](../Topic/ReceiveAndSendReply%20Template%20Designer.md).  
  
 In den nachfolgenden <xref:System.ServiceModel.Activities.Receive>\-Aktivitäten im Workflowdienst können auf das <xref:System.ServiceModel.Activities.CorrelationHandle>\-Objekt verweisen, das im vorherigen Beispiel von <xref:System.ServiceModel.Activities.SendReply> initialisiert wurde.  
  
```csharp  
Receive AddItem = new Receive  
{  
    ServiceContractName = "IOrderService",  
    OperationName = "AddItem",  
    CorrelatesWith = OrderHandle  
};  
```  
  
 Der Endpunkt wird dann auf dem <xref:System.ServiceModel.Activities.WorkflowServiceHost> konfiguriert, um eine kontextbasierte Bindung zu verwenden, z. B. <xref:System.ServiceModel.BasicHttpContextBinding>.  
  
```xml  
<endpoint  
  contract=”IOrderContract”  
  binding = “basicHttpContextBinding”  
  address=”http://localhost:8080/OrderService” />  
```  
  
### Konfigurieren der Kontextkorrelation in einem Workflowclient  
 Wenn der Client ein anderer Workflow ist, muss die Kontextkorrelation auch auf dem Client konfiguriert werden.Im Clientworkflow muss das <xref:System.ServiceModel.Activities.ReceiveReply>\-Objekt des <xref:System.ServiceModel.Activities.Send>\/<xref:System.ServiceModel.Activities.ReceiveReply>\-Paars, das den ursprünglichen Aufruf an den Workflowdienst durchführt, mit einem <xref:System.ServiceModel.Activities.ContextCorrelationInitializer> konfiguriert werden.  
  
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
  
 Nachdem die Korrelation initialisiert wurde, können nachfolgende <xref:System.ServiceModel.Activities.Send>\-Aktivitäten das <xref:System.ServiceModel.Activities.CorrelationHandle>\-Objekt verwenden, um Methoden auf der gleichen Dienstinstanz aufzurufen.  
  
```csharp  
Send request2 = new Send  
{  
    CorrelatesWith = cchandle,  
    // Remaining activity configuration omitted.  
};  
```  
  
 Beachten Sie, dass die Kontextkorrelation in diesen Beispielen explizit konfiguriert wurde.Wenn der Clientworkflow nicht auch in einem <xref:System.ServiceModel.Activities.WorkflowServiceHost>\-Objekt gehostet wird, muss die Korrelation explizit konfiguriert werden, es sei denn, die Aktivitäten sind in einer <xref:System.ServiceModel.Activities.CorrelationScope>\-Aktivität enthalten.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Kontextkorrelation finden Sie im [NetContextExchangeCorrelation](http://msdn.microsoft.com/de-de/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf)\-Beispiel.  
  
 Wenn der Client, der die Aufrufe an den Workflowdienst durchführt, kein Workflow ist, kann er trotzdem wiederholte Aufrufe ausführen. Es muss nur gewährleistet sein, dass er den explizit den Kontext übergibt, den der erste Aufruf an den Workflowdienst zurückgibt.Proxys, die durch das Hinzufügen eines Dienstverweises in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] generiert werden, speichern und übergeben diesen Kontext standardmäßig.