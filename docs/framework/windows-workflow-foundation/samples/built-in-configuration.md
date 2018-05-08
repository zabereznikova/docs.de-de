---
title: Integrierte Konfiguration
ms.date: 03/30/2017
ms.assetid: 34e85c9b-088d-4347-816c-0f77cb73ef2f
ms.openlocfilehash: 8488a753cb1c540d9c34d9bcf7b2a3112302a122
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="built-in-configuration"></a>Integrierte Konfiguration
In diesem Beispiel werden die Verwendung und die Konfiguration des SQL-Workflowinstanzspeichers veranschaulicht. Beim SQL-Workflowinstanzspeicher handelt es sich um die SQL-basierte Implementierung eines Instanzspeichers. Diese ermöglicht einer Instanz das Speichern und Laden von Zuständen in eine bzw. aus einer SQL Server- oder SQL Server Express-Datenbank.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie (Downloadseite) auf allen Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\BuiltInConfiguration`  
  
## <a name="sample-details"></a>Beispieldetails  
 Dieses Beispiel besteht aus einem Workflow, der einen Zähldienst implementiert. Wenn die Startmethode des Diensts aufgerufen wird, zählt der Dienst von 0 bis 59. Der Zählerwert wird alle zwei Sekunden erhöht. Der Workflow wird nach jeder Erhöhung des Zählerwerts gespeichert.  
  
 Der Zählworkflow wird auf einem Workflowdiensthost gehostet. Die `Main`-Methode des Programms erstellt eine Instanz des Workflowdiensthosts, auf dem der Zählworkflow gehostet ist. Zunächst werden die Endpunkte definiert, unter denen der Zählworkflow erreichbar ist. Anschließend wird das Verhalten zur Konfiguration des SQL-Workflowinstanzspeichers definiert. Dann erstellt das Programm einen Client, der die Startmethode des Zählworkflows aufruft.  
  
 Der Zählvorgang wird bei Programmstart automatisch gestartet. Beachten Sie, dass das Laden der Instanz und die Konfiguration des SQL-Workflowinstanzspeichers einige Sekunden dauern kann. Weitere Informationen zur workflowinstanzspeicher finden Sie unter [SQL-Workflowinstanzspeicher](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).  
  
 Das Beispiel besteht aus zwei Teilen:  
  
1.  InstanceStore1 zeigt, wie der <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> mit C#-Code konfiguriert wird (siehe "Program.cs").  
  
2.  InstanceStore2 zeigt, wie der <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> mit XML konfiguriert wird (siehe "App.config").  
  
 Die folgenden Einstellungen sind zur Konfiguration des SQL-Workflowinstanzspeichers verfügbar:  
  
-   Legen Sie den `HostLockRenewalPeriod`-Wert fest. Dieser Wert definiert das Intervall zur Erneuerung des Sperrbesitzes der auf dem Host ausgeführten Instanzen. Die Sperrinformationen werden im Instanzspeicher gespeichert. Wenn der Besitz im Verlauf von zwei der mit `HostLockRenewalPeriod` definierten Intervalle nicht erneuert wird, gilt die Instanz als abgebrochen. Wenn ein anderer <xref:System.ServiceModel.Activities.WorkflowServiceHost> denselben Workflow ausführt und mit demselben Instanzspeicher verbunden ist (auf demselben oder auf einem anderen Computer), stellt dieser die Instanz wieder her. (Die Instanzwiederherstellung wird in diesem Beispiel nicht behandelt.)  
  
-   Legen Sie den `RunnableInstancesDetectionPeriod`-Wert fest. Dieser Wert definiert das Intervall, mit dem der Host Abfragen nach ausführbaren Instanzen ausführt. Instanzen können ausführbar werden, wenn eines der folgenden Ereignisse auftritt:  
  
    -   Ein permanenter Zeitgeber (<xref:System.Activities.Statements.Delay>) läuft ab.  
  
    -   Ein anderer Host hält das `HostLockRenewal`-Intervall nicht ein (z. B. aufgrund eines Computerabsturzes), und die Instanz wird wiederhergestellt.  
  
-   Legen Sie den `InstanceCompletionAction`-Wert fest. Wenn Sie diese Eigenschaft auf `DeleteNothing` festlegen, verbleiben abgeschlossene Instanzen im Instanzspeicher. Wenn Sie diese Eigenschaft auf `DeleteAll` festlegen, werden abgeschlossene Instanzen aus dem Speicher gelöscht. Hinweis  
  
    > [!NOTE]
    >  Wenn Sie den Host vor Abschluss des Zählvorgangs durch Drücken der EINGABETASTE beenden, wird die Workflowinstanz nicht abgeschlossen.  
  
-   Legen Sie den `InstanceLockedExceptionAction`-Wert fest. Mit dieser Einstellung wird die Aktion definiert, die vom Host ausgeführt wird, um eine Instanz zu laden, die durch einen anderen Host gesperrt ist. Folgende Optionen sind verfügbar:  
  
    -   `NoRetry`: Der Ladevorgang wird nicht erneut versucht, und auf dem Host wird eine `InstanceLockedException` zurückgegeben.  
  
    -   `BasicRetry`: Der Versuch, die Instanz zu laden, wird wiederholt. Die Wiederholungen erfolgen nach einem einfachen linearen Algorithmus (z. B. alle fünf Sekunden).  
  
    -   `AggressiveRetry`: Der Versuch, die Instanz zu laden, wird wiederholt. Die Wiederholungen erfolgen nach einem exponentiellen Backoff-Algorithmus.  
  
-   Legen Sie die Codierungsoption fest. Mit dieser Einstellung definieren Sie, wie der Instanzstatus im SQL-Workflowinstanzspeicher gespeichert wird. Folgende Optionen sind verfügbar:  
  
    -   Der Instanzstatus wird mit dem GZip-Algorithmus komprimiert.  
  
    -   Der Instanzstatus wird nicht komprimiert.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie eine [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Eingabeaufforderung als Administrator, falls Sie über die erforderlichen Berechtigungen verfügen.  
  
2.  Navigieren Sie zum Beispielverzeichnis (\WF\Basic\Persistence\BuiltInConfiguration\CS), und führen Sie "CreateInstanceStore.cmd" aus.  
  
3.  Wenn Sie nicht über Administratorberechtigungen verfügen, erstellen Sie eine SQL Server-Anmeldung. Wechseln Sie zu `Security`, **Anmeldungen**. Mit der rechten Maustaste **Anmeldungen** und eine neue Anmeldung erstellen.  
  
4.  Fügen Sie der SQL-Rolle Ihr ACL-Benutzerkonto hinzu. Open **Datenbanken**, **InstanceStore**, **Sicherheit**. Mit der rechten Maustaste **Benutzer** , und wählen Sie **neue Benutzer**. Legen Sie die **Anmeldename** für den Benutzer, die im vorherigen Schritt erstellt haben. Fügen Sie den Benutzer, Mitgliedschaft in Datenbankrolle **System.Activities.DurableInstancing.InstanceStoreUsers** (und andere). Beachten Sie, dass der Benutzer möglicherweise bereits vorhanden ist (z. B. als DBO).  
  
5.  Öffnen Sie die Datei InstanceStore.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], und erstellen Sie die Projektmappe, indem Sie STRG+UMSCHALT+B drücken.  
  
6.  In [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], navigieren Sie zum Verzeichnis für das Beispiel entsprechende "bin\Debug" (\WF\Basic\Persistence\BuiltInConfiguration\cs\InstanceStore(1 or 2)\bin\debug), klicken Sie mit der rechten Maustaste auf InstanceStore.exe, und wählen Sie **Ausführen als Administrator**. Dieses Beispiel muss mit Administratorberechtigungen ausgeführt werden, da es einen Kanallistener öffnet.  
  
7.  Wenn Sie den Instanzspeicher nicht in der lokalen Installation von SQL Server Express erstellt haben, müssen Sie die Datenbankverbindungszeichenfolge (InstanceStore1-Projekt: `const string ConnectionString` in der Datei "Program.cs", InstanceStore2-Projekt: `connectionString`-Attribut in der Datei "App.config") im Beispiel aktualisieren und das Beispiel neu kompilieren.  
  
#### <a name="to-verify-the-sample-is-running-correctly"></a>So überprüfen Sie, ob das Beispiel ordnungsgemäß ausgeführt wird  
  
1.  Starten Sie SQL Server Management Studio, während das Beispiel ausgeführt wird.  
  
2.  In der **Objektexplorer**Option **Datenbanken**, **InstanceStore**, **Tabellen**, und klicken Sie dann  **System.Activities.DurableInstancing.InstanceTable**.  
  
3.  Klicken Sie mit der rechten Maustaste auf **InstanceTable** , und wählen Sie **oberste 1000 Zeilen auswählen**.  
  
4.  Beachten Sie, dass es einen neuen Eintrag, und dass die **Gültigkeit der Sperre** alle fünf Sekunden ändert (klicken Sie auf der Taskleiste **Execute** Schaltfläche, um die Abfrage zu aktualisieren). Dies ist eine Folge der Einstellung der **Host Lock Renewal Period** bis 5.  
  
5.  Nach Abschluss des Zählvorgangs wird der Eintrag aus der Instanztabelle entfernt. Dies ist eine Folge der Einstellung **Instance Completion Action** auf **DeleteAll**.  
  
6.  Drücken Sie EINGABETASTE, um die workflowhostanwendung zu beenden, und beachten Sie, dass die **LockOwnersTable** wird gelöscht.  
  
#### <a name="to-uninstall-the-sample"></a>So installieren Sie das Beispiel aus  
  
1.  Führen Sie "RemoveInstanceStore.cmd" im Beispielverzeichnis (\WF\Basic\Persistence\BuiltInConfiguration) aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\BuiltInConfiguration`  
  
## <a name="see-also"></a>Siehe auch  
 [AppFabric-Hosting und Persistenzbeispiele](http://go.microsoft.com/fwlink/?LinkId=193961)
