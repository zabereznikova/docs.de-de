---
title: "Instance Locked Exception Action | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 164a5419-315c-4987-ad72-54cbdb88d402
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Instance Locked Exception Action
Mit der <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.InstanceLockedExceptionAction%2A>\-Eigenschaft des SQL\-Workflowinstanzspeichers können Sie angeben, welche Aktion der SQL\-Persistenzanbieter durchführen soll, wenn er <xref:System.Runtime.DurableInstancing.InstanceLockedException> empfängt.Der Persistenzanbieter empfängt diese Ausnahme, wenn er versucht, eine Workflowdienstinstanz zu sperren, die von einem anderen Diensthost gesperrt wurde.Folgende Werte sind für diese Eigenschaft möglich <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>, <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction> und <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>.Der Standardwert ist <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>.In der folgenden Liste werden die drei Optionen beschrieben:  
  
-   <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>.Der Diensthost versucht nicht, die Workflowdienstinstanz zu sperren, und übergibt <xref:System.Runtime.DurableInstancing.InstanceLockedException> an den Aufrufer. Wenn der Workflow mehr als 60 Sekunden im Arbeitsspeicher verbleibt, verwenden Sie <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction> zum Wiederholen.Der Standardwert ist <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>.  
  
-   <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>.Der Diensthost versucht erneut, die Workflowdienstinstanz mit einem linearen Intervall zwischen Wiederholungsversuchen zu sperren, und übergibt am Ende der Sequenz <xref:System.Runtime.DurableInstancing.InstanceLockedException> an den Aufrufer.Wenn der Workflow etwa zwischen 5\-60 Sekunden im Arbeitsspeicher verbleibt und Nachrichten in Batches empfangen werden, wobei es wahrscheinlicher ist, dass die Nachrichten, an dieselbe Instanz auf demselben Host gesendet werden, um alle Nachrichten zu verarbeiten, bevor der Workflow entladen wird, verwenden Sie <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>, um die beste Latenz zu erreichen, ohne Ressourcen zu vergeuden.  
  
-   <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>.Der Diensthost versucht erneut, die Workflowdienstinstanz mit einem exponentiellen Backoffintervall zwischen Wiederholungsversuchen zu sperren, und übergibt am Ende der Sequenz die Ausnahme an den Aufrufer.Wenn der Workflow nur sehr kurze Zeit \(weniger als 5 Sekunden\) im Arbeitsspeicher verbleibt oder eine Webfarm umfangreich ist und die Wahrscheinlichkeit, dass demselben Host eine weitere Nachricht zugestellt wird, nicht sehr hoch ist, verwenden Sie <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>, um die beste Latenz zu erzielen.  
  
 Die Funktion Instance Locked Exception Action unterstützt die folgenden Szenarios.Für alle Szenarios gilt: Wenn die instanceLockedExceptionAction\-Eigenschaft des SqlWorkflowInstanceStore\-Objekts auf <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction> oder <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction> festgelegt ist, versucht der Host in regelmäßigen Abständen und transparent erneut, die Sperre für die Instanzen durchzusetzen.  
  
1.  **Ordnungsgemäßes Herunterfahren und überlappende Wiederverwendung von Anwendungsdomänen.** Nehmen Sie an, eine **AppDomain** mit einem Diensthost, der Workflowdienstinstanzen ausführt, wird wiederverwendet, und eine neue **AppDomain** wird für neue Anforderungen geladen, während die alte **AppDomain** ordnungsgemäß heruntergefahren wird.Mit dem Herunterfahren wird gewartet, bis die Workflowdienstinstanzen sich im Leerlauf befinden. Dann werden die Instanzen in den Persistenzspeicher verschoben und entladen.Versuche von Hosts in der neuen **AppDomain**, eine Instanz zu sperren, lösen <xref:System.Runtime.DurableInstancing.InstanceLockedException> aus.  
  
2.  **Horizontale Skalierung permanenter Workflows in einer homogenen Serverfarm.** Nehmen Sie an, ein Knoten in einer Serverfarm, auf dem eine Workflowinstanz ausgeführt wird, stürzt ab, und der Workflowhost kann die Sperren der ausgeführten Instanz nicht aufheben.Wenn an einem Diensthost, der auf einem anderen Knoten der Farm ausgeführt wird, eine Meldung für diese Workflowinstanz eingeht und dieser versucht, die Instanzen zu sperren, erhält er <xref:System.Runtime.DurableInstancing.InstanceLockedException>.Die Sperren laufen nach einem gewissen Zeitraum ab, da der für die Erneuerung der Sperren zuständige Host nicht mehr vorhanden ist.  
  
     **Horizontale Skalierung permanenter Workflows in einer homogenen Serverfarm.**  Nehmen Sie an, Sie möchten einen permanenten Workflow mit mehreren Hosts horizontal skalieren, denen ein Netzwerklastenausgleich \(Network Load Balancer, NLB\) vorgeschaltet ist. Der Workflowhost, der auf einem Knoten der Farm ausgeführt wird, lädt eine Workflowinstanz und verarbeitet eine Meldung, und die nächste Meldung für die Instanz wird an einen Host weitergeleitet, der auf einem anderen Knoten ausgeführt wird, da der Netzwerklastenausgleich über keinen Routingalgorithmus zur Weiterleitung von Meldungen an den Host verfügt, der die Instanz bereits ausführt.Bei Erhalt der Meldung versucht der zweite Host, die Workflowinstanz zu laden. Da diese jedoch durch den ersten Host gesperrt wurde, wird die <xref:System.Runtime.DurableInstancing.InstanceLockedException>\-Ausnahme ausgelöst.Der erste Host entsperrt die Instanz, wenn die Verarbeitung der ersten Meldung abgeschlossen ist, und der zweite Host kann die Instanz beim nächsten Versuch erfolgreich sperren, laden und die zweite Meldung verarbeiten.