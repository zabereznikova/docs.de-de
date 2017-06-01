---
title: "Verwenden von .NET Framework 3.0-WF-Aktivit&#228;ten unter .NET Framework 4 mit der Interop-Aktivit&#228;t | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 71f112ba-abb0-46f7-b05f-a5d2eb9d0c5c
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Verwenden von .NET Framework 3.0-WF-Aktivit&#228;ten unter .NET Framework 4 mit der Interop-Aktivit&#228;t
Die <xref:System.Activities.Statements.Interop> Aktivität ist eine [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] (WF 4.5)-Aktivität, die umschließt ein [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] (WF 3.5)-Aktivität in einen [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] Workflow. Die WF 3-Aktivität kann eine einzelne Blattaktivität oder eine ganze Aktivitätsstruktur darstellen. Die Ausführung (einschließlich Abbruch und Ausnahmebehandlung) und die Persistenz der [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]-Aktivität treten im Kontext der [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] Workflowinstanz auf, die ausgeführt wird.  
  
> [!NOTE]
>  Die <xref:System.Activities.Statements.Interop> Aktivität wird nicht in der Toolbox des Workflow-Designers angezeigt, es sei denn, der Workflow-Projekt die **Zielframework** eingestellt **.NET Framework 4.5**.  
  
## <a name="criteria-for-using-a-wf-3-activity-with-an-interop-activity"></a>Kriterien für die Verwendung einer WF 3-Aktivität mit einer Interop-Aktivität  
 Für eine WF 3-Aktivität, die erfolgreich in ausgeführt ein <xref:System.Activities.Statements.Interop> Aktivität, die folgenden Kriterien müssen erfüllt sein:  
  
-   Die WF 3-Aktivität durch Ableiten von <xref:System.Workflow.ComponentModel.Activity?displayProperty=fullName>.  
  
-   Die WF 3-Aktivität muss als `public` deklariert werden und darf nicht `abstract` sein.  
  
-   Die WF 3-Aktivität muss über einen öffentlichen Standardkonstruktor verfügen.  
  
