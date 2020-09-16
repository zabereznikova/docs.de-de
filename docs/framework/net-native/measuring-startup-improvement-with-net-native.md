---
title: Messung der Startverbesserung mit .NET Native
ms.date: 03/30/2017
ms.assetid: c4d25b24-9c1a-4b3e-9705-97ba0d6c0289
ms.openlocfilehash: 5d20fa77ee299065ced406bf8cd531b8c54b6c33
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540887"
---
# <a name="measuring-startup-improvement-with-net-native"></a>Messung der Startverbesserung mit .NET Native
Mit .net Native wird die Startzeit von apps erheblich verbessert. Diese Verbesserung ist besonders deutlich auf tragbaren Geräten mit geringem Energieverbrauch und bei komplexen Apps. Dieses Thema soll Ihnen den Einstieg in die grundlegende Instrumentierung erleichtern, die Sie benötigen, um diese Startverbesserung zu messen.  
  
 Um Leistungsuntersuchungen zu erleichtern, verwenden .NET Framework und Windows ein Ereignisframework namens Ereignisablaufverfolgung für Windows (Event Tracing for Windows, ETW), mit dem Ihre App Tools benachrichtigen kann, wenn Ereignisse auftreten. Sie können dann ein Tool namens PerfView verwenden, um ETW-Ereignisse anzuzeigen und zu analysieren. In diesem Thema wird Folgendes erläutert:  
  
- Verwenden der <xref:System.Diagnostics.Tracing.EventSource>-Klasse zum Ausgeben von Ereignissen.  
  
- Verwenden von PerfView zum Erfassen dieser Ereignisse.  
  
- Verwenden von PerfView zum Anzeigen dieser Ereignisse.  
  
## <a name="using-eventsource-to-emit-events"></a>Verwenden von EventSource zum Ausgeben von Ereignissen  
 <xref:System.Diagnostics.Tracing.EventSource> stellt eine Basisklasse für das Erstellen eines benutzerdefinierten Ereignisanbieters bereit. Im Allgemeinen erstellen Sie eine Unterklasse von <xref:System.Diagnostics.Tracing.EventSource> und schließen die `Write*`-Methoden in Ihre eigenen Ereignismethoden ein. Im Allgemeinen wird für jede <xref:System.Diagnostics.Tracing.EventSource>-Klasse ein Singleton-Muster verwendet.  
  
 Die Klasse im folgenden Beispiel kann z. B. verwendet werden, um zwei Leistungsmerkmale zu messen:  
  
- Die Zeit, bis der `App`-Klassenkonstruktor aufgerufen wurde.  
  
