---
title: Externalisierte Richtlinienaktivität in .NET Framework 4.5
ms.date: 03/30/2017
ms.assetid: 92fd6f92-23a1-4adf-b96a-2754ea93ad3e
ms.openlocfilehash: 00b671f169696728610e8ee32f874b44fbff9e33
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556914"
---
# <a name="externalized-policy-activity-in-net-framework-45"></a>Externalisierte Richtlinienaktivität in .NET Framework 4.5

In diesem Beispiel wird veranschaulicht, wie die ExternalizedPolicy4-Aktivität die Ausführung vorhandener WF 3,5-Objekte (.NET Framework 3,5 Windows Workflow Foundation) <xref:System.Workflow.Activities.Rules.RuleSet> in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] Windows Workflow Foundation (WF 4,5) direkt mithilfe der in WF 3,5 gelieferten Regel-Engine ermöglicht. Mit dieser Aktivität können Sie alle vorhandenen WF 3.5 <xref:System.Workflow.Activities.Rules.RuleSet>-Elemente öffnen und ausführen. Weitere Informationen zur WF 3,5-Regel-Engine, die im Rahmen Windows Workflow Foundation enthalten ist, finden Sie unter [Einführung in das Windows Workflow Foundation Regel-Engine](/previous-versions/dotnet/articles/aa480193(v=msdn.10)). Weitere Informationen zum Migrieren von Regeln zu [!INCLUDE[wf1](../../../../includes/wf1-md.md)] in finden Sie in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] der [Migrations Anleitung](../migration-guidance.md).

## <a name="projects-in-this-sample"></a>Projekte in diesem Beispiel

