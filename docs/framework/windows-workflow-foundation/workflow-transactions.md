---
title: Workflowtransaktionen
ms.date: 03/30/2017
ms.assetid: 6081fb02-c0f2-483d-97b8-f3b7dc03011d
ms.openlocfilehash: 2bb5f6498b365f3b773eea9a5adce1ec1158a289
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="workflow-transactions"></a>Workflowtransaktionen
[!INCLUDE[wf1](../../../includes/wf1-md.md)] bietet Unterstützung die Beteiligung an <xref:System.Transactions>-Transaktionen mithilfe der <xref:System.Activities.Statements.TransactionScope>-Aktivität, um eine transaktive Arbeitseinheit festzulegen. Während das <xref:System.Transactions.TransactionScope?displayProperty=nameWithType>-Objekt explizit abgeschlossen werden muss, ruft die <xref:System.Activities.Statements.TransactionScope?displayProperty=nameWithType>-Aktivität den Abschluss implizit auf, wenn die Transaktion erfolgreich abgeschlossen wurde. Alle im <xref:System.Activities.Statements.TransactionScope.Body%2A> der <xref:System.Activities.Statements.TransactionScope>-Aktivität enthaltenen Elemente sind an der Transaktion beteiligt. WF kann, um Transaktionen der <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Aktivität in einen Workflow zu übergeben. Wie die <xref:System.Activities.Statements.TransactionScope>-Aktivität sind alle in <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> enthaltenen Aktivitäten an der Transaktion beteiligt. WF stellt sicher, dass von <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType> abhängige Aktivitäten mit <xref:System.Activities.Statements.TransactionScope> und <xref:System.ServiceModel.Activities.TransactedReceiveScope> zusammenarbeiten können. Wenn die vom System bereitgestellten Aktivitäten nicht alle Anforderungen berücksichtigen, können mit dem <xref:System.Activities.RuntimeTransactionHandle>-Objekt benutzerdefinierte Aktivitäten erstellt werden, um erweiterte Szenarien für Fluss- und Transaktionssteuerelemente zu ermöglichen.  
  
 Im folgenden Beispiel entnommen der [grundlegender TransactionScope](../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md) Beispiel ein Workflow erstellt, bestehend aus einer <xref:System.Activities.Statements.Sequence> Aktivität, die untergeordneten Aktivitäten, einschließlich enthält eine <xref:System.Activities.Statements.TransactionScope> Aktivität. Die <xref:System.Activities.Statements.TransactionScope.Body%2A>-Aktivitäten von <xref:System.Activities.Statements.TransactionScope> werden unter der Transaktion ausgeführt, die von der <xref:System.Activities.Statements.TransactionScope>-Aktivität initialisiert wurde.  
  
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
  
 Weitere Informationen finden Sie in die grundlegende [Transaktionen](../../../docs/framework/windows-workflow-foundation/samples/transactions.md) Beispiele und das Szenario basierend [Transaktionen](../../../docs/framework/windows-workflow-foundation/samples/transactions.md) Beispiele. Weitere Informationen finden Sie unter zur Verwendung von <xref:System.ServiceModel.Activities.TransactedReceiveScope>, finden Sie unter [Transaktionen fließen in und aus Workflowdiensten](../../../docs/framework/wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Activities.Statements.TransactionScope>  
 <xref:System.Transactions.TransactionScope>  
 <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType>
