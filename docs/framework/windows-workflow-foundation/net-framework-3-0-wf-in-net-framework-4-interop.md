---
title: "Verwenden von .NET Framework 3.0-WF-Aktivitäten unter .NET Framework 4 mit der Interop-Aktivität"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71f112ba-abb0-46f7-b05f-a5d2eb9d0c5c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 51f11beb474758f16c6de0c47444e0467cac8bec
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="using-net-framework-30-wf-activities-in-net-framework-4-with-the-interop-activity"></a>Verwenden von .NET Framework 3.0-WF-Aktivitäten unter .NET Framework 4 mit der Interop-Aktivität
Die <xref:System.Activities.Statements.Interop>-Aktivität ist eine [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] (WF 4.5)-Aktivität, die eine [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] (WF 3.5)-Aktivität in einem [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]-Workflow umschließt. Die WF 3-Aktivität kann eine einzelne Blattaktivität oder eine ganze Aktivitätsstruktur darstellen. Die Ausführung (einschließlich Abbruch und Ausnahmebehandlung) und die Persistenz der [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]-Aktivität treten im Kontext der [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] Workflowinstanz auf, die ausgeführt wird.  
  
> [!NOTE]
>  Die <xref:System.Activities.Statements.Interop> Aktivität wird nicht in der Toolbox des Workflow-Designer angezeigt, es sei denn, das Projekt des Workflows dessen **Zielframework** eingestellt **.NET Framework 4.5**.  
  
## <a name="criteria-for-using-a-wf-3-activity-with-an-interop-activity"></a>Kriterien für die Verwendung einer WF 3-Aktivität mit einer Interop-Aktivität  
 Damit eine WF 3-Aktivität innerhalb einer <xref:System.Activities.Statements.Interop>-Aktivität erfolgreich ausgeführt werden kann, müssen die folgenden Kriterien erfüllt werden:  
  
-   Die WF 3-Aktivität muss von <xref:System.Workflow.ComponentModel.Activity?displayProperty=nameWithType> abgeleitet sein.  
  
-   Die WF 3-Aktivität muss als `public` deklariert werden und darf nicht `abstract` sein.  
  
-   Die WF 3-Aktivität muss über einen öffentlichen Standardkonstruktor verfügen.  
  
