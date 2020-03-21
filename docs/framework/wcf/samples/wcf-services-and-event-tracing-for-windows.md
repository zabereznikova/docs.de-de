---
title: WCF-Dienste und Ereignisablaufverfolgung für Windows
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: b8a1f30f20aa2c541a574a070b3644569d633ca2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183210"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a>WCF-Dienste und Ereignisablaufverfolgung für Windows
In diesem Beispiel wird veranschaulicht, wie die Analyseablaufverfolgung in Windows Communication Foundation (WCF) zum Aussenden von Ereignissen in Der Ereignisablaufverfolgung für Windows (ETW) verwendet wird. Die Analyseablaufverfolgungen sind Ereignisse, die an wichtigen Punkten im WCF-Stack emittiert werden und die Fehlerbehebung von WCF-Diensten in der Produktionsumgebung ermöglichen.

 Die Analyseablaufverfolgung in WCF-Diensten ist eine Ablaufverfolgung, die in einer Produktionsumgebung mit minimalen Auswirkungen auf die Leistung aktiviert werden kann. Diese Ablaufverfolgungen werden als Ereignisse zu einer ETW-Sitzung ausgegeben.

 Dieses Beispiel enthält einen grundlegenden WCF-Dienst, bei dem Ereignisse vom Dienst an das Ereignisprotokoll gesendet werden, die mit der Ereignisanzeige angezeigt werden können. Es ist auch möglich, eine dedizierte ETW-Sitzung zu starten, die auf Ereignisse aus dem WCF-Dienst lauscht. Das Beispiel enthält ein Skript zum Erstellen einer dedizierten ETW-Sitzung, in der Ereignisse in einer Binärdatei gespeichert werden, die mithilfe der Ereignisanzeige gelesen werden kann.

#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel

1. Öffnen Sie mit Visual Studio 2012 die Projektmappendatei EtwAnalyticTraceSample.sln.

2. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.

3. Drücken Sie STRG+F5, um die Projektmappe auszuführen.

     Klicken Sie im Webbrowser auf **Calculator.svc**. Der URI des WSDL-Dokuments für den Dienst wird daraufhin im Browser angezeigt. Kopieren Sie diesen URI.

     Standardmäßig beginnt der Dienst mit dem Abhören `http://localhost:1378/Calculator.svc`von Anforderungen an Port 1378 .

4. Führen Sie den WCF-Testclient (WcfTestClient.exe) aus.

     Der WCF-Testclient (WcfTestClient.exe) `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`befindet sich unter .  Die Standardmäßige Visual Studio 2012-Installation von dir ist `C:\Program Files\Microsoft Visual Studio 10.0`.

5. Fügen Sie den Dienst innerhalb des WCF-Testclients hinzu, indem Sie **Datei**auswählen und dann **Dienst hinzufügen**.

     Fügen Sie die Endpunktadresse im Eingabefeld hinzu. Der Standardwert lautet `http://localhost:1378/Calculator.svc`.

6. Öffnen Sie die Ereignisanzeige.

     Starten Sie vor dem Aufrufen des Dienstes die Ereignisanzeige, und stellen Sie sicher, dass das Ereignisprotokoll auf die Nachverfolgung von Ereignissen lauscht, die vom WCF-Dienst gesendet wurden.

7. Wählen Sie im **Startmenü** **Administrative Tools**aus, und dann **die Ereignisanzeige**.  Aktivieren Sie die **Analyse-** und **Debugprotokolle.**

8. Navigieren Sie in der Strukturansicht in der Ereignisanzeige zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**und dann **Application Server-Applications**. Klicken Sie mit der rechten Maustaste auf **Application Server-Applications**, wählen Sie **Ansicht**aus, und zeigen Sie dann **Analyse- und Debugprotokolle an.**

     Stellen Sie sicher, dass die Option **Analyse- und Debugprotokolle** anzeigen aktiviert ist.

9. Aktivieren Sie das **Analyseprotokoll.**

     Navigieren Sie in der Strukturansicht in der Ereignisanzeige zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**und dann **Application Server-Applications**. Klicken Sie mit der rechten Maustaste auf **Analytic,** und wählen Sie **Protokoll aktivieren**aus.

#### <a name="to-test-the-service"></a>So testen Sie den Dienst

1. Wechseln Sie zurück zum WCF-Testclient, und doppelklicken sie auf `Divide` die Standardwerte, die einen Nenner von 0 angeben.

     Wenn der Nenner 0 ist, löst der Dienst einen Fehler aus.

2. Beachten Sie die vom Dienst ausgegebenen Ereignisse.

     Wechseln Sie zurück zur Ereignisanzeige, und navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**und dann **Application Server-Applications**. Klicken Sie mit der rechten Maustaste auf **Analytic,** und wählen Sie **Aktualisieren**aus.

     Die analytischen Ablaufverfolgungsereignisse in WCF werden in der Ereignisanzeige angezeigt. Beachten Sie, dass ein Fehler als Ablaufverfolgungsereignis in der Ereignisanzeige angezeigt wird, da ein Fehler vom Dienst ausgelöst wurde.

3. Wiederholen Sie Schritt 1 und 2 mit gültigen Eingaben. Der Wert des `N2`-Parameters kann eine beliebige Zahl außer 0 sein.

     Aktualisieren Sie den analytischen Kanal, um die WCF-Ereignisse anzuzeigen, wobei keine Fehlerereignisse vorhanden sind.

 Im Beispiel werden die von einem WCF-Dienst ausgegebenen analytischen Ablaufverfolgungsereignisse veranschaulicht.

#### <a name="to-cleanup-optional"></a>So führen Sie eine (optionale) Bereinigung durch

1. Öffnen Sie die Ereignisanzeige.

2. Navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**und dann **Application-Server-Applications**. Klicken Sie mit der rechten Maustaste auf **Analytic,** und wählen Sie **Protokoll deaktivieren**aus.

3. Navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**und dann **Application-Server-Applications**. Klicken Sie mit der rechten Maustaste auf **Analytic,** und wählen Sie **Protokoll löschen**aus.

4. Wählen Sie die Option **Löschen** aus, um die Ereignisse zu löschen.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a>Weitere Informationen

- [AppFabric-Überwachungsbeispiele](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
