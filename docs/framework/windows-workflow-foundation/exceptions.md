---
title: Ausnahmen
ms.date: 03/30/2017
ms.assetid: 065205cc-52dd-4f30-9578-b17d8d113136
ms.openlocfilehash: 53cc8e3e27e131c5c2a9f8271851a0d8d7e0cbd7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280207"
---
# <a name="exceptions"></a>Ausnahmen

Die <xref:System.Activities.Statements.TryCatch>-Aktivität kann zur Behandlung von Ausnahmen verwendet werden, die während der Ausführung eines Workflows ausgelöst werden. Diese Ausnahmen können behandelt oder mit der <xref:System.Activities.Statements.Rethrow>-Aktivität erneut ausgelöst werden. Aktivitäten im Abschnitt <xref:System.Activities.Statements.TryCatch.Finally%2A> werden nach Abschluss des Abschnitts <xref:System.Activities.Statements.TryCatch.Try%2A> oder des Abschnitts <xref:System.Activities.Statements.TryCatch.Catches%2A> ausgeführt. Von einer-Instanz gehostete Workflows <xref:System.Activities.WorkflowApplication> können auch den- <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> Ereignishandler verwenden, um Ausnahmen zu behandeln, die nicht von einer-Aktivität behandelt werden <xref:System.Activities.Statements.TryCatch> .  
  
## <a name="causes-of-exceptions"></a>Ursachen von Ausnahmen  

 In einem Workflow können Ausnahmen auf die folgenden Weisen generiert werden:  
  
- Ein Timeout von Transaktionen in <xref:System.Activities.Statements.TransactionScope>.  
  
- Eine explizite vom Workflow mit der <xref:System.Activities.Statements.Throw>-Aktivität ausgelöste Ausnahme.  
  
- Eine von einer Aktivität ausgelöste [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]-Ausnahme.  
  
- Eine von externem Code ausgelöste Ausnahme, z. B. Bibliotheken, Komponenten oder Dienste, die im Workflow verwendet werden.  
  
## <a name="handling-exceptions"></a>Behandeln von Ausnahmen  

 Wenn eine Ausnahme von einer Aktivität ausgelöst und nicht behandelt wird, ist das Beenden der Workflowinstanz das Standardverhalten. Wenn ein benutzerdefinierter <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>-Handler vorhanden ist, kann dieser das Standardverhalten überschreiben. Mit diesem Handler kann der Autor des Workflowhosts die angemessene Behandlung bereitstellen, z. B. benutzerdefinierte Protokollierung, Abbruch des Workflows oder Beenden des Workflows.  Wenn ein Workflow eine nicht behandelte Ausnahme auslöst, wird der <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>-Handler aufgerufen. Es gibt drei mögliche Aktionen, die von <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> zurückgegeben werden und das endgültige Ergebnis des Workflows bestimmen.  
  
- **Abbrechen** -eine abgebrochene Workflow Instanz ist ein ordnungsgemäßes Beenden einer Verzweigungs Ausführung. Sie können das Abbruchverhalten anpassen (z. B. durch Verwendung einer CancellationScope-Aktivität). Der Completed-Handler wird aufgerufen, wenn der Abbruchprozess abgeschlossen wird. Ein abgebrochener Workflow befindet sich im Cancelled-Zustand.  
  
- **Beenden** -eine beendete Workflow Instanz kann nicht fortgesetzt oder neu gestartet werden.  Dadurch wird das Completed-Ereignis ausgelöst, in dem Sie eine Ausnahme als Grund für die Beendigung bereitstellen können. Der Terminated-Handler wird aufgerufen, wenn der Beendigungsprozess abgeschlossen wird. Ein beendeter Workflow befindet sich im Faulted-Zustand.  
  
- **Abbrechen-eine abgebrochene** Workflow Instanz kann nur fortgesetzt werden, wenn Sie als persistent konfiguriert wurde.  Ohne Persistenz kann ein Workflow nicht fortgesetzt werden.  An dem Punkt, an dem ein Workflow abgebrochen wird, gehen alle seit dem letzten Persistenzpunkt verarbeiteten Daten (im Arbeitsspeicher) verloren. Für einen abgebrochenen Workflow wird der Aborted-Handler unter Verwendung der Ausnahme als Grund ausgelöst, wenn der Abbruchprozess beendet wird. Im Gegensatz zum Cancelled- und Terminated-Handler wird der Completed-Handler jedoch nicht aufgerufen. Ein abgebrochener Workflow befindet sich in einem Aborted-Zustand.  
  
 Im folgenden Beispiel wird ein Workflow aufgerufen, der eine Ausnahme auslöst. Die Ausnahme wird vom Workflow nicht behandelt, und der <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>-Handler wird aufgerufen. Die <xref:System.Activities.WorkflowApplicationUnhandledExceptionEventArgs> werden überprüft, um Informationen zur Ausnahme bereitzustellen, und der Workflow wird beendet.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#1](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#1)]  
  
