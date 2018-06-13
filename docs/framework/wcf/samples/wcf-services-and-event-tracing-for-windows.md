---
title: WCF-Dienste und Ereignisablaufverfolgung für Windows
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: ea917ee87b598fc3ad01df70d9aedfadfd1396a4
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809832"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a>WCF-Dienste und Ereignisablaufverfolgung für Windows
Dieses Beispiel veranschaulicht, wie die analytische Ablaufverfolgung in der Windows Communication Foundation (WCF) verwenden, um Ereignisse in Event Tracing for Windows (ETW) auszugeben. Die analytische Ablaufverfolgung werden Ereignisse, die an Schlüsselpunkten im WCF-Stapel, die es ermöglichen, zur Problembehandlung von WCF-Diensten in produktionsumgebung ausgegeben.  
  
 Analytische Ablaufverfolgung in WCF-Diensten ist, die die Ablaufverfolgung aktiviert werden kann in einer produktiven Umgebung mit minimaler Auswirkung auf die Leistung. Diese Ablaufverfolgungen werden als Ereignisse zu einer ETW-Sitzung ausgegeben.  
  
 Dieses Beispiel enthält einen grundlegenden WCF-Dienst in dem Ereignisse aus dem Dienst in das Ereignisprotokoll ausgegeben werden mithilfe der Ereignisanzeige angezeigt werden können. Es ist auch möglich, eine dedizierte ETW-Sitzung zu starten, die für Ereignisse aus den WCF-Dienst überwacht. Das Beispiel enthält ein Skript zum Erstellen einer dedizierten ETW-Sitzung, in der Ereignisse in einer Binärdatei gespeichert werden, die mithilfe der Ereignisanzeige gelesen werden kann.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] die EtwAnalyticTraceSample.sln-Projektmappendatei.  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
     Klicken Sie in den Webbrowser auf **Calculator.svc**. Der URI des WSDL-Dokuments für den Dienst wird daraufhin im Browser angezeigt. Kopieren Sie diesen URI.  
  
     Standardmäßig Dienststart lauscht Anforderungen auf Port 1378 (http://localhost:1378/Calculator.svc).  
  
4.  Führen Sie den WCF-Testclient (WcfTestClient.exe).  
  
     WCF-Testclient (WcfTestClient.exe) befindet sich der \< [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] -Installationsverzeichnis > \Common7\IDE\ WcfTestClient.exe (Standardeinstellung [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Installationsverzeichnis ist C:\Program Files\Microsoft Visual Studio 10.0).  
  
5.  Fügen Sie innerhalb der WCF-Testclient den Dienst, indem Sie auswählen **Datei**, und klicken Sie dann **Dienst hinzufügen**.  
  
     Fügen Sie die Endpunktadresse im Eingabefeld hinzu. Die Standardeinstellung ist http://localhost:1378/Calculator.svc.  
  
6.  Öffnen Sie die Ereignisanzeige.  
  
     Vor dem Aufrufen des Diensts die Ereignisanzeige starten, und stellen Sie sicher, dass das Ereignisprotokoll eine Überwachung für vom WCF-Dienst ausgegebene Überwachungsereignisse ausführt.  
  
7.  Aus der **starten** klicken Sie im Menü **Verwaltung**, und klicken Sie dann **Ereignisanzeige**.  Aktivieren der **analytisch** und **Debuggen** Protokolle.  
  
8.  Wechseln Sie in der Strukturansicht in der Ereignisanzeige zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, und klicken Sie dann **Anwendungsserver-Anwendungen**. Mit der rechten Maustaste **Anwendungsserver-Anwendungen**Option **Ansicht**, und klicken Sie dann **anzeigen analytische und Debugprotokolle**.  
  
     Sicherstellen, dass die **anzeigen analytische und Debugprotokolle** Option aktiviert ist.  
  
9. Aktivieren der **analytisch** Protokoll.  
  
     Wechseln Sie in der Strukturansicht in der Ereignisanzeige zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, und klicken Sie dann **Anwendungsserver-Anwendungen**. Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll aktivieren**.  
  
#### <a name="to-test-the-service"></a>So testen Sie den Dienst  
  
1.  Wechseln Sie zurück zum WCF-Testclient, und doppelklicken Sie auf `Divide` und behalten Sie die Standardwerte, die als Nenner 0 angeben.  
  
     Wenn der Nenner 0 ist, löst der Dienst einen Fehler aus.  
  
2.  Beachten Sie die vom Dienst ausgegebenen Ereignisse.  
  
     Wechseln Sie zurück zur Ereignisanzeige, und navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, und klicken Sie dann **Anwendungsserver-Anwendungen**. Mit der rechten Maustaste **analytisch** , und wählen Sie **aktualisieren**.  
  
     Die analytischen Ablaufverfolgungsereignisse in WCF werden in der Ereignisanzeige angezeigt. Beachten Sie, dass ein Fehler als Ablaufverfolgungsereignis in der Ereignisanzeige angezeigt wird, da ein Fehler vom Dienst ausgelöst wurde.  
  
3.  Wiederholen Sie Schritt 1 und 2 mit gültigen Eingaben. Der Wert des `N2`-Parameters kann eine beliebige Zahl außer 0 sein.  
  
     Aktualisieren Sie den analytischen Kanal, um die WCF-Ereignisse anzuzeigen, wobei keine Fehlerereignisse vorhanden sind.  
  
 Im Beispiel werden die von einem WCF-Dienst ausgegebenen analytischen Ablaufverfolgungsereignisse veranschaulicht.  
  
#### <a name="to-cleanup-optional"></a>So führen Sie eine (optionale) Bereinigung durch  
  
1.  Öffnen Sie die Ereignisanzeige.  
  
2.  Navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, und klicken Sie dann  **Anwendungsserver-Anwendungen**. Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll deaktivieren**.  
  
3.  Navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, und klicken Sie dann  **Anwendungsserver-Anwendungen**. Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll löschen**.  
  
4.  Wählen Sie die **deaktivieren** Option aus, um die Ereignisse zu löschen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a>Siehe auch  
 [Überwachen der AppFabric-Beispiele](http://go.microsoft.com/fwlink/?LinkId=193959)
