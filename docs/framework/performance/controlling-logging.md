---
title: Steuern der Protokollierung in .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events, logging
ms.assetid: ce13088e-3095-4f0e-9f6b-fad30bbd3d41
ms.openlocfilehash: e7d7d6e60b2f582a579f5811225f4027c37c7876
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77504101"
---
# <a name="controlling-net-framework-logging"></a>Steuern der Protokollierung in .NET Framework

Sie können mithilfe der Ereignisablaufverfolgung für Windows (ETW) Common Language Runtime (CLR)-Ereignisse aufzeichnen. Sie können Ablaufverfolgungen mit den folgenden Tools erstellen und anzeigen:

- Die Befehlszeilentools [Logman](/windows-server/administration/windows-commands/logman) und [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) sind im Windows-Betriebssystem enthalten.

- Die [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference)-Tools im [Windows Performance Toolkit](/windows-hardware/test/wpt/). Weitere Informationen zu Xperf finden Sie im [Windows Performance-Blog](https://docs.microsoft.com/archive/blogs/pigscanfly/).

Wenn Sie CLR-Ereignisinformationen erfassen möchten, muss der CLR-Anbieter auf dem Computer installiert werden. Geben Sie an der Eingabeaufforderung `logman query providers` ein, um festzustellen, ob der Anbieter installiert ist. Eine Anbieterliste wird angezeigt. Diese Liste sollte wie folgt einen Eintrag für den CLR-Anbieter enthalten.

```output
Provider                                 GUID
-------------------------------------------------------------------------------
.NET Common Language Runtime    {E13C0D23-CCBC-4E12-931B-D9CC2EEE27E4}.
```

Wenn der CLR-Anbieter nicht aufgeführt ist, können Sie ihn unter Windows Vista und späteren Betriebssystemen mithilfe des Windows-Befehlszeilentools [Wevtutil](/windows-server/administration/windows-commands/wevtutil) installieren. Öffnen Sie das Eingabeaufforderungsfenster als Administrator. Ändern Sie das Eingabe Aufforderungs Verzeichnis in den Ordner .NET Framework 4 (%windir%\Microsoft.NET\Framework [64] \v4.\<.NET-Version > \). Dieser Ordner enthält die Datei "CLR-ETW.man". Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, um den CLR-Anbieter zu installieren:

`wevtutil im CLR-ETW.man`

## <a name="capturing-clr-etw-events"></a>Erfassen von CLR-ETW-Ereignissen

Sie können die Befehlszeilentools [Logman](/windows-server/administration/windows-commands/logman) und [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) verwenden, um ETW-Ereignisse zu erfassen. Mit den Tools [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) und [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) können Sie die Ablaufverfolgungsereignisse dekodieren.

Zum Aktivieren der Protokollierung müssen Benutzer drei Informationen angeben:

- Anbieter, mit dem kommuniziert werden soll.

- Eine 64-Bit-Zahl, die einen Satz von Schlüsselwörtern darstellt. Jedes Schlüsselwort stellt einen Satz von Ereignissen dar, den der Anbieter aktivieren kann. Die Zahl stellt einen kombinierten Satz von Schlüsselwörtern dar, die aktiviert werden sollen.

- Eine kleine Zahl, die die Ebene (den Ausführlichkeitsgrad) der Protokollierung darstellt. Ebene 1 ist die am wenigsten ausführliche, Ebene 5 die ausführlichste. Ebene 0 ist ein Standard mit anbieterspezifischer Bedeutung.

### <a name="to-capture-clr-etw-events-using-logman"></a>So erfassen Sie CLR-ETW-Ereignisse mit Logman

1. Geben Sie an der Eingabeaufforderung Folgendes ein:

     `logman start clrevents -p {e13c0d23-ccbc-4e12-931b-d9cc2eee27e4} 0x1CCBD 0x5 -ets -ct perf`

     Dabei gilt:

    - Durch den `-p`-Parameter wird die Anbieter-GUID identifiziert.

    - `0x1CCBD` gibt die Kategorien der Ereignisse an, die ausgelöst werden.

    - `0x5` legt die Ebene der Protokollierung fest (in diesem Fall "Ausführlich" (5)).

    - Mit dem `-ets`-Parameter wird Logman angewiesen, Befehle an Ereignisablaufverfolgungs-Sitzungen zu senden.

    - Der `-ct perf`-Parameter gibt an, dass mit der `QueryPerformanceCounter`-Funktion der Zeitstempel für jedes Ereignis protokolliert wird.

2. Geben Sie Folgendes ein, um die Protokollierung der Ereignisse zu beenden:

     `logman stop clrevents -ets`

     Mit diesem Befehl wird eine binäre Ablaufverfolgungsdatei mit dem Namen "clrevents.etl" erstellt.

### <a name="to-capture-clr-etw-events-using-xperf"></a>So erfassen Sie CLR-ETW-Ereignisse mit XPerf

1. Geben Sie an der Eingabeaufforderung Folgendes ein:

     `xperf -start clr -on e13c0d23-ccbc-4e12-931b-d9cc2eee27e4:0x1CCBD:5 -f clrevents.etl`

     Dabei ist die GUID die GUID des CLR-ETW-Anbieters, und `0x1CCBD:5` verfolgt sämtliche Vorgänge auf und unterhalb von Ebene 5 (Ausführlich).

2. Geben Sie Folgendes ein, um die Ablaufverfolgung zu beenden:

     `Xperf -stop clr`

     Mit diesem Befehl wird eine Ablaufverfolgungsdatei mit dem Namen "clrevents.etl" erstellt.

## <a name="viewing-clr-etw-events"></a>Anzeigen von CLR-ETW-Ereignissen

Verwenden Sie die unten aufgeführten Befehle, um die CLR-ETW-Ereignisse anzuzeigen. Eine Beschreibung der Ereignisse finden Sie unter [CLR-ETW-Ereignisse](clr-etw-events.md).

### <a name="to-view-clr-etw-events-using-tracerpt"></a>So zeigen Sie CLR-ETW-Ereignisse mit Tracerpt an

- Geben Sie an der Eingabeaufforderung Folgendes ein:

     `tracerpt clrevents.etl`

     Mit diesem Befehl werden zwei Dateien erstellt: "dumpfile.xml" und "summary.txt". In der Datei "dumpfile.xml" werden alle Ereignisse aufgeführt, wohingegen "summary.txt" eine Zusammenfassung der Ereignisse enthält.

### <a name="to-view-clr-etw-events-using-xperf"></a>So zeigen Sie CLR-ETW-Ereignisse mit Xperf an

- Geben Sie an der Eingabeaufforderung Folgendes ein:

     `xperf clrevents.etl`

     Mit diesem Befehl wird der ETL-Datei-Viewer von Xperf geöffnet. In diesem Viewer werden die CLR-Ereignisse in der Ansicht **Generische Ereignisse** angezeigt. Zum Anzeigen eines nach Typen kategorisierten Datenrasters von Ereignissen wählen Sie in der Ansicht einen Zeitraum aus, klicken Sie dann mit der rechten Maustaste, und wählen Sie **Zusammenfassung** aus.

### <a name="to-convert-the-etl-file-to-a-comma-separated-value-file"></a>So konvertieren Sie die ETL-Datei in eine CSV-Datei

- Geben Sie an der Eingabeaufforderung Folgendes ein:

     `xperf -i clrevents.etl -f clrevents.csv`

     Dieser Befehl bewirkt, dass XPerf die Ereignisse als CSV-Datei (CSV) sichert, die Sie anzeigen können. Da für unterschiedliche Ereignisse auch unterschiedliche Felder verfügbar sind, enthält diese CSV-Datei vor den Daten mehrere Headerzeilen. Das erste Feld jeder Zeile ist für den Ereignistyp vorgesehen, der den Header angibt, der zum Ermitteln der weiteren Felder verwendet werden soll.

## <a name="see-also"></a>Weitere Informationen

- [Windows Performance Toolkit](/windows-hardware/test/wpt/)
- [ETW-Ereignisse in der Common Language Runtime](etw-events-in-the-common-language-runtime.md)
