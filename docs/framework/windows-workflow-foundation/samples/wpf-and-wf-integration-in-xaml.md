---
title: WPF- und WF-Integration in XAML
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a4f53b48-fc90-4315-bca0-ba009562f488
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6bc761b93ff8d5c0dc79a86d0159d50d65fb727c
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="wpf-and-wf-integration-in-xaml"></a>WPF- und WF-Integration in XAML
Dieses Beispiel veranschaulicht, wie eine Anwendung erstellen, die Funktionen von Windows Presentation Foundation (WPF) und Windows Workflow Foundation (WF) in einem einzigen XAML-Dokument verwendet. Um dies zu erreichen, verwendet das Beispiel für Windows Workflow Foundation (WF) und die Verwendung von XAML-Erweiterbarkeit.  
  
## <a name="sample-details"></a>Beispieldetails  
 Die Datei ShowWindow.xaml führt eine Deserialisierung in eine <xref:System.Activities.Statements.Sequence>-Aktivität mit zwei Zeichenfolgenvariablen durch, die von den Aktivitäten der Sequenz bearbeitet werden: `ShowWindow` und `WriteLine`. Die <xref:System.Activities.Statements.WriteLine>-Aktivität gibt im Konsolenfenster den Ausdruck aus, den sie der <xref:System.Activities.Statements.WriteLine.Text%2A>-Eigenschaft zuweist. Die `ShowWindow`-Aktivität zeigt ein [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]-Fenster als Teil seiner Ausführungslogik an. Der <xref:System.Activities.ActivityContext.DataContext%2A> des Fensters schließt die in der Sequenz deklarierten Variablen ein. Die Steuerelemente des Fensters, die in der `ShowWindow`-Aktivität deklariert wurden, bearbeiten diese Variablen mithilfe der Datenbindung. Das Fenster enthält außerdem ein Schaltflächensteuerelement. Das `Click`-Ereignis für die Schaltfläche wird durch einen <xref:System.Activities.ActivityDelegate> behandelt, der als `MarkupExtension` bezeichnet wird und eine `CloseWindow`-Aktivität enthält. `MarkUpExtension` ruft die enthaltene Aktivität auf, die als Kontext alle durch `x:Name` gekennzeichneten Objekte sowie <xref:System.Activities.ActivityContext.DataContext%2A> des enthaltenden Fensters bereitstellt. Das `CloseWindow.InArgument<Window>` kann daher mit einem Ausdruck gebunden werden, der einen Verweis auf den Namen des Fensters enthält.  
  
 Die `ShowWindow`-Aktivität leitet sich von der <xref:System.Activities.AsyncCodeActivity%601>-Klasse ab, um ein [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]-Fenster anzuzeigen und wird abgeschlossen, wenn das Fenster geschlossen wird. Die `Window`-Eigenschaft weist den Typ `Func<Window>` auf, durch den das Fenster bei jeder Ausführung der Aktivität bei Bedarf erstellt werden kann. Die `Window`-Eigenschaft verwendet einen <xref:System.Xaml.XamlDeferringLoader> zum Aktivieren dieses verzögerten Auswertungsmodells. Der `FuncFactoryDeferringLoader` ermöglicht, dass ein `XamlReader` während der Serialisierung erfasst und während der Ausführung der Aktivität gelesen wird.  
  
 Eine gut geschriebene Aktivität blockiert nie den Planerthread. Die `ShowWindow`-Aktivität kann jedoch erst dann abgeschlossen werden, wenn das Fenster, das sie anzeigt, geschlossen wird. Die `ShowWindow`-Aktivität erzielt dieses Verhalten, indem sie von <xref:System.Activities.AsyncCodeActivity> ableitet, die <xref:System.Activities.WorkflowInvoker.BeginInvoke%2A>-Methode in der <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>-Methode aufruft und das Fenster modal anzeigt. Der Delegat wird durch den <xref:System.ServiceModel.InstanceContext.SynchronizationContext%2A> von WPF aufgerufen. Die `ShowWindow`-Aktivität weist der <xref:System.Activities.ActivityContext.DataContext%2A>-Eigenschaft die `Window.DataContext`-Eigenschaft zu, um datengebundenen Steuerelementezugriff auf die im Gültigkeitsbereich befindlichen Variablen zu gewähren.  
  
 Der letzte relevante Punkt in diesem Beispiel ist eine <xref:System.Workflow.ComponentModel.Serialization.MarkupExtension> mit dem Namen `DelegateActivityExtension`. Die `ProvideValue`-Methode dieser Markuperweiterung gibt einen Delegaten zurück, der eine eingebettete Aktivität aufruft. Diese Aktivität wird in einer Umgebung ausgeführt, die den [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]-Datenkontext und alle `x:Name`-Werte im Bereich einschließt. In der `GenericInvoke`-Methode wird diese Umgebung der Aktivität durch eine <xref:System.Activities.Hosting.SymbolResolver>-Erweiterung bereitgestellt. Diese Erweiterung wird einem <xref:System.Activities.WorkflowInvoker> hinzugefügt, mit dem die eingebettete Aktivität immer dann aufgerufen wird, wenn der Delegat der Markuperweiterung aufgerufen wird.  
  
> [!NOTE]
>  Der Standarddesigner unterstützt die ShowWindow-Aktivität nicht. Die Datei ShowWindow.Xaml wird daher nicht ordnungsgemäß im Designer angezeigt.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die WPFWFIntegration.sln-Projektmappendatei.  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie F5, um die Projektmappe auszuführen.  
  
4.  Geben Sie im Dialogfeld Ihren Vor- und Nachnamen ein.  
  
5.  Schließen Sie das Dialogfeld, und die Konsole wiederholt den Namen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\WPFWFIntegration`