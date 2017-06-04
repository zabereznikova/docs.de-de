---
title: "Anforderung-Antwort-Korrelation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cf4379bf-2d08-43f3-9584-dfa30ffcb1f6
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Anforderung-Antwort-Korrelation
Die Anforderung\-Antwort\-Korrelation wird mit einem <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply>\-Paar verwendet, um einen bidirektionalen Vorgang in einem Workflowdienst zu implementieren, und mit einem <xref:System.ServiceModel.Activities.Send>\/<xref:System.ServiceModel.Activities.ReceiveReply>\-Paar, um einen bidirektionalen Vorgang in einem anderen Webdienst aufzurufen.  Wenn in einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst ein bidirektionaler Vorgang aufgerufen wird, kann der Dienst entweder ein herkömmlicher obligatorischer [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Dienst sein, der auf Code basiert, oder es kann ein Workflowdienst sein.  Zum Verwenden der Anforderung\-Antwort\-Korrelation muss eine bidirektionale Bindung wie <xref:System.ServiceModel.BasicHttpBinding> verwendet werden.  Die Schritte zum Initialisieren der Korrelation sind für das Aufrufen und Implementieren eines bidirektionalen Vorgangs gleich und werden in diesem Abschnitt behandelt.  
  
## Verwenden der Korrelation in einem bidirektionalen Vorgang mit Receive\/SendReply  
 Ein <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply>\-Paar wird verwendet, um in einem Workflowdienst einen bidirektionalen Vorgang zu implementieren.  Die Laufzeit verwendet die Anforderung\-Antwort\-Korrelation, um sicherzustellen, dass die Antwort an den richtigen Aufrufer weitergeleitet wird.  Wenn ein Workflow dann mit <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostet wird, beispielsweise Workflowdienste, ist die standardmäßige Korrelationsinitialisierung ausreichend.  In diesem Szenario wird ein <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply>\-Paar von einem Workflow verwendet, und es ist keine spezielle Korrelationskonfiguration erforderlich.  
  
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
  
### Explizites Initialisieren der Anforderung\-Antwort\-Korrelation  
 Wenn andere bidirektionale Vorgänge parallel laufen, sollte die Korrelation explizit konfiguriert werden.  Geben Sie dazu <xref:System.ServiceModel.Activities.CorrelationHandle> und <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> an, oder fügen Sie das <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply>\-Paar in <xref:System.ServiceModel.Activities.CorrelationScope> ein.  In diesem Beispiel wird die Anforderung\-Antwort\-Korrelation für ein <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply>\-Paar konfiguriert.  
  
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
  
 Anstatt die Korrelation explizit zu konfigurieren, können Sie auch eine <xref:System.ServiceModel.Activities.CorrelationScope>\-Aktivität verwenden.  <xref:System.ServiceModel.Activities.CorrelationScope> stellt ein implizites <xref:System.ServiceModel.Activities.CorrelationHandle>\-Objekt für die darin enthaltenen Messagingaktivitäten bereit.  In diesem Beispiel ist ein <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply>\-Paar in einem <xref:System.ServiceModel.Activities.CorrelationScope>\-Objekt enthalten.  Es ist keine explizite Korrelationskonfiguration erforderlich.  
  
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
  
 Falls zusätzliche Korrelationen erforderlich sind, können diese mit der <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A>\-Eigenschaft der jeweiligen Messagingaktivitäten konfiguriert werden, indem die gewünschten `CorrelationInitializer`\-Typen verwendet werden.  
  
## Verwenden der Korrelation in einem bidirektionalen Vorgang mit Send\/ReceiveReply  
 Während die <xref:System.ServiceModel.Activities.Receive>\-Aktivität nur in einem von <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehosteten Workflowdienst verwendet werden kann, können <xref:System.ServiceModel.Activities.Send> und das <xref:System.ServiceModel.Activities.Send>\/<xref:System.ServiceModel.Activities.ReceiveReply>\-Paar in jedem Workflow verwendet werden, der eine Methode auf einem Webdienst aufrufen muss.  Wenn der Workflow mit <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostet wird, gilt die im vorherigen Abschnitt beschriebene Standardkorrelation. Falls nicht, muss die Korrelation entweder explizit mit den gewünschten Objekten <xref:System.ServiceModel.Activities.CorrelationInitializer> und <xref:System.ServiceModel.Activities.CorrelationHandle> oder per impliziter Handleverwaltung von <xref:System.ServiceModel.Activities.CorrelationScope> konfiguriert werden.  
  
 Beim Verwenden von **Dienstverweis hinzufügen** für einen Dienst mit bidirektionalen Vorgängen, werden Aktivitäten generiert, die aus der <xref:System.ServiceModel.Activities.Send>\/<xref:System.ServiceModel.Activities.ReceiveReply>\-Paaraktivität intern mit der explizit angegebenen Anforderung\-Antwort\-Korrelation einen Wrapper erstellen.