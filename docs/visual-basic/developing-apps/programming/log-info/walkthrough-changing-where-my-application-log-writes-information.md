---
title: Ändern des Orts, in den „My.Application.Log“ Informationen schreibt
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, walkthroughs
- event logs, changing output location
ms.assetid: ecc74f95-743c-450d-93f6-09a30db0fe4a
ms.openlocfilehash: bdee0a91360580b156c1734ef4c82139b18ce2b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74336736"
---
# <a name="walkthrough-changing-where-myapplicationlog-writes-information-visual-basic"></a>Exemplarische Vorgehensweise: Ändern des Orts, in den "My.Application.Log" Informationen schreibt (Visual Basic)

Sie können die Objekte `My.Application.Log` und `My.Log` verwenden, um Informationen über Ereignisse zu protokollieren, die in Ihrer Anwendung auftreten. In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie die Standardeinstellungen außer Kraft setzen und das `Log` -Objekt dazu bringen können, in andere Protokolllistener zu schreiben.

## <a name="prerequisites"></a>Voraussetzungen

Das `Log` -Objekt kann Informationen in mehrere Protokolllistener schreiben. Sie müssen die aktuelle Konfiguration der Protokolllistener bestimmen, bevor Sie die Konfigurationen ändern können. Weitere Informationen finden Sie unter [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).

Es kann nützlich sein, [Vorgehensweise: Schreiben von Ereignisinformationen in eine Textdatei](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md) oder [Vorgehensweise: Schreiben in ein Anwendungsereignisprotokoll](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md) durchzuarbeiten.

### <a name="to-add-listeners"></a>Hinzufügen von Listenern

1. Klicken Sie im **Projektmappen-Explorer** auf "app.config", und wählen Sie **Öffnen**aus.

     \- oder -

     Wenn keine app.config-Datei vorhanden ist:

    1. Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.

    2. Wählen Sie im Dialogfeld **Neues Element hinzufügen** den Eintrag **Anwendungskonfigurationsdatei**aus.

    3. Klicken Sie auf **Hinzufügen**.

2. Suchen Sie den `<listeners>` -Abschnitt unter dem `<source>` -Abschnitt mit dem `name` -Attribut "DefaultSource" im Abschnitt `<sources>` . Der Abschnitt `<sources>` befindet sich im `<system.diagnostics>` -Abschnitt im Abschnitt `<configuration>` der obersten Ebene.

3. Fügen Sie dem betreffenden `<listeners>` -Abschnitt diese Elemente hinzu.

    ```xml
    <!-- Uncomment to connect the application file log. -->
    <!-- <add name="FileLog" /> -->
    <!-- Uncomment to connect the event log. -->
    <!-- <add name="EventLog" /> -->
    <!-- Uncomment to connect the event log. -->
    <!-- <add name="Delimited" /> -->
    <!-- Uncomment to connect the XML log. -->
    <!-- <add name="XmlWriter" /> -->
    <!-- Uncomment to connect the console log. -->
    <!-- <add name="Console" /> -->
    ```

4. Entfernen Sie die Auskommentierungen der Protokolllistener, die `Log` -Meldungen empfangen sollen.

5. Suchen Sie den Abschnitt `<sharedListeners>` im `<system.diagnostics>` -Abschnitt im Abschnitt `<configuration>` der obersten Ebene.

6. Fügen Sie dem betreffenden `<sharedListeners>` -Abschnitt diese Elemente hinzu.

    ```xml
    <add name="FileLog"
         type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
               Microsoft.VisualBasic, Version=8.0.0.0,
               Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"
         initializeData="FileLogWriter" />
    <add name="EventLog"
         type="System.Diagnostics.EventLogTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="sample application"/>
    <add name="Delimited"
         type="System.Diagnostics.DelimitedListTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="c:\temp\sampleDelimitedFile.txt"
         traceOutputOptions="DateTime" />
    <add name="XmlWriter"
         type="System.Diagnostics.XmlWriterTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="c:\temp\sampleLogFile.xml" />
    <add name="Console"
         type="System.Diagnostics.ConsoleTraceListener,
               System, Version=2.0.0.0,
               Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="true" />
    ```

