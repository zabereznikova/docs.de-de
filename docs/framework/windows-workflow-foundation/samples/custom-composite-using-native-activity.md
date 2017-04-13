---
title: "Benutzerdefinierte Zusammensetzungen mit NativeActivity | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ef9e739c-8a8a-4d11-9e25-cb42c62e3c76
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Benutzerdefinierte Zusammensetzungen mit NativeActivity
In diesem Beispiel wird veranschaulicht, wie eine <xref:System.Activities.NativeActivity> geschrieben wird, die andere <xref:System.Activities.Activity>\-Objekte plant, um den Fluss der Ausführung eines Workflows zu steuern.Zur Veranschaulichung dieses Vorgangs werden in diesem Beispiel zwei häufige Ablaufsteuerungen verwendet: Sequence und While.  
  
## Beispieldetails  
 Beginnend bei `MySequence`ist die erste Sache, die zu beachten ist, dass diese von <xref:System.Activities.NativeActivity> abgeleitet ist.<xref:System.Activities.NativeActivity> ist das <xref:System.Activities.Activity>\-Objekt, das die volle Bandbreite der Workflow\-Laufzeit durch den <xref:System.Activities.NativeActivityContext> verfügbar macht, der an die `Execute`\-Methode übergeben wurde.  
  
 `MySequence` macht eine öffentliche Auflistung von <xref:System.Activities.Activity>\-Objekten verfügbar, die vom Workflowautor aufgefüllt werden.Bevor der Workflow ausgeführt wird, ruft die Workflowlaufzeit die <xref:System.Activities.Activity.CacheMetadata%2A>\-Methode in jeder Aktivität in einem Workflow auf.Während dieses Prozesses legt die Laufzeit Beziehungen zwischen übergeordneten und untergeordneten Elementen für Datenbereiche und Lebensdauerverwaltung fest.Die Standardimplementierung der <xref:System.Activities.Activity.CacheMetadata%2A>\-Methode verwendet die <xref:System.ComponentModel.TypeDescriptor>\-Instanzklasse für die `MySequence`\-Aktivität, um eine beliebige öffentliche Eigenschaft des Typs <xref:System.Activities.Activity> hinzuzufügen, oder <xref:System.Collections.IEnumerable>\<<xref:System.Activities.Activity>\> als untergeordnete Elemente der `MySequence`\-Aktivität.  
  
 Immer dann, wenn eine Aktivität eine öffentliche Auflistung von untergeordneten Aktivitäten verfügbar macht, ist es wahrscheinlich, dass diese untergeordneten Aktivitäten ihren Zustand freigeben.Für die übergeordnete Aktivität, in diesem Fall `MySequence`, besteht eine empfohlene Vorgehensweise darin, auch eine Auflistung von Variablen verfügbar zu machen, durch die die untergeordneten Aktivitäten dies erreichen können.Genau wie untergeordnete Aktivitäten fügt die <xref:System.Activities.Activity.CacheMetadata%2A>\-Methode öffentliche Eigenschaften des Typs <xref:System.Activities.Variable> oder <xref:System.Collections.IEnumerable>\<<xref:System.Activities.Variable>\> als Variablen, die der `MySequence`\-Aktivität zugewiesen sind, hinzu.  
  
 Neben den öffentlichen Variablen, die von den untergeordneten Elementen von `MySequence` bearbeitet werden, muss `MySequence` auch die Position aufzeichnen, an der es sich bei der Ausführung der untergeordneten Elemente befindet.Hierfür wird eine private Variable, `currentIndex`, verwendet.Diese Variable wird als Teil der `MySequence`\-Umgebung registriert, indem der <xref:System.Activities.NativeActivityMetadata.AddImplementationVariable%2A>\-Methode innerhalb <xref:System.Activities.Activity.CacheMetadata%2A>\-Methode der `MySequence`\-Aktivität ein Aufruf hinzugefügt wird.Die <xref:System.Activities.Activity>\-Objekte, die der `Activities`\-Auflistung von `MySequence` hinzugefügt werden, können nicht auf Variablen zugreifen, die auf diese Weise hinzugefügt wurden.  
  
 Wenn `MySequence` von der Laufzeit ausgeführt wird, ruft die Laufzeit die <xref:System.Activities.NativeActivity.Execute%2A>\-Methode auf und übergibt einen <xref:System.Activities.NativeActivityContext>.<xref:System.Activities.NativeActivityContext> ist der Proxy der Aktivität in der Laufzeit zum Dereferenzieren von Argumenten und Variablen sowie zum Planen von anderen <xref:System.Activities.Activity>\-Objekten oder `ActivityDelegates`.`MySequence` verwendet eine `InternalExecute`\-Methode zum Kapseln der Logik des Planens des ersten untergeordneten Elements sowie aller nachfolgenden untergeordneten Elemente in einer einzigen Methode.Es wird durch Dereferenzieren des `currentIndex` gestartet.Wenn dieser der Anzahl in der `Activities`\-Auflistung entspricht, wird die Sequenz beendet, die Aktivität gibt einen Wert zurück, ohne Aufgaben zu planen, und er wird von der Laufzeit in den Zustand <xref:System.Activities.ActivityInstanceState> verschoben.Wenn der `currentIndex` geringer als die Anzahl von Aktivitäten ist, wird das nächste untergeordnete Element aus der `Activities`\-Auflistung abgerufen, und `MySequence` ruft <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A> auf und übergibt das zu planende untergeordnete Element sowie einen <xref:System.Activities.CompletionCallback>, der auf die `InternalExecute`\-Methode zeigt.Schließlich wird der `currentIndex` inkrementiert, und die Steuerung wird zurück an die Laufzeit gegeben.Solange eine Instanz von `MySequence` über ein geplantes untergeordnetes <xref:System.Activities.Activity>\-Objekt verfügt, wird diese von der Laufzeit als im ausgeführten Zustand betrachtet.  
  
 Wenn die untergeordnete Aktivität abgeschlossen wird, wird der <xref:System.Activities.CompletionCallback> ausgeführt.Die Schleife fängt wieder von vorne an.Wie auch `Execute`, verwendet ein <xref:System.Activities.CompletionCallback> einen <xref:System.Activities.NativeActivityContext>, sodass die Implementierung Zugriff auf die Laufzeit erhält.  
  
 `MyWhile` unterscheidet sich von `MySequence` dahingehend, dass es ein einzelnes <xref:System.Activities.Activity>\-Objekt wiederholt plant und einen <xref:System.Activities.Activity%601>\<booleschen\> Wert mit dem Namen `Condition` verwendet, um zu ermitteln, ob diese Planung stattfinden soll.Wie auch `MySequence`, verwendet `MyWhile` eine `InternalExecute`\-Methode, um seine Planungslogik zu zentralisieren.Es plant den `Condition`<xref:System.Activities.Activity>\<booleschen\> Wert mit einem <xref:System.Activities.CompletionCallback%601>\<booleschen\> Wert mit dem Namen `OnEvaluationCompleted`.Wenn die Ausführung von `Condition` abgeschlossen ist, wird das Ergebnis durch diesen <xref:System.Activities.CompletionCallback> in einem stark typisierten Parameter mit dem Namen `result` verfügbar.Wenn `true`, `MyWhile`<xref:System.Activities.NativeActivityContext.ScheduleActivity%2A> aufruft, werden das `Body`<xref:System.Activities.Activity>\-Objekt und `InternalExecute` als <xref:System.Activities.CompletionCallback> übergeben.Wenn die Ausführung von `Body` abgeschlossen ist, wird `Condition` erneut in `InternalExecute` geplant, und die Starte beginn erneut von vorne.Wenn der `Condition``false` zurückgibt, gibt eine Instanz von `MyWhile` die Steuerung an die Laufzeit zurück, ohne den `Body` zu planen, und die Laufzeit verschiebt diesen in den Zustand <xref:System.Activities.ActivityInstanceState>.  
  
#### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Öffnen Sie die Beispielprojektmappe "Composite.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Erstellen Sie die Projektmappe, und führen Sie sie aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\CustomCompositeNativeActivity`  
  
## Siehe auch