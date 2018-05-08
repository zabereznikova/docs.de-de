---
title: Extrahieren von WF-Daten mithilfe der Nachverfolgung
ms.date: 03/30/2017
ms.assetid: e30c68f5-8c6a-495a-bd20-667a4364c68e
ms.openlocfilehash: 22b147521d4ce0c72fadfb7adc81e05f10ce52b1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="extract-wf-data-using-tracking"></a>Extrahieren von WF-Daten mithilfe der Nachverfolgung
In diesem Beispiel wird veranschaulicht, wie die Workflownachverfolgung verwendet wird, um Workflowvariablen und Argumente aus Aktivitäten zu extrahieren. Außerdem wird auch das Hinzufügen von Bemerkungen zu Überwachungsdatensätzen sowie das Extrahieren der Datennutzlast innerhalb von benutzerdefinierten Überwachungsdatensätzen dargestellt. Im Beispiel wird der ETW-Überwachungsteilnehmer (Ereignisablaufverfolgung für Windows) zum Extrahieren von Daten aus dem Workflow verwendet.  
  
## <a name="sample-details"></a>Beispieldetails  
 Windows Workflow Foundation (WF) ermöglicht die nachverfolgung, um einen Einblick in die Ausführung einer Workflowinstanz zu erhalten. Die Überwachungslaufzeit gibt während der Ausführung des Workflows Workflowüberwachungsdatensätze aus. Zusammen mit den Workflowüberwachungsdatensätzen können Daten innerhalb der Workflowinstanz aus dem Workflow extrahiert werden. In der folgenden Liste sind die Typen von Daten aufgeführt, die aus Überwachungsdatensätzen extrahiert werden können:  
  
1.  Workflowvariablen in einer Aktivität und Überwachungsdatensätze während der Aktivitätsausführung.  
  
     Um Workflowvariablen zu extrahieren, werden die zu extrahierenden Variablen in einem Profil angegeben. Zu extrahierende Variablen können nur mit `ActivityStateQueries` angegeben werden. Im folgenden Codebeispiel ist ein Überwachungsprofil dargestellt, das zum Extrahieren der Workflowvariablen aus einer Aktivität verwendet wird.  
  
    ```xml  
    <activityStateQuery activityName="StockPriceService">  
         <states>  
              <state name="Closed"/>  
         </states>  
         <variables>  
              <variable name="symbol"/>  
         </variables>  
    </activityStateQuery>  
    ```  
  
2.  Aktivitätsargumente und Aktivitätszustands-Überwachungsdatensätze.  
  
     Argumente definieren die Richtung, in der Daten in oder aus einer Aktivität fließen. Zu extrahierende Argumente werden mit einer <xref:System.Activities.Tracking.ActivityStateQuery> angegeben. Im folgenden Codebeispiel ist ein Überwachungsprofil dargestellt, das das `Value`-Argument extrahiert.  
  
    ```xml  
    <activityStateQuery activityName="GetStockPrice">  
         <states>  
              <state name="Closed"/>  
         </states>  
         <arguments>  
              <argument name="Value"/>  
         </arguments>  
    </activityStateQuery>  
    ```  
  
3.  Anmerkungen sind Schlüssel-Wert-Paare, die einem beliebigen Überwachungsdatensatz hinzugefügt werden können, der ausgegeben wird.  
  
     Anmerkungen dienen der Markierung von Überwachungsdatensätzen. Sie verwenden Überwachungsdatensätzen über ein Überwachungsprofil hinzugefügt. Anmerkungen können einem beliebigen Typ einer Workflowüberwachungsabfrage hinzugefügt werden. Im folgenden Codebeispiel ist ein Nachverfolgungsprofil dargestellt, das zeigt, wie einem Überwachungsdatensatz eine Anmerkung hinzugefügt werden kann.  
  
    ```xml  
    <workflowInstanceQuery>  
         <states>  
              <state name="Started"/>  
         </states>  
         <annotations>  
              <annotation name="StockPriceWorkflow" value="Begin"/>  
         </annotations>  
    </workflowInstanceQuery>  
    ```  
  
4.  Benutzerdefinierte Überwachungsdatensätze werden von benutzerdefinierten Aktivitäten ausgegeben.  
  
     Benutzerdefinierte Überwachungsdatensätze können innerhalb dieser Aktivität definierte Nutzlastdaten tragen. Durch Abonnieren von benutzerdefinierten Überwachungsdatensätzen in einem Überwachungsprofil wird das Extrahieren der Nutzlast innerhalb des Überwachungsdatensatzes ermöglicht. Die benutzerdefinierten Überwachungsdatensätze können mit einer benutzerdefinierten <xref:System.Activities.Tracking.TrackingQuery> extrahiert werden. Im folgenden Codebeispiel ist ein Überwachungsprofil dargestellt, das einen benutzerdefinierten Überwachungsdatensatz zusammen mit seiner Nutzlast extrahiert.  
  
    ```xml  
    <customTrackingQuery name="QuoteLookupEvent" activityName="GetStockPrice"/>  
    ```  
  
 In dem Beispiel wird das Extrahieren von Variablen, Argumenten, benutzerdefinierten Datensätzen und das Hinzufügen von Anmerkungen mithilfe eines in "Web.config" angegebenen Profils veranschaulicht. Die Nachverfolgung wird in dem Beispielworkflowdienst durch Hinzufügen eines `<etwTracking>`-Verhaltenselements ermöglicht. Im folgenden Codebeispiel wird die Verfolgung für das `ExtractWorkflowVariables`-Nachverfolgungsprofil aktiviert.  
  
