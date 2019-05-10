---
title: Fehlerbehandlung in asynchronen Aktivitäten
ms.date: 03/30/2017
ms.assetid: e8f8ce2b-50c9-4e44-b187-030e0cf30a5d
ms.openlocfilehash: 7a1db144e4738870d3ff5fe68df11b2fb06ef3d7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64640960"
---
# <a name="error-handling-in-asynchronous-activities"></a>Fehlerbehandlung in asynchronen Aktivitäten
Bei der Bereitstellung der Fehlerbehandlung in <xref:System.Activities.AsyncCodeActivity> wird der Fehler durch das Rückrufsystem der Aktivität zurückverfolgt. In diesem Thema wird mithilfe des Beispiels zur SendMail-Aktivität beschrieben, wie ein Fehler, der in einem asynchronen Vorgang auftritt, an den Host zurückgegeben wird.  
  
## <a name="returning-an-error-thrown-in-an-asynchronous-activity-back-to-the-host"></a>Zurückgeben eines Fehlers, der in einer asynchronen Aktivität ausgelöst wurde, an den Host  
 Das Zurückleiten eines Fehlers in einem asynchronen Vorgang an den Host im Beispiel zur SendMail-Aktivität umfasst die folgenden Schritte:  
  
- Fügen Sie der `SendMailAsyncResult`-Klasse eine Exception-Eigenschaft hinzu.  
  
- Kopieren Sie den ausgelösten Fehler in diese Eigenschaft im `SendCompleted`-Ereignishandler.  
  
- Lösen Sie die Ausnahme im `EndExecute`-Ereignishandler aus.  
  
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
