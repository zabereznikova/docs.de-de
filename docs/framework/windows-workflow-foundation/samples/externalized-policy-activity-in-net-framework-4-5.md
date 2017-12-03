---
title: "Externalisierte Richtlinienaktivität in .NET Framework 4.5"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 92fd6f92-23a1-4adf-b96a-2754ea93ad3e
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 468d0ca5f4afa4e84b69f58887672ffcf1a14fa6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="externalized-policy-activity-in-net-framework-45"></a>Externalisierte Richtlinienaktivität in .NET Framework 4.5
In diesem Beispiel wird veranschaulicht, wie die ExternalizedPolicy4-Aktivität ermöglicht Ausführung vorhandener [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] [!INCLUDE[wf2](../../../../includes/wf2-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> Objekte im [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] [!INCLUDE[wf2](../../../../includes/wf2-md.md)] (WF 4.5) direkt in das Regelmodul, die in WF 3.5 geliefert wird. Mit dieser Aktivität können Sie alle vorhandenen WF 3.5 <xref:System.Workflow.Activities.Rules.RuleSet>-Elemente öffnen und ausführen. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]WF 3.5-Regelmodul als Bestandteil von Windows Workflow Foundation, lesen Sie [Einführung in das Windows Workflow Foundation-Regelmodul](http://go.microsoft.com/fwlink/?LinkId=166079). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Migrieren von Regeln zum [!INCLUDE[wf1](../../../../includes/wf1-md.md)] in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)], lesen Sie die migrationsanleitung am [Migrationsanleitung](../../../../docs/framework/windows-workflow-foundation/migration-guidance.md).  
  
## <a name="projects-in-this-sample"></a>Projekte in diesem Beispiel  
  
|Projektname|Beschreibung|Hauptdateien|  
|-|-|-|  
|ExternalizedPolicy4|Enthält die ExternalizedPolicy4-Aktivität und ihren WF 4.5-Designer.|**ExternalizedPolicy4.cs**: Aktivitätsdefinition.<br /><br /> **ExternalizedPolicy4Designer.xaml**: benutzerdefinierter Designer für die ExternalizedPolicy4-Aktivität. Er verwendet den Regeleditor (<xref:System.Workflow.Activities.Rules.Design.RuleSetDialog>) des WF 3.5-Regelmoduls.|  
|ImperativeCodeClientSample|Beispielclientanwendung, die einen Workflow mithilfe einer ExternalizedPolicy4-Anwendung mit obligatorischem C#-Code konfiguriert und ausführt (kein Designer verwendet).|**ApplyDiscount.rules**: Datei mit dem [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Regeldefinitionen.<br /><br /> **Order.cs**: Typ, der einen kundenbestellung darstellt. Regeln werden auf Objekte dieses Typs angewendet.<br /><br /> **Datei "Program.cs"**: konfiguriert und führt einen Workflow, der eine Policy4-Aktivität in Instanzen von Order-Objekten ApplyDiscount.rules definierte Regeln angewendet wurde.<br /><br /> App.config: Die Konfigurationsdatei mit dem Pfad der Regeldatei.|  
|DesignerClientSample|Beispielclientanwendung, die einen Workflow mithilfe einer ExternalPolicy4-Anwendung im [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Designer konfiguriert und ausführt.|**Sequence1.XAML**: sequenzieller Workflow, der eine Policy4-Aktivität verwendet, um regelauswertungen durchzuführen.<br /><br /> **Datei "Program.cs"**: führt eine Instanz des in Sequence1.xaml definierten Workflows aus.|  
  
## <a name="the-externalizedpolicy4-activity"></a>Die ExternalizedPolicy4-Aktivität  
 Die ExternalizedPolicy4-Aktivität ist eine <xref:System.Activities.NativeActivity>, mit der die Ausführung von <xref:System.Workflow.Activities.Rules.RuleSet>-Objekten in WF 3.5 innerhalb von WF 4.5-Workflows ermöglicht wird. Das folgende Beispiel ist eine vereinfachte Definition des öffentlichen Objektmodells der Aktivität.  
  
```  
public class ExternalizedPolicy4Activity<TResult>: CodeActivity  
{  
    public string RulesFilePath   
  
    public string RuleSetName           
  
    [RequiredArgument]  
    public InArgument<T> TargetObject   
  
    [RequiredArgument]  
    public OutArgument<T> ResultObject   
  
    public OutArgument<ValidationErrorCollection> ValidationErrors   
}  
```  
  
|Eigenschaft|Beschreibung|  
|-|-|  
|RuleSetFilePath|Pfad zur .NET Framework 3.5 <xref:System.Workflow.Activities.Rules.RuleSet> Datei, die beim Ausführen der Aktivität ausgewertet werden soll.|  
|RuleSetName|Name des <xref:System.Workflow.Activities.Rules.RuleSet>, der in der RULES-Datei verwendet werden soll.|  
|TargetObject|Das Objekt, für das die <xref:System.Workflow.Activities.Rules.Rule>-Objekte im <xref:System.Workflow.Activities.Rules.RuleSet> ausgewertet werden.|  
|ResultObject|Das Objekt, das sich nach der Anwendung der Regeln ergibt. (Die Regeln werden zum Beispiel auf das Input-Argument angewendet, und das Ergebnis wird im Result-Argument gespeichert.)|  
|ValidationError|Die Liste der Validierungsfehler, die vom WF 3.5-Regelmodul beim Überprüfen des <xref:System.Workflow.Activities.Rules.RuleSet> für das Zielobjekt vor der Ausführung zurückgegeben wurde.|  
  
## <a name="externalizedpolicy4-activity-designer"></a>ExternalizedPolicy4-Aktivitätsdesigner  
 Mit dem ExternalizedPolicy4-Designer können Sie eine Aktivität zur Verwendung eines vorhandenen RuleSet konfigurieren, ohne dass Sie Code schreiben müssen. Geben Sie den Pfad an, in dem sich die RULES-Datei befindet, und legen Sie den zu verwendenden  <xref:System.Workflow.Activities.Rules.RuleSet>-Namen fest. Sie können außerdem das <xref:System.Workflow.Activities.Rules.RuleSet> ändern. Nach dem Erstellen der Projektmappe befindet sich dies im Abschnitt Microsoft.Samples.Activities.Rules. Mit dem Designer können Sie eine RULES-Datei und ein <xref:System.Workflow.Activities.Rules.RuleSet> auswählen. Wenn die **Regelsatz bearbeiten** Schaltfläche geklickt wird, wird die WF 3.5 <xref:System.Workflow.Activities.Rules.Design.RuleSetDialog> wird angezeigt. Dieses Dialogfeld ist der neu gehostete WF 3.5-Regeleditor. Es wird verwendet, um die von der ExternalizedPolicy4-Aktivität ausgeführten Regeln anzuzeigen und zu bearbeiten.  
  
## <a name="policy4-and-externalpolicy4"></a>Policy4 und ExternalPolicy4  
 Die [Richtlinienaktivität in .NET Framework 4.5](../../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) Aktivität können Sie zum Erstellen und Ausführen einer .NET Framework 3.5-RuleSet in einem WF 4.5-Workflow. Das <xref:System.Workflow.Activities.Rules.RuleSet> wird inline in der XAML-Definition der Policy4-Aktivität serialisiert. Im ExternalizedPolicy4-Beispiel wird gezeigt, wie ein vorhandenes externes <xref:System.Workflow.Activities.Rules.RuleSet> (enthalten in einer RULES-Datei) verwendet wird.  
  
## <a name="using-this-sample"></a>Verwenden dieses Beispiels  
 Zum Ausführen dieses Beispiels ist keine spezielle Einrichtung erforderlich. Öffnen Sie die Projektmappe in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], und drücken Sie F5, um die Anwendung auszuführen.  
  
 Dieses Beispiel umfasst zwei Clientanwendungen: ImperativeCodeClientSample und DesignerClientSample. Der ImperativeCodeClientSample-Client zeigt, wie die ExternalizedPolicy4-Aktivität mit obligatorischem C#-Code konfiguriert und ausgeführt wird. Das DesignerClientSample zeigt, wie die ExternalizedPolicy4-Aktivität mithilfe des Designers konfiguriert und ausgeführt wird.  
  
#### <a name="to-run-the-imperativecodeclientsample-application"></a>So führen Sie die ImperativeCodeClientSample-Anwendung aus  
  
1.  Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] die Projektmappendatei Policy4sample.sln.  
  
2.  In **Projektmappen-Explorer**, mit der rechten Maustaste die **ImperativeCodeClientSample** Projekt, und wählen Sie dann **als Startprojekt festlegen**.  
  
3.  Drücken Sie zum Ausführen des Projekts STRG+F5.  
  
#### <a name="to-run-the-designerclientsample-application"></a>So führen Sie die DesignerClientSample-Anwendung aus  
  
1.  Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] die Projektmappendatei Policy4sample.sln.  
  
2.  In **Projektmappen-Explorer**, mit der rechten Maustaste die **DesignerClientSample** Projekt, und wählen Sie dann **als Startprojekt festlegen**.  
  
3.  Drücken Sie STRG+UMSCHALT+B, um das Projekt zu kompilieren.  
  
4.  Drücken Sie STRG+F5, um das Projekt auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Rules-ExternalizedPolicy4`
