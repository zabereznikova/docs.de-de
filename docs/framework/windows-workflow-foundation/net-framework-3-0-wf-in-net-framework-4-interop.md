---
title: Verwenden von .NET Framework 3.0-WF-Aktivitäten unter .NET Framework 4 mit der Interop-Aktivität
ms.date: 03/30/2017
ms.assetid: 71f112ba-abb0-46f7-b05f-a5d2eb9d0c5c
ms.openlocfilehash: 02f7a4d9cdda0a6c4f23574c5a20ac78eb783ef2
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556075"
---
# <a name="using-net-framework-30-wf-activities-in-net-framework-4-with-the-interop-activity"></a>Verwenden von .NET Framework 3.0-WF-Aktivitäten unter .NET Framework 4 mit der Interop-Aktivität
Bei der <xref:System.Activities.Statements.Interop> Aktivität handelt es sich um eine-Aktivität [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] (WF 4,5), die eine .NET Framework 3,5 (WF 3,5)-Aktivität innerhalb eines Workflows umschließt [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] . Die WF 3-Aktivität kann eine einzelne Blattaktivität oder eine ganze Aktivitätsstruktur darstellen. Die Ausführung (einschließlich Abbruch und Ausnahmebehandlung) und die Persistenz der .NET Framework 3,5-Aktivität erfolgen innerhalb des Kontexts der [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] Workflow Instanz, die ausgeführt wird.  
  
> [!NOTE]
> Die- <xref:System.Activities.Statements.Interop> Aktivität wird nicht in der Toolbox des Workflow-Designers angezeigt, es sei denn, für das Projekt des Workflows ist die Einstellung für das **Ziel Framework** auf " **.NET Framework 4,5**  
  
## <a name="criteria-for-using-a-wf-3-activity-with-an-interop-activity"></a>Kriterien für die Verwendung einer WF 3-Aktivität mit einer Interop-Aktivität  
 Damit eine WF 3-Aktivität innerhalb einer <xref:System.Activities.Statements.Interop>-Aktivität erfolgreich ausgeführt werden kann, müssen die folgenden Kriterien erfüllt werden:  
  
- Die WF 3-Aktivität muss von <xref:System.Workflow.ComponentModel.Activity?displayProperty=nameWithType> abgeleitet sein.  
  
- Die WF 3-Aktivität muss als `public` deklariert werden und darf nicht `abstract` sein.  
  
- Die WF 3-Aktivität muss über einen öffentlichen Parameter losen Konstruktor verfügen.  
  
- Aufgrund von Einschränkungen bei den Schnittstellentypen, die die <xref:System.Activities.Statements.Interop>-Aktivität unterstützen kann, können das <xref:System.Workflow.Activities.HandleExternalEventActivity>-Objekt und das <xref:System.Workflow.Activities.CallExternalMethodActivity>-Objekt nicht direkt verwendet werden. Abgeleitete Aktivitäten, die mit dem Tool für Workflow-Kommunikationsaktivitäten (WCA.exe) erstellt wurden, können jedoch verwendet werden. Weitere Informationen finden Sie unter [Windows Workflow Foundation Tools](/previous-versions/dotnet/netframework-3.5/ms734408(v=vs.90)) .  
  
## <a name="configuring-a-wf-3-activity-within-an-interop-activity"></a>Konfigurieren einer WF 3-Aktivität innerhalb einer Interop-Aktivität  
 Um Daten zu konfigurieren und in bzw. aus einer WF 3-Aktivität über die Grenzen der Interoperation zu übergeben, werden die Eigenschaften und die Metadateneigenschaften der WF 3-Aktivität von der <xref:System.Activities.Statements.Interop>-Aktivität verfügbar gemacht. Die Metadateneigenschaften der WF 3-Aktivität (z. B. <xref:System.Workflow.ComponentModel.Activity.Name%2A>) werden über die <xref:System.Activities.Statements.Interop.ActivityMetaProperties%2A>-Auflistung verfügbar gemacht. Dies ist eine Auflistung von Name-Wert-Paaren, mit denen die Werte für die Metadateneigenschaften der WF 3-Aktivität definiert werden. Eine Metadateneigenschaft ist eine Eigenschaft, die von der Abhängigkeitseigenschaft unterstützt wird, für die das <xref:System.Workflow.ComponentModel.DependencyPropertyOptions.Metadata>-Kennzeichen festgelegt ist.  
  
 Die Eigenschaften der WF 3-Aktivität werden über die <xref:System.Activities.Statements.Interop.ActivityProperties%2A>-Auflistung verfügbar gemacht. Dies ist ein Satz von Name-Wert-Paaren, wobei jeder Wert ein <xref:System.Activities.Argument>-Objekt ist, mit dem Argumente für die Eigenschaften der WF 3-Aktivität definiert werden. Da die Richtung einer WF 3-Aktivitäts Eigenschaft nicht abgeleitet werden kann, wird jede Eigenschaft als <xref:System.Activities.InArgument> / <xref:System.Activities.OutArgument> paar angezeigt. Abhängig von der Verwendung der Aktivitätseigenschaft empfiehlt es sich, einen <xref:System.Activities.InArgument>-Eintrag, einen <xref:System.Activities.OutArgument>-Eintrag oder beides bereitzustellen. Der erwartete Name des <xref:System.Activities.InArgument>-Eintrags in der Auflistung entspricht dem Namen der Eigenschaft, wie sie für die WF 3-Aktivität definiert wurde. Der erwartete Name des <xref:System.Activities.OutArgument> Eintrags in der Auflistung ist eine Verkettung des Namens der Eigenschaft und der Zeichenfolge "out".  
  
