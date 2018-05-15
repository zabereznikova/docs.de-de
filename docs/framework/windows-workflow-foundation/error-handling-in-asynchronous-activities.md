---
title: Fehlerbehandlung in asynchronen Aktivitäten
ms.date: 03/30/2017
ms.assetid: e8f8ce2b-50c9-4e44-b187-030e0cf30a5d
ms.openlocfilehash: 4a7cbecef596eec6eaa128b8ffc7bc5c6e4b79bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="error-handling-in-asynchronous-activities"></a><span data-ttu-id="6b31f-102">Fehlerbehandlung in asynchronen Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="6b31f-102">Error handling in asynchronous activities</span></span>
<span data-ttu-id="6b31f-103">Bei der Bereitstellung der Fehlerbehandlung in <xref:System.Activities.AsyncCodeActivity> wird der Fehler durch das Rückrufsystem der Aktivität zurückverfolgt.</span><span class="sxs-lookup"><span data-stu-id="6b31f-103">Providing error handling in an <xref:System.Activities.AsyncCodeActivity> involves routing the error through the activity’s callback system.</span></span> <span data-ttu-id="6b31f-104">In diesem Thema wird mithilfe des Beispiels zur SendMail-Aktivität beschrieben, wie ein Fehler, der in einem asynchronen Vorgang auftritt, an den Host zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6b31f-104">This topic describes how to get an error that is thrown in an asynchronous operation back to the host, using the SendMail activity sample.</span></span>  
  
## <a name="returning-an-error-thrown-in-an-asynchronous-activity-back-to-the-host"></a><span data-ttu-id="6b31f-105">Zurückgeben eines Fehlers, der in einer asynchronen Aktivität ausgelöst wurde, an den Host</span><span class="sxs-lookup"><span data-stu-id="6b31f-105">Returning an error thrown in an asynchronous activity back to the host</span></span>  
 <span data-ttu-id="6b31f-106">Das Zurückleiten eines Fehlers in einem asynchronen Vorgang an den Host im Beispiel zur SendMail-Aktivität umfasst die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="6b31f-106">Routing an error in an asynchronous operation back to the host in the SendMail activity sample involves the following steps:</span></span>  
  
-   <span data-ttu-id="6b31f-107">Fügen Sie der `SendMailAsyncResult`-Klasse eine Exception-Eigenschaft hinzu.</span><span class="sxs-lookup"><span data-stu-id="6b31f-107">Add an Exception property to the `SendMailAsyncResult` class.</span></span>  
  
-   <span data-ttu-id="6b31f-108">Kopieren Sie den ausgelösten Fehler in diese Eigenschaft im `SendCompleted`-Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="6b31f-108">Copy the thrown error to that property in the `SendCompleted` event handler.</span></span>  
  
-   <span data-ttu-id="6b31f-109">Lösen Sie die Ausnahme im `EndExecute`-Ereignishandler aus.</span><span class="sxs-lookup"><span data-stu-id="6b31f-109">Throw the exception in the `EndExecute` event handler.</span></span>  
  
 <span data-ttu-id="6b31f-110">Der resultierende Code lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="6b31f-110">The resulting code is as follows.</span></span>  
  
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