-   Aufgrund von Einschränkungen bei den Schnittstellentypen, die die <xref:System.Activities.Statements.Interop>-Aktivität unterstützen kann, können das <xref:System.Workflow.Activities.HandleExternalEventActivity>-Objekt und das <xref:System.Workflow.Activities.CallExternalMethodActivity>-Objekt nicht direkt verwendet werden. Abgeleitete Aktivitäten, die mit dem Tool für Workflow-Kommunikationsaktivitäten (WCA.exe) erstellt wurden, können jedoch verwendet werden. Finden Sie unter [Windows Workflow Foundation – Tools](http://go.microsoft.com/fwlink/?LinkId=178889) Details.  
  
## <a name="configuring-a-wf-3-activity-within-an-interop-activity"></a>Konfigurieren einer WF 3-Aktivität innerhalb einer Interop-Aktivität  
 Um Daten zu konfigurieren und in bzw. aus einer WF 3-Aktivität über die Grenzen der Interoperation zu übergeben, werden die Eigenschaften und die Metadateneigenschaften der WF 3-Aktivität von der <xref:System.Activities.Statements.Interop>-Aktivität verfügbar gemacht. Die Metadateneigenschaften der WF 3-Aktivität (z. B. <xref:System.Workflow.ComponentModel.Activity.Name%2A>) werden über die <xref:System.Activities.Statements.Interop.ActivityMetaProperties%2A>-Auflistung verfügbar gemacht. Dies ist eine Auflistung von Name-Wert-Paaren, mit denen die Werte für die Metadateneigenschaften der WF 3-Aktivität definiert werden. Eine Metadateneigenschaft ist eine Eigenschaft, die von der Abhängigkeitseigenschaft unterstützt wird, für die das <xref:System.Workflow.ComponentModel.DependencyPropertyOptions.Metadata>-Kennzeichen festgelegt ist.  
  
 Die Eigenschaften der WF 3-Aktivität werden über die <xref:System.Activities.Statements.Interop.ActivityProperties%2A>-Auflistung verfügbar gemacht. Dies ist ein Satz von Name-Wert-Paaren, wobei jeder Wert ein <xref:System.Activities.Argument>-Objekt ist, mit dem Argumente für die Eigenschaften der WF 3-Aktivität definiert werden. Da die Richtung der Eigenschaft einer WF 3-Aktivität nicht abgeleitet werden kann, wird jede Eigenschaft Diagnoseinformationen werden als ein <xref:System.Activities.InArgument> / <xref:System.Activities.OutArgument> Paar. Abhängig von der Verwendung der Aktivitätseigenschaft empfiehlt es sich, einen <xref:System.Activities.InArgument>-Eintrag, einen <xref:System.Activities.OutArgument>-Eintrag oder beides bereitzustellen. Der erwartete Name des <xref:System.Activities.InArgument>-Eintrags in der Auflistung entspricht dem Namen der Eigenschaft, wie sie für die WF 3-Aktivität definiert wurde. Der erwartete Name des der <xref:System.Activities.OutArgument> Eintrag in der Auflistung besteht aus einer Verkettung des Namens der Eigenschaft und die Zeichenfolge "Out".  
  
## <a name="limitations-of-using-a-wf-3-activity-within-an-interop-activity"></a>Einschränkungen bei der Verwendung einer WF 3-Aktivität innerhalb einer Interop-Aktivität  
 Die vom System bereitgestellten WF 3-Aktivitäten können nicht direkt in einer <xref:System.Activities.Statements.Interop>-Aktivität umschlossen werden. Bei einigen WF 3-Aktivitäten ist der Grund hierfür, dass es eine analoge WF 4.5-Aktivität wie z. B. <xref:System.Workflow.Activities.DelayActivity> gibt. Bei anderen rührt dies daher, dass die Funktionalität der Aktivität nicht unterstützt wird. Viele vom System bereitgestellte WF 3-Aktivitäten können in Workflows verwendet werden, die von der <xref:System.Activities.Statements.Interop>-Aktivität umschlossen werden, jedoch mit folgenden Einschränkungen:  
  
1.  Das <xref:System.ServiceModel.Activities.Send>-Objekt und das <xref:System.ServiceModel.Activities.Receive>-Objekt können nicht in einer <xref:System.Activities.Statements.Interop>-Aktivität verwendet werden.  
  
2.  Die Objekte <xref:System.Workflow.Activities.WebServiceInputActivity>, <xref:System.Workflow.Activities.WebServiceOutputActivity> und <xref:System.Workflow.Activities.WebServiceFaultActivity> können nicht in einer <xref:System.Activities.Statements.Interop>-Aktivität verwendet werden.  
  
3.  Das <xref:System.Workflow.Activities.InvokeWorkflowActivity>-Objekt kann nicht in einer <xref:System.Activities.Statements.Interop>-Aktivität verwendet werden.  
  
4.  Das <xref:System.Workflow.ComponentModel.SuspendActivity>-Objekt kann nicht in einer <xref:System.Activities.Statements.Interop>-Aktivität verwendet werden.  
  
5.  Kompensationsbezogene Aktivitäten können nicht in einer <xref:System.Activities.Statements.Interop>-Aktivität verwendet werden.  
  
 Es gibt auch einige bestimmte Verhaltensmerkmale bezüglich der Verwendung von WF 3-Aktivitäten in der <xref:System.Activities.Statements.Interop>-Aktivität:  
  
1.  In einer <xref:System.Activities.Statements.Interop>-Aktivität enthaltene WF 3-Aktivitäten werden initialisiert, wenn die <xref:System.Activities.Statements.Interop>-Aktivität ausgeführt wird. In WF 4.5 gibt es vor der Ausführung keine Initialisierungsphase für eine Workflowinstanz.  
  
2.  Die WF 4.5-Laufzeit setzt unabhängig davon, wo diese Transaktion beginnt (innerhalb oder außerhalb einer <xref:System.Activities.Statements.Interop>-Aktivität), keinen Prüfpunkt für den Workflowinstanzzustand, wenn eine Transaktion beginnt.  
  
3.  WF 3-Nachverfolgungsdatensätze für Aktivitäten in einer <xref:System.Activities.Statements.Interop>-Aktivität werden für WF 4.5-Nachverfolgungsteilnehmer in Form von <xref:System.Activities.Tracking.InteropTrackingRecord>-Objekten bereitgestellt. <xref:System.Activities.Tracking.InteropTrackingRecord> ist eine Ableitung von <xref:System.Activities.Tracking.CustomTrackingRecord>.  
  
4.  Eine benutzerdefinierte WF 3-Aktivität kann über Workflowwarteschlangen in der Interoperationsumgebung auf Daten zugreifen, wie dies auch innerhalb der WF 3-Workflowlaufzeit möglich ist. Es sind keine benutzerdefinierten Änderungen an Aktivitätscode erforderlich. Auf dem Host werden Daten in eine WF 3-Workflowwarteschlange eingereiht, indem ein <xref:System.Activities.Bookmark>-Objekt wieder aufgenommen wird. Der Name des Lesezeichens entspricht dem Workflow-Warteschlangennamen des <xref:System.IComparable>-Objekts in Form einer Zeichenfolge.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden einer .NET Framework 3.0 oder .NET Framework 3.5-Aktivität in einem .NET Framework 4.5-Workflow](../../../docs/framework/windows-workflow-foundation/samples/using-a-net-3-0-or-net-3-5-activity-in-a-net-4-5-workflow.md)
