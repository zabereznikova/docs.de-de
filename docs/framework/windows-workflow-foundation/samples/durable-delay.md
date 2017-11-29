---
title: "Permanente Verzögerung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 220ec240-b958-430c-81ff-b734a6aa97ae
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a7023d7548db99d511ae18ad4d52b9a8168c4243
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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
  
2.  Führen Sie [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] mit erhöhten Berechtigungen, indem Sie mit der rechten Maustaste die [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] und wählen Sie dann **als Administrator ausführen**.  
  
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
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelay`  
  
## <a name="see-also"></a>Siehe auch
