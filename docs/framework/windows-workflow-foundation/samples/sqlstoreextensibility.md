---
title: "SQLStoreExtensibility | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5da1b5a3-f144-41ba-b9c4-02818b28b15d
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# SQLStoreExtensibility
In diesem Beispiel werden die Verwendung und die Konfiguration von höher gestuften Eigenschaften im SQL\-Workflowinstanzspeicher veranschaulicht.Beim SQL\-Workflowinstanzspeicher handelt es sich um die SQL\-basierte Implementierung eines Instanzspeichers.Diese ermöglicht einer Instanz das Speichern und Laden von Zuständen in eine bzw. aus einer SQL Server\- oder SQL Server Express\-Datenbank.Die Speichererweiterbarkeitsfunktion ermöglicht es Benutzern, Eigenschaften zu definieren, die im Instanzspeicher gespeichert werden.Diese Eigenschaften werden in einer höher gestuften Eigenschaftenansicht angezeigt, die es Benutzern ermöglicht, sie abzufragen.  
  
 Dieses Beispiel besteht aus einem Workflow, der einen Zähldienst implementiert.Wenn die Startmethode des Diensts aufgerufen wird, zählt der Dienst von 0 bis 29.Der Zählerwert wird alle zwei Sekunden erhöht.Der Workflow wird nach jeder Erhöhung des Zählerwerts gespeichert.Der aktuelle Zählerwert wird im Instanzspeicher als höher gestufte Eigenschaft gespeichert.  
  
 Der Zählworkflow wird von einem Workflowdiensthost gehostet.Die `Main`\-Methode des Programms führt die folgenden Aktionen aus:  
  
-   Erstellt eine Instanz des Workflowdiensthosts, der den Zählworkflow hostet und die Endpunkte definiert, an denen der Zählworkflow erreicht werden kann.  
  
-   Definiert das Verhalten des SQL\-Workflowinstanzspeichers zur Konfiguration des SQL\-Workflowinstanzspeichers.Der Speicher wird angewiesen, `CountStatus` als höher gestufte Eigenschaft zu behandeln.  
  
-   Erstellt einen Client, der die Startmethode des Zählworkflows aufruft.  
  
 Der Zählvorgang wird bei Programmstart automatisch gestartet.Beachten Sie, dass das Laden der Instanz und die Konfiguration des SQL\-Workflowinstanzspeichers einige Sekunden dauern kann.  
  
 Um den Zählerwert als benutzerdefinierte Eigenschaft höher zu stufen, müssen die folgenden Schritte ausgeführt werden:  
  
1.  Die `CounterStatus`\-Klasse definiert eine Instanzerweiterung mit dem Typ <xref:System.Activities.Persistence.PersistenceParticipant>, der von Aktivitäten verwendet wird, um die Zustandsvariablen anzugeben.`Count` wird als lesegeschützter Wert definiert.Wenn eine Workflowinstanz einen Persistenzpunkt erreicht, speichert die Instanzerweiterung die `Count`\-Eigenschaft in die Persistenzdatensammlung.  
  
2.  Beim Erstellen des Instanzspeichers wird eine neue Eigenschaft, `CountStatus`, durch die `store.Promote()`\-Methode definiert.  
  
3.  Die `SaveCounter`\-Aktivität des Workflows weist den aktuellen Zählerwert dem `Count`\-Statusfeld zu.  
  
### So verwenden Sie dieses Beispiel  
  
1.  Erstellen Sie die Instanzspeicherdatenbank.  
  
    1.  Öffnen Sie eine [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]\-Eingabeaufforderung.  
  
    2.  Navigieren Sie zum Beispielverzeichnis \("\\WF\\Basic\\Persistence\\SqlStoreExtensibility\\CS"\), und führen Sie "CreateInstanceStore.cmd" an der [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]\-Eingabeaufforderung aus.  
  
        > [!WARNING]
        >  Das Skript "CreateInstanceStore.cmd" versucht, die Datenbank in der Standardinstanz von SQL Server 2008 Express zu erstellen.Wenn Sie die Datenbank in einer anderen Instanz installieren möchten, ändern Sie hierfür das Skript.  
  
2.  Öffnen Sie [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], laden Sie die Projektmappe "SqlStoreExtensibility.sln", und erstellen Sie sie, indem Sie STRG\+UMSCHALT\+B drücken.  
  
    > [!WARNING]
    >  Wenn Sie die Datenbank auf einer nicht standardmäßigen Instanz von SQL Server installiert haben, aktualisieren Sie vor dem Erstellen der Projektmappe die Verbindungszeichenfolge im Code.  
  
3.  Führen Sie das Beispiel mit Administratorrechten aus, indem Sie in [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] zum Verzeichnis "bin" \("\\WF\\Basic\\Persistence\\SqlStoreExtensibility\\bin\\Debug"\) des Projekts navigieren, mit der rechten Maustaste auf "SqlStoreExtensibility.exe" klicken und **Als Administrator ausführen** auswählen.  
  
### So überprüfen Sie die ordnungsgemäße Funktionsfähigkeit des Beispiels  
  
1.  Zeigen Sie den Inhalt der Instanztabelle mithilfe von SQL Server Management Studio an, indem Sie **Datenbanken**, **InstanceStore** und dann **System.ServiceModel.Activities.DurableInstancing.InstanceTable** im Objekt\-Explorer auswählen, mit der rechten Maustaste auf **System.ServiceModel.Activities.DurableInstancing.InstanceTable** klicken und **Oberste 1000 Zeilen auswählen** auswählen.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu SQL Server Management Studio finden Sie unter [Einführung in SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=165645).  
  
2.  Achten Sie auf die aufgeführten Workflowinstanzen.  
  
3.  Führen Sie an einer [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]\-Eingabeaufforderung das Skript "QueryInstanceStore.cmd" aus, das sich im Beispielverzeichnis \("\\WF\\Basic\\Persistence\\SqlStoreExtensibility"\) befindet.  
  
4.  Achten Sie auf den unter **CountStatus** angezeigten Zählerwert.  
  
5.  Führen Sie das Skript einige Male aus, um festzustellen, dass sich der **CountStats**\-Wert ändert.  
  
6.  Drücken Sie die EINGABETASTE, um die Workflowanwendung zu beenden.  
  
### So deinstallieren Sie das Beispiel  
  
1.  Entfernen Sie die Instanzspeicherdatenbank, indem Sie das Skript "RemoveInstanceStore.cmd" ausführen, das sich im Beispielverzeichnis \("\\WF\\Basic\\Persistence\\SqlStoreExtensibility"\) befindet.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\SQLStoreExtensibility`  
  
## Siehe auch  
 [Workflowpersistenz](../../../../docs/framework/windows-workflow-foundation//workflow-persistence.md)   
 [Workflowdienste](../../../../docs/framework/wcf/feature-details/workflow-services.md)   
 [AppFabric\-Hosting\- und \-Persistenzbeispiele](http://go.microsoft.com/fwlink/?LinkId=193961)