```xml  
<serviceBehaviors>  
     <behavior>  
               <etwTracking profileName="ExtractWorkflowVariables"/>  
     </behavior>  
</serviceBehaviors>  
```  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "WFStockPriceApplication.sln".  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie F5, um die Projektmappe auszuführen.  
  
     Das Browserfenster wird geöffnet und zeigt die Verzeichnisliste für die Anwendung an.  
  
4.  Klicken Sie im Browser auf "StockPriceService.xamlx".  
  
5.  Der Browser zeigt die Seite "StockPriceService" an, die die WSDL-Adresse des lokalen Diensts enthält. Kopieren Sie diese Adresse.  
  
     Das folgende Beispiel zeigt eine WSDL-Adresse des lokalen Diensts. `http://localhost:53797/StockPriceService.xamlx?wsdl`  
  
6.  Starten Sie vor dem Aufrufen des Diensts die Ereignisanzeige, und stellen Sie sicher, dass das Ereignisprotokoll eine Überwachung für vom Workflowdienst ausgegebene Überwachungsereignisse ausführt.  
  
7.  Aus der **starten** klicken Sie im Menü **Verwaltung** und dann **Ereignisanzeige**.  
  
8.  Wechseln Sie in der Strukturansicht in der Ereignisanzeige zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, und **Microsoft**. Mit der rechten Maustaste **Microsoft** , und wählen Sie **Ansicht** und dann **anzeigen analytische und Debugprotokolle**.  
  
     Sicherstellen, dass die **anzeigen analytische und Debugprotokolle** Option aktiviert ist.  
  
9. Wechseln Sie in der Strukturansicht in der Ereignisanzeige zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**,  **Anwendungsserver-Anwendungen**. Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll aktivieren**.  
  
10. Öffnen Sie den WCF-Testclient mit [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)].  
  
     WCF-Testclient (WcfTestClient.exe) befindet sich der \< [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] -Installationsordner > \Common7\IDE\-Ordner.  
  
     Der standardmäßige [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Installationsordner ist "C:\Programme\Microsoft-Visual Studio 10.0".  
  
11. Wählen Sie im WCF-Testclient **Dienst hinzufügen** aus der **Datei** Menü.  
  
     Fügen Sie die WSDL-Adresse des lokalen Diensts, die Sie zuvor kopiert haben, in das Eingabefeld ein.  
  
12. Doppelklicken Sie im WCF-Testclient auf `GetStockPrice`.  
  
     Dadurch wird die `GetStockPrice`-Methode geöffnet. Die Anforderung akzeptiert einen Parameter. Verwenden Sie den Wert **Contoso**.  
  
13. Klicken Sie auf **Aufrufen**.  
  
14. Wechseln Sie zurück zur Ereignisanzeige, und navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**,  **Anwendungsserver-Anwendungen**. Mit der rechten Maustaste **analytisch** , und wählen Sie **aktualisieren**. Die Workflowereignisse befinden sich im Ereignis-ID-Bereich 100-199.  
  
     Die Ereignisse enthalten die Anmerkungen, Variablen, Argumente und benutzerdefinierten Überwachungsdatensätze, die in der Ereignisanzeige angezeigt werden können.  
  
## <a name="cleaning-up-in-the-event-viewer"></a>Bereinigen in der Ereignisanzeige  
 Der analytische Channel im Ereignisprotokoll kann in der Ereignisanzeige folgendermaßen bereinigt werden.  
  
#### <a name="to-clean-up-optional"></a>So führen Sie eine Bereinigung aus (optional)  
  
1.  Öffnen Sie die Ereignisanzeige.  
  
2.  Navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, **Anwendung Server-Applications**. Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll deaktivieren**.  
  
3.  Navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, **Anwendung Server-Applications**. Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll löschen**.  
  
     Wählen Sie die **deaktivieren** Option aus, um die Ereignisse zu löschen.  
  
## <a name="known-issue"></a>Bekanntes Problem  
  
> [!NOTE]
>  Es gibt ein bekanntes Problem in der Ereignisanzeige, bei dem bei der Decodierung von ETW-Ereignissen ein Fehler auftritt. Möglicherweise wird eine Fehlermeldung ähnlich der Folgenden angezeigt.  
>   
>  `The description for Event ID <id> from source Microsoft-Windows-Application Server-Applications cannot be found. Either the component that raises this event is not installed on your local computer or the installation is corrupted. You can install or repair the component on the local computer.`  
>   
>  Wenn dieser Fehler auftritt, klicken Sie auf **aktualisieren** klicken Sie im Bereich "Aktionen". Das Ereignis sollte jetzt ordnungsgemäß decodiert werden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\ExtractWfData`  
  
## <a name="see-also"></a>Siehe auch  
 [Überwachen der AppFabric-Beispiele](http://go.microsoft.com/fwlink/?LinkId=193959)