## <a name="limitations-of-using-a-wf-3-activity-within-an-interop-activity"></a>Einschränkungen bei der Verwendung einer WF 3-Aktivität innerhalb einer Interop-Aktivität  
 Die vom System bereitgestellten WF 3-Aktivitäten können nicht direkt in einer <xref:System.Activities.Statements.Interop>-Aktivität umschlossen werden. Bei einigen WF 3-Aktivitäten ist der Grund hierfür, dass es eine analoge WF 4.5-Aktivität wie z. B. <xref:System.Workflow.Activities.DelayActivity> gibt. Bei anderen rührt dies daher, dass die Funktionalität der Aktivität nicht unterstützt wird. Viele vom System bereitgestellte WF 3-Aktivitäten können in Workflows verwendet werden, die von der <xref:System.Activities.Statements.Interop>-Aktivität umschlossen werden, jedoch mit folgenden Einschränkungen:  
  
1. Das <xref:System.ServiceModel.Activities.Send>-Objekt und das <xref:System.ServiceModel.Activities.Receive>-Objekt können nicht in einer <xref:System.Activities.Statements.Interop>-Aktivität verwendet werden.  
  
2. Die Objekte <xref:System.Workflow.Activities.WebServiceInputActivity>, <xref:System.Workflow.Activities.WebServiceOutputActivity> und <xref:System.Workflow.Activities.WebServiceFaultActivity> können nicht in einer <xref:System.Activities.Statements.Interop>-Aktivität verwendet werden.  
  
3. Das <xref:System.Workflow.Activities.InvokeWorkflowActivity>-Objekt kann nicht in einer <xref:System.Activities.Statements.Interop>-Aktivität verwendet werden.  
  
4. Das <xref:System.Workflow.ComponentModel.SuspendActivity>-Objekt kann nicht in einer <xref:System.Activities.Statements.Interop>-Aktivität verwendet werden.  
  
5. Kompensationsbezogene Aktivitäten können nicht in einer <xref:System.Activities.Statements.Interop>-Aktivität verwendet werden.  
  
 Es gibt auch einige bestimmte Verhaltensmerkmale bezüglich der Verwendung von WF 3-Aktivitäten in der <xref:System.Activities.Statements.Interop>-Aktivität:  
  
1. In einer <xref:System.Activities.Statements.Interop>-Aktivität enthaltene WF 3-Aktivitäten werden initialisiert, wenn die <xref:System.Activities.Statements.Interop>-Aktivität ausgeführt wird. In WF 4.5 gibt es vor der Ausführung keine Initialisierungsphase für eine Workflowinstanz.  
  
2. Die WF 4.5-Laufzeit setzt unabhängig davon, wo diese Transaktion beginnt (innerhalb oder außerhalb einer <xref:System.Activities.Statements.Interop>-Aktivität), keinen Prüfpunkt für den Workflowinstanzzustand, wenn eine Transaktion beginnt.  
  
3. WF 3-Nachverfolgungsdatensätze für Aktivitäten in einer <xref:System.Activities.Statements.Interop>-Aktivität werden für WF 4.5-Nachverfolgungsteilnehmer in Form von <xref:System.Activities.Tracking.InteropTrackingRecord>-Objekten bereitgestellt. <xref:System.Activities.Tracking.InteropTrackingRecord> ist eine Ableitung von <xref:System.Activities.Tracking.CustomTrackingRecord>.  
  
4. Eine benutzerdefinierte WF 3-Aktivität kann über Workflowwarteschlangen in der Interoperationsumgebung auf Daten zugreifen, wie dies auch innerhalb der WF 3-Workflowlaufzeit möglich ist. Es sind keine benutzerdefinierten Änderungen an Aktivitätscode erforderlich. Auf dem Host werden Daten in eine WF 3-Workflowwarteschlange eingereiht, indem ein <xref:System.Activities.Bookmark>-Objekt wieder aufgenommen wird. Der Name des Lesezeichens entspricht dem Workflow-Warteschlangennamen des <xref:System.IComparable>-Objekts in Form einer Zeichenfolge.
