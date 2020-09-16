---
title: WCF-Dienste und Ereignisablaufverfolgung für Windows
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: 38e26c369d17f4aa9ccb39d2ae649facffe65418
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552965"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a>WCF-Dienste und Ereignisablaufverfolgung für Windows
In diesem Beispiel wird veranschaulicht, wie die analytische Ablauf Verfolgung in Windows Communication Foundation (WCF) verwendet wird, um Ereignisse in der Ereignis Ablauf Verfolgung für Windows (ETW) auszugeben. Die analytischen Ablauf Verfolgungen sind Ereignisse, die an wichtigen Punkten im WCF-Stapel ausgegeben werden und die Problembehandlung von WCF-Diensten in der Produktionsumgebung ermöglichen.

 Die analytische Ablauf Verfolgung in WCF-Diensten ist die Ablauf Verfolgung, die in einer Produktionsumgebung mit minimalen Auswirkungen auf die Leistung aktiviert werden kann. Diese Ablaufverfolgungen werden als Ereignisse zu einer ETW-Sitzung ausgegeben.

 Dieses Beispiel enthält einen einfachen WCF-Dienst, in dem Ereignisse vom Dienst an das Ereignisprotokoll ausgegeben werden, das mithilfe von Ereignisanzeige angezeigt werden kann. Es ist auch möglich, eine dedizierte ETW-Sitzung zu starten, die auf Ereignisse vom WCF-Dienst lauscht. Das Beispiel enthält ein Skript zum Erstellen einer dedizierten ETW-Sitzung, in der Ereignisse in einer Binärdatei gespeichert werden, die mithilfe der Ereignisanzeige gelesen werden kann.

#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel

1. Öffnen Sie mit Visual Studio 2012 die Projektmappendatei "EtwAnalyticTraceSample. sln".

2. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.

3. Drücken Sie STRG+F5, um die Projektmappe auszuführen.

     Klicken Sie im Webbrowser auf **Calculator. svc**. Der URI des WSDL-Dokuments für den Dienst wird daraufhin im Browser angezeigt. Kopieren Sie diesen URI.

     Standardmäßig beginnt der Dienst mit dem lauschen auf Anforderungen an Port 1378 `http://localhost:1378/Calculator.svc` .

4. Führen Sie den WCF-Test Client (WcfTestClient.exe) aus.

     Der WCF-Test Client (WcfTestClient.exe) befindet sich unter `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe` .  Der Standard Installationsverzeichnis von Visual Studio 2012 lautet `C:\Program Files\Microsoft Visual Studio 10.0` .

5. Fügen Sie im WCF-Test Client den Dienst hinzu, indem Sie auf **Datei**und dann auf **Dienst hinzufügen**klicken.

     Fügen Sie die Endpunktadresse im Eingabefeld hinzu. Der Standardwert ist `http://localhost:1378/Calculator.svc`.

6. Öffnen Sie die Ereignisanzeige.

     Bevor Sie den Dienst aufrufen, starten Sie Ereignisanzeige, und stellen Sie sicher, dass das Ereignisprotokoll nach Verfolgungs Ereignissen lauscht, die vom WCF-Dienst ausgegeben werden.

7. Klicken Sie im **Startmenü** auf **Verwaltung**, und klicken Sie dann auf **Ereignisanzeige**.  Aktivieren Sie die **analytischen** und **Debugprotokolle** .

8. Navigieren Sie in der Strukturansicht in Ereignisanzeige zu **Ereignisanzeige**, Anwendungs **-und Dienst Protokolle**, **Microsoft**, **Windows**und dann zu **Anwendungs Server-Anwendungen**. Klicken Sie mit der rechten Maustaste auf **Anwendungs Server-Anwendungen**, wählen Sie **Ansicht**und dann **analytische und Debugprotokolle anzeigen**aus.

     Stellen Sie sicher, dass die Option **analytische und Debugprotokolle anzeigen** aktiviert ist.

9. Aktivieren Sie das **analytische** Protokoll.

     Navigieren Sie in der Strukturansicht in Ereignisanzeige zu **Ereignisanzeige**, Anwendungs **-und Dienst Protokolle**, **Microsoft**, **Windows**und dann zu **Anwendungs Server-Anwendungen**. Klicken Sie mit der rechten Maustaste auf **Analyse** , und wählen Sie **Protokoll aktivieren**

#### <a name="to-test-the-service"></a>So testen Sie den Dienst

1. Wechseln Sie zurück zum WCF-Test Client, und doppelklicken Sie auf `Divide` , und behalten Sie die Standardwerte bei, die einen Nenner von 0 angeben.

     Wenn der Nenner 0 ist, löst der Dienst einen Fehler aus.

2. Beachten Sie die vom Dienst ausgegebenen Ereignisse.

     Wechseln Sie zurück zu Ereignisanzeige, und navigieren Sie zu **Ereignisanzeige**, Anwendungs **-und Dienst Protokolle**, **Microsoft**, **Windows**und dann zu **Anwendungs Server-Anwendungen**. Klicken Sie mit der rechten Maustaste auf **Analyse** , **und wählen Sie**

     Die analytischen Ablaufverfolgungsereignisse in WCF werden in der Ereignisanzeige angezeigt. Beachten Sie, dass ein Fehler als Ablaufverfolgungsereignis in der Ereignisanzeige angezeigt wird, da ein Fehler vom Dienst ausgelöst wurde.

3. Wiederholen Sie Schritt 1 und 2 mit gültigen Eingaben. Der Wert des `N2`-Parameters kann eine beliebige Zahl außer 0 sein.

     Aktualisieren Sie den analytischen Kanal, um die WCF-Ereignisse anzuzeigen, wobei keine Fehlerereignisse vorhanden sind.

 Im Beispiel werden die von einem WCF-Dienst ausgegebenen analytischen Ablaufverfolgungsereignisse veranschaulicht.

#### <a name="to-cleanup-optional"></a>So führen Sie eine (optionale) Bereinigung durch

1. Öffnen Sie die Ereignisanzeige.

2. Navigieren Sie zu **Ereignisanzeige**, Anwendungs- **und Dienst Protokolle**, **Microsoft**, **Windows**und dann zu **Anwendungs Server-Anwendungen**. Klicken Sie mit der rechten Maustaste auf **Analyse** , und wählen Sie **Protokoll deaktivieren**

3. Navigieren Sie zu **Ereignisanzeige**, Anwendungs- **und Dienst Protokolle**, **Microsoft**, **Windows**und dann zu **Anwendungs Server-Anwendungen**. Klicken Sie mit der rechten Maustaste auf **Analyse** , und wählen Sie **Protokoll löschen**

4. Wählen Sie die Option **Clear** aus, um die Ereignisse zu löschen.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a>Siehe auch

- [AppFabric-Überwachungsbeispiele](/previous-versions/appfabric/ff383407(v=azure.10))
