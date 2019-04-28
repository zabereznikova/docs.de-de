---
title: Analytische Ablaufverfolgung von WCF
ms.date: 03/30/2017
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
ms.openlocfilehash: 9ed89bdbe2469a96f2a959c9fda8442e80b6f7ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723354"
---
# <a name="wcf-analytic-tracing"></a>Analytische Ablaufverfolgung von WCF
In diesem Beispiel wird veranschaulicht, wie Sie Ihre eigenen Ablaufverfolgungsereignisse in den Stream der analytischen ablaufverfolgungen hinzufügen, die Windows Communication Foundation (WCF) in ETW in schreibt [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]. Analytische Ablaufverfolgungen sollen die Dienste sichtbar machen, ohne die Leistung deutlich zu beeinträchtigen. Dieses Beispiel zeigt, wie Sie mit der <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> APIs, um Ereignisse zu schreiben, die in WCF-Dienste integrieren.  
  
 Weitere Informationen zu den <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> -APIs finden Sie unter <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>.  
  
 Weitere Informationen zur ereignisablaufverfolgung in Windows finden Sie unter [verbessertes Debugging und Leistungsoptimierung mit ETW](https://go.microsoft.com/fwlink/?LinkId=166488).  
  
## <a name="disposing-eventprovider"></a>Freigeben von EventProvider  
 In diesem Beispiel wird die <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType>-Klasse verwendet, die <xref:System.IDisposable?displayProperty=nameWithType> implementiert. Bei der Implementierung der Ablaufverfolgung für einen WCF-Dienst, ist es wahrscheinlich, verwenden Sie die <xref:System.Diagnostics.Eventing.EventProvider>der Ressourcen für die Lebensdauer des Diensts. Aus diesem Grund und zur besseren Lesbarkeit gibt das Beispiel nie die eingebundene <xref:System.Diagnostics.Eventing.EventProvider> frei. Wenn der Dienst aus irgendeinem Grund andere Anforderungen an die Ablaufverfolgung stellt und Sie diese Ressource freigeben müssen, sollten Sie dieses Beispiel in Übereinstimmung mit den empfohlenen Vorgehensweisen zum Freigeben von nicht verwalteten Ressourcen ändern. Weitere Informationen zu nicht verwaltete Ressourcen freigibt, finden Sie unter [Implementieren einer Dispose-Methode](https://go.microsoft.com/fwlink/?LinkId=166436).  
  
## <a name="self-hosting-vs-web-hosting"></a>Selbsthosting gegenüber Webhosting  
 Für im Web gehostete Dienste bieten die analytischen ablaufverfolgungen von WCF ein Feld mit dem Namen "hostreference" bereit, die verwendet wird, um den Dienst zu identifizieren, der die ablaufverfolgungen ausgibt. Die erweiterbaren Benutzerablaufverfolgungen können in diesem Modell verwendet werden, und dieses Beispiel zeigt die entsprechenden empfohlenen Vorgehensweisen. Das Format von einem Webhost zu verweisen, wenn der Pipe "&#124;' Zeichen tatsächlich angezeigt wird, in die resultierende Zeichenfolge kann eine der folgenden sein:  
  
- Wenn sich die Anwendung nicht im Stammverzeichnis befindet.  
  
     \<SiteName>\<ApplicationVirtualPath>&#124;\<ServiceVirtualPath>&#124;\<ServiceName>  
  
- Wenn sich die Anwendung im Stammverzeichnis befindet.  
  
     \<SiteName>&#124;\<ServiceVirtualPath>&#124;\<ServiceName>  
  
 Für selbst gehostete Dienste werden die analytischen ablaufverfolgungen von WCF nicht das Feld "HostReference" aufgefüllt. Die `WCFUserEventProvider`-Klasse in diesem Beispiel verhält sich konsistent, wenn sie von einem selbst gehosteten Dienst verwendet wird.  
  
## <a name="custom-event-details"></a>Details der benutzerdefinierten Ereignisse  
 Der WCF-definiert ETW-Ereignisanbieter drei Ereignisse, die von WCF-dienstautoren im Dienstcode ausgegeben werden sollen. In der folgenden Tabelle werden die drei Ereignisse aufgelistet.  
  
|event|Beschreibung|Ereignis-ID|  
|-----------|-----------------|--------------|  
|UserDefinedInformationEventOccurred|Geben Sie dieses Ereignis bei einem Vorfall im Dienst aus, bei dem es sich nicht um ein Problem handelt. Sie könnten z. B. ein Ereignis nach dem erfolgreichen Aufruf einer Datenbank ausgeben.|301|  
|UserDefinedWarningOccurred|Geben Sie dieses Ereignis aus, wenn ein Problem auftritt, das möglicherweise in der Zukunft einen Fehler verursacht. Wenn beispielsweise der Aufruf einer Datenbank fehlschlägt, Sie jedoch auf einen redundanten Datenspeicher zurückgreifen können, können Sie ein Warnereignis ausgeben.|302|  
|UserDefinedErrorOccurred|Geben Sie dieses Ereignis aus, wenn sich der Dienst nicht den Erwartungen entsprechend verhält. Sie könnten dieses Ereignis z. B. ausgeben, wenn der Aufruf einer Datenbank fehlschlägt und Sie die Daten nicht von einer anderen Stelle abrufen können.|303|  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1. Öffnen Sie die Projektmappendatei wcfanalytictracingextensibility.sln in mit Visual Studio 2012.  
  
2. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3. Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
     Klicken Sie im Webbrowser auf **Calculator.svc**. Der URI des WSDL-Dokuments für den Dienst wird daraufhin im Browser angezeigt. Kopieren Sie diesen URI.  
  
4. Führen Sie den WCF-Testclient (WcfTestClient.exe).  
  
     WCF-Testclient (WcfTestClient.exe) befindet sich unter `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`. Der standardmäßige Visual Studio 2012 ist `C:\Program Files\Microsoft Visual Studio 10.0`.  
  
5. Fügen Sie innerhalb der WCF-Testclient den Dienst dazu **Datei**, und klicken Sie dann **Dienst hinzufügen**.  
  
     Fügen Sie die Endpunktadresse im Eingabefeld hinzu.  
  
6. Klicken Sie auf **OK** um das Dialogfeld zu schließen.  
  
     Der ICalculator-Dienst wird im linken Bereich unter hinzugefügt **Meine Dienstprojekte**.  
  
7. Öffnen Sie die Ereignisanzeige.  
  
     Vor dem Aufrufen des Diensts die Ereignisanzeige starten, und stellen Sie sicher, dass das Ereignisprotokoll eine Überwachung für vom WCF-Dienst ausgegebene Überwachungsereignisse ausführt.  
  
8. Von der **starten** , wählen Sie im Menü **Verwaltung**, und klicken Sie dann **Ereignisanzeige**. Aktivieren der **analytisch** und **Debuggen** Protokolle.  
  
9. In der Strukturansicht in der Ereignisanzeige, navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, und klicken Sie dann **Anwendungsserver-Anwendungen**. Mit der rechten Maustaste **Anwendungsserver-Anwendungen**Option **Ansicht**, und klicken Sie dann **analytische und Debugprotokolle**.  
  
     Sicherstellen, dass die **analytische und Debugprotokolle** Option aktiviert ist. Aktivieren der **analytisch** Protokoll.  
  
     In der Strukturansicht in der Ereignisanzeige, navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**,  **Anwendungsserver-Anwendungen**, und klicken Sie dann **analytische**. Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll aktivieren**.  
  
10. Testen Sie den Dienst mit dem WCF-Testclient.  
  
    1. Doppelklicken Sie in der WCF-Testclient auf **Add()** unter dem Knoten ICalculator-Dienst.  
  
         Die **Add()** -Methode wird im rechten Bereich mit zwei Parametern angezeigt.  
  
    2. Geben Sie für den ersten Parameter 2 und für den zweiten Parameter 3 ein.  
  
    3. Klicken Sie auf **Invoke** zum Aufrufen der Methode.  
  
11. Wechseln Sie zu der **Ereignisanzeige** Fenster, das bereits geöffnet ist. Navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, **Anwendung Server-Anwendungen**.  
  
12. Mit der rechten Maustaste die **analytisch** Knoten, und wählen **aktualisieren**.  
  
     Die Ereignisse werden im rechten Bereich angezeigt.  
  
13. Suchen Sie das Ereignis mit der ID 303, und doppelklicken Sie darauf, um es zu öffnen und seinen Inhalt zu untersuchen.  
  
     Dieses Ereignis ausgegeben wurde, indem die `Add()` -Methode des ICalculator-Diensts und verfügt über eine Nutzlast gleich "2 + 3 = 5".  
  
#### <a name="to-clean-up-optional"></a>So führen Sie eine Bereinigung aus (optional)  
  
1. Open **Ereignisanzeige**.  
  
2. Navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, und klicken Sie dann  **Anwendungsserver-Anwendungen**. Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll deaktivieren**.  
  
3. Navigieren Sie zu **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**,  **Anwendungsserver-Anwendungen**, und klicken Sie dann **analytische**. Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll löschen**.  
  
4. Klicken Sie auf **löschen** um die Ereignisse zu löschen.  
  
## <a name="known-issue"></a>Bekanntes Problem  
 Es ist ein bekanntes Problem in der **Ereignisanzeige** , in denen es möglicherweise nicht Decodierung von ETW-Ereignissen. Sie können eine Fehlermeldung angezeigt, die besagt: "Die Beschreibung für Ereigniskennung \<Id > aus der Quelle Microsoft Windows-Anwendungsserver-Anwendungen wurde nicht gefunden. Entweder ist die Komponente, die dieses Ereignis auslöst, nicht auf dem lokalen Computer installiert, oder die Installation ist beschädigt. Sie können installieren oder reparieren Sie die Komponente auf dem lokalen Computer." Wenn dieser Fehler auftritt, wählen Sie **aktualisieren** aus der **Aktionen** Menü. Das Ereignis sollte dann ordnungsgemäß decodiert werden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## <a name="see-also"></a>Siehe auch

- [AppFabric-Überwachungsbeispiele](https://go.microsoft.com/fwlink/?LinkId=193959)
