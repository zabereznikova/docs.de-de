---
title: Permanente Verzögerung in XAMLX
ms.date: 03/30/2017
ms.assetid: efc38df4-2d34-453c-8e59-2c21d1307354
ms.openlocfilehash: 1eef9211c67d190ecb5f329c481fa2e3d1763353
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43873928"
---
# <a name="durable-delay-in-xamlx"></a>Permanente Verzögerung in XAMLX
In diesem Beispiel wird veranschaulicht, wie eine permanente Verzögerung verwendet wird, eine Verzögerung, die den Workflow während der Verzögerung auf einem permanenten Gerät beibehält.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlx`  
  
## <a name="discussion"></a>Diskussion  
 Der Beispielworkflow enthält zwei Meldungen zu einer lokalen Datei, die durch eine Verzögerung getrennt sind. Wenn die Verzögerung ausgelöst wird, wird der Workflow entladen und verbleibt 5 Sekunden im Workflowinstanzspeicher, bevor er erneut in den Speicher geladen wird.  
  
 Die xamlx-Datei ist ein Workflowdienst, der in Visual Studio gehostet wird. Visual Studio verwendet Cassini, das einen Workflowdienst zum Hosten verwendet den Workflow.  
  
 Neben dem Hosten des Workflows verwaltet der Workflowdiensthost die Workflowinstanzen durch Laden und Entladen. Um eine Instanz der Windows Workflow Foundation (WF)-Definition (auf dem Workflowdiensthost) zu beginnen, legen Sie einen Client, der eine Nachricht, sendet der <xref:System.ServiceModel.Activities.Receive> Aktivität im Workflow. Die <xref:System.ServiceModel.Activities.Receive>-Eigenschaft von <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> ist auf `true` festgelegt, sodass eine neue Instanz des Workflows erstellt werden kann, sobald eine Nachricht empfangen wird.  
  
 Während der Initialisierung wird der Konfigurationsdatei, die den Workflowdiensthost angibt, unter dem eine Instanz in den Persistenzspeicher (Datenbank) entladen werden soll, ein Verhalten zum Entladen von Instanzen hinzugefügt. Für dieses Beispiel wird die Instanz entladen, unmittelbar nachdem der Workflow in den Leerlauf eintritt (wenn die Verzögerung ausgelöst wird).  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie eine [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Eingabeaufforderung.  
  
2.  Navigieren Sie zum Ordner "DurableDelayXamlx\CS".  
  
3.  Führen Sie Setup.cmd aus.  
  
4.  Führen Sie [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] als Administrator aus.  
  
5.  Öffnen Sie die Projektmappendatei "DurableDelayXamlx.sln".  
  
6.  In **Projektmappen-Explorer**mit der rechten Maustaste auf die Projektmappe, und wählen Sie **Eigenschaften**.  
  
7.  Wählen Sie **mehrere Startprojekte** , und legen Sie beide Projekte auf **starten**.  
  
8.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
9. Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
#### <a name="to-uninstall-this-sample"></a>So deinstallieren Sie das Beispiel  
  
1.  Öffnen Sie eine [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Eingabeaufforderung.  
  
2.  Navigieren Sie zum Ordner "DurableDelayXamlx\CS".  
  
3.  Führen Sie die Datei "Cleanup.cmd" aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlX`
