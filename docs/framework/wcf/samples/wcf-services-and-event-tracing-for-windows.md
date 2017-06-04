---
title: "WCF-Dienste und Ereignisablaufverfolgung f&#252;r Windows | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# WCF-Dienste und Ereignisablaufverfolgung f&#252;r Windows
In diesem Beispiel wird gezeigt, wie die analytische Ablaufverfolgung von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] verwendet wird, um Ereignisse in der Ereignisablaufverfolgung für Windows \(ETW\) auszugeben.  Die analytische Ablaufverfolgung besteht aus Ereignissen, die an Schlüsselpunkten im [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Stapel ausgegeben werden und die Problembehandlung der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienste in der Produktionsumgebung zulassen.  
  
 Die analytische Ablaufverfolgung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ist eine Methode der Ablaufverfolgung, die in einer Produktionsumgebung mit minimalen Auswirkungen auf die Leistung aktiviert werden kann.  Diese Ablaufverfolgungen werden als Ereignisse zu einer ETW\-Sitzung ausgegeben.  
  
 Dieses Beispiel enthält einen grundlegenden [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst, in dem Ereignisse vom Dienst an das Ereignisprotokoll ausgegeben werden. Dieses kann mit der Ereignisanzeige angezeigt werden.  Es ist auch möglich, eine dedizierte ETW\-Sitzung zu starten, die Ereignisse des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensts überwacht.  Das Beispiel enthält ein Skript zum Erstellen einer dedizierten ETW\-Sitzung, in der Ereignisse in einer Binärdatei gespeichert werden, die mithilfe der Ereignisanzeige gelesen werden kann.  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] die EtwAnalyticTraceSample.sln\-Projektmappendatei.  
  
2.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG\+F5, um die Projektmappe auszuführen.  
  
     Klicken Sie im Webbrowser auf **Calculator.svc**.  Der URI des WSDL\-Dokuments für den Dienst wird daraufhin im Browser angezeigt.  Kopieren Sie diesen URI.  
  
     Standardmäßig beginnt der Dienst damit, Anforderungen auf Port 1378 \(http:\/\/localhost:1378\/Calculator .svc\) zu überwachen.  
  
4.  Führen Sie den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Testclient \(WcfTestClient.exe\) aus.  
  
     Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Testclient \(WcfTestClient.exe\) befindet sich unter "\<[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]\-Installationsverzeichnis\>\\Common7\\IDE\\ WcfTestClient.exe" \(das Standardinstallationsverzeichnis von [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] ist "C:\\Programme\\Microsoft Visual Studio 10.0"\).  
  
5.  Fügen Sie im [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Testclient den Dienst hinzu, indem Sie **Datei** und dann **Dienst hinzufügen** auswählen.  
  
     Fügen Sie die Endpunktadresse im Eingabefeld hinzu.  Die Standardadresse ist http:\/\/localhost:1378\/Calculator.svc.  
  
6.  Öffnen Sie die Ereignisanzeige.  
  
     Starten Sie vor dem Aufrufen des Diensts die Ereignisanzeige, und stellen Sie sicher, dass das Ereignisprotokoll eine Überwachung für von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ausgegebene Überwachungsereignisse ausführt.  
  
7.  Wählen Sie aus dem Menü **Start** die Option **Verwaltung** und dann **Ereignisanzeige** aus.  Aktivieren Sie die Protokolle **Analytisch** und **Debuggen**.  
  
8.  Navigieren Sie in der Strukturansicht der Ereignisanzeige zu **Ereignisanzeige**, **Anwendungs\- und Dienstprotokolle**, **Microsoft**, **Windows** und dann zu **Anwendungsserver\-Anwendungen**.  Klicken Sie mit der rechten Maustaste auf **Anwendungsserver\-Anwendungen**, und wählen Sie **Ansicht** und danach **Analytische und Debugprotokolle einblenden** aus.  
  
     Stellen Sie sicher, dass die Option **Analytische und Debugprotokolle einblenden** aktiviert ist.  
  
9. Aktivieren Sie das Protokoll **Analytisch**.  
  
     Navigieren Sie in der Strukturansicht der Ereignisanzeige zu **Ereignisanzeige**, **Anwendungs\- und Dienstprotokolle**, **Microsoft**, **Windows** und dann zu **Anwendungsserver\-Anwendungen**.  Klicken Sie mit der rechten Maustaste auf **Analytisch**, und wählen Sie **Protokoll aktivieren** aus.  
  
#### So testen Sie den Dienst  
  
1.  Wechseln Sie zurück zum [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Testclient, doppelklicken Sie auf `Divide`, und behalten Sie die Standardwerte bei, die als Nenner 0 angeben.  
  
     Wenn der Nenner 0 ist, löst der Dienst einen Fehler aus.  
  
2.  Beachten Sie die vom Dienst ausgegebenen Ereignisse.  
  
     Wechseln Sie zurück zur Ereignisanzeige, und navigieren Sie zu **Ereignisanzeige**, **Anwendungs\- und Dienstprotokolle**, **Microsoft**, **Windows** und dann zu **Anwendungsserver\-Anwendungen**.  Klicken Sie mit der rechten Maustaste auf **Analytisch**, und wählen Sie **Aktualisieren**.  
  
     Die analytischen Ablaufverfolgungsereignisse in WCF werden in der Ereignisanzeige angezeigt.  Beachten Sie, dass ein Fehler als Ablaufverfolgungsereignis in der Ereignisanzeige angezeigt wird, da ein Fehler vom Dienst ausgelöst wurde.  
  
3.  Wiederholen Sie Schritt 1 und 2 mit gültigen Eingaben.  Der Wert des `N2`\-Parameters kann eine beliebige Zahl außer 0 sein.  
  
     Aktualisieren Sie den analytischen Kanal, um die WCF\-Ereignisse anzuzeigen, wobei keine Fehlerereignisse vorhanden sind.  
  
 Im Beispiel werden die von einem WCF\-Dienst ausgegebenen analytischen Ablaufverfolgungsereignisse veranschaulicht.  
  
#### So führen Sie eine \(optionale\) Bereinigung durch  
  
1.  Öffnen Sie die Ereignisanzeige.  
  
2.  Navigieren Sie zu **Ereignisanzeige**, **Anwendungs\- und Dienstprotokolle**, **Microsoft**, **Windows**, **Anwendungsserver\-Anwendungen**.  Klicken Sie mit der rechten Maustaste auf **Analytisch**, und wählen Sie **Protokoll deaktivieren** aus.  
  
3.  Navigieren Sie zu **Ereignisanzeige**, **Anwendungs\- und Dienstprotokolle**, **Microsoft**, **Windows**, **Anwendungsserver\-Anwendungen**.  Klicken Sie mit der rechten Maustaste auf **Analytisch**, und wählen Sie **Protokoll löschen** aus.  
  
4.  Wählen Sie die Option **Löschen** aus, um die Ereignisse zu löschen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.  Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.  Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## Siehe auch  
 [AppFabric\-Überwachungsbeispiele](http://go.microsoft.com/fwlink/?LinkId=193959)