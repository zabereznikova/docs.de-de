---
title: Kontextaustauschkorrelation
ms.date: 03/30/2017
ms.assetid: 1e2852be-3601-45ae-b507-ccc465d45c60
ms.openlocfilehash: da5ab2c89e4e2011c38f5fca99aeb5c2c73801a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33492322"
---
# <a name="context-exchange-correlation"></a>Kontextaustauschkorrelation
Kontextkorrelation basiert auf dem kontextaustauschmechanismus, der gemäß der [.NET Context Exchange Protocol Specification](http://go.microsoft.com/fwlink/?LinkId=166059). Bei der Kontextkorrelation wird ein bekannter Kontextheader oder ein Cookie verwendet, um Nachrichten der richtigen Instanz zuzuordnen. Zur Durchführung der Kontextkorrelation muss eine kontextbasierte Bindung wie <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> oder <xref:System.ServiceModel.NetTcpContextBinding> auf dem Endpunkt verwendet werden, der für <xref:System.ServiceModel.Activities.WorkflowServiceHost> bereitgestellt wird. In diesem Thema wird erläutert, wie die Kontextkorrelation mit Messagingaktivitäten in einem Workflowdienst verwendet wird.  
  
## <a name="using-context-correlation"></a>Verwenden der Kontextkorrelation  
 Die Kontextkorrelation wird verwendet, wenn ein Client häufig Aufrufe an einen Workflowdienst durchführen muss und der Dienst mit einer der Kontextbindungen gehostet wird. Diese Art der Korrelation wird initialisiert, indem eine <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> -Paar im Workflow Service. Der Kontext wird zusammen mit der Antwort an den Client zurückgesendet, und der Client fügt diesen Kontext dann an nachfolgende Aufrufe des Diensts an.  
  
### <a name="configuring-context-correlation-in-a-workflow-service"></a>Konfigurieren der Kontextkorrelation in einem Workflowdienst  
 Die Kontextkorrelation wird mit einem <xref:System.ServiceModel.Activities.ContextCorrelationInitializer> initialisiert, der der <xref:System.ServiceModel.Activities.SendReply>-Aktivität zugeordnet ist. Diese Aktivität antwortet auf die ursprüngliche eingehende Nachricht. Im folgenden Beispiel wird <xref:System.ServiceModel.Activities.SendReply> konfiguriert, um eine Kontextkorrelation zu initialisieren.  
  
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
>  In diesem Beispiel werden zwei Korrelationstypen verwendet: die Kontextkorrelation und die Anforderung-Antwort-Korrelation. Die Kontextkorrelation wird verwendet, damit Aufrufe von Clients an die richtige Instanz weitergeleitet werden. Die Anforderung-Antwort-Korrelation wird von den <xref:System.ServiceModel.Activities.Receive>-Aktivitäten und den <xref:System.ServiceModel.Activities.SendReply>-Aktivitäten gemeinsam verwendet, um den von diesen Aktivitäten modellierten bidirektionalen Vorgang zu implementieren. In diesem Beispiel nur die kontextkorrelation explizit konfiguriert ist, und die <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> -Paar verwendet die standardmäßige Anforderung / Antwort-Korrelation, die über die implizite bereitgestellt wird <xref:System.ServiceModel.Activities.CorrelationHandle> Verwaltung von <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Bei Verwendung der **ReceiveAndSendReply** -Aktivitätsvorlage im Workflow-Designer, Anforderung / Antwort-Korrelation explizit konfiguriert. Weitere Informationen zur Anforderung / Antwort-Korrelation und implizite korrelationshandleverwaltung finden Sie unter [Anforderung / Antwort-](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md) und [Übersicht über die Korrelation](../../../../docs/framework/wcf/feature-details/correlation-overview.md). Weitere Informationen zu den **ReceiveAndSendReply** Aktivitätsvorlage, finden Sie unter [ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer).  
  
 In den nachfolgenden <xref:System.ServiceModel.Activities.Receive>-Aktivitäten im Workflowdienst können auf das <xref:System.ServiceModel.Activities.CorrelationHandle>-Objekt verweisen, das im vorherigen Beispiel von <xref:System.ServiceModel.Activities.SendReply> initialisiert wurde.  
  
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
  contract="IOrderContract"  
  binding = "basicHttpContextBinding"  
  address="http://localhost:8080/OrderService" />  
```  
  
### <a name="configuring-context-correlation-in-a-workflow-client"></a>Konfigurieren der Kontextkorrelation in einem Workflowclient  
 Wenn der Client ein anderer Workflow ist, muss die Kontextkorrelation auch auf dem Client konfiguriert werden. Im clientworkflow der <xref:System.ServiceModel.Activities.ReceiveReply> von der <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> -Paar, den erste Aufruf an den Workflowdienst besteht, muss konfiguriert sein, mit einer <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>.  
  
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
  
 Nachdem die Korrelation initialisiert wurde, können nachfolgende <xref:System.ServiceModel.Activities.Send>-Aktivitäten das <xref:System.ServiceModel.Activities.CorrelationHandle>-Objekt verwenden, um Methoden auf der gleichen Dienstinstanz aufzurufen.  
  
```csharp  
Send request2 = new Send  
{  
    CorrelatesWith = cchandle,  
    // Remaining activity configuration omitted.  
};  
```  
  
 Beachten Sie, dass die Kontextkorrelation in diesen Beispielen explizit konfiguriert wurde. Wenn der Clientworkflow nicht auch in einem <xref:System.ServiceModel.Activities.WorkflowServiceHost>-Objekt gehostet wird, muss die Korrelation explizit konfiguriert werden, es sei denn, die Aktivitäten sind in einer <xref:System.ServiceModel.Activities.CorrelationScope>-Aktivität enthalten. Weitere Informationen zu kontextkorrelation, finden Sie unter der [NetContextExchangeCorrelation](http://msdn.microsoft.com/library/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf) Beispiel.  
  
 Wenn der Client, der die Aufrufe an den Workflowdienst durchführt, kein Workflow ist, kann er trotzdem wiederholte Aufrufe ausführen. Es muss nur gewährleistet sein, dass er den explizit den Kontext übergibt, den der erste Aufruf an den Workflowdienst zurückgibt. Proxys, die durch das Hinzufügen eines Dienstverweises in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] generiert werden, speichern und übergeben diesen Kontext standardmäßig.
