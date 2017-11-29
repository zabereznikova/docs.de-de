---
title: "Fehlerbehandlung in asynchronen Aktivitäten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8f8ce2b-50c9-4e44-b187-030e0cf30a5d
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7606aeeeb3e2e583f9a217b78bcae4aebc6d8662
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="error-handling-in-asynchronous-activities"></a>Fehlerbehandlung in asynchronen Aktivitäten
Bei der Bereitstellung der Fehlerbehandlung in <xref:System.Activities.AsyncCodeActivity> wird der Fehler durch das Rückrufsystem der Aktivität zurückverfolgt. In diesem Thema wird mithilfe des Beispiels zur SendMail-Aktivität beschrieben, wie ein Fehler, der in einem asynchronen Vorgang auftritt, an den Host zurückgegeben wird.  
  
## <a name="returning-an-error-thrown-in-an-asynchronous-activity-back-to-the-host"></a>Zurückgeben eines Fehlers, der in einer asynchronen Aktivität ausgelöst wurde, an den Host  
 Das Zurückleiten eines Fehlers in einem asynchronen Vorgang an den Host im Beispiel zur SendMail-Aktivität umfasst die folgenden Schritte:  
  
-   Fügen Sie der `SendMailAsyncResult`-Klasse eine Exception-Eigenschaft hinzu.  
  
-   Kopieren Sie den ausgelösten Fehler in diese Eigenschaft im `SendCompleted`-Ereignishandler.  
  
-   Lösen Sie die Ausnahme im `EndExecute`-Ereignishandler aus.  
  
 Der resultierende Code lautet wie folgt.  
  
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
