---
title: SQLStoreExtensibility
ms.date: 03/30/2017
ms.assetid: 5da1b5a3-f144-41ba-b9c4-02818b28b15d
ms.openlocfilehash: f49d05244cf9f65a8e06f39c7e40391aaebd9f77
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43408764"
---
# <a name="sqlstoreextensibility"></a>SQLStoreExtensibility
In diesem Beispiel werden die Verwendung und die Konfiguration von höher gestuften Eigenschaften im SQL-Workflowinstanzspeicher veranschaulicht. Beim SQL-Workflowinstanzspeicher handelt es sich um die SQL-basierte Implementierung eines Instanzspeichers. Diese ermöglicht einer Instanz das Speichern und Laden von Zuständen in eine bzw. aus einer SQL Server- oder SQL Server Express-Datenbank. Die Speichererweiterbarkeitsfunktion ermöglicht es Benutzern, Eigenschaften zu definieren, die im Instanzspeicher gespeichert werden. Diese Eigenschaften werden in einer höher gestuften Eigenschaftenansicht angezeigt, die es Benutzern ermöglicht, sie abzufragen.  
  
 Dieses Beispiel besteht aus einem Workflow, der einen Zähldienst implementiert. Wenn die Startmethode des Diensts aufgerufen wird, zählt der Dienst von 0 bis 29. Der Zählerwert wird alle zwei Sekunden erhöht. Der Workflow wird nach jeder Erhöhung des Zählerwerts gespeichert. Der aktuelle Zählerwert wird im Instanzspeicher als höher gestufte Eigenschaft gespeichert.  
  
 Der Zählworkflow wird von einem Workflowdiensthost gehostet. Die `Main`-Methode des Programms führt die folgenden Aktionen aus:  
  
-   Erstellt eine Instanz des Workflowdiensthosts, der den Zählworkflow hostet und die Endpunkte definiert, an denen der Zählworkflow erreicht werden kann.  
  
-   Definiert das Verhalten des SQL-Workflowinstanzspeichers zur Konfiguration des SQL-Workflowinstanzspeichers. Der Speicher wird angewiesen, `CountStatus` als höher gestufte Eigenschaft zu behandeln.  
  
-   Erstellt einen Client, der die Startmethode des Zählworkflows aufruft.  
  
 Der Zählvorgang wird bei Programmstart automatisch gestartet. Beachten Sie, dass das Laden der Instanz und die Konfiguration des SQL-Workflowinstanzspeichers einige Sekunden dauern kann.  
  
 Um den Zählerwert als benutzerdefinierte Eigenschaft höher zu stufen, müssen die folgenden Schritte ausgeführt werden:  
  
1.  Die `CounterStatus`-Klasse definiert eine Instanzerweiterung mit dem Typ <xref:System.Activities.Persistence.PersistenceParticipant>, der von Aktivitäten verwendet wird, um die Zustandsvariablen bereitzustellen. `Count` wird als lesegeschützter Wert definiert. Wenn eine Workflowinstanz einen Persistenzpunkt erreicht, speichert die Instanzerweiterung die `Count`-Eigenschaft in die Persistenzdatensammlung.  
  
2.  Beim Erstellen des Instanzspeichers wird eine neue Eigenschaft, `CountStatus`, durch die `store.Promote()`-Methode definiert.  
  
3.  Die `SaveCounter`-Aktivität des Workflows weist den aktuellen Zählerwert dem `Count`-Statusfeld zu.  
  
### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Erstellen Sie die Instanzspeicherdatenbank.  
  
    1.  Öffnen Sie eine [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Eingabeaufforderung.  
  
    2.  Navigieren Sie zum Beispielverzeichnis ("\WF\Basic\Persistence\SqlStoreExtensibility\CS"), und führen Sie "CreateInstanceStore.cmd" an der [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Eingabeaufforderung aus.  
  
        > [!WARNING]
        >  Das Skript "CreateInstanceStore.cmd" versucht, die Datenbank auf der Standardinstanz von SQL Server 2008 Express zu erstellen. Wenn Sie die Datenbank auf einer anderen Instanz installieren möchten, ändern Sie hierfür das Skript.  
  
2.  Öffnen Sie [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], laden Sie die Projektmappe "SqlStoreExtensibility.sln", und erstellen Sie sie, indem Sie STRG+UMSCHALT+B drücken.  
  
    > [!WARNING]
    >  Wenn Sie die Datenbank auf einer nicht standardmäßigen Instanz von SQL Server installiert haben, aktualisieren Sie vor dem Erstellen der Projektmappe die Verbindungszeichenfolge im Code.  
  
3.  Führen Sie das Beispiel mit Administratorrechten empfängerrollenbildschirm Bin-Verzeichnis des Projekts (\WF\Basic\Persistence\SqlStoreExtensibility\bin\Debug) im [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], mit der rechten Maustaste SqlStoreExtensibility.exe und Auswählen von **Ausführen als Administrator**.  
  
### <a name="to-verify-the-sample-is-working-correctly"></a>So überprüfen Sie die ordnungsgemäße Funktionsfähigkeit des Beispiels  
  
1.  Verwenden Sie SQL Server Management Studio, um den Inhalt der instanztabelle dazu anzeigen **Datenbanken**, **InstanceStore**, und klicken Sie dann  **System.ServiceModel.Activities.DurableInstancing.InstanceTable** im Objekt-Explorer mit der Maustaste **System.ServiceModel.Activities.DurableInstancing.InstanceTable** , und wählen Sie  **Wählen Sie die ersten 1000 Zeilen**. Weitere Informationen zu SQL Server Management Studio, finden Sie unter [Einführung in SQL Server Management Studio](https://go.microsoft.com/fwlink/?LinkId=165645)  
  
2.  Achten Sie auf die aufgeführten Workflowinstanzen.  
  
3.  Führen Sie an einer [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Eingabeaufforderung das Skript "QueryInstanceStore.cmd" aus, das sich im Beispielverzeichnis ("\WF\Basic\Persistence\SqlStoreExtensibility") befindet.  
  
4.  Beobachten der Wert dieses Indikators angezeigt **CountStatus**.  
  
5.  Führen Sie das Skript einige Male, finden Sie unter den **CountStats** -Wert ändert.  
  
6.  Drücken Sie die EINGABETASTE, um die Workflowanwendung zu beenden.  
  
### <a name="to-uninstall-the-sample"></a>So installieren Sie das Beispiel aus  
  
1.  Entfernen Sie die Instanzspeicherdatenbank, indem Sie das Skript "RemoveInstanceStore.cmd" ausführen, das sich im Beispielverzeichnis ("\WF\Basic\Persistence\SqlStoreExtensibility") befindet.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\SQLStoreExtensibility`  
  
## <a name="see-also"></a>Siehe auch  
 [Workflowpersistenz](../../../../docs/framework/windows-workflow-foundation/workflow-persistence.md)  
 [Workflowdienste](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [AppFabric-Hosting- und-persistenzbeispiele](https://go.microsoft.com/fwlink/?LinkId=193961)
