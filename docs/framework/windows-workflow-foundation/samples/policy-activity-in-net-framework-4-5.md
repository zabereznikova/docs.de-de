---
title: Richtlinienaktivität in .NET Framework 4.5
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e375e0c-d7c1-4d69-88ab-36d52db0aa7e
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d8457182b666570853953830a92c3f2380a0eb85
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="policy-activity-in-net-framework-45"></a>Richtlinienaktivität in .NET Framework 4.5
Die Policy4-Aktivität ermöglicht Windows Workflow Foundation in [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> Objekte in Windows Workflow Foundation in zu verwendende [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) direkt mithilfe der WF 3.5 gehörende ist Regelmodul. Mit dieser Aktivität können Sie <xref:System.Workflow.Activities.Rules.RuleSet> für WF 3.5 erstellen und ausführen. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum WF 3.5-Regelmodul als Bestandteil von Windows Workflow Foundation finden Sie in der Einführung in das Windows Workflow Foundation-Regelmodul. Weitere Informationen zum Migrieren von Regeln für WF in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)], lesen Sie [Migrationsanleitung](../../../../docs/framework/windows-workflow-foundation/migration-guidance.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Rules-Policy4`  
  
## <a name="projects-in-this-sample"></a>Projekte in diesem Beispiel  
  
|Projektname|Beschreibung|Hauptdateien|  
|------------------|-----------------|----------------|  
|Policy4|Enthält die Policy4-Aktivität und den zugehörigen [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Designer.|**Policy4.cs**: Policy4-Aktivitätsdefinition.<br /><br /> **PolicyDesigner.xaml**: benutzerdefinierter Designer für die Policy4-Aktivität. Er verwendet den Regeleditor ([RuleSetDialog Class](http://go.microsoft.com/fwlink/?LinkId=150378)) von [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Regelmodul.|  
|ImperativeCodeClientSample|Beispielclientanwendung, die einen Workflow mithilfe einer Policy4-Anwendung mit imperativem C#-Code konfiguriert und ausführt (kein [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Designer wird verwendet).|**ApplyDiscount.rules**: Datei mit dem [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Regeldefinitionen.<br /><br /> **Order.cs**: Typ, der einen kundenbestellung darstellt. Regeln werden auf Objekte dieses Typs angewendet.<br /><br /> **Datei "Program.cs"**: konfiguriert und führt einen Workflow, der eine Policy4-Aktivität in Instanzen von Order-Objekten ApplyDiscount.rules definierte Regeln angewendet wurde.<br /><br /> **"App.config"**: Konfigurationsdatei mit dem Pfad der Regeldatei.|  
|DesignerClientSample|Beispielclientanwendung, die einen Workflow mithilfe einer Policy4-Anwendung im [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Designer konfiguriert und ausführt.|**Sequence1.XAML**: sequenzieller Workflow, der eine Policy4-Aktivität verwendet, um regelauswertungen durchzuführen.<br /><br /> `Program.cs`: Führt eine Instanz des in "Sequence1.xaml" definierten Workflows aus.|  
  
## <a name="the-policy4-activity"></a>Policy4-Aktivität  
 Die Policy4-Aktivität ist eine Klasse, die von der <xref:System.Activities.NativeActivity%601>-Klasse abgeleitet wird, die es Workflows ermöglicht, RuleSets von [!INCLUDE[wf1](../../../../includes/wf1-md.md)] auszuführen. Das folgende Codebeispiel ist eine vereinfachte Definition des öffentlichen Objektmodells der Aktivität.  
  
```csharp  
public class Policy4Activity<TResult>: NativeActivity<TResult>  
{  
    public RuleSet RuleSet  
  
    [IsRequired]  
    public InArgument Input  
  
    public OutArgument<ValidationErrorCollection> ValidationErrors  
}  
```  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|RuleSet|Die WF [RuleSet-Klasse](http://go.microsoft.com/fwlink/?LinkId=150379) für .NET Framework 3.5 ausgewertet werden soll, wenn die Aktivität ausgeführt wird.|  
|TargetObject|Das Objekt, mit dem die Regeln in der [RuleSet-Klasse](http://go.microsoft.com/fwlink/?LinkId=150379) ausgewertet werden.|  
|ValidationError|Die Liste der Überprüfungsfehler, die zurückgegeben werden, indem Sie die [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Regelmodul für .NET Framework 3.5 bei der Überprüfung der [RuleSet-Klasse](http://go.microsoft.com/fwlink/?LinkId=150379) für das Zielobjekt vor der Ausführung.|  
  
## <a name="policy4-activity-designer"></a>Policy4-Aktivitätsdesigner  
 Der Policy4-Designer ermöglicht es, eine Policy4-Aktivität zu konfigurieren, ohne Code zu schreiben. Nach dem Erstellen der Projektmappe kann gefunden werden in der Toolbox im Abschnitt **Microsoft.Samples.Activities.Rules**.  
  
 Mit dem WF-Designer können Sie ein Zielobjekt und ein RuleSet konfigurieren. Wenn die **Regelsatz bearbeiten** Schaltfläche geklickt wird, wird die WF [RuleSetDialog Class](http://go.microsoft.com/fwlink/?LinkId=150378) für [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] wird angezeigt. Dieses Dialogfeld ist der neu gehostete [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)]-Regel-Editor. Verwenden Sie den Editor, um die Regeln zu erstellen und zu bearbeiten, die die Policy4-Aktivität ausführt.  
  
## <a name="using-this-sample"></a>Verwenden dieses Beispiels  
 Zum Ausführen dieses Beispiels ist keine spezielle Einrichtung erforderlich. Öffnen Sie einfach die Projektmappe in Visual Studio, und drücken Sie F5, um die Anwendung auszuführen.  
  
 Dieses Beispiel umfasst zwei Clientanwendungen: ImperativeCodeClientSample und DesignerClientSample. Der ImperativeCodeClientSample-Client zeigt, wie die Policy40-Aktivität mit imperativem C#-Code konfiguriert und ausgeführt wird. DesignerClientSample zeigt, wie die Policy4-Aktivität mithilfe des Designers konfiguriert und ausgeführt wird.  
  
#### <a name="to-run-the-imperativecodeclientsample-client-application"></a>So führen Sie die ImperativeCodeClientSample-Clientanwendung aus  
  
1.  Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] die Projektmappendatei "Policy4Sample.sln".  
  
2.  In **Projektmappen-Explorer**, mit der rechten Maustaste die **ImperativeCodeClientSample** Projekt, und wählen Sie dann **als Startprojekt festlegen**.  
  
3.  Drücken Sie zum Ausführen des Projekts STRG+F5.  
  
#### <a name="to-run-the-imperativecodeclientsample-client-application"></a>So führen Sie die ImperativeCodeClientSample-Clientanwendung aus  
  
1.  Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] die Projektmappendatei "Policy4Sample.sln".  
  
2.  In **Projektmappen-Explorer**, mit der rechten Maustaste die **DesignerClientSample** Projekt.  
  
    -   Wählen Sie **als Startprojekt festlegen**.  
  
3.  Drücken Sie STRG+UMSCHALT+B, um das Projekt zu kompilieren.  
  
4.  Drücken Sie zum Ausführen des Projekts STRG+F5.