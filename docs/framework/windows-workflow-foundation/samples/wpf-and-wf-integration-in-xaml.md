---
title: WPF- und WF-Integration in XAML
ms.date: 03/30/2017
ms.assetid: a4f53b48-fc90-4315-bca0-ba009562f488
ms.openlocfilehash: b8015e5c526f58875beb58ab48a21c050bdc8a06
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960090"
---
# <a name="wpf-and-windows-workflow-foundation-integration-in-xaml"></a>WPF-und Windows Workflow Foundation Integration in XAML

In diesem Beispiel wird veranschaulicht, wie eine Anwendung erstellt wird, die Windows Presentation Foundation Funktionen (WPF) und Windows Workflow Foundation (WF) in einem einzelnen XAML-Dokument verwendet. Um dies zu erreichen, verwendet das Beispiel Windows Workflow Foundation-und XAML-Erweiterbarkeit.

## <a name="sample-details"></a>Beispieldetails

 Die Datei ShowWindow.xaml führt eine Deserialisierung in eine <xref:System.Activities.Statements.Sequence>-Aktivität mit zwei Zeichenfolgenvariablen durch, die von den Aktivitäten der Sequenz bearbeitet werden: `ShowWindow` und `WriteLine`. Die <xref:System.Activities.Statements.WriteLine>-Aktivität gibt im Konsolenfenster den Ausdruck aus, den sie der <xref:System.Activities.Statements.WriteLine.Text%2A>-Eigenschaft zuweist. Die `ShowWindow`-Aktivität zeigt ein WPF-Fenster als Teil der Ausführungs Logik an. Der <xref:System.Activities.ActivityContext.DataContext%2A> des Fensters schließt die in der Sequenz deklarierten Variablen ein. Die Steuerelemente des Fensters, die in der `ShowWindow`-Aktivität deklariert wurden, bearbeiten diese Variablen mithilfe der Datenbindung. Das Fenster enthält außerdem ein Schaltflächensteuerelement. Das `Click`-Ereignis für die Schaltfläche wird durch einen <xref:System.Activities.ActivityDelegate> behandelt, der als `MarkupExtension` bezeichnet wird und eine `CloseWindow`-Aktivität enthält. `MarkUpExtension` ruft die enthaltene Aktivität auf, die als Kontext alle durch `x:Name` gekennzeichneten Objekte sowie <xref:System.Activities.ActivityContext.DataContext%2A> des enthaltenden Fensters bereitstellt. Das `CloseWindow.InArgument<Window>` kann daher mit einem Ausdruck gebunden werden, der einen Verweis auf den Namen des Fensters enthält.

 Die `ShowWindow`-Aktivität wird von der <xref:System.Activities.AsyncCodeActivity%601>-Klasse abgeleitet, um ein WPF-Fenster anzuzeigen und wird abgeschlossen, wenn das Fenster geschlossen wird. Die `Window`-Eigenschaft weist den Typ `Func<Window>` auf, durch den das Fenster bei jeder Ausführung der Aktivität bei Bedarf erstellt werden kann. Die `Window`-Eigenschaft verwendet einen <xref:System.Xaml.XamlDeferringLoader> zum Aktivieren dieses verzögerten Auswertungsmodells. Der `FuncFactoryDeferringLoader` ermöglicht, dass ein `XamlReader` während der Serialisierung erfasst und während der Ausführung der Aktivität gelesen wird.

 Eine gut geschriebene Aktivität blockiert nie den Planerthread. Die `ShowWindow`-Aktivität kann jedoch erst dann abgeschlossen werden, wenn das Fenster, das sie anzeigt, geschlossen wird. Die `ShowWindow`-Aktivität erzielt dieses Verhalten, indem sie von <xref:System.Activities.AsyncCodeActivity> ableitet, die <xref:System.Activities.WorkflowInvoker.BeginInvoke%2A>-Methode in der <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>-Methode aufruft und das Fenster modal anzeigt. Der Delegat wird durch den <xref:System.ServiceModel.InstanceContext.SynchronizationContext%2A> von WPF aufgerufen. Die `ShowWindow`-Aktivität weist der <xref:System.Activities.ActivityContext.DataContext%2A>-Eigenschaft die `Window.DataContext`-Eigenschaft zu, um datengebundenen Steuerelementezugriff auf die im Gültigkeitsbereich befindlichen Variablen zu gewähren.

 Der letzte relevante Punkt in diesem Beispiel ist eine <xref:System.Workflow.ComponentModel.Serialization.MarkupExtension> mit dem Namen `DelegateActivityExtension`. Die `ProvideValue`-Methode dieser Markuperweiterung gibt einen Delegaten zurück, der eine eingebettete Aktivität aufruft. Diese Aktivität wird in einer Umgebung ausgeführt, die den WPF-Datenkontext und alle `x:Name` Werte im Gültigkeitsbereich enthält. In der `GenericInvoke`-Methode wird diese Umgebung der Aktivität durch eine <xref:System.Activities.Hosting.SymbolResolver>-Erweiterung bereitgestellt. Diese Erweiterung wird einem <xref:System.Activities.WorkflowInvoker> hinzugefügt, mit dem die eingebettete Aktivität immer dann aufgerufen wird, wenn der Delegat der Markuperweiterung aufgerufen wird.

> [!NOTE]
> Der Standarddesigner unterstützt die ShowWindow-Aktivität nicht. Die Datei ShowWindow.Xaml wird daher nicht ordnungsgemäß im Designer angezeigt.

## <a name="run-the-sample"></a>Beispielausführung

1. Öffnen Sie in Visual Studio die Projektmappendatei "WPFWFIntegration. sln".

2. Um die Projekt Mappe zu erstellen, drücken Sie **STRG**+**UMSCHALT**+**B**.

3. Drücken Sie **F5**, um die Lösung auszuführen.

4. Geben Sie im Dialogfeld Ihren Vor- und Nachnamen ein.

5. Schließen Sie das Dialogfeld, und die Konsole wiederholt den Namen.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\WPFWFIntegration`
