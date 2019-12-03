---
title: Benutzerdefinierte Zusammensetzungen mit NativeActivity
ms.date: 03/30/2017
ms.assetid: ef9e739c-8a8a-4d11-9e25-cb42c62e3c76
ms.openlocfilehash: 57c724ad55c3aa2960e9a2d11fcd8419a94a0c72
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715178"
---
# <a name="custom-composite-using-native-activity"></a>Benutzerdefinierte Zusammensetzungen mit NativeActivity
In diesem Beispiel wird veranschaulicht, wie eine <xref:System.Activities.NativeActivity> geschrieben wird, die andere <xref:System.Activities.Activity>-Objekte plant, um den Fluss der Ausführung eines Workflows zu steuern. Zur Veranschaulichung dieses Vorgangs werden in diesem Beispiel zwei häufige Ablaufsteuerungen verwendet: Sequence und While.

## <a name="sample-details"></a>Beispieldetails
 Beginnend bei `MySequence` muss als Erstes beachtet werden, dass diese von <xref:System.Activities.NativeActivity> abgeleitet ist. <xref:System.Activities.NativeActivity> ist das <xref:System.Activities.Activity>-Objekt, das die volle Bandbreite der Workflowlaufzeit durch den <xref:System.Activities.NativeActivityContext> verfügbar macht, der an die `Execute`-Methode übergeben wurde.

 `MySequence` macht eine öffentliche Auflistung von <xref:System.Activities.Activity>-Objekten verfügbar, die vom Workflowautor aufgefüllt werden. Bevor der Workflow ausgeführt wird, ruft die Workflowlaufzeit die <xref:System.Activities.Activity.CacheMetadata%2A>-Methode in jeder Aktivität in einem Workflow auf. Während dieses Prozesses legt die Laufzeit Beziehungen zwischen übergeordneten und untergeordneten Elementen für Datenbereiche und Lebensdauerverwaltung fest. Die Standard Implementierung der <xref:System.Activities.Activity.CacheMetadata%2A>-Methode verwendet die <xref:System.ComponentModel.TypeDescriptor> Instance-Klasse für die `MySequence`-Aktivität, um eine beliebige öffentliche Eigenschaft des Typs <xref:System.Activities.Activity> oder <xref:System.Collections.IEnumerable>\<<xref:System.Activities.Activity>> als untergeordnete Elemente der `MySequence`-Aktivität hinzuzufügen.

 Immer dann, wenn eine Aktivität eine öffentliche Auflistung von untergeordneten Aktivitäten verfügbar macht, ist es wahrscheinlich, dass diese untergeordneten Aktivitäten ihren Zustand freigeben. Für die übergeordnete Aktivität, in diesem Fall `MySequence`, besteht eine empfohlene Vorgehensweise darin, auch eine Auflistung von Variablen verfügbar zu machen, durch die die untergeordneten Aktivitäten dies erreichen können. Wie untergeordnete Aktivitäten werden von der <xref:System.Activities.Activity.CacheMetadata%2A>-Methode öffentliche Eigenschaften des Typs <xref:System.Activities.Variable> oder <xref:System.Collections.IEnumerable>\<<xref:System.Activities.Variable>> als Variablen, die der `MySequence` Aktivität zugeordnet sind, hinzugefügt.

 Neben den öffentlichen Variablen, die von den untergeordneten Elementen von `MySequence` bearbeitet werden, muss `MySequence` auch die Position aufzeichnen, an der es sich bei der Ausführung der untergeordneten Elemente befindet. Hierfür wird eine private Variable, `currentIndex`, verwendet. Diese Variable wird als Teil der `MySequence`-Umgebung registriert, indem der <xref:System.Activities.NativeActivityMetadata.AddImplementationVariable%2A>-Methode innerhalb `MySequence`-Methode der <xref:System.Activities.Activity.CacheMetadata%2A>-Aktivität ein Aufruf hinzugefügt wird. Die <xref:System.Activities.Activity>-Objekte, die der `MySequence`-Auflistung von `Activities`hinzugefügt werden, können nicht auf Variablen zugreifen, die auf diese Weise hinzugefügt wurden.

 Wenn `MySequence` von der Laufzeit ausgeführt wird, ruft die Laufzeit die <xref:System.Activities.NativeActivity.Execute%2A>-Methode auf und übergibt einen <xref:System.Activities.NativeActivityContext>. <xref:System.Activities.NativeActivityContext> ist der Proxy der Aktivität in der Laufzeit zum Dereferenzieren von Argumenten und Variablen sowie zum Planen von anderen <xref:System.Activities.Activity>-Objekten oder `ActivityDelegates`. `MySequence` verwendet eine `InternalExecute`-Methode zum Kapseln der Planungslogik des ersten untergeordneten Elements sowie aller nachfolgenden untergeordneten Elemente in einer einzelnen Methode. Es wird durch Dereferenzieren des `currentIndex` gestartet. Wenn dieser der Anzahl in der `Activities`-Auflistung entspricht, wird die Sequenz beendet, die Aktivität gibt einen Wert zurück, ohne Aufgaben zu planen, und er wird von der Laufzeit in den Zustand <xref:System.Activities.ActivityInstanceState.Closed> verschoben. Wenn die `currentIndex` kleiner als die Anzahl der Aktivitäten ist, wird das nächste untergeordnete Element aus der `Activities` Auflistung abgerufen, und `MySequence` ruft <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>auf, wobei das zu planende untergeordnete Element und eine <xref:System.Activities.CompletionCallback>, die auf die `InternalExecute` Methode zeigt, übergeben werden. Schließlich wird der `currentIndex` inkrementiert, und die Steuerung wird zurück an die Laufzeit gegeben. Solange eine Instanz von `MySequence` über ein geplantes untergeordnetes <xref:System.Activities.Activity>-Objekt verfügt, wird diese von der Laufzeit als im ausgeführten Zustand betrachtet.

 Wenn die untergeordnete Aktivität abgeschlossen wird, wird der <xref:System.Activities.CompletionCallback> ausgeführt. Die Schleife fängt wieder von vorne an. Wie auch `Execute`, verwendet ein <xref:System.Activities.CompletionCallback> einen <xref:System.Activities.NativeActivityContext>, sodass die Implementierung Zugriff auf die Laufzeit erhält.

 `MyWhile` unterscheidet sich von `MySequence` darin, dass es ein einzelnes <xref:System.Activities.Activity> Objekt wiederholt plant und in dem ein <xref:System.Activities.Activity%601>< boolescher\> mit dem Namen `Condition` verwendet wird, um zu bestimmen, ob diese Planung stattfinden soll. Wie auch `MySequence`, verwendet `MyWhile` eine `InternalExecute`-Methode, um seine Planungslogik zu zentralisieren. Sie plant den `Condition`<xref:System.Activities.Activity>< booleschen\> mit einem <xref:System.Activities.CompletionCallback%601>\<booleschen > mit dem Namen `OnEvaluationCompleted`. Wenn die Ausführung von `Condition` abgeschlossen ist, wird das Ergebnis durch diesen <xref:System.Activities.CompletionCallback> in einem stark typisierten Parameter mit dem Namen `result` verfügbar. Wenn `true`, `MyWhile`<xref:System.Activities.NativeActivityContext.ScheduleActivity%2A> aufruft, werden das `Body`<xref:System.Activities.Activity>-Objekt und `InternalExecute` als <xref:System.Activities.CompletionCallback> übergeben. Wenn die Ausführung von `Body` abgeschlossen ist, wird `Condition` erneut in `InternalExecute` geplant, und die Starte beginn erneut von vorne. Wenn der `Condition``false` zurückgibt, gibt eine Instanz von `MyWhile` die Steuerung an die Laufzeit zurück, ohne den `Body` zu planen, und die Laufzeit verschiebt diesen in den Zustand <xref:System.Activities.ActivityInstanceState.Closed>.

#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Öffnen Sie die Beispiel Projekt Mappe "Composite. sln" in Visual Studio 2010.

2. Erstellen Sie die Projektmappe, und führen Sie sie aus.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\CustomCompositeNativeActivity`
