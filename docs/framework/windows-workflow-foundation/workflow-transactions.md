---
title: Workflowtransaktionen
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6081fb02-c0f2-483d-97b8-f3b7dc03011d
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 66eecb9795c5a65b03559c28f2bfab0b3992bc8f
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="workflow-transactions"></a><span data-ttu-id="99d0c-102">Workflowtransaktionen</span><span class="sxs-lookup"><span data-stu-id="99d0c-102">Workflow Transactions</span></span>
[!INCLUDE[wf1](../../../includes/wf1-md.md)]<span data-ttu-id="99d0c-103"> bietet Unterstützung die Beteiligung an <xref:System.Transactions>-Transaktionen mithilfe der <xref:System.Activities.Statements.TransactionScope>-Aktivität, um eine transaktive Arbeitseinheit festzulegen.</span><span class="sxs-lookup"><span data-stu-id="99d0c-103"> provides support for participating in <xref:System.Transactions> transactions by using the <xref:System.Activities.Statements.TransactionScope> activity to scope a transacted unit of work.</span></span> <span data-ttu-id="99d0c-104">Während das <xref:System.Transactions.TransactionScope?displayProperty=nameWithType>-Objekt explizit abgeschlossen werden muss, ruft die <xref:System.Activities.Statements.TransactionScope?displayProperty=nameWithType>-Aktivität den Abschluss implizit auf, wenn die Transaktion erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="99d0c-104">While the <xref:System.Transactions.TransactionScope?displayProperty=nameWithType> must be explicitly completed the <xref:System.Activities.Statements.TransactionScope?displayProperty=nameWithType> activity implicitly calls complete on the transaction upon successful completion.</span></span> <span data-ttu-id="99d0c-105">Alle im <xref:System.Activities.Statements.TransactionScope.Body%2A> der <xref:System.Activities.Statements.TransactionScope>-Aktivität enthaltenen Elemente sind an der Transaktion beteiligt.</span><span class="sxs-lookup"><span data-stu-id="99d0c-105">Any activities that are contained in the <xref:System.Activities.Statements.TransactionScope.Body%2A> of the <xref:System.Activities.Statements.TransactionScope> activity participate in the transaction.</span></span> <span data-ttu-id="99d0c-106">WF kann, um Transaktionen der <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Aktivität in einen Workflow zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="99d0c-106">WF can to flow transactions into a workflow through the use of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="99d0c-107">Wie die <xref:System.Activities.Statements.TransactionScope>-Aktivität sind alle in <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> enthaltenen Aktivitäten an der Transaktion beteiligt.</span><span class="sxs-lookup"><span data-stu-id="99d0c-107">Like the <xref:System.Activities.Statements.TransactionScope> activity, any activity contained in the <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> participates in the transaction.</span></span> <span data-ttu-id="99d0c-108">WF stellt sicher, dass von <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType> abhängige Aktivitäten mit <xref:System.Activities.Statements.TransactionScope> und <xref:System.ServiceModel.Activities.TransactedReceiveScope> zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="99d0c-108">WF ensures that activities dependent on <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType> works with both <xref:System.Activities.Statements.TransactionScope> and <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span> <span data-ttu-id="99d0c-109">Wenn die vom System bereitgestellten Aktivitäten nicht alle Anforderungen berücksichtigen, können mit dem <xref:System.Activities.RuntimeTransactionHandle>-Objekt benutzerdefinierte Aktivitäten erstellt werden, um erweiterte Szenarien für Fluss- und Transaktionssteuerelemente zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="99d0c-109">If the system-provided activities do not address all requirements, custom activities can be built using the <xref:System.Activities.RuntimeTransactionHandle> to enable advanced flow and transaction control scenarios.</span></span>  
  
 <span data-ttu-id="99d0c-110">Im folgenden Beispiel entnommen der [grundlegender TransactionScope](../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md) Beispiel ein Workflow erstellt, bestehend aus einer <xref:System.Activities.Statements.Sequence> Aktivität, die untergeordneten Aktivitäten, einschließlich enthält eine <xref:System.Activities.Statements.TransactionScope> Aktivität.</span><span class="sxs-lookup"><span data-stu-id="99d0c-110">In the following example, taken from the [Basic TransactionScope](../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md) sample, a workflow is constructed consisting of a <xref:System.Activities.Statements.Sequence> activity that contains child activities including a <xref:System.Activities.Statements.TransactionScope> activity.</span></span> <span data-ttu-id="99d0c-111">Die <xref:System.Activities.Statements.TransactionScope.Body%2A>-Aktivitäten von <xref:System.Activities.Statements.TransactionScope> werden unter der Transaktion ausgeführt, die von der <xref:System.Activities.Statements.TransactionScope>-Aktivität initialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="99d0c-111">The <xref:System.Activities.Statements.TransactionScope.Body%2A> activities of the <xref:System.Activities.Statements.TransactionScope> execute under the transaction initialized by the <xref:System.Activities.Statements.TransactionScope> activity.</span></span>  
  
```csharp  
static Activity ScenarioOne()  
{  
    return new Sequence  
    {  
        Activities =  
        {  
            new WriteLine { Text = "    Begin workflow" },  
  
            new TransactionScope  
            {  
                Body = new Sequence  
                {  
                    Activities =   
                    {  
                        new WriteLine { Text = "    Begin TransactionScope" },  
  
                        new PrintTransactionId(),  
  
                        new TransactionScopeTest(),  
  
                        new WriteLine { Text = "    End TransactionScope" },  
                    },  
                },  
            },  
  
            new WriteLine { Text = "    End workflow" },  
        }  
    };  
}  
```  
  
 <span data-ttu-id="99d0c-112">Weitere Informationen finden Sie in die grundlegende [Transaktionen](../../../docs/framework/windows-workflow-foundation/samples/transactions.md) Beispiele und das Szenario basierend [Transaktionen](../../../docs/framework/windows-workflow-foundation/samples/transactions.md) Beispiele.</span><span class="sxs-lookup"><span data-stu-id="99d0c-112">For more information, see the basic [Transactions](../../../docs/framework/windows-workflow-foundation/samples/transactions.md) samples, and the scenario based [Transactions](../../../docs/framework/windows-workflow-foundation/samples/transactions.md) samples.</span></span> <span data-ttu-id="99d0c-113">Weitere Informationen finden Sie unter zur Verwendung von <xref:System.ServiceModel.Activities.TransactedReceiveScope>, finden Sie unter [Transaktionen fließen in und aus Workflowdiensten](../../../docs/framework/wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="99d0c-113">For more information, see about using <xref:System.ServiceModel.Activities.TransactedReceiveScope>, see [Flowing Transactions into and out of Workflow Services](../../../docs/framework/wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99d0c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99d0c-114">See Also</span></span>  
 <xref:System.Activities.Statements.TransactionScope>  
 <xref:System.Transactions.TransactionScope>  
 <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType>
