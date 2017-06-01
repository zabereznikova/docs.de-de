---
title: "Workflowtransaktionen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6081fb02-c0f2-483d-97b8-f3b7dc03011d
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Workflowtransaktionen
[!INCLUDE[wf1](../../../includes/wf1-md.md)] bietet Unterstützung die Beteiligung an <xref:System.Transactions>\-Transaktionen mithilfe der <xref:System.Activities.Statements.TransactionScope>\-Aktivität, um eine transaktive Arbeitseinheit festzulegen.Während das <xref:System.Transactions.TransactionScope?displayProperty=fullName>\-Objekt explizit abgeschlossen werden muss, ruft die <xref:System.Activities.Statements.TransactionScope?displayProperty=fullName>\-Aktivität den Abschluss implizit auf, wenn die Transaktion erfolgreich abgeschlossen wurde.Alle im <xref:System.Activities.Statements.TransactionScope.Body%2A>\-Element der <xref:System.Activities.Statements.TransactionScope>\-Aktivität enthaltenen Elemente sind an der Transaktion beteiligt.WF kann, um Transaktionen der <xref:System.ServiceModel.Activities.TransactedReceiveScope>\-Aktivität in einen Workflow zu übergeben.Wie die <xref:System.Activities.Statements.TransactionScope>\-Aktivität sind alle in <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> enthaltenen Aktivitäten an der Transaktion beteiligt.WF stellt sicher, dass von <xref:System.Transactions.Transaction.Current%2A?displayProperty=fullName> abhängige Aktivitäten mit <xref:System.Activities.Statements.TransactionScope> und <xref:System.ServiceModel.Activities.TransactedReceiveScope> zusammenarbeiten können.Wenn die vom System bereitgestellten Aktivitäten nicht alle Anforderungen berücksichtigen, können mit dem <xref:System.Activities.RuntimeTransactionHandle>\-Objekt benutzerdefinierte Aktivitäten erstellt werden, um erweiterte Szenarien für Fluss\- und Transaktionssteuerelemente zu ermöglichen.  
  
 Im folgenden Ausschnitt aus dem Beispiel [Grundlegender TransactionScope](../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md) wird ein Workflow aus einer <xref:System.Activities.Statements.Sequence>\-Aktivität erstellt, die über untergeordnete Aktivitäten, einschließlich einer <xref:System.Activities.Statements.TransactionScope>\-Aktivität, verfügt.Die <xref:System.Activities.Statements.TransactionScope.Body%2A>\-Aktivitäten von <xref:System.Activities.Statements.TransactionScope> werden unter der Transaktion ausgeführt, die von der <xref:System.Activities.Statements.TransactionScope>\-Aktivität initialisiert wurde.  
  
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
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] zu grundlegenden Beispielen zu [Transaktionen](../../../docs/framework/windows-workflow-foundation/samples/basic-transactions.md) und zu szenariobasierten Beispielen zu [Transaktionen](../../../docs/framework/windows-workflow-foundation/samples/transactions.md).[!INCLUDE[crdefault](../../../includes/crdefault-md.md)] zur Verwendung von <xref:System.ServiceModel.Activities.TransactedReceiveScope> finden Sie unter [Transaktionsfluss in Workflowdienste und aus Workflowdiensten](../../../docs/framework/wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md).  
  
## Siehe auch  
 <xref:System.Activities.Statements.TransactionScope>   
 <xref:System.Transactions.TransactionScope>   
 <xref:System.Transactions.Transaction.Current%2A?displayProperty=fullName>