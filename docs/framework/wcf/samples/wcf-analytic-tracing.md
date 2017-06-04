---
title: "Analytische Ablaufverfolgung von WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
caps.latest.revision: 21
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 21
---
# Analytische Ablaufverfolgung von WCF
In diesem Beispiel wird veranschaulicht, wie Sie Ihre eigenen Ablaufverfolgungsereignisse in den Stream der analytischen Ablaufverfolgungen hinzufügen können, die [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] in ETW schreibt.Analytische Ablaufverfolgungen sollen die Dienste sichtbar machen, ohne die Leistung deutlich zu beeinträchtigen.In diesem Beispiel wird gezeigt, wie die <xref:System.Diagnostics.Eventing?displayProperty=fullName>\-APIs verwendet werden, um Ereignisse zu schreiben, die in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienste integriert werden.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu <xref:System.Diagnostics.Eventing?displayProperty=fullName>\-APIs finden Sie unter <xref:System.Diagnostics.Eventing?displayProperty=fullName>.  
  
 Weitere Informationen zur Ereignisablaufverfolgung in Windows finden Sie unter [Verbessertes Debugging und Leistungsoptimierung mit ETW](http://go.microsoft.com/fwlink/?LinkId=166488).  
  
## Freigeben von EventProvider  
 In diesem Beispiel wird die <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=fullName>\-Klasse verwendet, die <xref:System.IDisposable?displayProperty=fullName> implementiert.Bei der Implementierung der Ablaufverfolgung für einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst verwenden Sie wahrscheinlich die <xref:System.Diagnostics.Eventing.EventProvider>\-Ressourcen für die Lebensdauer des Diensts.Aus diesem Grund und zur besseren Lesbarkeit gibt das Beispiel nie die eingebundene <xref:System.Diagnostics.Eventing.EventProvider> frei.Wenn der Dienst aus irgendeinem Grund andere Anforderungen an die Ablaufverfolgung stellt und Sie diese Ressource freigeben müssen, sollten Sie dieses Beispiel in Übereinstimmung mit den empfohlenen Vorgehensweisen zum Freigeben von nicht verwalteten Ressourcen ändern.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Freigeben von nicht verwalteten Ressourcen finden Sie unter [Implementieren einer Dispose\-Methode](http://go.microsoft.com/fwlink/?LinkId=166436) finden.  
  
## Selbsthosting gegenüberWebhosting  
 Für im Internet gehostete Dienste stellen die analytischen Ablaufverfolgungen von WCF ein Feld mit dem Namen "HostReference" bereit, das zur Identifizierung des Diensts verwendet wird, der die Ablaufverfolgungen ausgibt.Die erweiterbaren Benutzerablaufverfolgungen können in diesem Modell verwendet werden, und dieses Beispiel zeigt die entsprechenden empfohlenen Vorgehensweisen.Wenn der senkrechte Strich "&#124;" in der Ergebniszeichenfolge tatsächlich angezeigt wird, kann der Webhostverweis in einem der folgenden Formate vorliegen:  
  
-   Wenn sich die Anwendung nicht im Stammverzeichnis befindet.  
  
     \<SiteName\>\<ApplicationVirtualPath\>&#124;\<ServiceVirtualPath\>&#124;\<ServiceName\>  
  
-   Wenn sich die Anwendung im Stammverzeichnis befindet.  
  
     \<SiteName\>&#124;\<ServiceVirtualPath\>&#124;\<ServiceName\>  
  
 Bei selbst gehosteten Diensten wird das Feld "HostReference" von den analytischen Ablaufverfolgungen von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nicht aufgefüllt.Die `WCFUserEventProvider`\-Klasse in diesem Beispiel verhält sich konsistent, wenn sie von einem selbst gehosteten Dienst verwendet wird.  
  
## Details der benutzerdefinierten Ereignisse  
 Der ETW\-Ereignisanbieter von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] definiert drei Ereignisse, die von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienstautoren aus dem Dienstcode ausgegeben werden sollen.In der folgenden Tabelle werden die drei Ereignisse aufgelistet.  
  
|Ereignis|Beschreibung|Ereignis\-ID|  
|--------------|------------------|------------------|  
|UserDefinedInformationEventOccurred|Geben Sie dieses Ereignis bei einem Vorfall im Dienst aus, bei dem es sich nicht um ein Problem handelt.Sie könnten z. B. ein Ereignis nach dem erfolgreichen Aufruf einer Datenbank ausgeben.|301|  
|UserDefinedWarningOccurred|Geben Sie dieses Ereignis aus, wenn ein Problem auftritt, das möglicherweise in der Zukunft einen Fehler verursacht.Wenn beispielsweise der Aufruf einer Datenbank fehlschlägt, Sie jedoch auf einen redundanten Datenspeicher zurückgreifen können, können Sie ein Warnereignis ausgeben.|302|  
|UserDefinedErrorOccurred|Geben Sie dieses Ereignis aus, wenn sich der Dienst nicht den Erwartungen entsprechend verhält.Sie könnten dieses Ereignis z. B. ausgeben, wenn der Aufruf einer Datenbank fehlschlägt und Sie die Daten nicht von einer anderen Stelle abrufen können.|303|  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Projektmappendatei WCFAnalyticTracingExtensibility.sln in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG\+F5, um die Projektmappe auszuführen.  
  
     Klicken Sie im Webbrowser auf **Calculator.svc**.Der URI des WSDL\-Dokuments für den Dienst wird daraufhin im Browser angezeigt.Kopieren Sie diesen URI.  
  
4.  Führen Sie den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Testclient \(WcfTestClient.exe\) aus.  
  
     Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Testclient \(WcfTestClient.exe\) befindet sich unter \<[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]\-Installationsverzeichnis\>\\Common7\\IDE\\ WcfTestClient.exe \(das Standardinstallationsverzeichnis von [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] ist C:\\Programme\\Microsoft Visual Studio 10.0\).  
  
5.  Fügen Sie im [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Testclient den Dienst hinzu, indem Sie **Datei** und dann **Dienst hinzufügen** auswählen.  
  
     Fügen Sie die Endpunktadresse im Eingabefeld hinzu.  
  
6.  Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
     Der ICalculator\-Dienst wird im linken Bereich unter **Meine Dienstprojekte** hinzugefügt.  
  
7.  Öffnen Sie die Ereignisanzeige.  
  
     Starten Sie vor dem Aufrufen des Diensts die Ereignisanzeige, und stellen Sie sicher, dass das Ereignisprotokoll eine Überwachung für von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ausgegebene Überwachungsereignisse ausführt.  
  
8.  Wählen Sie aus dem Menü **Start** die Option **Verwaltung** und dann **Ereignisanzeige** aus.Aktivieren Sie die Protokolle **Analytisch** und **Debuggen**.  
  
9. Navigieren Sie in der Strukturansicht der Ereignisanzeige zu **Ereignisanzeige**, **Anwendungs\- und Dienstprotokolle**, **Microsoft**, **Windows** und dann zu **Anwendungsserver\-Anwendungen**.Klicken Sie mit der rechten Maustaste auf **Anwendungsserver\-Anwendungen**, und wählen Sie **Ansicht** und danach **Analytische und Debugprotokolle einblenden** aus.  
  
     Stellen Sie sicher, dass die Option **Analytische und Debugprotokolle einblenden** aktiviert ist.Aktivieren Sie das Protokoll **Analytisch**.  
  
     Navigieren Sie in der Strukturansicht der Ereignisanzeige zu **Ereignisanzeige**, **Anwendungs\- und Dienstprotokolle**, **Microsoft**, **Windows**, **Anwendungsserver\-Anwendungen** und dann zu **Analytisch**.Klicken Sie mit der rechten Maustaste auf **Analytisch**, und wählen Sie **Protokoll aktivieren** aus.  
  
10. Testen Sie den Dienst mit dem WCF\-Testclient.  
  
    1.  Doppelklicken Sie im WCF\-Testclient unter dem Knoten ICalculator\-Dienst auf **Add\(\)**.  
  
         Die **Add\(\)**\-Methode wird im rechten Bereich mit zwei Parametern angezeigt.  
  
    2.  Geben Sie für den ersten Parameter 2 und für den zweiten Parameter 3 ein.  
  
    3.  Klicken Sie auf **Aufrufen**, um die Methode aufzurufen.  
  
11. Wechseln Sie zum Fenster **Ereignisanzeige**, das bereits geöffnet ist.Navigieren Sie zu **Ereignisanzeige**, **Anwendungs\- und Dienstprotokolle**, **Microsoft**, **Windows**, **Anwendungsserver\-Anwendungen**.  
  
12. Klicken Sie mit der rechten Maustaste auf den Knoten **Analytisch**, und wählen Sie **Aktualisieren** aus.  
  
     Die Ereignisse werden im rechten Bereich angezeigt.  
  
13. Suchen Sie das Ereignis mit der ID 303, und doppelklicken Sie darauf, um es zu öffnen und seinen Inhalt zu untersuchen.  
  
     Dieses Ereignis wurde von der `Add()`\-Methode des ICalculator\-Diensts ausgegeben und verfügt über eine Nutzlast gleich "2\+3\=5."  
  
#### So führen Sie eine Bereinigung aus \(optional\)  
  
1.  Öffnen Sie die **Ereignisanzeige**.  
  
2.  Navigieren Sie zu **Ereignisanzeige**, **Anwendungs\- und Dienstprotokolle**, **Microsoft**, **Windows**, **Anwendungsserver\-Anwendungen**.Klicken Sie mit der rechten Maustaste auf **Analytisch**, und wählen Sie **Protokoll deaktivieren** aus.  
  
3.  Navigieren Sie zu **Ereignisanzeige**, **Anwendungs\- und Dienstprotokolle**, **Microsoft**, **Windows**, **Anwendungsserver\-Anwendungen**, **Analytisch**.Klicken Sie mit der rechten Maustaste auf **Analytisch**, und wählen Sie **Protokoll löschen** aus.  
  
4.  Klicken Sie auf **Löschen**, um die Ereignisse zu löschen.  
  
## Bekannte Probleme  
 Es gibt ein bekanntes Problem in der **Ereignisanzeige**, bei dem bei der Decodierung von ETW\-Ereignissen ein Fehler auftritt.Die folgende Fehlermeldung wird möglicherweise angezeigt: "Die Beschreibung für die Ereignis\-ID "\<id\>" aus der Quelle "Microsoft\-Windows\-Application Server\-Applications" wurde nicht gefunden.Entweder ist die Komponente, die dieses Ereignis auslöst, nicht auf dem lokalen Computer installiert, oder die Installation ist beschädigt.Sie können die Komponente auf dem lokalen Computer installieren oder reparieren." Wenn dieser Fehler auftritt, wählen Sie im Menü **Aktionen** die Option **Aktualisieren** aus.Das Ereignis sollte dann ordnungsgemäß decodiert werden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## Siehe auch  
 [AppFabric\-Überwachungsbeispiele](http://go.microsoft.com/fwlink/?LinkId=193959)