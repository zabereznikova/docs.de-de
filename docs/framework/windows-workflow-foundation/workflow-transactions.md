---
title: Workflowtransaktionen
ms.date: 03/30/2017
ms.assetid: 6081fb02-c0f2-483d-97b8-f3b7dc03011d
ms.openlocfilehash: 17e4b712f5b6955ab777168d60d8a28e8b0ebd63
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670195"
---
# <a name="workflow-transactions"></a>Workflowtransaktionen

[!INCLUDE[wf1](../../../includes/wf1-md.md)] bietet Unterstützung die Beteiligung an <xref:System.Transactions>-Transaktionen mithilfe der <xref:System.Activities.Statements.TransactionScope>-Aktivität, um eine transaktive Arbeitseinheit festzulegen. Während das <xref:System.Transactions.TransactionScope?displayProperty=nameWithType>-Objekt explizit abgeschlossen werden muss, ruft die <xref:System.Activities.Statements.TransactionScope?displayProperty=nameWithType>-Aktivität den Abschluss implizit auf, wenn die Transaktion erfolgreich abgeschlossen wurde. Alle im <xref:System.Activities.Statements.TransactionScope.Body%2A> der <xref:System.Activities.Statements.TransactionScope>-Aktivität enthaltenen Elemente sind an der Transaktion beteiligt. WF kann, um Transaktionen der <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Aktivität in einen Workflow zu übergeben. Wie die <xref:System.Activities.Statements.TransactionScope>-Aktivität sind alle in <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> enthaltenen Aktivitäten an der Transaktion beteiligt. WF stellt sicher, dass von <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType> abhängige Aktivitäten mit <xref:System.Activities.Statements.TransactionScope> und <xref:System.ServiceModel.Activities.TransactedReceiveScope> zusammenarbeiten können. Wenn die vom System bereitgestellten Aktivitäten nicht alle Anforderungen berücksichtigen, können mit dem <xref:System.Activities.RuntimeTransactionHandle>-Objekt benutzerdefinierte Aktivitäten erstellt werden, um erweiterte Szenarien für Fluss- und Transaktionssteuerelemente zu ermöglichen.  
  
Im folgenden Beispiel wird ein Workflow erstellt, bestehend aus einem <xref:System.Activities.Statements.Sequence> Aktivität, die untergeordneten Aktivitäten, einschließlich einer <xref:System.Activities.Statements.TransactionScope> Aktivität. Die <xref:System.Activities.Statements.TransactionScope.Body%2A>-Aktivitäten von <xref:System.Activities.Statements.TransactionScope> werden unter der Transaktion ausgeführt, die von der <xref:System.Activities.Statements.TransactionScope>-Aktivität initialisiert wurde.  
  
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
  
Weitere Informationen finden Sie unter zur Verwendung von <xref:System.ServiceModel.Activities.TransactedReceiveScope>, finden Sie unter [Transaktionen fließen in und aus Workflowdiensten](../wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Activities.Statements.TransactionScope>
- <xref:System.Transactions.TransactionScope>
- <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType>
