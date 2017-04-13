---
title: "Fehlerbehandlung in asynchronen Aktivit&#228;ten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e8f8ce2b-50c9-4e44-b187-030e0cf30a5d
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Fehlerbehandlung in asynchronen Aktivit&#228;ten
Bei der Bereitstellung der Fehlerbehandlung in <xref:System.Activities.AsyncCodeActivity> wird der Fehler durch das Rückrufsystem der Aktivität zurückverfolgt.In diesem Thema wird beschrieben, wie ein Fehler, der in einem asynchronen Vorgang an den Host zurückgegeben wird, mithilfe des Beispiels zur SendMail\-Aktivität ermittelt wird.  
  
## Zurückgeben eines Fehlers, der in einer asynchronen Aktivität ausgelöst wurde, an den Host  
 Das Zurückleiten eines Fehlers in einem asynchronen Vorgang an den Host im Beispiel zur SendMail\-Aktivität umfasst die folgenden Schritte:  
  
-   Hinzufügen einer Exception\-Eigenschaft zur `SendMailAsyncResult`\-Klasse  
  
-   Kopieren des ausgelösten Fehlers in diese Eigenschaft im `SendCompleted`\-Ereignishandler  
  
-   Auslösen der Ausnahme im `EndExecute`\-Ereignishandler  
  
 Der resultierede Code lautet wie folgt.  
  
```csharp  
class SendMailAsyncResult : IAsyncResult  
        {  
            …  
            public Exception Error { get; set; }   
            …  
            void SendCompleted(object sender, AsyncCompletedEventArgs e)  
            {  
                Error = e.Error;  
                this.asyncWaitHandle.Set();  
                callback(this);  
            }  
         }  
  
    public sealed class SendMail: AsyncCodeActivity  
    {  
         …  
        protected override void EndExecute(AsyncCodeActivityContext context, IAsyncResult result)  
        {  
            SendMailAsyncResult sendMailResult = result as SendMailAsyncResult;  
            if (sendMailResult != null && sendMailResult.Error != null)  
                throw sendMailResult.Error;   
        }  
    }  
  
```