- Die Zeit, bis der `MainPage`-Konstruktor aufgerufen wurde.  
  
 [!code-csharp[ProjectN_ETW#1](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_etw/cs/etw1.cs#1)]  
  
 Es gibt ein paar Punkte zu beachten. Zuerst wird ein Singleton in `AppEventSource.Log` erstellt. Diese Instanz wird für die gesamte Protokollierung verwendet. Zweitens hat jede Ereignismethode ein <xref:System.Diagnostics.Tracing.EventAttribute>. Damit können Tools den Index der <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A>-Methode der Methode, die für `AppEventSource` aufgerufen wurde, zuordnen.  
  
 Beachten Sie, dass diese Ereignisse lediglich zu Illustrationszwecken dienen. Der meiste App-Code wird nach diesen Ereignissen ausgeführt. Sie sollten ermitteln, welche Ereignisse im Code Benutzerinteraktionen entsprechen, diese messen und die betreffenden Benchmarks verbessern. Darüber hinaus protokollieren die Ereignisse selbst jeweils nur eine einzige Instanz. Es ist oft hilfreich, Paare von Start- und Stop-Ereignissen für jeden Vorgang zu verwenden. Bei der Untersuchung des App-Starts ist das Startereignis in der Regel das "Process/Start"-Ereignis, das das Betriebssystem ausgibt.  
  
 Angenommen, Sie erstellen einen RSS-Reader. Ein paar interessante Stellen zum Protokollieren eines Ereignisses sind folgende:  
  
- Wenn die Hauptseite gerendert wird.  
  
- Wenn alte RSS-Nachrichten aus dem lokalen Speicher deserialisiert werden.  
  
- Wenn Ihre App beginnt, neue Nachrichten zu synchronisieren.  
  
- Wenn Ihre App das Synchronisieren neuer Nachrichten abgeschlossen hat.  
  
 Das Instrumentieren einer App ist einfach: Rufen Sie nur die entsprechende Methode für die abgeleitete Klasse auf. Mit `AppEventSource` aus dem vorherigen Beispiel können Sie eine Anwendung wie folgt instrumentieren:  
  
 [!code-csharp[ProjectN_ETW#2](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_etw/cs/etw2.cs#2)]  
  
 Wenn die App instrumentiert ist, können Sie Ereignisse erfassen.  
  
## <a name="gathering-events-with-perfview"></a>Erfassen von Ereignissen mit PerfView  
 PerfView verwendet ETW-Ereignisse, um Sie bei allen möglichen Leistungsuntersuchungen für Ihre App zu unterstützen. Darüber hinaus ist eine grafische Benutzeroberfläche für die Konfiguration enthalten, mit der Sie die Protokollierung für unterschiedliche Typen von Ereignissen aktivieren oder deaktivieren können. PerfView ist ein kostenloses Tool, das über das [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=28567) heruntergeladen werden kann. Weitere Informationen erhalten Sie in den [Videotutorials für PerfView](https://channel9.msdn.com/Series/PerfView-Tutorial).  
  
> [!NOTE]
> PerfView kann nicht zum Erfassen von Ereignissen auf ARM-Systemen verwendet werden. Zum Erfassen von Ereignissen auf ARM-Systemen verwenden Sie Windows Performance Recorder (WPR). Weitere Informationen finden Sie im [Blogbeitrag von Vance Morrison](/archive/blogs/vancem/collecting-etwperfview-data-on-an-windows-rt-winrt-arm-surface-device).  
  
 Sie können PerfView auch von der Befehlszeile aus aufrufen. Um nur die Ereignisse von Ihrem Anbieter zu protokollieren, öffnen Sie das Eingabeaufforderungsfenster und geben folgenden Befehl ein:  
  
```console
perfview -KernelEvents:Process -OnlyProviders:*MyCompany-MyApp collect outputFile
```  
  
 Dabei gilt Folgendes:  
  
 `-KernelEvents:Process`  
 Gibt an, dass Sie wissen möchten, wann der Prozess startet und endet. Sie benötigen das Process/Start-Ereignis für Ihre App, damit die Zeit von anderen Ereigniszeiten abgezogen werden kann.  
  
 `-OnlyProviders:*MyCompany-MyApp`  
 Deaktiviert andere Anbieter, die PerfView standardmäßig aktiviert, und aktiviert den Anbieter MyCompany-MyApp.  (Das Sternchen gibt an, dass es sich um eine <xref:System.Diagnostics.Tracing.EventSource> handelt.)  
  
 `collect outputFile`  
 Gibt an, dass die Erhebung gestartet werden soll und die Daten in outputFile.etl.zip gespeichert werden sollen.  
  
 Führen Sie Ihre App nach dem Starten von PerfView aus. Es gibt ein paar Dinge zu beachten, wenn Sie Ihre App ausführen:  
  
- Verwenden Sie einen Releasebuild, keine Debugversion. Debugversionen enthalten häufig zusätzlichen Fehlerprüfungs- und Fehlerbehandlungscode, der die Ausführung Ihrer App verzögern kann.  
  
- Das Ausführen der App mit einem angefügten Debugger wirkt sich auf die Leistung der App aus.  
  
- Windows verwendet mehrere Zwischenspeicherstrategien, um App-Startzeiten zu beschleunigen. Wenn Ihre Anwendung im Speicher zwischengespeichert ist und nicht von der Festplatte geladen werden muss, wird sie schneller gestartet. Zur Gewährleistung der Konsistenz starten und schließen Sie Ihre App mehrmals, bevor Sie sie messen.  
  
 Wenn Sie Ihre App ausgeführt haben, sodass PerfView ausgegebene Ereignisse erfassen kann, klicken Sie auf die Schaltfläche **Auflistung beenden**. Im Allgemeinen sollten Sie die Erfassung beenden, bevor Sie die App schließen, um keine irrelevanten Ereignisse zu erfassen. Wenn Sie jedoch die Leistung beim Herunterfahren oder bei einer Unterbrechung messen, sollten Sie die Erfassung fortsetzen.  
  
## <a name="displaying-the-events"></a>Anzeigen der Ereignisse  
 Um die bereits aufgelisteten Ereignisse anzuzeigen, öffnen Sie mit PerfView die erstellte ETL- oder ETL-ZIP-Datei, und wählen Sie **Ereignisse** aus. ETW sollte Informationen über eine große Anzahl von Ereignissen, einschließlich der Ereignisse von anderen Prozessen, gesammelt haben. Um die Untersuchung zu konzentrieren, füllen Sie in der Ereignisansicht die folgenden Textfelder aus:  
  
- Geben Sie im Feld **Process Filter** (Prozessfilter) den Namen Ihrer App an (ohne „.exe“).  
  
- Geben Sie im Feld **Event Types Filter** (Ereignistypfilter) `Process/Start | MyCompany-MyApp` an. Hierdurch wird ein Filter für Ereignisse von MyCompany-MyApp und das Windows Kernel/Process/Start-Ereignis festgelegt.  
  
 Wählen Sie alle im linken Bereich aufgelisteten Ereignisse aus (STRG+A), und drücken Sie die **EINGABETASTE**. Nun sollten die Zeitstempel jedes Ereignisses angezeigt werden. Diese Zeitstempel sind relativ zum Start der Ablaufverfolgung, sodass Sie die Zeit der einzelnen Ereignisse von der Startzeit des Prozesses abziehen müssen, um die verstrichene Zeit seit dem Start zu ermitteln. Wenn mit STRG+Klick zwei Zeitstempel auswählen, wird der Unterschied zwischen diesen in der Statusleiste am unteren Rand der Seite angezeigt. Auf diese Weise können Sie ganz einfach die abgelaufene Zeit zwischen zwei beliebigen Ereignissen in der Anzeige (einschließlich des Prozessstarts) sehen. Sie können das Kontextmenü für die Ansicht öffnen und eine Reihe nützlicher Optionen auswählen, wie beispielsweise das Exportieren in CSV-Dateien oder das Öffnen von Microsoft Excel zum Speichern oder Verarbeiten der Daten.  
  
 Durch Wiederholen des Verfahrens für Ihre ursprüngliche APP und die Version, die Sie mit der .net Native-Toolkette erstellt haben, können Sie den Unterschied in der Leistung vergleichen.   .Net Native apps werden im Allgemeinen schneller als Non-.net Native apps gestartet. Wenn Sie an weiteren Details interessiert sind, kann PerfView auch die Teile des Codes identifizieren, die die meiste Zeit verbrauchen. Weitere Informationen erhalten Sie in den [PerfView-Tutorials](https://channel9.msdn.com/Series/PerfView-Tutorial) oder durch Lesen des [Blogbeitrags von Vance Morrison](/archive/blogs/vancem/publication-of-the-perfview-performance-analysis-tool).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Diagnostics.Tracing.EventSource>
