---
title: Fehlerbehandlung in asynchronen Aktivitäten
ms.date: 03/30/2017
ms.assetid: e8f8ce2b-50c9-4e44-b187-030e0cf30a5d
ms.openlocfilehash: c63ce231687b03bdba57edd38c32270eabeff834
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182951"
---
# <a name="error-handling-in-asynchronous-activities"></a><span data-ttu-id="47f90-102">Fehlerbehandlung in asynchronen Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="47f90-102">Error handling in asynchronous activities</span></span>
<span data-ttu-id="47f90-103">Bei der Bereitstellung der Fehlerbehandlung in <xref:System.Activities.AsyncCodeActivity> wird der Fehler durch das Rückrufsystem der Aktivität zurückverfolgt.</span><span class="sxs-lookup"><span data-stu-id="47f90-103">Providing error handling in an <xref:System.Activities.AsyncCodeActivity> involves routing the error through the activity’s callback system.</span></span> <span data-ttu-id="47f90-104">In diesem Thema wird mithilfe des Beispiels zur SendMail-Aktivität beschrieben, wie ein Fehler, der in einem asynchronen Vorgang auftritt, an den Host zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="47f90-104">This topic describes how to get an error that is thrown in an asynchronous operation back to the host, using the SendMail activity sample.</span></span>  
  
## <a name="returning-an-error-thrown-in-an-asynchronous-activity-back-to-the-host"></a><span data-ttu-id="47f90-105">Zurückgeben eines Fehlers, der in einer asynchronen Aktivität ausgelöst wurde, an den Host</span><span class="sxs-lookup"><span data-stu-id="47f90-105">Returning an error thrown in an asynchronous activity back to the host</span></span>  
 <span data-ttu-id="47f90-106">Das Zurückleiten eines Fehlers in einem asynchronen Vorgang an den Host im Beispiel zur SendMail-Aktivität umfasst die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="47f90-106">Routing an error in an asynchronous operation back to the host in the SendMail activity sample involves the following steps:</span></span>  
  
- <span data-ttu-id="47f90-107">Fügen Sie der `SendMailAsyncResult`-Klasse eine Exception-Eigenschaft hinzu.</span><span class="sxs-lookup"><span data-stu-id="47f90-107">Add an Exception property to the `SendMailAsyncResult` class.</span></span>  
  
- <span data-ttu-id="47f90-108">Kopieren Sie den ausgelösten Fehler in diese Eigenschaft im `SendCompleted`-Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="47f90-108">Copy the thrown error to that property in the `SendCompleted` event handler.</span></span>  
  
- <span data-ttu-id="47f90-109">Lösen Sie die Ausnahme im `EndExecute`-Ereignishandler aus.</span><span class="sxs-lookup"><span data-stu-id="47f90-109">Throw the exception in the `EndExecute` event handler.</span></span>  
  
 <span data-ttu-id="47f90-110">Der resultierende Code lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="47f90-110">The resulting code is as follows.</span></span>  
  
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