7. Der Inhalt der app.config-Datei sollte ähnlich dem folgenden XML-Code sein:

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <system.diagnostics>
        <sources>
          <!-- This section configures My.Application.Log -->
          <source name="DefaultSource" switchName="DefaultSwitch">
            <listeners>
              <add name="FileLog"/>
              <!-- Uncomment to connect the application file log. -->
              <!-- <add name="FileLog" /> -->
              <!-- Uncomment to connect the event log. -->
              <!-- <add name="EventLog" /> -->
              <!-- Uncomment to connect the event log. -->
              <!-- <add name="Delimited" /> -->
              <!-- Uncomment to connect the XML log. -->
              <!-- <add name="XmlWriter" /> -->
              <!-- Uncomment to connect the console log. -->
              <!-- <add name="Console" /> -->
            </listeners>
          </source>
        </sources>
        <switches>
          <add name="DefaultSwitch" value="Information" />
        </switches>
        <sharedListeners>
          <add name="FileLog"
               type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
                     Microsoft.VisualBasic, Version=8.0.0.0,
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"
               initializeData="FileLogWriter" />
          <add name="EventLog"
               type="System.Diagnostics.EventLogTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="sample application"/>
          <add name="Delimited"
               type="System.Diagnostics.DelimitedListTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="c:\temp\sampleDelimitedFile.txt"
               traceOutputOptions="DateTime" />
          <add name="XmlWriter"
               type="System.Diagnostics.XmlWriterTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="c:\temp\sampleLogFile.xml" />
          <add name="Console"
               type="System.Diagnostics.ConsoleTraceListener,
                     System, Version=2.0.0.0,
                     Culture=neutral, PublicKeyToken=b77a5c561934e089"
               initializeData="true" />
        </sharedListeners>
      </system.diagnostics>
    </configuration>
    ```

### <a name="to-reconfigure-a-listener"></a>Umkonfigurieren eines Listeners

1. Suchen Sie im Abschnitt `<add>` das `<sharedListeners>` -Element des Listeners.

2. Das `type` -Attribut enthält den Namen des Listenertyps. Dieser Typ muss von der <xref:System.Diagnostics.TraceListener> -Klasse erben. Verwenden Sie den starken Typnamen, um sicherzustellen, dass der richtige Typ verwendet wird. Weitere Informationen finden Sie unten im Abschnitt "Verweise auf Typen mit starken Namen".

     Dies sind einige der Typen, die Sie verwenden können:

    - Ein <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> -Listener, der in eine Protokolldatei schreibt.

    - Ein <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> -Listener, der Informationen in das Ereignisprotokoll des Computers schreibt, das im `initializeData` -Parameter angegeben ist.

    - Die <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> - und <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> -Listener, die in die Datei schreiben, die im `initializeData` -Parameter angegeben ist.

    - Ein <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> -Listener, der in die Befehlszeilenkonsole schreibt.

     Informationen dazu, wohin andere Typen von Protokolllistenern Informationen schreiben, finden Sie in der Dokumentation zum entsprechenden Typ.

3. Wenn die Anwendung das Protokolllistenerobjekt erstellt, übergibt sie das `initializeData` -Attribut als Konstruktorparameter. Die Bedeutung des `initializeData` -Attributs hängt vom Ablaufverfolgungslistener ab.

4. Nach dem Erstellen des Protokolllisteners legt die Anwendung die Eigenschaften des Listeners fest. Diese Eigenschaften werden durch die anderen Attribute im `<add>` -Element definiert. Weitere Informationen zu den Eigenschaften für einen bestimmten Listener finden Sie in der Dokumentation für den betreffenden Listenertyp.

### <a name="to-reference-a-strongly-named-type"></a>Verweise auf Typen mit starkem Namen

1. Um sicherzustellen, dass der richtige Typ für Ihren Protokolllistener verwendet wird, achten Sie darauf, den vollqualifizierten Typnamen und den starken Assemblynamen zu verwenden. Die Syntax für einen Typ mit starkem Namen ist wie folgt:

     \<*Typname*>, \<*Assemblyname*>, \<*Versionsnummer*>, \<*Kultur*>, \<*starker Name*>

2. Dieses Codebeispiel zeigt, wie Sie den starken Typnamen für einen vollqualifizierten Typ bestimmen – in diesem Fall "System.Diagnostics.FileLogTraceListener".

     [!code-vb[VbVbalrMyApplicationLog#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#15)]

     Dies ist die Ausgabe, und sie kann verwendet werden, um eindeutig auf einen Typ mit starkem Namen zu verweisen, wie in der Verfahrensweise "Hinzufügen von Listenern" oben.

     `Microsoft.VisualBasic.Logging.FileLogTraceListener, Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`

## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceListener>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType>
- <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>
- [Gewusst wie: Schreiben von Ereignisinformationen in eine Textdatei](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md)
- [Gewusst wie: Schreiben in ein Anwendungsereignisprotokoll](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md)
