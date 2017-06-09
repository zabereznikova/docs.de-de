---
title: "Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Caching [.NET Framework]"
  - "Zwischenspeicherung [WPF]"
  - "Exemplarische Vorgehensweisen [WPF], Zwischenspeichern"
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung
Mithilfe der Zwischenspeicherung können Daten für einen schnellen Zugriff im Arbeitsspeicher gespeichert werden.  Wenn erneut auf die Daten zugegriffen wird, können Anwendungen die Daten aus dem Cache abrufen, anstatt sie aus der ursprünglichen Quelle abzurufen.  Dadurch kann die Leistung und Skalierbarkeit verbessert werden.  Zudem bietet die Zwischenspeicherung den Vorteil, dass Daten auch zur Verfügung stehen, wenn die Datenquelle vorübergehend nicht verfügbar ist.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] stellt Klassen bereit, mit denen Sie das Zwischenspeichern in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Anwendungen zu verwenden.  Diese Klassen sind im <xref:System.Runtime.Caching> Namespace.  
  
> [!NOTE]
>  Der <xref:System.Runtime.Caching>\-Namespace ist neu in [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  Dieser Namespace ermöglicht das Zwischenspeichern für alle [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Anwendungen.  In früheren Versionen von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] war das Zwischenspeichern nur im <xref:System.Web>\-Namespace verfügbar und erforderte daher eine Abhängigkeit von ASP.NET\-Klassen.  
  
 In dieser exemplarischen Vorgehensweise wird die Verwendung der Zwischenspeicherungsfunktionen erläutert, die in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] als Teil einer [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Anwendung verfügbar sind.  In der exemplarischen Vorgehensweise wird der Inhalt einer Textdatei zwischengespeichert.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. die folgenden Aufgaben beschrieben:  
  
-   Erstellen eines WPF\-Anwendungsprojekts  
  
-   Hinzufügen eines Verweises zu [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]  
  
-   Initialisieren eines Cache  
  
-   Hinzufügen eines Cacheeintrags, der den Inhalt einer Textdatei enthält  
  
-   Bereitstellen einer Entfernungsrichtlinie für den Cacheeintrag  
  
-   Überwachen des Pfads der zwischengespeicherten Datei und Benachrichtigen der Cacheinstanz über Änderungen am überwachten Element  
  
## Vorbereitungsmaßnahmen  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Microsoft [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
-   Eine Textdatei, die eine kleine Menge an Text enthält.  \(Sie zeigen den Inhalt der Textdatei in einem Meldungsfeld an.\) Der in der exemplarischen Vorgehensweise dargestellte Code setzt voraus, dass Sie mit der folgenden Datei arbeiten:  
  
     `c:\cache\cacheText.txt`  
  
     Sie können jedoch eine beliebige Textdatei verwenden und kleine Änderungen am Code dieser exemplarischen Vorgehensweise vornehmen.  
  
## Erstellen eines WPF\-Anwendungsprojekts  
 Als Erstes erstellen Sie ein WPF\-Anwendungsprojekt.  
  
#### So erstellen Sie eine WPF\-Anwendung  
  
1.  Starten Sie [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
2.  Klicken Sie im Menü **Datei** auf **Neu** und anschließend auf **Neues Projekt**.  
  
     Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
3.  Wählen Sie unter **Installierte Vorlagen** die gewünschte Programmiersprache aus \(**Visual Basic** oder **Visual C\#**\).  
  
4.  Wählen Sie im Dialogfeld **Neues Projekt** die Vorlage **WPF\-Anwendung** aus.  
  
    > [!NOTE]
    >  Falls die Vorlage **WPF\-Anwendung** nicht angezeigt wird, stellen Sie sicher, dass Sie eine [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Version, die WPF unterstützt, als Zielversion festgelegt haben.  Wählen Sie im Dialogfeld **Neues Projekt** in der Liste [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] aus.  
  
5.  Geben Sie im Textfeld **Name** einen Namen für das Projekt an.  Sie können z. B. "WPFCaching" eingeben.  
  
6.  Aktivieren Sie das Kontrollkästchen **Projektmappenverzeichnis erstellen**.  
  
7.  Klicken Sie auf **OK**.  
  
     Der WPF\-Designer wird in der Ansicht **Entwurf** geöffnet, und die Datei "MainWindow.xaml" wird angezeigt.  [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellt den Ordner **Mein Projekt**, die Datei "Application.xaml" und die Datei "MainWindow.xaml".  
  
## Festlegen von .NET Framework als Ziel und Hinzufügen eines Verweises auf die Caching\-Assemblys  
 Standardmäßig ist für WPF\-Anwendungen [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)] als Zielversion festgelegt.  Wenn Sie den <xref:System.Runtime.Caching>\-Namespace in einer WPF\-Anwendung verwenden möchten, muss für die Anwendung [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] als Zielversion festgelegt werden \(nicht [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]\), und die Anwendung muss einen Verweis auf den Namespace enthalten.  
  
 Im nächsten Schritt wird daher die .NET Framework\-Zielversion geändert und ein Verweis auf den <xref:System.Runtime.Caching>\-Namespace hinzugefügt.  
  
> [!NOTE]
>  Die Prozedur zum Ändern der .NET Framework\-Zielversion unterscheidet sich bei Visual Basic\- und Visual C\#\-Projekten.  
  
#### So ändern Sie die .NET Framework\-Zielversion in Visual Basic  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Projektnamen, und klicken Sie dann auf **Eigenschaften**.  
  
     Das Eigenschaftenfenster für die Anwendung wird angezeigt.  
  
2.  Klicken Sie auf die Registerkarte **Kompilieren**.  
  
3.  Klicken Sie unten im Fenster auf **Erweiterte Kompilierungsoptionen**.  
  
     Das Dialogfeld **Erweiterte Compilereinstellungen** wird angezeigt.  
  
4.  In der **Zielframework \(alle Konfigurationen\)** Liste ausgewähltes [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  \(Wählen Sie [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]nicht aus.\)  
  
5.  Klicken Sie auf **OK**.  
  
     Das Dialogfeld **Änderung des Zielframeworks** wird angezeigt.  
  
6.  Klicken Sie im Dialogfeld **Änderung des Zielframeworks** auf **Ja**.  
  
     Das Projekt wird geschlossen und dann erneut geöffnet.  
  
7.  Fügen Sie einen Verweis auf die Caching\-Assembly hinzu, indem Sie die folgenden Schritte ausführen:  
  
    1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Projekt, und klicken Sie anschließend auf **Verweis hinzufügen**.  
  
    2.  Klicken Sie auf die Registerkarte **.NET**, wählen Sie `System.Runtime.Caching` aus, und klicken Sie dann auf **OK**.  
  
#### So ändern Sie die .NET Framework\-Zielversion in einem Visual C\#\-Projekt  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Projektnamen und dann auf **Eigenschaften**.  
  
     Das Eigenschaftenfenster für die Anwendung wird angezeigt.  
  
2.  Klicken Sie auf die Registerkarte **Anwendung**.  
  
3.  Wählen Sie in der Liste **Zielframework** [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] aus.  \(Wählen Sie nicht **.NET Framework 4 Client Profile** aus.\)  
  
4.  Fügen Sie einen Verweis auf die Caching\-Assembly hinzu, indem Sie die folgenden Schritte ausführen:  
  
    1.  Klicken Sie mit der rechten Maustaste auf den Ordner **Verweise**, und wählen Sie dann **Verweis hinzufügen** aus.  
  
    2.  Klicken Sie auf die Registerkarte **.NET**, wählen Sie `System.Runtime.Caching` aus, und klicken Sie dann auf **OK**.  
  
## Hinzufügen einer Schaltfläche zum WPF\-Fenster  
 Als Nächstes fügen Sie ein Schaltflächen\-Steuerelement hinzu, und Sie erstellen einen Ereignishandler für das `Click`\-Ereignis der Schaltfläche.  Später fügen Sie Code hinzu, damit beim Klicken auf die Schaltfläche der Inhalt der Textdatei zwischengespeichert und angezeigt wird.  
  
#### So fügen Sie ein Schaltflächen\-Steuerelement hinzu  
  
1.  Doppelklicken Sie im **Projektmappen\-Explorer** auf die Datei "MainWindow.xaml, um sie zu öffnen.  
  
2.  Ziehen Sie aus der **Toolbox** unter **Häufig verwendete WPF\-Steuerelemente** ein `Button`\-Steuerelement in das `MainWindow`\-Fenster.  
  
3.  Legen Sie im Fenster **Eigenschaften** die `Content`\-Eigenschaft des `Button`\-Steuerelements auf "Cache abrufen" fest.  
  
## Initialisieren des Cache und Zwischenspeichern eines Eintrags  
 Als Nächstes fügen Sie den Code hinzu, um die folgenden Aufgaben auszuführen:  
  
-   Erstellen Sie eine Instanz der Cacheklasse, d. h. Sie instanziieren ein neues <xref:System.Runtime.Caching.MemoryCache>\-Objekt.  
  
-   Geben Sie an, dass der Cache ein <xref:System.Runtime.Caching.HostFileChangeMonitor>\-Objekt zum Überwachen der Änderungen in der Textdatei verwendet.  
  
-   Lesen Sie die Textdatei, und zwischenspeichern Sie den Inhalt als Cacheeintrag.  
  
-   Zeigen Sie den Inhalt der zwischengespeicherten Textdatei an.  
  
#### So erstellen Sie das Cacheobjekt  
  
1.  Doppelklicken Sie auf die Schaltfläche, die Sie gerade hinzugefügt haben, um einen Ereignishandler in der Datei "MainWindow.xaml.cs" bzw. "MainWindow.Xaml.vb" zu erstellen.  
  
2.  Fügen Sie am Anfang der Datei \(vor der Klassendeklaration\) die folgenden `Imports`\-Anweisungen \(Visual Basic\) oder `using`\-Anweisungen \(Visual C\#\) hinzu:  
  
    ```csharp  
    using System.Runtime.Caching;  
    using System.IO;  
    ```  
  
    ```vb  
    Imports System.Runtime.Caching  
    Imports System.IO  
    ```  
  
3.  Fügen Sie im Ereignishandler den folgenden Code hinzu, um das Cacheobjekt zu instanziieren:  
  
    ```csharp  
    ObjectCache cache = MemoryCache.Default;  
    ```  
  
    ```vb  
    Dim cache As ObjectCache = MemoryCache.Default  
    ```  
  
     Die <xref:System.Runtime.Caching.ObjectCache>\-Klasse ist eine integrierte Klasse, die einen Objektcache im Arbeitsspeicher bereitstellt.  
  
4.  Fügen Sie den folgenden Code hinzu, um den Inhalt eines Cacheeintrags mit dem Namen `filecontents` zu lesen:  
  
    ```vb  
    Dim fileContents As String = TryCast(cache("filecontents"), String)  
    ```  
  
    ```csharp  
    string fileContents = cache["filecontents"] as string;  
    ```  
  
5.  Fügen Sie den folgenden Code hinzu, um zu überprüfen, ob der Cacheeintrag mit dem Namen `filecontents` vorhanden ist:  
  
    ```vb  
    If fileContents Is Nothing Then  
  
    End If  
    ```  
  
    ```csharp  
    if (fileContents == null)  
    {  
  
    }  
    ```  
  
     Wenn der angegebene Cacheeintrag nicht vorhanden ist, müssen Sie die Textdatei lesen und sie dem Cache als Cacheeintrag hinzufügen.  
  
6.  Fügen Sie im `if/then`\-Block den folgenden Code hinzu, um ein neues <xref:System.Runtime.Caching.CacheItemPolicy>\-Objekt zu erstellen, das angibt, dass der Cacheeintrag nach 10 Sekunden abläuft.  
  
    ```vb  
    Dim policy As New CacheItemPolicy()  
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)  
    ```  
  
    ```csharp  
    CacheItemPolicy policy = new CacheItemPolicy();  
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);  
    ```  
  
     Wenn keine Entfernungs\- oder Ablaufinformationen bereitgestellt werden, ist <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration> die Standardeinstellung. Dies bedeutet, dass Cacheeinträge niemals nur basierend auf einer absoluten Zeit ablaufen.  Stattdessen laufen Cacheeinträge nur ab, wenn kein ausreichender Arbeitsspeicher vorhanden ist.  Als Best Practice sollten Sie immer explizit entweder einen absoluten oder variablen Ablauf bereitstellen.  
  
7.  Fügen Sie im `if/then`\-Block nach dem im vorherigen Schritt hinzugefügten Code den folgenden Code hinzu, um eine Auflistung für die zu überwachenden Dateipfade zu erstellen und der Auflistung den Pfad der Textdatei hinzufügen:  
  
    ```vb  
    Dim filePaths As New List(Of String)()  
    filePaths.Add("c:\cache\cacheText.txt")  
    ```  
  
    ```csharp  
    List<string> filePaths = new List<string>();  
    filePaths.Add("c:\\cache\\cacheText.txt");  
    ```  
  
    > [!NOTE]
    >  Wenn Sie nicht die Textdatei `c:\cache\cacheText.txt` verwenden möchten, geben Sie den Pfad der gewünschten Textdatei an.  
  
8.  Fügen Sie nach dem im vorherigen Schritt hinzugefügten Code den folgenden Code hinzu, um ein neues <xref:System.Runtime.Caching.HostFileChangeMonitor>\-Objekt für die Auflistung von Änderungsüberwachungen für den Cacheeintrag hinzuzufügen:  
  
    ```vb  
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))  
    ```  
  
    ```csharp  
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));  
    ```  
  
     Das <xref:System.Runtime.Caching.HostFileChangeMonitor>\-Objekt überwacht den Pfad der Textdatei und benachrichtigt den Cache, wenn Änderungen auftreten.  In diesem Beispiel läuft der Cacheeintrag ab, wenn sich der Inhalt der Datei ändert.  
  
9. Fügen Sie nach dem im vorherigen Schritt hinzugefügten Code den folgenden Code hinzu, um den Inhalt der Textdatei zu lesen:  
  
    ```vb  
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()  
    ```  
  
    ```csharp  
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + + "\n" + DateTime.Now;   
    ```  
  
     Der Datum\- und Uhrzeitzeitstempel wird hinzugefügt, sodass Sie sehen können, wann der Cacheeintrag abläuft.  
  
10. Fügen Sie nach dem im vorherigen Schritt hinzugefügten Code den folgenden Code hinzu, um den Inhalt der Datei als <xref:System.Runtime.Caching.CacheItem>\-Instanz in das Cacheobjekt einzufügen:  
  
    ```vb  
    cache.Set("filecontents", fileContents, policy)  
    ```  
  
    ```csharp  
    cache.Set("filecontents", fileContents, policy);  
    ```  
  
     Sie können Informationen dazu angeben, wie der Cacheeintrag entfernt werden soll, indem Sie das zuvor erstellte <xref:System.Runtime.Caching.CacheItemPolicy>\-Objekt als Parameter übergeben.  
  
11. Fügen Sie nach dem `if/then`\-Block den folgenden Code hinzu, um den zwischengespeicherten Dateiinhalt in einem Meldungsfeld anzuzeigen:  
  
    ```vb  
    MessageBox.Show(fileContents)  
    ```  
  
    ```csharp  
    MessageBox.Show(fileContents);  
    ```  
  
12. Klicken Sie im Menü **Erstellen** auf **WPFCaching erstellen**, um das Projekt zu erstellen.  
  
## Testen der Zwischenspeicherung in der WPF\-Anwendung  
 Sie können die Anwendung jetzt testen.  
  
#### So testen Sie die Zwischenspeicherung in der WPF\-Anwendung  
  
1.  Drücken Sie STRG\+F5, um die Anwendung auszuführen.  
  
     Das `MainWindow`\-Fenster wird angezeigt.  
  
2.  Klicken Sie auf **Cache abrufen**.  
  
     Der zwischengespeicherte Inhalt der Textdatei wird in einem Meldungsfeld angezeigt.  Beachten Sie den Zeitstempel der Datei.  
  
3.  Schließen Sie das Meldungsfeld, und klicken Sie dann erneut auf **Cache abrufen**.  
  
     Der Zeitstempel ist unverändert.  Das bedeutet, dass der zwischengespeicherte Inhalt angezeigt wird.  
  
4.  Warten Sie mindestens 10 Sekunden, und klicken Sie dann erneut auf **Cache abrufen**.  
  
     Dieses Mal wird ein neuer Zeitstempel angezeigt.  Dies bedeutet, dass der Cache aufgrund der Cacherichtlinie nach 10 Sekunden abgelaufen ist und neuer zwischengespeicherter Inhalt angezeigt wird.  
  
5.  Öffnen Sie die erstellte Textdatei in einem Text\-Editor.  Nehmen Sie noch keine Änderungen vor.  
  
6.  Schließen Sie das Meldungsfeld, und klicken Sie dann erneut auf **Cache abrufen**.  
  
     Beachten Sie wieder den Zeitstempel.  
  
7.  Nehmen Sie eine Änderung an der Textdatei vor, und speichern Sie dann die Datei.  
  
8.  Schließen Sie das Meldungsfeld, und klicken Sie dann erneut auf **Cache abrufen**.  
  
     Dieses Meldungsfeld enthält den aktualisierten Inhalt der Textdatei und einen neuen Zeitstempel.  Dies bedeutet, dass die Hostdatei\-Änderungsüberwachung den Cacheeintrag sofort entfernt hat, als Sie die Datei geändert haben, obwohl das absolute Timeout nicht abgelaufen war.  
  
    > [!NOTE]
    >  Sie können die Entfernungszeit auf 20 Sekunden oder mehr erhöhen, damit Sie mehr Zeit haben, um in der Datei eine Änderung vornehmen.  
  
## Codebeispiel  
 Nachdem Sie diese exemplarische Vorgehensweise abgeschlossen haben, entspricht der Code für das von Ihnen erstellte Projekt dem folgenden Beispiel.  
  
 [!code-csharp[CachingWPFApplications#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]  
  
## Siehe auch  
 <xref:System.Runtime.Caching.MemoryCache>   
 <xref:System.Runtime.Caching.ObjectCache>   
 <xref:System.Runtime.Caching>   
 [Caching in .NET Framework\-Anwendungen](../../../../docs/framework/performance/caching-in-net-framework-applications.md)