### <a name="handling-exceptions-with-the-trycatch-activity"></a>Behandeln von Ausnahmen mit der TryCatch-Aktivität  

 Zur Behandlung von Ausnahmen innerhalb eines Workflows dient die <xref:System.Activities.Statements.TryCatch>-Aktivität. Die <xref:System.Activities.Statements.TryCatch>-Aktivität verfügt über eine <xref:System.Activities.Statements.TryCatch.Catches%2A>-Auflistung von <xref:System.Activities.Statements.Catch>-Aktivitäten, von denen jede einzelne einem bestimmten <xref:System.Exception>-Typ zugeordnet ist. Wenn die Ausnahme, die von einer Aktivität im <xref:System.Activities.Statements.TryCatch.Try%2A>-Abschnitt einer <xref:System.Activities.Statements.TryCatch>-Aktivität ausgelöst wurde, der Ausnahme einer <xref:System.Activities.Statements.Catch%601>-Aktivität in der <xref:System.Activities.Statements.TryCatch.Catches%2A>-Auflistung entspricht, wird die Ausnahme behandelt. Wenn die Ausnahme explizit erneut ausgelöst wird oder eine neue Ausnahme ausgelöst wird, erfolgt die Übergabe dieser Ausnahme an die übergeordnete Aktivität. Das folgende Codebeispiel zeigt eine <xref:System.Activities.Statements.TryCatch>-Aktivität, mit der eine <xref:System.ApplicationException>-Ausnahme behandelt wird, die im <xref:System.Activities.Statements.TryCatch.Try%2A>-Abschnitt von einer <xref:System.Activities.Statements.Throw>-Aktivität ausgelöst wurde. Die Meldung der Ausnahme wird von der <xref:System.Activities.Statements.Catch%601>-Aktivität auf der Konsole ausgegeben. Anschließend wird eine Meldung im <xref:System.Activities.Statements.TryCatch.Finally%2A>-Abschnitt auf der Konsole ausgegeben.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#33](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#33)]  
  
 Die Aktivitäten im <xref:System.Activities.Statements.TryCatch.Finally%2A>-Abschnitt werden ausgeführt, wenn entweder der <xref:System.Activities.Statements.TryCatch.Try%2A>-Abschnitt oder der <xref:System.Activities.Statements.TryCatch.Catches%2A>-Abschnitt erfolgreich ausgeführt wurde. Der <xref:System.Activities.Statements.TryCatch.Try%2A>-Abschnitt wird erfolgreich abgeschlossen, sofern er keine Ausnahmen auslöst, und der <xref:System.Activities.Statements.TryCatch.Catches%2A>-Abschnitt wird erfolgreich abgeschlossen, wenn er keine Ausnahmen auslöst oder erneut auslöst. Wenn im <xref:System.Activities.Statements.TryCatch.Try%2A>-Abschnitt von <xref:System.Activities.Statements.TryCatch> eine Ausnahme ausgelöst und nicht von einem <xref:System.Activities.Statements.Catch%601> im <xref:System.Activities.Statements.TryCatch.Catches%2A>-Abschnitt behandelt wird oder durch <xref:System.Activities.Statements.TryCatch.Catches%2A> erneut ausgelöst wird, werden die Aktivitäten in <xref:System.Activities.Statements.TryCatch.Finally%2A> erst ausgeführt, nachdem eines der folgenden Ereignisse eintritt.  
  
- Die Ausnahme wird von einer <xref:System.Activities.Statements.TryCatch>-Workflowaktivität auf einer höheren Ebene abgefangen, unabhängig davon, ob sie von <xref:System.Activities.Statements.TryCatch> auf dieser höheren Ebene erneut ausgelöst wird.  
  
- Die Ausnahme wird nicht von <xref:System.Activities.Statements.TryCatch> auf einer höheren Ebene behandelt, schützt den Stamm des Workflows mit Escapezeichen, und der Workflow wird so konfiguriert, dass er abgebrochen wird, anstatt beendet oder abgebrochen zu werden. Workflows, die mithilfe von <xref:System.Activities.WorkflowApplication> gehostet werden, können diese Konfiguration vornehmen, indem sie <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> behandeln und <xref:System.Activities.UnhandledExceptionAction.Cancel> zurückgeben. Ein Beispiel für die Behandlung von <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> wurde zuvor in diesem Thema bereitgestellt. Workflowdienste können diese Konfiguration vornehmen, indem sie <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> verwenden und <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction.Cancel> angeben. Ein Beispiel für das Konfigurieren von <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> finden Sie unter [Erweiterbarkeit des Workflow Dienst Hosts](../wcf/feature-details/workflow-service-host-extensibility.md).  
  
## <a name="exception-handling-versus-compensation"></a>Ausnahmebehandlung und Kompensierung  

 Der Unterschied zwischen Ausnahmebehandlung und Kompensierung besteht darin, dass die Ausnahmebehandlung während der Ausführung einer Aktivität erfolgt. Die Kompensierung erfolgt, nachdem eine Aktivität erfolgreich abgeschlossen wurde. Die Ausnahmebehandlung bietet eine Möglichkeit, nach dem Auslösen der Ausnahme durch die Aktivität eine Bereinigung durchzuführen. Die Kompensierung dagegen stellt einen Mechanismus bereit, mit dem die erfolgreich abgeschlossene Arbeit einer zuvor abgeschlossenen Aktivität rückgängig gemacht werden kann. Weitere Informationen finden Sie unter [Kompensierung](compensation.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Activities.Statements.TryCatch>
- <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>
- <xref:System.Activities.Statements.CompensableActivity>
