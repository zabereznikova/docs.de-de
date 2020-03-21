---
title: Analytische Ablaufverfolgung von WCF
ms.date: 03/30/2017
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
ms.openlocfilehash: ef636a672d9384e8e3d658f0488cfaadb8d293e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183218"
---
# <a name="wcf-analytic-tracing"></a>Analytische Ablaufverfolgung von WCF
In diesem Beispiel wird veranschaulicht, wie Sie eigene Ablaufverfolgungsereignisse in den Stream von Analyseablaufverfolgungen hinzufügen, die Windows Communication Foundation (WCF) in in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]schreibt. Analytische Ablaufverfolgungen sollen die Dienste sichtbar machen, ohne die Leistung deutlich zu beeinträchtigen. In diesem Beispiel wird <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> gezeigt, wie die APIs zum Schreiben von Ereignissen verwendet werden, die in WCF-Dienste integriert werden.  
  
 Weitere Informationen zu <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> den APIs finden Sie unter <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>.  
  
 Weitere Informationen zur Ereignisablaufverfolgung in Windows finden Sie unter [Verbessern des Debuggens und der Leistungsoptimierung mit ETW](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw).  
  
## <a name="disposing-eventprovider"></a>Freigeben von EventProvider  
 In diesem Beispiel wird die <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType>-Klasse verwendet, die <xref:System.IDisposable?displayProperty=nameWithType> implementiert. Beim Implementieren der Ablaufverfolgung für einen WCF-Dienst <xref:System.Diagnostics.Eventing.EventProvider>ist es wahrscheinlich, dass Sie die Ressourcen der Dienstressourcen für die Gesamteinzeit des Dienstes verwenden. Aus diesem Grund und zur besseren Lesbarkeit gibt das Beispiel nie die eingebundene <xref:System.Diagnostics.Eventing.EventProvider> frei. Wenn der Dienst aus irgendeinem Grund andere Anforderungen an die Ablaufverfolgung stellt und Sie diese Ressource freigeben müssen, sollten Sie dieses Beispiel in Übereinstimmung mit den empfohlenen Vorgehensweisen zum Freigeben von nicht verwalteten Ressourcen ändern. Weitere Informationen zum Entsorgen nicht verwalteter Ressourcen finden Sie unter [Implementieren einer Dispose-Methode](https://docs.microsoft.com/dotnet/standard/garbage-collection/implementing-dispose).  
  
## <a name="self-hosting-vs-web-hosting"></a>Selbsthosting gegenüber Webhosting  
 Für webgehostete Dienste stellen die Analyseablaufverfolgungen von WCF ein Feld namens "HostReference" bereit, das zum Identifizieren des Dienstes verwendet wird, der die Ablaufverfolgungen ausgibt. Die erweiterbaren Benutzerablaufverfolgungen können in diesem Modell verwendet werden, und dieses Beispiel zeigt die entsprechenden empfohlenen Vorgehensweisen. Das Format eines Webhostverweises, wenn das Zeichen "&#124;" tatsächlich in der resultierenden Zeichenfolge angezeigt wird, kann eines der folgenden sein:  
  
- Wenn sich die Anwendung nicht im Stammverzeichnis befindet.  
  
     \<SiteName \<>ApplicationVirtualPath>&#124;\< \<ServiceVirtualPath>&#124;ServiceName>  
  
- Wenn sich die Anwendung im Stammverzeichnis befindet.  
  
     \<SiteName \<>&#124;ServiceVirtualPath>&#124;\<ServiceName>  
  
 Bei selbst gehosteten Diensten füllen die Analyseablaufverfolgungen von WCF das Feld "HostReference" nicht aus. Die `WCFUserEventProvider`-Klasse in diesem Beispiel verhält sich konsistent, wenn sie von einem selbst gehosteten Dienst verwendet wird.  
  
## <a name="custom-event-details"></a>Details der benutzerdefinierten Ereignisse  
 Das WCF-Ereignisanbietermanifest von WCF definiert drei Ereignisse, die von WCF-Dienstautoren innerhalb des Dienstcodes ausgesendet werden sollen. In der folgenden Tabelle werden die drei Ereignisse aufgelistet.  
  
|Ereignis|Beschreibung|Ereignis-ID|  
|-----------|-----------------|--------------|  
|UserDefinedInformationEventOccurred|Geben Sie dieses Ereignis bei einem Vorfall im Dienst aus, bei dem es sich nicht um ein Problem handelt. Sie könnten z. B. ein Ereignis nach dem erfolgreichen Aufruf einer Datenbank ausgeben.|301|  
|UserDefinedWarningOccurred|Geben Sie dieses Ereignis aus, wenn ein Problem auftritt, das möglicherweise in der Zukunft einen Fehler verursacht. Wenn beispielsweise der Aufruf einer Datenbank fehlschlägt, Sie jedoch auf einen redundanten Datenspeicher zurückgreifen können, können Sie ein Warnereignis ausgeben.|302|  
|UserDefinedErrorOccurred|Geben Sie dieses Ereignis aus, wenn sich der Dienst nicht den Erwartungen entsprechend verhält. Sie könnten dieses Ereignis z. B. ausgeben, wenn der Aufruf einer Datenbank fehlschlägt und Sie die Daten nicht von einer anderen Stelle abrufen können.|303|  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1. Öffnen Sie mit Visual Studio 2012 die Projektmappendatei WCFAnalyticTracingExtensibility.sln.  
  
2. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3. Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
     Klicken Sie im Webbrowser auf **Calculator.svc**. Der URI des WSDL-Dokuments für den Dienst wird daraufhin im Browser angezeigt. Kopieren Sie diesen URI.  
  
4. Führen Sie den WCF-Testclient (WcfTestClient.exe) aus.  
  
     Der WCF-Testclient (WcfTestClient.exe) `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`befindet sich unter . Die Standardmäßige Visual Studio 2012-Installation von dir ist `C:\Program Files\Microsoft Visual Studio 10.0`.  
  
5. Fügen Sie den Dienst innerhalb des WCF-Testclients hinzu, indem Sie **Datei**auswählen und dann **Dienst hinzufügen**.  
  
     Fügen Sie die Endpunktadresse im Eingabefeld hinzu.  
  
6. Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
     Der ICalculator-Dienst wird im linken Bereich unter **Meine Dienstprojekte**hinzugefügt.  
  
7. Öffnen Sie die Ereignisanzeige.  
  
     Starten Sie vor dem Aufrufen des Dienstes die Ereignisanzeige, und stellen Sie sicher, dass das Ereignisprotokoll auf die Nachverfolgung von Ereignissen lauscht, die vom WCF-Dienst gesendet wurden.  
  
8. Wählen Sie im **Startmenü** **Administrative Tools**aus, und dann **die Ereignisanzeige**. Aktivieren Sie die **Analyse-** und **Debugprotokolle.**  
  
9. Navigieren Sie in der Strukturansicht in der Ereignisanzeige zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**und dann **Application Server-Applications**. Klicken Sie mit der rechten Maustaste auf **Application Server-Applications**, wählen Sie **Ansicht**aus, und zeigen Sie dann **Analyse- und Debugprotokolle an.**  
  
     Stellen Sie sicher, dass die Option **Analyse- und Debugprotokolle** anzeigen aktiviert ist. Aktivieren Sie das **Analyseprotokoll.**  
  
     Navigieren Sie in der Strukturansicht in der Ereignisanzeige zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, **Application Server-Applications**und dann **analytic**. Klicken Sie mit der rechten Maustaste auf **Analytic,** und wählen Sie **Protokoll aktivieren**aus.  
  
10. Testen Sie den Dienst mit dem WCF-Testclient.  
  
    1. Doppelklicken Sie im WCF-Testclient unter dem ICalculator-Dienstknoten auf **Hinzufügen().**  
  
         Die **Add()-Methode** wird im rechten Bereich mit zwei Parametern angezeigt.  
  
    2. Geben Sie für den ersten Parameter 2 und für den zweiten Parameter 3 ein.  
  
    3. Klicken Sie auf **Aufrufen,** um die Methode aufzurufen.  
  
11. Wechseln Sie zum **Event Viewer-Fenster,** das Sie bereits geöffnet haben. Navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, **Application Server-Applications**.  
  
12. Klicken Sie mit der rechten Maustaste auf den **Analyseknoten,** und wählen Sie **Aktualisieren**aus.  
  
     Die Ereignisse werden im rechten Bereich angezeigt.  
  
13. Suchen Sie das Ereignis mit der ID 303, und doppelklicken Sie darauf, um es zu öffnen und seinen Inhalt zu untersuchen.  
  
     Dieses Ereignis wurde von `Add()` der Methode des ICalculator-Dienstes emittiert und hat eine Nutzlast von "2+3=5".  
  
#### <a name="to-clean-up-optional"></a>So führen Sie eine Bereinigung aus (optional)  
  
1. Öffnen Sie die **Ereignisanzeige**.  
  
2. Navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**und dann **Application-Server-Applications**. Klicken Sie mit der rechten Maustaste auf **Analytic,** und wählen Sie **Protokoll deaktivieren**aus.  
  
3. Navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, **Application-Server-Applications**und dann **Analytic**. Klicken Sie mit der rechten Maustaste auf **Analytic,** und wählen Sie **Protokoll löschen**aus.  
  
4. Klicken Sie auf **Löschen,** um die Ereignisse zu löschen.  
  
## <a name="known-issue"></a>Bekanntes Problem  
 Es gibt ein bekanntes Problem in der **Ereignisanzeige,** bei dem ETW-Ereignisse möglicherweise nicht decodiert werden. Möglicherweise wird eine Fehlermeldung angezeigt, die besagt: "Die Beschreibung für die Ereignis-ID-ID \<> aus der Quelle Microsoft-Windows-Application Server-Applications kann nicht gefunden werden. Entweder ist die Komponente, die dieses Ereignis auslöst, auf Ihrem lokalen Computer nicht installiert, oder die Installation ist beschädigt. Sie können die Komponente auf dem lokalen Computer installieren oder reparieren." Wenn dieser Fehler auftritt, wählen Sie im Menü **Aktionen** die Option **Aktualisieren** aus. Das Ereignis sollte dann ordnungsgemäß decodiert werden.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## <a name="see-also"></a>Weitere Informationen

- [AppFabric-Überwachungsbeispiele](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