-   Aufgrund von Einschränkungen in der Benutzeroberfläche aufgeführt, die die <xref:System.Activities.Statements.Interop> -Aktivität unterstützen kann, <xref:System.Workflow.Activities.HandleExternalEventActivity> und <xref:System.Workflow.Activities.CallExternalMethodActivity> nicht direkt verwendete werden, jedoch abgeleitete Aktivitäten, die mit dem Workflow-Kommunikationsaktivität-Tool (WCA.exe) erstellt verwendet werden kann. Finden Sie unter [Windows Workflow Foundation – Tools](http://go.microsoft.com/fwlink/?LinkId=178889) Details.  
  
## <a name="configuring-a-wf-3-activity-within-an-interop-activity"></a>Konfigurieren einer WF 3-Aktivität innerhalb einer Interop-Aktivität  
 Zum Konfigurieren und Daten in und aus einer WF 3-Aktivität über die Grenzen der interoperation übergeben, die WF 3-Aktivität Eigenschaften und Metadaten-Eigenschaften sind verfügbar von der <xref:System.Activities.Statements.Interop> Aktivität. Metadateneigenschaften der WF 3-Aktivität (z. B. <xref:System.Workflow.ComponentModel.Activity.Name%2A>) verfügbar gemacht werden, werden über die <xref:System.Activities.Statements.Interop.ActivityMetaProperties%2A> Auflistung. Dies ist eine Auflistung von Name-Wert-Paaren, mit denen die Werte für die Metadateneigenschaften der WF 3-Aktivität definiert werden. Eine Metadateneigenschaft ist eine Eigenschaft, die von der Abhängigkeitseigenschaft unterstützt wird, für die die <xref:System.Workflow.ComponentModel.DependencyPropertyOptions> -Flag festgelegt ist.  
  
 Eigenschaften der WF 3-Aktivität werden verfügbar gemacht, über die <xref:System.Activities.Statements.Interop.ActivityProperties%2A> Auflistung. Dies ist ein Satz von Name-Wert-Paare, in denen jeder Wert ein <xref:System.Activities.Argument> Objekt, das verwendet wird, um die Argumente für die Eigenschaften der WF 3-Aktivität zu definieren. Da die Richtung der Eigenschaft einer WF 3-Aktivität nicht abgeleitet werden kann, wird jede Eigenschaft angegeben, als ein <xref:System.Activities.InArgument>/<xref:System.Activities.OutArgument> Paar. Je nach der Aktivität die Verwendung der Eigenschaft, möchten Sie evtl. Angeben einer <xref:System.Activities.InArgument> Eintrag ein <xref:System.Activities.OutArgument> -Eintrag oder beides. Der erwartete Name des dem <xref:System.Activities.InArgument> Eintrag in der Auflistung ist der Name der Eigenschaft für die WF 3-Aktivität definiert. Der erwartete Name des dem <xref:System.Activities.OutArgument> Eintrag in der Auflistung ist eine Verkettung des Namens der Eigenschaft und die Zeichenfolge "Out".  
  
## <a name="limitations-of-using-a-wf-3-activity-within-an-interop-activity"></a>Einschränkungen bei der Verwendung einer WF 3-Aktivität innerhalb einer Interop-Aktivität  
 Die vom System bereitgestellten WF 3-Aktivitäten können nicht direkt innerhalb einer <xref:System.Activities.Statements.Interop> Aktivität. Bei einigen WF 3-Aktivitäten wie z. B. <xref:System.Workflow.Activities.DelayActivity>, dies ist, da eine analoge WF 4.5-Aktivität. Bei anderen rührt dies daher, dass die Funktionalität der Aktivität nicht unterstützt wird. Viele WF 3-System bereitgestellte Aktivitäten in Workflows, die vom verwendet werden können die <xref:System.Activities.Statements.Interop> Aktivität, jedoch mit folgenden Einschränkungen:  
  
1.  <xref:System.ServiceModel.Activities.Send> und <xref:System.ServiceModel.Activities.Receive> kann nicht verwendet werden, eine <xref:System.Activities.Statements.Interop> Aktivität.  
  
2.  <xref:System.Workflow.Activities.WebServiceInputActivity>, <xref:System.Workflow.Activities.WebServiceOutputActivity>, und <xref:System.Workflow.Activities.WebServiceFaultActivity> kann nicht verwendet werden, in eine <xref:System.Activities.Statements.Interop> Aktivität.  
  
3.  <xref:System.Workflow.Activities.InvokeWorkflowActivity> kann nicht verwendet werden, in eine <xref:System.Activities.Statements.Interop> Aktivität.  
  
4.  <xref:System.Workflow.ComponentModel.SuspendActivity> kann nicht verwendet werden, in eine <xref:System.Activities.Statements.Interop> Aktivität.  
  
5.  Kompensationsbezogene Aktivitäten können nicht verwendet werden, in eine <xref:System.Activities.Statements.Interop> Aktivität.  
  
 Es gibt auch einige Verhaltensmerkmale bezüglich der Verwendung von WF 3-Aktivitäten in der <xref:System.Activities.Statements.Interop> Aktivität:  
  
1.  WF 3 enthaltenen Aktivitäten aus einer <xref:System.Activities.Statements.Interop> Aktivitäten werden initialisiert, wenn die <xref:System.Activities.Statements.Interop> Aktivität ausgeführt wird. In WF 4.5 gibt es vor der Ausführung keine Initialisierungsphase für eine Workflowinstanz.  
  
2.  Die WF 4.5-Laufzeit ist nicht Prüfpunkt Zustand der Workflowinstanz zu Beginn eine Transaktion unabhängig davon, wo diese Transaktion beginnt (innerhalb oder außerhalb einer <xref:System.Activities.Statements.Interop> Aktivität).  
  
3.  WF 3-Nachverfolgungsdatensätze für Aktivitäten in einem <xref:System.Activities.Statements.Interop> Aktivität werden bereitgestellt, um WF 4.5-Nachverfolgungsteilnehmer als <xref:System.Activities.Tracking.InteropTrackingRecord> Objekte. <xref:System.Activities.Tracking.InteropTrackingRecord> ist eine Ableitung von <xref:System.Activities.Tracking.CustomTrackingRecord>.  
  
4.  Eine benutzerdefinierte WF 3-Aktivität kann über Workflowwarteschlangen in der Interoperationsumgebung auf Daten zugreifen, wie dies auch innerhalb der WF 3-Workflowlaufzeit möglich ist. Es sind keine benutzerdefinierten Änderungen an Aktivitätscode erforderlich. Daten sind auf dem Host in einer WF 3-Workflowwarteschlange eingereiht durch die Wiederaufnahme einer <xref:System.Activities.Bookmark>. Der Name des Lesezeichens ist die Form einer Zeichenfolge der <xref:System.IComparable> Workflow-Warteschlangennamen.  
  
## <a name="see-also"></a>Siehe auch  
 [Mithilfe von .NET Framework 3.0 oder .NET Framework 3.5-Aktivität in einem .NET Framework 4.5-Workflow](../../../docs/framework/windows-workflow-foundation/samples/using-a-net-3-0-or-net-3-5-activity-in-a-net-4-5-workflow.md)