---
title: 'Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
caps.latest.revision: 25
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a8d3fe2dbfe0b4b5fb9081d71cec080dfa54add8
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a>Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung
Das Zwischenspeichern ermöglicht es Ihnen, Daten für schnellen Zugriff im Arbeitsspeicher zu speichern. Die Daten erneut zugegriffen wird, können Anwendungen die Daten aus dem Cache, die sie aus der Originalquelle stattdessen abrufen zu erzielen. Dies kann die Leistung und Skalierbarkeit verbessern. Darüber hinaus macht das Zwischenspeichern Daten verfügbar, wenn die Datenquelle vorübergehend nicht verfügbar ist.  
  
 Die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] bietet Klassen, die Ihnen ermöglichen, verwenden der Zwischenspeicherung in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Anwendungen. Diese Klassen befinden sich der <xref:System.Runtime.Caching> Namespace.  
  
> [!NOTE]
>  Die <xref:System.Runtime.Caching> Namespace ist neu in der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]. Dieser Namespace stellt Zwischenspeichern steht allen [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Anwendungen. In früheren [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Versionen war die Zwischenspeicherung nur im <xref:System.Web>-Namespace verfügbar, und erforderte daher eine Abhängigkeit der ASP.NET-Klassen.  
  
 In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie die Funktionen zum Zwischenspeichern verwenden, das in verfügbar ist die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] als Teil einer [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendung. In der exemplarischen Vorgehensweise Zwischenspeichern Sie den Inhalt einer Textdatei.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. die folgenden Aufgaben beschrieben:  
  
-   Erstellen ein WPF-Anwendungsprojekt.  
  
-   Hinzufügen eines Verweises auf die [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
-   Initialisieren einen Cache.  
  
-   Hinzufügen eines Cache-Eintrags mit dem Inhalt einer Textdatei.  
  
-   Bereitstellen einer Entfernungsrichtlinie für den Cacheeintrag.  
  
-   Überwachen den Pfad der zwischengespeicherte Datei und die Cacheinstanz zu benachrichtigen, die in der Überwachungskapazität für Elemente geändert werden.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Microsoft [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
-   Eine Textdatei, die eine kleine Menge an Text enthält. (Der Inhalt der Textdatei wird in einem Meldungsfeld angezeigt werden.) In der exemplarischen Vorgehensweise dargestellte Code wird davon ausgegangen, dass Sie mit der folgenden Datei arbeiten:  
  
     `c:\cache\cacheText.txt`  
  
     Allerdings können Sie eine Textdatei verwenden und kleine Änderungen an den Code in dieser exemplarischen Vorgehensweise.  
  
## <a name="creating-a-wpf-application-project"></a>Erstellen eines WPF-Anwendungsprojekts  
 Sie werden gestartet, indem Sie ein WPF-Anwendungsprojekt erstellen.  
  
#### <a name="to-create-a-wpf-application"></a>So erstellen Sie eine WPF-Anwendung.  
  
1.  Starten Sie Visual Studio.  
  
2.  In der **Datei** Menü klicken Sie auf **neu**, und klicken Sie dann auf **neues Projekt**.  
  
     Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
3.  Klicken Sie unter **installierte Vorlagen**, wählen Sie die Programmiersprache ab, die Sie verwenden möchten (**Visual Basic** oder **Visual C#-**).  
  
4.  In der **neues Projekt** wählen Sie im Dialogfeld **WPF-Anwendung**.  
  
    > [!NOTE]
    >  Wenn Sie nicht sehen die **WPF-Anwendung** Vorlage, stellen Sie sicher, dass eine Version des anvisierten der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] , die WPF unterstützt. In der **neues Projekt** wählen Sie im Dialogfeld [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] aus der Liste.  
  
5.  In der **Namen** Text Geben Sie einen Namen für das Projekt. Sie können z. B. eingeben **"WPFCaching"**.  
  
6.  Wählen Sie die **Projektmappenverzeichnis erstellen** Kontrollkästchen.  
  
7.  Klicken Sie auf **OK**.  
  
     Der WPF-Designer wird geöffnet, **Entwurf** anzeigen und die Datei "MainWindow.xaml" angezeigt. Visual Studio erstellt die **Mein Projekt** Ordner die Datei "Application.xaml" und die Datei "MainWindow.xaml".  
  
## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a>Für .NET Framework und Hinzufügen eines Verweises auf die Caching-Assemblys  
 Standardmäßig ist Ziel der WPF-Anwendungen die [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]. Verwenden der <xref:System.Runtime.Caching> Namespace in einer WPF-Anwendung, die Anwendung muss Ziel der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (nicht die [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) und einen Verweis auf den Namespace enthalten.  
  
 Daher ist der nächste Schritt zum Ändern der Zielversion von .NET Framework, und fügen einen Verweis auf die <xref:System.Runtime.Caching> Namespace.  
  
> [!NOTE]
>  Das Verfahren zum Ändern der Zielversion von .NET Framework unterscheidet sich in einem Visual Basic-Projekt und in einem Visual C#-Projekt.  
  
#### <a name="to-change-the-target-net-framework-in-visual-basic"></a>So ändern Sie das Ziel-.NET Framework in Visual Basic  
  
1.  In **Projektmappen-Explorer**mit der rechten Maustaste auf den Projektnamen, und klicken Sie dann auf **Eigenschaften**.  
  
     Das Eigenschaftenfenster für die Anwendung wird angezeigt.  
  
2.  Klicken Sie auf die Registerkarte **Kompilieren**.  
  
3.  Klicken Sie am unteren Rand des Fensters, **Erweiterte Kompilierungsoptionen...** .  
  
     Die **erweiterte Compilereinstellungen** Dialogfeld wird angezeigt.  
  
4.  In der **Zielframework (alle Konfigurationen)** Liste [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]. (Wählen Sie nicht [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)  
  
5.  Klicken Sie auf **OK**.  
  
     Die **Änderung des Zielframeworks** Dialogfeld wird angezeigt.  
  
6.  In der **Änderung des Zielframeworks** (Dialogfeld), klicken Sie auf **Ja**.  
  
     Das Projekt wird geschlossen und erneut geöffnet wird.  
  
7.  Fügen Sie einen Verweis auf die caching-Assembly hinzu, durch die folgenden Schritte:  
  
    1.  In **Projektmappen-Explorer**mit der rechten Maustaste auf den Namen des Projekts, und klicken Sie dann auf **Verweis hinzufügen**.  
  
    2.  Wählen Sie die **.NET** Registerkarte `System.Runtime.Caching`, und klicken Sie dann auf **OK**.  
  
#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a>So ändern Sie das Ziel-.NET Framework in einem Visual C#-Projekt  
  
1.  In **Projektmappen-Explorer**mit der rechten Maustaste auf den Projektnamen, und klicken Sie dann auf **Eigenschaften**.  
  
     Das Eigenschaftenfenster für die Anwendung wird angezeigt.  
  
2.  Klicken Sie auf die Registerkarte **Anwendung** .  
  
3.  In der **Zielframework** Liste [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]. (Wählen Sie nicht **.NET Framework 4 Client Profile**.)  
  
4.  Fügen Sie einen Verweis auf die caching-Assembly hinzu, durch die folgenden Schritte:  
  
    1.  Mit der rechten Maustaste die **Verweise** Ordner, und klicken Sie dann auf **Verweis hinzufügen**.  
  
    2.  Wählen Sie die **.NET** Registerkarte `System.Runtime.Caching`, und klicken Sie dann auf **OK**.  
  
## <a name="adding-a-button-to-the-wpf-window"></a>Hinzufügen einer Schaltfläche zum WPF-Fenster  
 Als Nächstes fügen Sie ein Button-Steuerelement und erstellen Sie einen Ereignishandler für der Schaltfläche `Click` Ereignis. Später fügen Sie Code hinzu, wenn Sie die Schaltfläche klicken, den Inhalt der Textdatei zwischengespeichert und angezeigt werden.  
  
#### <a name="to-add-a-button-control"></a>So fügen Sie ein Button-Steuerelement hinzu  
  
1.  In **Projektmappen-Explorer**, doppelklicken Sie auf die Datei "MainWindow.xaml", um ihn zu öffnen.  
  
2.  Aus der **Toolbox**unter **WPF-Standardsteuerelementen**, ziehen Sie eine `Button` die Steuerung an die `MainWindow` Fenster.  
  
3.  In der **Eigenschaften** legen die `Content` Eigenschaft von der `Button` die Steuerung an **Cache abrufen**.  
  
## <a name="initializing-the-cache-and-caching-an-entry"></a>Initialisieren des Caches und Zwischenspeichern eines Eintrags  
 Anschließend fügen Sie den Code, um die folgenden Aufgaben ausführen:  
  
-   Erstellen Sie eine Instanz der Cacheklasse – d. h., instanziieren Sie ein neues <xref:System.Runtime.Caching.MemoryCache> Objekt.  
  
-   Gibt an, dass der Cache verwendet einen <xref:System.Runtime.Caching.HostFileChangeMonitor> Objekt zum Überwachen von Änderungen in der Textdatei.  
  
-   Lesen Sie die Textdatei, und sein Inhalt als einen Eintrag im Cache zwischengespeichert.  
  
-   Zeigt den Inhalt der zwischengespeicherten Textdatei.  
  
#### <a name="to-create-the-cache-object"></a>Zum Erstellen des Cache-Objekts  
  
1.  Doppelklicken Sie auf die Schaltfläche, die Sie gerade hinzugefügt haben, um einen Ereignishandler in der Datei "MainWindow.Xaml.cs" oder "MainWindow.Xaml.vb" zu erstellen.  
  
2.  Fügen Sie am Anfang der Datei (vor der Klassendeklaration) die folgenden `Imports` (Visual Basic) oder `using` (c#)-Anweisungen:  
  
    ```csharp  
    using System.Runtime.Caching;  
    using System.IO;  
    ```  
  
    ```vb  
    Imports System.Runtime.Caching  
    Imports System.IO  
    ```  
  
3.  Fügen Sie in der Ereignishandler den folgenden Code zum Instanziieren des Cache-Objekts:  
  
    ```csharp  
    ObjectCache cache = MemoryCache.Default;  
    ```  
  
    ```vb  
    Dim cache As ObjectCache = MemoryCache.Default  
    ```  
  
     Die <xref:System.Runtime.Caching.ObjectCache> ist eine integrierte Klasse, die einen in-Memory-Objektcache bereitstellt.  
  
4.  Hinzufügen des folgenden Codes zum Lesen des Inhalts eines Cache-Eintrags mit dem Namen `filecontents`:  
  
    ```vb  
    Dim fileContents As String = TryCast(cache("filecontents"), String)  
    ```  
  
    ```csharp  
    string fileContents = cache["filecontents"] as string;  
    ```  
  
5.  Fügen Sie den folgenden Code zum Überprüfen, ob der Cacheeintrag mit dem Namen `filecontents` vorhanden ist:  
  
    ```vb  
    If fileContents Is Nothing Then  
  
    End If  
    ```  
  
    ```csharp  
    if (fileContents == null)  
    {  
  
    }  
    ```  
  
     Der angegebene Cacheeintrag nicht vorhanden ist, müssen Lesen die Textdatei und als einen Cacheeintrag in den Cache hinzufügen.  
  
6.  In der `if/then` blockieren, fügen Sie den folgenden Code zum Erstellen eines neuen <xref:System.Runtime.Caching.CacheItemPolicy> Objekt, das angibt, dass nach 10 Sekunden der Cacheeintrag abläuft.  
  
    ```vb  
    Dim policy As New CacheItemPolicy()  
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)  
    ```  
  
    ```csharp  
    CacheItemPolicy policy = new CacheItemPolicy();  
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);  
    ```  
  
     Wenn keine Entfernung oder den Ablauf von Informationen bereitgestellt wird, ist die Standardeinstellung <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, was bedeutet, dass die Einträge im Cache nur auf einem absoluten Zeitpunkt nie basierend ablaufen. Stattdessen ablaufen Cacheeinträge nur, wenn Arbeitsspeicher vorhanden ist. Als bewährte Methode sollten Sie entweder ein absoluter oder ein Wetterseite Ablauf immer explizit bereitstellen.  
  
7.  Innerhalb der `if/then` blockieren und gemäß den Code, die Sie im vorherigen Schritt hinzugefügt haben, fügen Sie den folgenden Code zum Erstellen einer Auflistung für die Dateipfade, die zur Überwachung sowie den Pfad der Textdatei, die Auflistung hinzugefügt werden sollen:  
  
    ```vb  
    Dim filePaths As New List(Of String)()  
    filePaths.Add("c:\cache\cacheText.txt")  
    ```  
  
    ```csharp  
    List<string> filePaths = new List<string>();  
    filePaths.Add("c:\\cache\\cacheText.txt");  
    ```  
  
    > [!NOTE]
    >  Die Textdatei, die Sie verwenden möchten ist nicht `c:\cache\cacheText.txt`, geben Sie den Pfad die Textdatei, die Sie verwenden möchten.  
  
8.  Hinter dem Code, die Sie im vorherigen Schritt hinzugefügt haben, fügen Sie den folgenden Code zum Hinzufügen einer neuen <xref:System.Runtime.Caching.HostFileChangeMonitor> Objekt, das die Auflistung der Änderung für den Cacheeintrag überwacht:  
  
    ```vb  
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))  
    ```  
  
    ```csharp  
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));  
    ```  
  
     Die <xref:System.Runtime.Caching.HostFileChangeMonitor> -Objekt überwacht die Textdatei Pfad und den Cache benachrichtigt, wenn Änderungen auftreten. In diesem Beispiel wird der Cacheeintrag abläuft, wenn der Inhalt der Datei geändert.  
  
9. Fügen Sie nach dem Code, der Sie im vorherigen Schritt hinzugefügt haben den folgenden Code zum Lesen des Inhalts der Textdatei hinzu:  
  
    ```vb  
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()  
    ```  
  
    ```csharp  
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + + "\n" + DateTime.Now;   
    ```  
  
     Der Datums- und Zeitstempel hinzugefügt, damit Sie werden sehen, wenn der Cacheeintrag abläuft.  
  
10. Hinter dem Code, die Sie im vorherigen Schritt hinzugefügt haben, fügen Sie den folgenden Code zum Einfügen von den Inhalt der Datei in das Cacheobjekt als eine <xref:System.Runtime.Caching.CacheItem> Instanz:  
  
    ```vb  
    cache.Set("filecontents", fileContents, policy)  
    ```  
  
    ```csharp  
    cache.Set("filecontents", fileContents, policy);  
    ```  
  
     Geben Sie Informationen wie der Cacheeintrag soll, indem übergeben entfernt werden der <xref:System.Runtime.Caching.CacheItemPolicy> -Objekt, das Sie zuvor erstellt, als Parameter haben.  
  
11. Nach der `if/then` blockieren, fügen Sie folgenden Code aus, um den zwischengespeicherten Dateiinhalt in einem Meldungsfeld anzuzeigen:  
  
    ```vb  
    MessageBox.Show(fileContents)  
    ```  
  
    ```csharp  
    MessageBox.Show(fileContents);  
    ```  
  
12. In der **erstellen** Menü klicken Sie auf **"WPFCaching erstellen"** zum Erstellen des Projekts.  
  
## <a name="testing-caching-in-the-wpf-application"></a>Testen der Zwischenspeicherung in der WPF-Anwendung  
 Sie können nun die Anwendung testen.  
  
#### <a name="to-test-caching-in-the-wpf-application"></a>So testen Sie caching in der WPF-Anwendung  
  
1.  Drücken Sie STRG+F5, um die Anwendung auszuführen.  
  
     Die `MainWindow` Fenster wird angezeigt.  
  
2.  Klicken Sie auf **Cache abrufen**.  
  
     Zwischengespeicherte Inhalt aus der Textdatei wird in einem Meldungsfeld angezeigt. Beachten Sie den Zeitstempel der Datei.  
  
3.  Das Meldungsfeld zu schließen, und klicken Sie dann auf **Cache abrufen** erneut **.**  
  
     Der Zeitstempel ist unverändert. Dies gibt an, dass zwischengespeicherte Inhalt angezeigt wird.  
  
4.  Warten Sie mindestens 10 Sekunden festzulegen, und klicken Sie dann auf **Cache abrufen** erneut aus.  
  
     Dieses Mal wird ein neuer Zeitstempel angezeigt. Dies gibt an, dass die Richtlinie des Eintrags im Cache ablaufen lassen und neue zwischengespeicherte Inhalte angezeigt wird.  
  
5.  Öffnen Sie in einem Text-Editor die Textdatei, die Sie erstellt haben. Nehmen Sie Änderungen noch nicht.  
  
6.  Das Meldungsfeld zu schließen, und klicken Sie dann auf **Cache abrufen** erneut **.**  
  
     Beachten Sie den Zeitstempel erneut ein.  
  
7.  Nehmen Sie eine Änderung in der Textdatei, und speichern Sie die Datei.  
  
8.  Das Meldungsfeld zu schließen, und klicken Sie dann auf **Cache abrufen** erneut aus.  
  
     Das Meldungsfeld enthält des aktualisierten Inhalts aus der Textdatei und einen neuen Zeitstempel. Dies gibt an, dass der Hostdatei geändert Monitor der Cacheeintrag entfernt sofort, wenn Sie die Datei geändert haben, obwohl das absolute Timeout nicht abgelaufen ist.  
  
    > [!NOTE]
    >  Sie können die Entfernungszeit auf 20 Sekunden oder mehr zusätzlichen Zeitaufwand für das Sie in der Datei ändern zu erhöhen.  
  
## <a name="code-example"></a>Codebeispiel  
 Nachdem Sie diese exemplarische Vorgehensweise abgeschlossen haben, wird der Code für das Projekt erstellten im folgende Beispiel entsprechen.  
  
 [!code-csharp[CachingWPFApplications#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.Caching.MemoryCache>  
 <xref:System.Runtime.Caching.ObjectCache>  
 <xref:System.Runtime.Caching>  
 [Caching in .NET Framework Applications (Caching in .NET Framework-Anwendungen)](../../../../docs/framework/performance/caching-in-net-framework-applications.md)
