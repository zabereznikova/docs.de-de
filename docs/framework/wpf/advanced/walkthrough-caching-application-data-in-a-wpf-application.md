---
title: App-Daten zwischenspeichern
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
ms.openlocfilehash: b7d999f94e2f2ae410a16e537d51c0f890def4e1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728059"
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a>Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung
Das Zwischenspeichern ermöglicht es Ihnen, Daten für schnellen Zugriff im Arbeitsspeicher zu speichern. Wenn erneut auf die Daten zugegriffen wird, erhalten Anwendungen die Daten aus dem Zwischenspeicher, anstatt sie aus der Originalquelle abzurufen. Dies kann die Leistung und Skalierbarkeit verbessern. Darüber hinaus macht das Zwischenspeichern Daten verfügbar, wenn die Datenquelle vorübergehend nicht verfügbar ist.

 Der .NET Framework stellt Klassen bereit, die es Ihnen ermöglichen, das Caching in .NET Framework Anwendungen zu verwenden. Diese Klassen befinden sich im <xref:System.Runtime.Caching>-Namespace.

> [!NOTE]
> Der <xref:System.Runtime.Caching>-Namespace ist neu in .NET Framework 4. Dieser Namespace macht das Zwischenspeichern für alle .NET Framework Anwendungen verfügbar. In früheren Versionen der .NET Framework war das Zwischenspeichern nur im <xref:System.Web>-Namespace verfügbar und erforderte daher eine Abhängigkeit von ASP.NET-Klassen.

 In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie die im .NET Framework verfügbare cachingrichtfunktion als Teil einer [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendung verwenden. In der exemplarischen Vorgehensweise Zwischenspeichern Sie den Inhalt einer Textdatei.

 In dieser exemplarischen Vorgehensweise werden u. a. die folgenden Aufgaben beschrieben:

- Erstellen eines WPF-Anwendungs Projekts.

- Hinzufügen eines Verweises auf die .NET Framework 4.

- Initialisieren eines Caches.

- Hinzufügen eines Cache Eintrags, der den Inhalt einer Textdatei enthält.

- Bereitstellen einer Entfernungs Richtlinie für den Cache Eintrag.

- Überwachen des Pfads der zwischengespeicherten Datei und Benachrichtigen der Cache Instanz über Änderungen am überwachten Element.

## <a name="prerequisites"></a>Erforderliche Komponenten
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:

- Visual Studio 2010.

- Eine Textdatei, die eine kleine Menge an Text enthält. (Der Inhalt der Textdatei wird in einem Meldungs Feld angezeigt.) Der in der exemplarischen Vorgehensweise dargestellte Code setzt voraus, dass Sie mit der folgenden Datei arbeiten:

     `c:\cache\cacheText.txt`

     Allerdings können Sie eine beliebige Textdatei verwenden und kleinere Änderungen am Code in dieser exemplarischen Vorgehensweise vornehmen.

## <a name="creating-a-wpf-application-project"></a>Erstellen eines WPF-Anwendungs Projekts
 Zunächst erstellen Sie ein WPF-Anwendungsprojekt.

#### <a name="to-create-a-wpf-application"></a>So erstellen Sie eine WPF-Anwendung.

1. Starten Sie Visual Studio.

2. Klicken Sie im Menü **Datei** auf **neu**, und klicken Sie dann auf **Neues Projekt**.

     Das Dialogfeld **Neues Projekt** wird angezeigt.

3. Wählen Sie unter **installierte Vorlagen**die Programmiersprache aus, die Sie verwenden möchten (**Visual Basic** oder **Visual C#** ).

4. Wählen Sie im Dialogfeld **Neues Projekt** die Option **WPF-Anwendung**aus.

    > [!NOTE]
    > Wenn die **WPF-Anwendungs** Vorlage nicht angezeigt wird, stellen Sie sicher, dass Sie auf eine Version der .NET Framework abzielen, die WPF unterstützt. Wählen Sie im Dialogfeld **Neues Projekt** in der Liste .NET Framework 4 aus.

5. Geben Sie im Textfeld **Name** einen Namen für das Projekt ein. Sie können z. b. **wpfcaching**eingeben.

6. Aktivieren Sie das Kontrollkästchen **Verzeichnis für Projektmappe erstellen**.

7. Klicken Sie auf **OK**.

     Der WPF-Designer wird in der **Entwurfs** Ansicht geöffnet und zeigt die Datei "MainWindow. XAML" an. Visual Studio erstellt den Ordner " **My Project** ", die Datei "Application. XAML" und die Datei "MainWindow. XAML".

## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a>.NET Framework und Hinzufügen eines Verweises auf die cacheassemblys
 Standardmäßig richten sich WPF-Anwendungen an das .NET Framework 4 Client Profile. Um den <xref:System.Runtime.Caching>-Namespace in einer WPF-Anwendung zu verwenden, muss die Anwendung auf .NET Framework 4 (nicht auf das .NET Framework 4-Client Profil) abzielen und muss einen Verweis auf den-Namespace enthalten.

 Der nächste Schritt besteht daher darin, das .NET Framework Ziel zu ändern und einen Verweis auf den <xref:System.Runtime.Caching>-Namespace hinzuzufügen.

> [!NOTE]
> Die Vorgehensweise zum Ändern des .NET Framework Ziels unterscheidet sich in einem Visual Basic Projekt und in C# einem visuellen Projekt.

#### <a name="to-change-the-target-net-framework-in-visual-basic"></a>So ändern Sie die Ziel .NET Framework in Visual Basic

1. Klicken Sie im Projektmappen- **Explorer**mit der rechten Maustaste auf den Projektnamen, und klicken Sie auf **Eigenschaften**.

     Das Fenster Eigenschaften für die Anwendung wird angezeigt.

2. Klicken Sie auf die Registerkarte **Kompilieren**.

3. Klicken Sie am unteren Rand des Fensters auf **Erweiterte Kompilierungsoptionen...** .

     Das Dialogfeld **Erweiterte Compilereinstellungen** wird angezeigt.

4. Wählen Sie in der Liste **Ziel Framework (alle Konfigurationen)** die Option .NET Framework 4 aus. (Wählen Sie nicht .NET Framework 4 Client Profil aus.)

5. Klicken Sie auf **OK**.

     Das Dialogfeld **Änderung des Zielframeworks** wird angezeigt.

6. Klicken Sie im Dialogfeld **Ziel Framework-Änderung** auf **Ja**.

     Das Projekt ist geschlossen und wird dann erneut geöffnet.

7. Fügen Sie einen Verweis auf die Cacheassembly hinzu, indem Sie die folgenden Schritte ausführen:

    1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf den Namen des Projekts, und klicken Sie dann auf **Verweis hinzufügen**.

    2. Wählen Sie die Registerkarte **.net** , wählen Sie `System.Runtime.Caching`aus, und klicken Sie dann auf **OK**.

#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a>So ändern Sie die Ziel .NET Framework in einem C# visuellen Projekt

1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf den Projektnamen, und klicken Sie dann auf **Eigenschaften**.

     Das Fenster Eigenschaften für die Anwendung wird angezeigt.

2. Klicken Sie auf die Registerkarte **Anwendung** .

3. Wählen Sie in der Liste **Ziel Framework** die Option .NET Framework 4 aus. (Wählen Sie nicht **.NET Framework 4 Client Profil**aus.)

4. Fügen Sie einen Verweis auf die Cacheassembly hinzu, indem Sie die folgenden Schritte ausführen:

    1. Klicken Sie mit der rechten Maustaste auf den Ordner **Verweise** und dann auf **Verweis hinzufügen**.

    2. Wählen Sie die Registerkarte **.net** , wählen Sie `System.Runtime.Caching`aus, und klicken Sie dann auf **OK**.

## <a name="adding-a-button-to-the-wpf-window"></a>Hinzufügen einer Schaltfläche zum WPF-Fenster
 Als Nächstes fügen Sie ein Schaltflächen-Steuerelement hinzu und erstellen einen Ereignishandler für das `Click`-Ereignis der Schaltfläche. Später fügen Sie Code hinzu. Wenn Sie auf die Schaltfläche klicken, wird der Inhalt der Textdatei zwischengespeichert und angezeigt.

#### <a name="to-add-a-button-control"></a>Hinzufügen eines Schaltflächen-Steuer Elements

1. Doppelklicken Sie in **Projektmappen-Explorer**auf die Datei "MainWindow. XAML", um Sie zu öffnen.

2. Ziehen Sie aus der **Toolbox**unter **Common WPF**-Steuerelemente ein `Button`-Steuerelement in das Fenster `MainWindow`.

3. Legen Sie im Fenster **Eigenschaften** für die `Content`-Eigenschaft des `Button`-Steuer Elements den Wert **Get Cache**fest.

## <a name="initializing-the-cache-and-caching-an-entry"></a>Initialisieren des Caches und Zwischenspeichern eines Eintrags
 Fügen Sie als nächstes den Code hinzu, um die folgenden Aufgaben auszuführen:

- Erstellen Sie eine Instanz der Cache-Klasse, d. –., Sie instanziieren Sie ein neues <xref:System.Runtime.Caching.MemoryCache>-Objekt.

- Legen Sie fest, dass der Cache ein <xref:System.Runtime.Caching.HostFileChangeMonitor> Objekt verwendet, um Änderungen in der Textdatei zu überwachen.

- Lesen Sie die Textdatei, und speichern Sie Ihren Inhalt als Cache Eintrag.

- Zeigen Sie den Inhalt der zwischengespeicherten Textdatei an.

#### <a name="to-create-the-cache-object"></a>So erstellen Sie das Cache Objekt

1. Doppelklicken Sie auf die Schaltfläche, die Sie soeben hinzugefügt haben, um einen Ereignishandler in der MainWindow.XAML.cs-oder MainWindow. XAML. vb-Datei zu erstellen.

2. Fügen Sie am Anfang der Datei (vor der Klassen Deklaration) die folgenden `Imports` (Visual Basic)-oder `using` (C#)-Anweisung hinzu:

    ```csharp
    using System.Runtime.Caching;
    using System.IO;
    ```

    ```vb
    Imports System.Runtime.Caching
    Imports System.IO
    ```

3. Fügen Sie im-Ereignishandler den folgenden Code hinzu, um das Cache Objekt zu instanziieren:

    ```csharp
    ObjectCache cache = MemoryCache.Default;
    ```

    ```vb
    Dim cache As ObjectCache = MemoryCache.Default
    ```

     Die <xref:System.Runtime.Caching.ObjectCache>-Klasse ist eine integrierte Klasse, die einen in-Memory-Objekt Cache bereitstellt.

4. Fügen Sie den folgenden Code hinzu, um den Inhalt eines Cache Eintrags namens `filecontents`zu lesen:

    ```vb
    Dim fileContents As String = TryCast(cache("filecontents"), String)
    ```

    ```csharp
    string fileContents = cache["filecontents"] as string;
    ```

5. Fügen Sie folgenden Code hinzu, um zu überprüfen, ob der Cache Eintrag namens `filecontents` vorhanden ist:

    ```vb
    If fileContents Is Nothing Then

    End If
    ```

    ```csharp
    if (fileContents == null)
    {

    }
    ```

     Wenn der angegebene Cache Eintrag nicht vorhanden ist, müssen Sie die Textdatei lesen und als Cache Eintrag dem Cache hinzufügen.

6. Fügen Sie im `if/then`-Block den folgenden Code hinzu, um ein neues <xref:System.Runtime.Caching.CacheItemPolicy>-Objekt zu erstellen, das angibt, dass der Cache Eintrag nach 10 Sekunden abläuft.

    ```vb
    Dim policy As New CacheItemPolicy()
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)
    ```

    ```csharp
    CacheItemPolicy policy = new CacheItemPolicy();
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);
    ```

     Wenn keine Entfernungs-oder Ablauf Informationen bereitgestellt werden, wird der Standardwert <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>. Dies bedeutet, dass die Cache Einträge nie auf der Grundlage eines absoluten Zeitraums ablaufen. Stattdessen laufen Cache Einträge nur dann ab, wenn genügend Arbeitsspeicher vorhanden ist. Als bewährte Vorgehensweise sollten Sie immer explizit einen absoluten oder einen gleitenden Ablauf angeben.

7. Fügen Sie im `if/then` Block und befolgen Sie den Code, den Sie im vorherigen Schritt hinzugefügt haben, um eine Sammlung für die Dateipfade zu erstellen, die Sie überwachen möchten, und um den Pfad der Textdatei der Auflistung hinzuzufügen:

    ```vb
    Dim filePaths As New List(Of String)()
    filePaths.Add("c:\cache\cacheText.txt")
    ```

    ```csharp
    List<string> filePaths = new List<string>();
    filePaths.Add("c:\\cache\\cacheText.txt");
    ```

    > [!NOTE]
    > Wenn die zu verwendende Textdatei nicht `c:\cache\cacheText.txt`ist, geben Sie den Pfad an, in dem die Textdatei verwendet werden soll.

8. Fügen Sie nach dem Code, den Sie im vorherigen Schritt hinzugefügt haben, den folgenden Code hinzu, um der Sammlung von Änderungs Monitoren für den Cache Eintrag ein neues <xref:System.Runtime.Caching.HostFileChangeMonitor> Objekt hinzuzufügen:

    ```vb
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))
    ```

    ```csharp
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));
    ```

     Das <xref:System.Runtime.Caching.HostFileChangeMonitor>-Objekt überwacht den Pfad der Textdatei und benachrichtigt den Cache, wenn Änderungen auftreten. In diesem Beispiel läuft der Cache Eintrag ab, wenn sich der Inhalt der Datei ändert.

9. Fügen Sie nach dem Code, den Sie im vorherigen Schritt hinzugefügt haben, den folgenden Code hinzu, um den Inhalt der Textdatei zu lesen:

    ```vb
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()
    ```

    ```csharp
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + "\n" + DateTime.Now;
    ```

     Der Zeitstempel für Datum und Uhrzeit wird hinzugefügt, damit Sie sehen können, wann der Cache Eintrag abläuft.

10. Fügen Sie nach dem Code, den Sie im vorherigen Schritt hinzugefügt haben, den folgenden Code hinzu, um den Inhalt der Datei in das Cache Objekt als <xref:System.Runtime.Caching.CacheItem> Instanz einzufügen:

    ```vb
    cache.Set("filecontents", fileContents, policy)
    ```

    ```csharp
    cache.Set("filecontents", fileContents, policy);
    ```

     Sie geben Informationen darüber an, wie der Cache Eintrag entfernt werden soll, indem Sie das <xref:System.Runtime.Caching.CacheItemPolicy> Objekt, das Sie zuvor erstellt haben, als Parameter übergeben.

11. Fügen Sie nach dem `if/then`-Block den folgenden Code hinzu, um den zwischengespeicherten Dateiinhalt in einem Meldungs Feld anzuzeigen:

    ```vb
    MessageBox.Show(fileContents)
    ```

    ```csharp
    MessageBox.Show(fileContents);
    ```

12. Klicken Sie im Menü **Erstellen** auf **wpfcaching erstellen** , um das Projekt zu erstellen.

## <a name="testing-caching-in-the-wpf-application"></a>Testen der Zwischenspeicherung in der WPF-Anwendung
 Die Anwendung kann nun getestet werden.

#### <a name="to-test-caching-in-the-wpf-application"></a>So testen Sie die Zwischenspeicherung in der WPF-Anwendung

1. Drücken Sie STRG+F5, um die Anwendung auszuführen.

     Das Fenster `MainWindow` wird angezeigt.

2. Klicken Sie auf **Cache erhalten**.

     Der zwischengespeicherte Inhalt aus der Textdatei wird in einem Meldungs Feld angezeigt. Beachten Sie den Zeitstempel der Datei.

3. Schließen Sie das Meldungs Feld, und klicken Sie dann erneut auf **Cache erhalten** .

     Der Zeitstempel ist unverändert. Dies gibt an, dass der zwischengespeicherte Inhalt angezeigt wird.

4. Warten Sie 10 Sekunden oder mehr, und klicken Sie dann erneut auf **Cache erhalten** .

     Dieses Mal wird ein neuer Zeitstempel angezeigt. Dies gibt an, dass die Richtlinie den Cache Eintrag ablaufen lässt und dass neuer zwischen gespeicherter Inhalt angezeigt wird.

5. Öffnen Sie in einem Text-Editor die Textdatei, die Sie erstellt haben. Nehmen Sie noch keine Änderungen vor.

6. Schließen Sie das Meldungs Feld, und klicken Sie dann erneut auf **Cache erhalten** .

     Beachten Sie den Zeitstempel.

7. Nehmen Sie eine Änderung an der Textdatei vor, und speichern Sie die Datei.

8. Schließen Sie das Meldungs Feld, und klicken Sie dann erneut auf **Cache erhalten** .

     Dieses Meldungs Feld enthält den aktualisierten Inhalt aus der Textdatei und einen neuen Zeitstempel. Dadurch wird angegeben, dass der Cache Eintrag vom Host Datei-Änderungs Monitor sofort entfernt wurde, als Sie die Datei geändert haben, obwohl der absolute Timeout Zeitraum nicht abgelaufen war.

    > [!NOTE]
    > Sie können die Entfernungs Zeit auf 20 Sekunden oder mehr erhöhen, damit Sie mehr Zeit für eine Änderung in der Datei haben.

## <a name="code-example"></a>Codebeispiel
 Nachdem Sie diese exemplarische Vorgehensweise abgeschlossen haben, ähnelt der Code für das Projekt, das Sie erstellt haben, dem folgenden Beispiel.

 [!code-csharp[CachingWPFApplications#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.Caching.MemoryCache>
- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching>
- [Caching in .NET Framework Applications (Caching in .NET Framework-Anwendungen)](../../performance/caching-in-net-framework-applications.md)
