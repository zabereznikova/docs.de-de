---
title: "Richtlinienaktivit&#228;t in .NET Framework 4.5 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8e375e0c-d7c1-4d69-88ab-36d52db0aa7e
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Richtlinienaktivit&#228;t in .NET Framework 4.5
Die Policy4\-Aktivität ermöglicht die Verwendung von [!INCLUDE[wf2](../../../../includes/wf2-md.md)] in [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] \(WF 3.5\) <xref:System.Workflow.Activities.Rules.RuleSet>\-Objekten direkt in [!INCLUDE[wf2](../../../../includes/wf2-md.md)]in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] \(WF 4.5\), indem das zu WF 3.5 gehörende Regelmodul verwendet wird.Mit dieser Aktivität können Sie <xref:System.Workflow.Activities.Rules.RuleSet> für WF 3.5 erstellen und ausführen.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum WF 3.5\-Regelmodul als Bestandteil von Windows Workflow Foundation finden Sie in der Einführung in das Windows Workflow Foundation\-Regelmodul.Weitere Informationen zum Migrieren von Regeln in WF in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] finden Sie unter [Migrationsanleitung](../../../../docs/framework/windows-workflow-foundation//migration-guidance.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Rules-Policy4`  
  
## Projekte in diesem Beispiel  
  
|Projektname|Beschreibung|Hauptdateien|  
|-----------------|------------------|------------------|  
|Policy4|Enthält die Policy4\-Aktivität und den zugehörigen [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Designer.|**Policy4.cs**: Policy4\-Aktivitätsdefinition.<br /><br /> **PolicyDesigner.xaml**: Benutzerdefinierter Designer für die Policy4\-Aktivität.Er verwendet den Regeln\-Editor \([RuleSetDialog\-Klasse](http://go.microsoft.com/fwlink/?LinkId=150378)\) des [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Regelmoduls.|  
|ImperativeCodeClientSample|Beispielclientanwendung, die einen Workflow mithilfe einer Policy4\-Anwendung mit imperativem C\#\-Code konfiguriert und ausführt \(kein [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Designer wird verwendet\).|**ApplyDiscount.rules**: Datei mit [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Regeldefinitionen.<br /><br /> **Order.cs**: Typ, der einen Kundenbestellung darstellt.Regeln werden auf Objekte dieses Typs angewendet.<br /><br /> **Program.cs**: Konfiguriert und führt einen Workflow aus, der über eine Policy4\-Aktivität verfügt, mit der in "ApplyDiscount.rules" definierte Regeln auf Instanzen von Order\-Objekten angewendet werden.<br /><br /> **App.config**: Konfigurationsdatei mit dem Pfad der Regeldatei.|  
|DesignerClientSample|Beispielclientanwendung, die einen Workflow mithilfe einer Policy4\-Anwendung im [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Designer konfiguriert und ausführt.|**Sequence1.xaml**: Sequenzieller Workflow, der eine Policy4\-Aktivität verwendet, um Regelauswertungen durchzuführen.<br /><br /> `Program.cs`: Führt eine Instanz des in "Sequence1.xaml" definierten Workflows aus.|  
  
## Policy4\-Aktivität  
 Die Policy4\-Aktivität ist eine Klasse, die von der <xref:System.Activities.NativeActivity%601>\-Klasse abgeleitet wird, die es Workflows ermöglicht, RuleSets von [!INCLUDE[wf1](../../../../includes/wf1-md.md)] auszuführen.Das folgende Codebeispiel ist eine vereinfachte Definition des öffentlichen Objektmodells der Aktivität.  
  
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
|-----------------|------------------|  
|RuleSet|Die [RuleSet\-Klasse](http://go.microsoft.com/fwlink/?LinkId=150379) von WF für .NET Framework 3.5, die ausgewertet werden soll, wenn die Aktivität ausgeführt wird.|  
|TargetObject|Das Objekt, für das die Regeln in der [RuleSet\-Klasse](http://go.microsoft.com/fwlink/?LinkId=150379) ausgewertet werden.|  
|ValidationError|Die Liste der Validierungsfehler, die vom [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Regelmodul für .NET Framework 3.5 zurückgegeben wurden, als die [RuleSet\-Klasse](http://go.microsoft.com/fwlink/?LinkId=150379) vor der Ausführung für das Zielobjekt überprüft wurde.|  
  
## Policy4\-Aktivitätsdesigner  
 Der Policy4\-Designer ermöglicht es, eine Policy4\-Aktivität zu konfigurieren, ohne Code zu schreiben.Nach dem Erstellen der Projektmappe befindet sich dies im Abschnitt **Microsoft.Samples.Activities.Rules**.  
  
 Mit dem WF\-Designer können Sie ein Zielobjekt und ein RuleSet konfigurieren.Wenn auf die Schaltfläche **Regelsatz bearbeiten** geklickt wird, wird die [RuleSetDialog\-Klasse](http://go.microsoft.com/fwlink/?LinkId=150378) von WF für [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] angezeigt.Dieses Dialogfeld ist der neu gehostete [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)]\-Regel\-Editor.Verwenden Sie den Editor, um die Regeln zu erstellen und zu bearbeiten, die die Policy4\-Aktivität ausführt.  
  
## Verwenden dieses Beispiels  
 Zum Ausführen dieses Beispiels ist keine spezielle Einrichtung erforderlich.Öffnen Sie einfach die Projektmappe in Visual Studio, und drücken Sie F5, um die Anwendung auszuführen.  
  
 Dieses Beispiel umfasst zwei Clientanwendungen: ImperativeCodeClientSample und DesignerClientSample.Der ImperativeCodeClientSample\-Client zeigt, wie die Policy40\-Aktivität mit imperativem C\#\-Code konfiguriert und ausgeführt wird.DesignerClientSample zeigt, wie die Policy4\-Aktivität mithilfe des Designers konfiguriert und ausgeführt wird.  
  
#### So führen Sie die ImperativeCodeClientSample\-Clientanwendung aus  
  
1.  Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] die Projektmappendatei "Policy4Sample.sln".  
  
2.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Projekt **ImperativeCodeClientSample**, und wählen Sie **Als Startprojekt festlegen** aus.  
  
3.  Drücken Sie zum Ausführen des Projekts STRG\+F5.  
  
#### So führen Sie die ImperativeCodeClientSample\-Clientanwendung aus  
  
1.  Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] die Projektmappendatei "Policy4Sample.sln".  
  
2.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Projekt **DesignerClientSample**.  
  
    -   Wählen Sie **Als Startprojekt festlegen** aus.  
  
3.  Drücken Sie STRG\+UMSCHALT\+B, um das Projekt zu kompilieren.  
  
4.  Drücken Sie zum Ausführen des Projekts STRG\+F5.  
  
## Siehe auch