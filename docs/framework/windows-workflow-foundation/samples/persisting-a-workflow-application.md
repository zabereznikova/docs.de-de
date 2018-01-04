---
title: Beibehalten einer Workflowanwendung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: abcff14c-f047-4195-ba26-d27f4a82c24e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cf23b8e33766ea7a15135418142082a0e7b715ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="persisting-a-workflow-application"></a>Beibehalten einer Workflowanwendung
In diesem Beispiel wird veranschaulicht, wie eine <xref:System.Activities.WorkflowApplication> ausgeführt wird, wie sie im Leerlauf entladen wird und wie sie neu geladen wird, um ihre Ausführung fortzusetzen.  
  
## <a name="sample-details"></a>Beispieldetails  
 <xref:System.Activities.WorkflowApplication> ist ein Host für eine einzelne Workflowinstanz, die eine einfache Schnittstelle bereitstellt und mehrere der allgemeineren Hostingszenarien aktiviert. Ein solches Szenario stellen lang ausgeführte, durch Dauerhaftigkeit unterstützte Workflows dar. Die Hoststeuerung der Dauerhaftigkeit wird entweder durch Aufrufen eines Dauerhaftigkeitvorgangs in der <xref:System.Activities.WorkflowApplication> oder durch das Behandeln eines <xref:System.Activities.WorkflowApplication>-Ereignisses und die Angabe, dass die <xref:System.Activities.WorkflowApplication> dauerhaft sein soll, durchgeführt.  
  
 Der Beispielworkflow ist eine <xref:System.Activities.Statements.WriteLine>-Aktivität, die den Benutzer zur Eingabe seines Namens auffordert, eine `ReadLine`-Aktivität zum Empfangen des Namens durch die Wiederaufnahme eines <xref:System.Activities.Bookmark> als Eingabe und einer anderen <xref:System.Activities.Statements.WriteLine>-Aktivität zum Ausgeben eines Grußes an den Benutzer. Wenn ein Workflow auf eine Eingabe wartet, stellt dies einen natürlichen Punkt für Dauerhaftigkeit dar. Dies wird häufig als <xref:System.Workflow.Runtime.Tracking.TrackingWorkflowEvent.Idle>-Punkt bezeichnet. <xref:System.Activities.WorkflowApplication> löst das <xref:System.Workflow.Runtime.Tracking.TrackingWorkflowEvent.Idle>-Ereignis immer dann aus, wenn das Workflowprogramm beibehalten werden kann, auf die Wiederaufnahme eines Lesezeichens wartet und keine andere Verarbeitung erfolgt. Im Workflow dieses Beispiels tritt dieser Punkt sofort auf, nachdem die `ReadLine`-Aktivität mit der Ausführung begonnen hat.  
  
 Ein <xref:System.Activities.WorkflowApplication> ist zum Ausführen von Persistenz mit Einrichten einer <!--zz <xref:System.Runtime.Persistence.InstanceStore> --> `System.Runtime.Persistence.InstanceStore`. In diesem Beispiel wird der <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> verwendet. Die <!--zz <xref:System.Runtime.Persistence.InstanceStore> --> `System.Runtime.Persistence.InstanceStore` zugewiesen werden, die <xref:System.Activities.WorkflowApplication.InstanceStore%2A> Eigenschaft, bevor die <xref:System.Activities.WorkflowApplication> ausgeführt wird.  
  
 Im Beispiel wird dem <xref:System.Activities.WorkflowApplication.PersistableIdle%2A>-Ereignis ein Handler hinzugefügt. Der Handler für dieses Ereignis gibt durch die Rückgabe einer <xref:System.Activities.WorkflowApplication> an, was die <xref:System.Activities.PersistableIdleAction> durchführen soll. Wenn <xref:System.Activities.PersistableIdleAction.Unload> zurückgegeben wird, wird die <xref:System.Activities.WorkflowApplication> entladen.  
  
 Im Beispiel wird dann eine Benutzereingabe akzeptiert, und der beibehaltene Workflow wird in eine neue <xref:System.Activities.WorkflowApplication> geladen. Dies erfolgt durch Erstellen eines neuen <xref:System.Activities.WorkflowApplication>, Neuerstellen der <!--zz <xref:System.Runtime.Persistence.InstanceStore> --> `System.Runtime.Persistence.InstanceStore`, und Zuordnen der abgeschlossenen und entladenen Ereignisse zur Instanz, und dem anschließenden Aufrufen <xref:System.Activities.WorkflowApplication.Load%2A> durch den Bezeichner der Ziel-Workflowinstanz. Sobald die Instanz abgerufen wurde, wird das Lesezeichen der `ReadLine`-Aktivität fortgesetzt. Der Workflow setzt die Ausführung aus der `ReadLine`-Aktivität bis zum Abschluss fort. Wenn der Workflow abgeschlossen und entladen wurde, die <!--zz <xref:System.Runtime.Persistence.InstanceStore> --> `System.Runtime.Persistence.InstanceStore` ist ein letztes Mal aufgerufen, um den Workflow zu löschen.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie eine [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Eingabeaufforderung.  
  
     Für dieses Beispiel ist SQL Server Express erforderlich, das standardmäßig zusammen mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] installiert wird.  
  
2.  Navigieren Sie zum Beispielverzeichnis (\WF\Basic\Persistence\InstancePersistence\CS), und führen Sie CreateInstanceStore.cmd aus.  
  
    > [!CAUTION]
    >  Das Skript "CreateInstanceStore.cmd" versucht, die Datenbank auf der Standardinstanz von SQL Server 2008 Express zu erstellen. Wenn Sie die Datenbank auf einer anderen Instanz installieren möchten, ändern Sie hierfür das Skript.  
  
3.  Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Persistence.sln-Projektmappendatei, und drücken Sie STRG+UMSCHALT+B, um sie zu erstellen.  
  
    > [!CAUTION]
    >  Wenn Sie die Datenbank auf einer nicht standardmäßigen Instanz von SQL Server installiert haben, aktualisieren Sie vor dem Erstellen der Projektmappe die Verbindungszeichenfolge im Code.  
  
4.  Führen Sie das Beispiel mit Administratorrechten aus, navigieren Sie zur Bin-Verzeichnis des Projekts (\WF\Basic\Persistence\InstancePersistence\bin\Debug) in [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]mit der rechten Maustaste auf Workflow.exe, und Auswählen von **als AdministratorAusführen**.  
  
#### <a name="to-remove-the-instance-store-database"></a>So entfernen Sie die Instanzspeicherdatenbank  
  
1.  Öffnen Sie eine [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Eingabeaufforderung.  
  
2.  Navigieren Sie zum Beispielverzeichnis, und führten Sie RemoveInstanceStore.cmd aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\InstancePersistence`  
  
## <a name="see-also"></a>Siehe auch  
 [AppFabric-Hosting und Persistenzbeispiele](http://go.microsoft.com/fwlink/?LinkId=193961)
