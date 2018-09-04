---
title: Externalisierte Richtlinienaktivität in .NET Framework 4.5
ms.date: 03/30/2017
ms.assetid: 92fd6f92-23a1-4adf-b96a-2754ea93ad3e
ms.openlocfilehash: 4d107188bbcb46006ba6a6eab491ccb97aa4a83d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43503406"
---
# <a name="externalized-policy-activity-in-net-framework-45"></a>Externalisierte Richtlinienaktivität in .NET Framework 4.5

In diesem Beispiel wird veranschaulicht, wie die ExternalizedPolicy4-Aktivität ermöglicht die Ausführung vorhandener [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] Windows Workflow Foundation (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> Objekte im [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] Windows Workflow Foundation (WF 4.5) direkt unter Verwendung der Regel-Engine wird in WF 3.5 versendet. Mit dieser Aktivität können Sie alle vorhandenen WF 3.5 <xref:System.Workflow.Activities.Rules.RuleSet>-Elemente öffnen und ausführen. Weitere Informationen zu WF 3.5 Regelmodul als Bestandteil von Windows Workflow Foundation, finden Sie [Einführung in das Windows Workflow Foundation-Regelmodul](https://go.microsoft.com/fwlink/?LinkId=166079). Weitere Informationen zum Migrieren Regeln [!INCLUDE[wf1](../../../../includes/wf1-md.md)] in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)], lesen Sie den migrationsanleitungen unter [Migrationsanleitung](../../../../docs/framework/windows-workflow-foundation/migration-guidance.md).

## <a name="projects-in-this-sample"></a>Projekte in diesem Beispiel

|Projektname|Beschreibung|Hauptdateien|
|-|-|-|
|ExternalizedPolicy4|Enthält die ExternalizedPolicy4-Aktivität und ihren WF 4.5-Designer.|**ExternalizedPolicy4.cs**: Aktivitätsdefinition.<br /><br /> **ExternalizedPolicy4Designer.xaml**: benutzerdefinierter Designer für die ExternalizedPolicy4-Aktivität. Er verwendet den Regeleditor (<xref:System.Workflow.Activities.Rules.Design.RuleSetDialog>) der WF 3.5-Regel-Engine.|
|ImperativeCodeClientSample|Beispielclientanwendung, die einen Workflow mithilfe einer ExternalizedPolicy4-Anwendung mit obligatorischem C#-Code konfiguriert und ausführt (kein Designer verwendet).|**ApplyDiscount.rules**: Datei mit [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Regeldefinitionen.<br /><br /> **Order.cs**: Typ, der einen kundenbestellung darstellt. Regeln werden auf Objekte dieses Typs angewendet.<br /><br /> **"Program.cs"**: konfiguriert und führt einen Workflow aus, die eine Policy4-Aktivität in ApplyDiscount.rules auf Instanzen von Order-Objekte definierte Regeln anwenden.<br /><br /> App.config: Die Konfigurationsdatei mit dem Pfad der Regeldatei.|
|DesignerClientSample|Beispielclientanwendung, die einen Workflow mithilfe einer ExternalPolicy4-Anwendung im [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Designer konfiguriert und ausführt.|**Sequence1.XAML**: sequenzieller Workflow, der eine Policy4-Aktivität verwendet, um regelauswertungen durchzuführen.<br /><br /> **"Program.cs"**: führt eine Instanz des in Sequence1.xaml definierten Workflows.|

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
|ValidationError|Die Liste der Validierungsfehler, die von der WF 3.5-Regel-Engine beim Überprüfen des <xref:System.Workflow.Activities.Rules.RuleSet> für das Zielobjekt vor der Ausführung zurückgegeben wurde.|

## <a name="externalizedpolicy4-activity-designer"></a>ExternalizedPolicy4-Aktivitätsdesigner

Mit dem ExternalizedPolicy4-Designer können Sie eine Aktivität zur Verwendung eines vorhandenen RuleSet konfigurieren, ohne dass Sie Code schreiben müssen. Geben Sie den Pfad an, in dem sich die RULES-Datei befindet, und legen Sie den zu verwendenden  <xref:System.Workflow.Activities.Rules.RuleSet>-Namen fest. Sie können außerdem das <xref:System.Workflow.Activities.Rules.RuleSet> ändern. Nach dem Erstellen der Projektmappe befindet sich dies im Abschnitt Microsoft.Samples.Activities.Rules. Mit dem Designer können Sie eine RULES-Datei und ein <xref:System.Workflow.Activities.Rules.RuleSet> auswählen. Wenn die **Regelsatz bearbeiten** Schaltfläche geklickt wird, wird die WF 3.5 <xref:System.Workflow.Activities.Rules.Design.RuleSetDialog> wird angezeigt. Dieses Dialogfeld ist der neu gehostete WF 3.5-Regeleditor. Es wird verwendet, um die von der ExternalizedPolicy4-Aktivität ausgeführten Regeln anzuzeigen und zu bearbeiten.

## <a name="policy4-and-externalpolicy4"></a>Policy4 und ExternalPolicy4

Die [Richtlinienaktivität in .NET Framework 4.5](../../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) Aktivität können Sie zum Erstellen und Ausführen einer .NET Framework 3.5-Regelsatz in einem WF 4.5-Workflow. Das <xref:System.Workflow.Activities.Rules.RuleSet> wird inline in der XAML-Definition der Policy4-Aktivität serialisiert. Im ExternalizedPolicy4-Beispiel wird gezeigt, wie ein vorhandenes externes <xref:System.Workflow.Activities.Rules.RuleSet> (enthalten in einer RULES-Datei) verwendet wird.

## <a name="use-this-sample"></a>Verwenden Sie dieses Beispiel

Zum Ausführen dieses Beispiels ist keine spezielle Einrichtung erforderlich. Öffnen Sie die Projektmappe in Visual Studio, und drücken Sie dann die **F5** zum Ausführen der Anwendung.

Dieses Beispiel umfasst zwei Clientanwendungen: ImperativeCodeClientSample und DesignerClientSample. Der ImperativeCodeClientSample-Client zeigt, wie die ExternalizedPolicy4-Aktivität mit obligatorischem C#-Code konfiguriert und ausgeführt wird. Das DesignerClientSample zeigt, wie die ExternalizedPolicy4-Aktivität mithilfe des Designers konfiguriert und ausgeführt wird.

### <a name="run-the-imperativecodeclientsample-application"></a>Führen Sie die ImperativeCodeClientSample-Anwendung

1.  Öffnen Sie Visual Studio mit der *Policy4sample.sln* Projektmappendatei.

2.  In **Projektmappen-Explorer**, mit der rechten Maustaste die **ImperativeCodeClientSample** und wählen Sie dann **als Startprojekt festlegen**.

3.  Um das Projekt auszuführen, drücken Sie **STRG**+**F5**.

### <a name="run-the-designerclientsample-application"></a>Führen Sie die DesignerClientSample-Anwendung

1.  Öffnen Sie Visual Studio mit der *Policy4sample.sln* Projektmappendatei.

2.  In **Projektmappen-Explorer**, mit der rechten Maustaste die **DesignerClientSample** und wählen Sie dann **als Startprojekt festlegen**.

3.  Drücken Sie **STRG**+**UMSCHALT**+**B** zum Kompilieren des Projekts.

4.  Drücken Sie **STRG**+**F5** um das Projekt auszuführen.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.
>
> Dieses Beispiel befindet sich im folgenden Verzeichnis:
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Rules-ExternalizedPolicy4`
