---
title: Bestimmen, wohin „My.Application.Log“ Informationen schreibt
ms.date: 07/20/2015
helpviewer_keywords:
- My.Log object, output location
- output, application log location
- My.Application.Log object, output location
- event logs, determining output location
- application event logs, output location
- applications [Visual Basic], output location
ms.assetid: 5b70143a-7741-45f2-ae1d-03324a3a4189
ms.openlocfilehash: f3fd0ed0388276f1400bf77d0abfb488634a45a5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353603"
---
# <a name="walkthrough-determining-where-myapplicationlog-writes-information-visual-basic"></a>Exemplarische Vorgehensweise: Bestimmen, wohin „My.Application.Log“ Informationen schreibt (Visual Basic)

Das `My.Application.Log` -Objekt kann Informationen in verschiedene Protokolllistener schreiben. Die Protokolllistener werden durch die Konfigurationsdatei des Computers konfiguriert und können durch die Konfigurationsdatei einer Anwendung außer Kraft gesetzt werden. Dieses Thema beschreibt die Standardeinstellungen und erläutert, wie Sie die Einstellungen für Ihre Anwendung ermitteln.

Weitere Informationen zu den Standardausgabeorten finden Sie unter [Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).

### <a name="to-determine-the-listeners-for-myapplicationlog"></a>Bestimmen der Listener für "My.Application.Log"

1. Suchen Sie die Konfigurationsdatei der Assembly. Wenn Sie die Assembly entwickeln, können Sie in Visual Studio im **Projektmappen-Explorer** auf die „app.config“ zugreifen. Andernfalls ist der Name der Konfigurationsdatei der Name der Assembly mit angefügtem ".config" und befindet sich im gleichen Verzeichnis wie die Assembly.

    > [!NOTE]
    > Nicht jede Assembly verfügt über eine Konfigurationsdatei.

    Bei der Konfigurationsdatei handelt es sich um eine XML-Datei.

2. Suchen Sie den `<listeners>` -Abschnitt, der sich im `<source>` -Abschnitt mit dem `name` -Attribut "DefaultSource" im Abschnitt `<sources>` befindet. Der Abschnitt `<sources>` befindet sich im `<system.diagnostics>` -Abschnitt im Abschnitt `<configuration>` der obersten Ebene.

    Wenn diese Abschnitte nicht vorhanden sind, werden die `My.Application.Log` -Protokolllistener möglicherweise durch die Konfigurationsdatei des Computers konfiguriert. In den folgenden Schritten ist beschrieben, wie Sie bestimmen, was in der Computerkonfigurationsdatei definiert ist:

    1. Suchen Sie die Datei "machine.config" des Computers. In der Regel befindet sie sich im Verzeichnis *SystemRoot\Microsoft.NET\Framework\frameworkVersion\CONFIG*, wobei `SystemRoot` das Betriebssystemverzeichnis und `frameworkVersion` die Version von .NET Framework ist.

        Die Einstellungen in "machine.config" können durch die Konfigurationsdatei einer Anwendung außer Kraft gesetzt werden.

        Wenn die unten aufgelisteten optionalen Elemente nicht vorhanden sind, können Sie sie erstellen.

    2. Suchen Sie den Abschnitt `<listeners>` im Abschnitt `<source>` mit dem `name` -Attribut "DefaultSource" im `<sources>` -Abschnitt im `<system.diagnostics>` -Abschnitt im `<configuration>` -Abschnitt der obersten Ebene.

        Wenn diese Abschnitte nicht vorhanden sind, verfügt `My.Application.Log` nur über die standardmäßigen Protokolllistener.

3. Suchen Sie die <`add>`-Elemente im <`listeners>`-Abschnitt.

     Diese Elemente fügen die benannten Protokolllistener zur `My.Application.Log` -Quelle hinzu.

4. Suchen Sie die `<add>` -Elemente mit den Namen der Protokolllistener im `<sharedListeners>` -Abschnitt im `<system.diagnostics>` -Abschnitt im `<configuration>` -Abschnitt der obersten Ebene.

5. Bei vielen freigegebenen Listenern enthalten die Initialisierungdaten des Listeners eine Beschreibung, wohin der Listener die Daten leitet:

    - Ein <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType>-Listener schreibt in ein Dateiprotokoll, wie in der Einführung beschrieben.

    - Ein <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>-Listener schreibt Informationen in das Ereignisprotokoll des Computers, das im `initializeData`-Parameter angegeben ist. Zum Anzeigen von Ereignisprotokollen können Sie den **Server-Explorer** oder die **Windows-Ereignisanzeige**verwenden. Weitere Informationen finden Sie unter [ETW Events in the .NET Framework](../../../../framework/performance/etw-events.md).

    - Die <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>- und <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>-Listener schreiben in die Datei, die im `initializeData`-Parameter angegeben ist.

    - Ein <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>-Listener schreibt in die Befehlszeilenkonsole.

    - Informationen dazu, wohin andere Typen von Protokolllistenern Informationen schreiben, finden Sie in der Dokumentation zum entsprechenden Typ.

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.DelimitedListTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics>
- [Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [Vorgehensweise: Protokollieren von Ausnahmen](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
- [Vorgehensweise: Schreiben von Protokollmeldungen](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)
- [Exemplarische Vorgehensweise: Ändern des Orts, in den „My.Application.Log“ Informationen schreibt](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
- [ETW Events in the .NET Framework (ETW-Ereignisse in .NET Framework)](../../../../framework/performance/etw-events.md)
- [Problembehandlung: Protokolllistener](../../../../visual-basic/developing-apps/programming/log-info/troubleshooting-log-listeners.md)
