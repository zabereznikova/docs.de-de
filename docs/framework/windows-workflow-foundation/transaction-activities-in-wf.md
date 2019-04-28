---
title: Transaktionsaktivitäten in WF
ms.date: 03/30/2017
ms.assetid: fb33378e-82c6-4ea0-870f-76dc77e7f0fe
ms.openlocfilehash: 7ffd64abdc6edf45174d4b756833d65ec0ef747c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670260"
---
# <a name="transaction-activities-in-wf"></a>Transaktionsaktivitäten in WF
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] verfügt über mehrere vom System bereitgestellte Aktivitäten, um Transaktionen, Kompensationen und Abbrüche zu modellieren. Diese Programmiermodelle ermöglichen es dem Workflow, sich weiter vorwärts zu bewegen, falls Änderungen in der Geschäftslogik auftreten oder eine Fehlerbehandlung ausgeführt wird. Weitere Informationen zu Transaktionen, kompensationen und Abbrüche finden Sie unter [Transaktionen](workflow-transactions.md), [Kompensierung](compensation.md), und [Abbruch](modeling-cancellation-behavior-in-workflows.md).  
  
## <a name="transaction-activities"></a>Transaktionsaktivitäten  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.CancellationScope>|Ordnet Abbruchlogik in Form einer Aktivität einem Hauptausführungspfad zu. Wird auch als Aktivität ausgedrückt.|  
|<xref:System.Activities.Statements.CompensableActivity>|Unterstützt die Kompensation der untergeordneten Aktivitäten.|  
|<xref:System.Activities.Statements.Compensate>|Ruft den Kompensationshandler einer <xref:System.Activities.Statements.CompensableActivity> explizit auf|  
|<xref:System.Activities.Statements.Confirm>|Ruft den Bestätigungshandler einer <xref:System.Activities.Statements.CompensableActivity> explizit auf|  
|<xref:System.Activities.Statements.TransactionScope>|Demarkiert eine Transaktionsgrenze.|  
|<xref:System.ServiceModel.Activities.TransactedReceiveScope>|Legt Bereiche für die Lebensdauer einer Transaktion fest, die von einer empfangenen Meldung initiiert wird. Die Transaktion kann in den Workflow der initiierenden Meldung übergeben oder vom Verteiler erstellt werden, wenn die Meldung empfangen wird. **Hinweis**:  Die <xref:System.ServiceModel.Activities.TransactedReceiveScope> befindet sich in der **Messaging** Teil der **Toolbox**.|
