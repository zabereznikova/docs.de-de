---
title: Analytische Ablaufverfolgung von WCF
ms.date: 03/30/2017
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
ms.openlocfilehash: 3ed9c5f08e89d978f8290dcda5ab1ecfd8b9c56c
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094825"
---
# <a name="wcf-analytic-tracing"></a>Analytische Ablaufverfolgung von WCF
In diesem Beispiel wird veranschaulicht, wie Sie Ihre eigenen Ablauf Verfolgungs Ereignisse dem Stream von analytischen Ablauf Verfolgungen hinzufügen, die Windows Communication Foundation (WCF) in die etw in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]schreibt. Analytische Ablaufverfolgungen sollen die Dienste sichtbar machen, ohne die Leistung deutlich zu beeinträchtigen. Dieses Beispiel zeigt, wie Sie die <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>-APIs verwenden, um Ereignisse zu schreiben, die in WCF-Dienste integriert werden.  
  
 Weitere Informationen zu den <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>-APIs finden Sie unter <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>.  
  
 Weitere Informationen zur Ereignis Ablauf Verfolgung in Windows finden Sie unter [verbessern des Debuggens und Leistungsoptimierung mit etw](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw).  
  
## <a name="disposing-eventprovider"></a>Freigeben von EventProvider  
 In diesem Beispiel wird die <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType>-Klasse verwendet, die <xref:System.IDisposable?displayProperty=nameWithType> implementiert. Beim Implementieren der Ablauf Verfolgung für einen WCF-Dienst ist es wahrscheinlich, dass Sie die Ressourcen des <xref:System.Diagnostics.Eventing.EventProvider>für die Lebensdauer des Dienstanbieter verwenden können. Aus diesem Grund und zur besseren Lesbarkeit gibt das Beispiel nie die eingebundene <xref:System.Diagnostics.Eventing.EventProvider> frei. Wenn der Dienst aus irgendeinem Grund andere Anforderungen an die Ablaufverfolgung stellt und Sie diese Ressource freigeben müssen, sollten Sie dieses Beispiel in Übereinstimmung mit den empfohlenen Vorgehensweisen zum Freigeben von nicht verwalteten Ressourcen ändern. Weitere Informationen zum Freigeben von nicht verwalteten Ressourcen finden Sie unter [Implementieren einer](https://docs.microsoft.com/dotnet/standard/garbage-collection/implementing-dispose)verwerfen-Methode.  
  
## <a name="self-hosting-vs-web-hosting"></a>Selbsthosting gegenüber Webhosting  
 Für im Internet gehostete Dienste stellen die analytischen Ablauf Verfolgungen von WCF ein Feld namens "hostreferenzierung" bereit, das verwendet wird, um den Dienst zu identifizieren, der die Ablauf Verfolgungen ausgibt. Die erweiterbaren Benutzerablaufverfolgungen können in diesem Modell verwendet werden, und dieses Beispiel zeigt die entsprechenden empfohlenen Vorgehensweisen. Das Format eines Webhost Verweises, wenn das Pipe&#124;-Zeichen in der resultierenden Zeichenfolge tatsächlich angezeigt wird, kann eines der folgenden sein:  
  
- Wenn sich die Anwendung nicht im Stammverzeichnis befindet.  
  
     \<Sitename >\<ApplicationVirtualPath >&#124;\<servicevirtualpath >&#124;\<ServiceName >  
  
- Wenn sich die Anwendung im Stammverzeichnis befindet.  
  
     \<Sitename >&#124;\<servicevirtualpath >&#124;\<ServiceName >  
  
 Für selbst gehostete Dienste füllt die analytische Ablauf Verfolgung von WCF das Feld "hostreferenzierung" nicht auf. Die `WCFUserEventProvider`-Klasse in diesem Beispiel verhält sich konsistent, wenn sie von einem selbst gehosteten Dienst verwendet wird.  
  
## <a name="custom-event-details"></a>Details der benutzerdefinierten Ereignisse  
 Das ETW-Ereignis Anbieter Manifest von WCF definiert drei Ereignisse, die von WCF-Dienst Autoren innerhalb von Dienst Code ausgegeben werden sollen. In der folgenden Tabelle werden die drei Ereignisse aufgelistet.  
  
|Ereignis|BESCHREIBUNG|Ereignis-ID|  
|-----------|-----------------|--------------|  
|UserDefinedInformationEventOccurred|Geben Sie dieses Ereignis bei einem Vorfall im Dienst aus, bei dem es sich nicht um ein Problem handelt. Sie könnten z. B. ein Ereignis nach dem erfolgreichen Aufruf einer Datenbank ausgeben.|301|  
|UserDefinedWarningOccurred|Geben Sie dieses Ereignis aus, wenn ein Problem auftritt, das möglicherweise in der Zukunft einen Fehler verursacht. Wenn beispielsweise der Aufruf einer Datenbank fehlschlägt, Sie jedoch auf einen redundanten Datenspeicher zurückgreifen können, können Sie ein Warnereignis ausgeben.|302|  
|UserDefinedErrorOccurred|Geben Sie dieses Ereignis aus, wenn sich der Dienst nicht den Erwartungen entsprechend verhält. Sie könnten dieses Ereignis z. B. ausgeben, wenn der Aufruf einer Datenbank fehlschlägt und Sie die Daten nicht von einer anderen Stelle abrufen können.|303|  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1. Öffnen Sie die Projektmappendatei wcfanalytictracingextensibility. sln mithilfe von Visual Studio 2012.  
  
2. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3. Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
     Klicken Sie im Webbrowser auf **Calculator. svc**. Der URI des WSDL-Dokuments für den Dienst wird daraufhin im Browser angezeigt. Kopieren Sie diesen URI.  
  
4. Führen Sie den WCF-Test Client (WcfTestClient. exe) aus.  
  
     Der WCF-Test Client (WcfTestClient. exe) befindet sich unter `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`. Der Standard Installationsverzeichnis von Visual Studio 2012 ist `C:\Program Files\Microsoft Visual Studio 10.0`.  
  
5. Fügen Sie im WCF-Test Client den Dienst hinzu, indem Sie auf **Datei**und dann auf **Dienst hinzufügen**klicken.  
  
     Fügen Sie die Endpunktadresse im Eingabefeld hinzu.  
  
6. Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
     Der ICalculator-Dienst wird im linken Bereich unter **meine Dienstprojekte**hinzugefügt.  
  
7. Öffnen Sie die Ereignisanzeige.  
  
     Bevor Sie den Dienst aufrufen, starten Sie Ereignisanzeige, und stellen Sie sicher, dass das Ereignisprotokoll nach Verfolgungs Ereignissen lauscht, die vom WCF-Dienst ausgegeben werden.  
  
8. Klicken Sie im **Startmenü** auf **Verwaltung**, und klicken Sie dann auf **Ereignisanzeige**. Aktivieren Sie die **analytischen** und **Debugprotokolle** .  
  
9. Navigieren Sie in der Strukturansicht in Ereignisanzeige zu **Ereignisanzeige**, Anwendungs **-und Dienst Protokolle**, **Microsoft**, **Windows**und dann zu **Anwendungs Server-Anwendungen**. Klicken Sie mit der rechten Maustaste auf **Anwendungs Server-Anwendungen**, wählen Sie **Ansicht**und dann **analytische und Debugprotokolle anzeigen**aus.  
  
     Stellen Sie sicher, dass die Option **analytische und Debugprotokolle anzeigen** aktiviert ist. Aktivieren Sie das **analytische** Protokoll.  
  
     Navigieren Sie in der Strukturansicht in Ereignisanzeige zu **Ereignisanzeige**, Anwendungs **-und Dienst Protokolle**, **Microsoft**, **Windows**, **Anwendungs Server-Anwendungen**und anschließend zu **analytisch**. Klicken Sie mit der rechten Maustaste auf **Analyse** , und wählen Sie **Protokoll aktivieren**  
  
10. Testen Sie den Dienst mit dem WCF-Testclient.  
  
    1. Doppelklicken Sie im WCF-Test Client unter dem Knoten ICalculator-Dienst auf **hinzufügen ()** .  
  
         Die **Add ()** -Methode wird im rechten Bereich mit zwei Parametern angezeigt.  
  
    2. Geben Sie für den ersten Parameter 2 und für den zweiten Parameter 3 ein.  
  
    3. Klicken Sie auf **aufrufen** , um die Methode aufzurufen.  
  
11. Wechseln Sie zum **Ereignisanzeige** Fenster, das Sie bereits geöffnet haben. Navigieren Sie zu **Ereignisanzeige**, Anwendungs **-und Dienst Protokolle**, **Microsoft**, **Windows**, **Anwendungs Server-Anwendungen**.  
  
12. Klicken Sie mit der rechten Maustaste auf den Knoten **Analyse** , und wählen Sie **Aktualisieren**  
  
     Die Ereignisse werden im rechten Bereich angezeigt.  
  
13. Suchen Sie das Ereignis mit der ID 303, und doppelklicken Sie darauf, um es zu öffnen und seinen Inhalt zu untersuchen.  
  
     Dieses Ereignis wurde von der `Add()`-Methode des ICalculator-Dienstanbieter ausgegeben und hat eine Nutzlast gleich "2 + 3 = 5".  
  
#### <a name="to-clean-up-optional"></a>So führen Sie eine Bereinigung aus (optional)  
  
1. Öffnen Sie die **Ereignisanzeige**.  
  
2. Navigieren Sie zu **Ereignisanzeige**, Anwendungs- **und Dienst Protokolle**, **Microsoft**, **Windows**und dann zu **Anwendungs Server-Anwendungen**. Klicken Sie mit der rechten Maustaste auf **Analyse** , und wählen Sie **Protokoll deaktivieren**  
  
3. Navigieren Sie **zu Ereignisanzeige**, **Anwendungs-und Dienst Protokolle**, **Microsoft**, **Windows**, **Anwendungs Server-Anwendungen**und anschließend zu **analytisch**. Klicken Sie mit der rechten Maustaste auf **Analyse** , und wählen Sie **Protokoll löschen**  
  
4. Klicken Sie auf **Löschen** , um die Ereignisse zu löschen.  
  
## <a name="known-issue"></a>Bekanntes Problem  
 Im **Ereignisanzeige** ist ein bekanntes Problem aufgetreten, bei dem ETW-Ereignisse möglicherweise nicht decodiert werden. Möglicherweise wird die folgende Fehlermeldung angezeigt: "die Beschreibung für die Ereignis-ID \<ID > von der Quelle Microsoft-Windows-Anwendungs Server-Anwendungen können nicht gefunden werden. Entweder ist die Komponente, die dieses Ereignis auslöst, auf Ihrem lokalen Computer nicht installiert, oder die Installation ist beschädigt. Sie können die Komponente auf dem lokalen Computer installieren oder reparieren. " Wenn dieser Fehler auftritt, wählen Sie im Menü **Aktionen** die Option **Aktualisieren** aus. Das Ereignis sollte dann ordnungsgemäß decodiert werden.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## <a name="see-also"></a>Weitere Informationen

- [AppFabric-Überwachungs Beispiele](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