|Projektname|BESCHREIBUNG|Hauptdateien|
|-|-|-|
|ExternalizedPolicy4|Enthält die ExternalizedPolicy4-Aktivität und ihren WF 4.5-Designer.|**ExternalizedPolicy4.cs**: Aktivitäts Definition.<br /><br /> **ExternalizedPolicy4Designer. XAML**: benutzerdefinierter Designer für die ExternalizedPolicy4-Aktivität. Er verwendet den Regeleditor (<xref:System.Workflow.Activities.Rules.Design.RuleSetDialog>) der WF 3.5-Regel-Engine.|
|ImperativeCodeClientSample|Beispielclientanwendung, die einen Workflow mithilfe einer ExternalizedPolicy4-Anwendung mit obligatorischem C#-Code konfiguriert und ausführt (kein Designer verwendet).|**ApplyDiscount. Rules**: Datei mit [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Regeldefinitionen.<br /><br /> **Order.cs**: Typ, der eine Kundenbestellung darstellt. Regeln werden auf Objekte dieses Typs angewendet.<br /><br /> **Program.cs**: konfiguriert und führt einen Workflow aus, der über eine Policy4-Aktivität verfügt, um in ApplyDiscount. Rules definierte Regeln auf Instanzen von Order-Objekten anzuwenden.<br /><br /> App.config: Die Konfigurationsdatei mit dem Pfad der Regeldatei.|
|DesignerClientSample|Beispielclientanwendung, die einen Workflow mithilfe einer ExternalPolicy4-Anwendung im [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Designer konfiguriert und ausführt.|**Sequence1. XAML**: ein sequenzieller Workflow, der eine Policy4-Aktivität verwendet, um Regel Auswertungen auszuführen.<br /><br /> **Program.cs**: führt eine Instanz des Workflows aus, der in Sequence1. XAML definiert ist.|

## <a name="the-externalizedpolicy4-activity"></a>Die ExternalizedPolicy4-Aktivität

Die ExternalizedPolicy4-Aktivität ist eine <xref:System.Activities.NativeActivity>, mit der die Ausführung von <xref:System.Workflow.Activities.Rules.RuleSet>-Objekten in WF 3.5 innerhalb von WF 4.5-Workflows ermöglicht wird. Das folgende Beispiel ist eine vereinfachte Definition des öffentlichen Objektmodells der Aktivität.

```csharp
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

|Eigenschaft|BESCHREIBUNG|
|-|-|
|RuleSetFilePath|Pfad zur .NET Framework 3.5 <xref:System.Workflow.Activities.Rules.RuleSet> Datei, die beim Ausführen der Aktivität ausgewertet werden soll.|
|RuleSetName|Name des <xref:System.Workflow.Activities.Rules.RuleSet>, der in der RULES-Datei verwendet werden soll.|
|TargetObject|Das Objekt, für das die <xref:System.Workflow.Activities.Rules.Rule>-Objekte im <xref:System.Workflow.Activities.Rules.RuleSet> ausgewertet werden.|
|ResultObject|Das Objekt, das sich nach der Anwendung der Regeln ergibt. (Die Regeln werden zum Beispiel auf das Input-Argument angewendet, und das Ergebnis wird im Result-Argument gespeichert.)|
|ValidationError|Die Liste der Validierungsfehler, die von der WF 3.5-Regel-Engine beim Überprüfen des <xref:System.Workflow.Activities.Rules.RuleSet> für das Zielobjekt vor der Ausführung zurückgegeben wurde.|

## <a name="externalizedpolicy4-activity-designer"></a>ExternalizedPolicy4-Aktivitätsdesigner

Mit dem ExternalizedPolicy4-Designer können Sie eine Aktivität zur Verwendung eines vorhandenen RuleSet konfigurieren, ohne dass Sie Code schreiben müssen. Geben Sie den Pfad an, in dem sich die RULES-Datei befindet, und legen Sie den zu verwendenden <xref:System.Workflow.Activities.Rules.RuleSet>-Namen fest. Sie können außerdem das <xref:System.Workflow.Activities.Rules.RuleSet> ändern. Nach dem Erstellen der Projektmappe befindet sich dies im Abschnitt Microsoft.Samples.Activities.Rules. Mit dem Designer können Sie eine RULES-Datei und ein <xref:System.Workflow.Activities.Rules.RuleSet> auswählen. Wenn auf die Schaltfläche **Regelsatz bearbeiten** geklickt wird, wird WF 3,5 <xref:System.Workflow.Activities.Rules.Design.RuleSetDialog> angezeigt. Dieses Dialogfeld ist der neu gehostete WF 3.5-Regeleditor. Es wird verwendet, um die von der ExternalizedPolicy4-Aktivität ausgeführten Regeln anzuzeigen und zu bearbeiten.

## <a name="policy4-and-externalpolicy4"></a>Policy4 und ExternalPolicy4

Mit der Policy-Aktivität können Sie eine .NET Framework 3,5-RuleSet in einem WF 4,5-Workflow erstellen und ausführen. Das <xref:System.Workflow.Activities.Rules.RuleSet> wird inline in der XAML-Definition der Policy4-Aktivität serialisiert. Im ExternalizedPolicy4-Beispiel wird gezeigt, wie ein vorhandenes externes <xref:System.Workflow.Activities.Rules.RuleSet> (enthalten in einer RULES-Datei) verwendet wird.

## <a name="use-this-sample"></a>Verwenden Sie dieses Beispiel

Zum Ausführen dieses Beispiels ist keine spezielle Einrichtung erforderlich. Öffnen Sie die Projekt Mappe in Visual Studio, und drücken Sie dann **F5** , um die Anwendung auszuführen.

Dieses Beispiel umfasst zwei Clientanwendungen: ImperativeCodeClientSample und DesignerClientSample. Der ImperativeCodeClientSample-Client zeigt, wie die ExternalizedPolicy4-Aktivität mit obligatorischem C#-Code konfiguriert und ausgeführt wird. Das DesignerClientSample zeigt, wie die ExternalizedPolicy4-Aktivität mithilfe des Designers konfiguriert und ausgeführt wird.

### <a name="run-the-imperativecodeclientsample-application"></a>Ausführen der ImperativeCodeClientSample-Anwendung

1. Öffnen Sie die Projektmappendatei *Policy4sample. sln* mithilfe von Visual Studio.

2. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt **ImperativeCodeClientSample** , und wählen Sie dann **als Startprojekt festlegen**aus.

3. Drücken Sie **STRG**F5, um das Projekt auszuführen + **F5**.

### <a name="run-the-designerclientsample-application"></a>Ausführen der Anwendung DesignerClientSample

1. Öffnen Sie die Projektmappendatei *Policy4sample. sln* mithilfe von Visual Studio.

2. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt **DesignerClientSample** , und wählen Sie dann **als Startprojekt festlegen**aus.

3. Drücken Sie **STRG** + **UMSCHALT** + **B** , um das Projekt zu kompilieren.

4. Drücken Sie **STRG** + **F5** , um das Projekt auszuführen.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .
>
> Dieses Beispiel befindet sich im folgenden Verzeichnis:
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Rules-ExternalizedPolicy4`
