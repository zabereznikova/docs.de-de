---
title: Permanente Verzögerung
ms.date: 03/30/2017
ms.assetid: 220ec240-b958-430c-81ff-b734a6aa97ae
ms.openlocfilehash: 2a7692e28d60232913ae5d11a90025e59664c0e5
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507632"
---
# <a name="durable-delay"></a>Permanente Verzögerung
In diesem Beispiel wird veranschaulicht, wie eine permanente Verzögerung verwendet wird, eine Verzögerung, die den Workflow während der Verzögerung auf einem permanenten Gerät beibehält. Der Beispielworkflow enthält zwei Meldungen an die Konsole, die durch eine Verzögerung getrennt sind. Wenn die Verzögerung ausgelöst wird, wird der Workflow entladen und verbleibt 5 Sekunden im Workflowinstanzspeicher, bevor er erneut in den Speicher geladen wird.  
  
## <a name="workflow-details"></a>Workflowdetails  
 Der Workflowdiensthost hostet den Workflow und verwaltet die Workflowinstanzen durch Laden und Entladen. Zum Starten einer Instanz der Workflowdefinition wird im Beispiel ein Proxy festgelegt, der eine Meldung an die <xref:System.ServiceModel.Activities.Receive>-Aktivität im Workflow sendet. Die <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A>-Eigenschaft wird auf `true` festgelegt, sodass eine neue Instanz des Workflows erstellt werden kann, sobald eine Meldung empfangen wird.  
  
 Die folgende Liste enthält das Setup des Workflowdiensthosts während der Initialisierung.  
  
1.  Erstellt einen Diensthost mit einer Adresse (http://localhost:8080/Client).  
  
2.  Erstellt einen Endpunkt im Diensthost, um Kommunikation mit der <xref:System.ServiceModel.Activities.Receive>-Aktivität im Workflow zu aktivieren.  
  
3.  Richtet einen SQL-Instanzspeicher ein.  
  
4.  Fügt ein Verhalten zum Entladen von Instanzen hinzu, das die Bedingungen angibt, unter denen der Workflowdiensthost eine Workflowinstanz in den SQL-Persistenzspeicher entladen soll. Für dieses Beispiel wird die Instanz entladen, unmittelbar nachdem der Workflow in den Leerlauf eintritt (wenn die Verzögerung ausgelöst wird).  
  
5.  Erstellt den Proxy, der eine Meldung an die <xref:System.ServiceModel.Activities.Receive>-Aktivität im Workflow sendet.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Richten Sie die Persistenzdatenbank ein.  
  
    1.  Öffnen Sie eine [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Eingabeaufforderung.  
  
    2.  Navigieren Sie zu der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Verzeichnis (C:\Windows\Microsoft.NET\Framework\v4. X\\).  
  
    3.  Bearbeiten Sie die Datei "WorkflowManagementService.exe.config", und fügen Sie die folgende Verbindungszeichenfolge im <`database`>-Element hinzu.  
  
        ```xml  
        <database connectionString="Data Source=localhost\SQLEXPRESS;Initial Catalog=DefaultSampleStore;Integrated Security=True;Asynchronous Processing=True" />  
        ```  
  
    4.  Navigieren Sie zum Verzeichnis DurableDelay\CS.  
  
    5.  Führen Sie Setup.cmd aus.  
  
2.  Führen Sie [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] mithilfe erhöhter Berechtigungen mit der rechten Maustaste die [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] und wählen Sie dann **als Administrator ausführen**.  
  
3.  Öffnen Sie die Projektmappendatei "Delay.sln".  
  
4.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
5.  Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
#### <a name="to-uninstall-this-sample"></a>So deinstallieren Sie das Beispiel  
  
1.  Öffnen Sie eine [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Eingabeaufforderung.  
  
2.  Navigieren Sie zum Verzeichnis DurableDelay\CS.  
  
3.  Führen Sie die Datei "Cleanup.cmd" aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelay`