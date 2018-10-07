---
title: Übersicht über den Nachrichtenfluss
ms.date: 03/30/2017
ms.assetid: fb0899e1-84cc-4d90-b45b-dc5a50063943
ms.openlocfilehash: 73ad66389d8458c0508c7a8cae28f54ca38ed574
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2018
ms.locfileid: "48841981"
---
# <a name="message-flow-overview"></a>Übersicht über den Nachrichtenfluss
In einem verteilten System mit untereinander verbundenen Diensten müssen kausale Beziehungen zwischen den Diensten bestimmt werden. Es ist unerlässlich, die verschiedenen Komponenten eines Anforderungsflusses zu verstehen, wenn kritische Szenarien wie Systemüberwachung, Fehlerbehebung und Fehlerursachenanalyse unterstützt werden sollen. Um eine Korrelation der Ablaufverfolgungen verschiedener Dienste zu ermöglichen, wurde in .NET Framework 4 eine entsprechende Unterstützung über folgende Funktionen hinzugefügt:

-   Analytische Ablaufverfolgung: Hierbei handelt es sich um eine Ablaufverfolgungsfunktion mit hoher Leistung und geringer Ausführlichkeit, die auf der Ereignisablaufverfolgung für Windows (Event Tracing for Windows, ETW) aufbaut.

-   End-to-End-Aktivitätsmodell für WCF/WF-Dienste: Diese Funktion unterstützt die Korrelation von Ablaufverfolgungen, die vom <xref:System.ServiceModel>-Namespace und vom <xref:System.Workflow.ComponentModel>-Namespace generiert wurden.

-   ETW-Nachverfolgung für WF: Diese Funktion verwendet Überwachungsdatensätze, die von WF-Diensten generiert wurden, um einen Überblick über den aktuellen Status und Fortschritt eines bestimmten Workflows zu geben.

 Anhand der in einem Überwachungs- oder Ablaufverfolgungsdatensatz protokollierten Fehler können Codefehler oder fehlerhaft formatierte Nachrichten aufgefunden werden. Mit der ActivityId-Eigenschaft des Knotens Korrelation im Nachrichtenheader des Ereignisses kann die Aktivität ermittelt werden, die den Fehler verursacht hat. Zum Aktivieren der Ablaufverfolgung des Nachrichtenflusses nach Aktivitäts-ID finden Sie unter [Configuring Message Flow Tracing](../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md). In diesem Thema wird veranschaulicht, wie die Ablaufverfolgung des Nachrichtenflusses im Projekt aktiviert wird, das im Lernprogramm "Erste Schritte" erstellt wurde.

### <a name="to-enable-message-flow-tracing-in-the-getting-started-tutorial"></a>So aktivieren Sie die Ablaufverfolgung des Nachrichtenflusses im Lernprogramm "Erste Schritte"

1.  Ereignisanzeige öffnen, indem Sie auf **starten**, **ausführen**, und geben Sie `eventvwr.exe`.

2.  Wenn Sie analytische Ablaufverfolgung nicht aktiviert haben, erweitern Sie **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, **Anwendungsserver-Anwendungen** . Wählen Sie **Ansicht**, **analytische und Debugprotokolle einblenden**. Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll aktivieren**. Lassen Sie die Ereignisanzeige geöffnet, damit die Ablaufverfolgungen eingesehen werden können.

3.  Öffnen Sie das Beispiel erstellt der [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md) in Visual Studio 2012. Beachten Sie, dass Sie Visual Studio 2012 als Administrator ausführen müssen, damit der Dienst erstellt werden kann. Wenn Sie die WCF-Beispiele installiert haben, können Sie öffnen die [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md), enthält das abgeschlossene Projekt, das in diesem Tutorial erstellt haben.

4.  Mit der rechten Maustaste die **Service** Projekt, und wählen **hinzufügen**, **neues Element**. Wählen Sie **Anwendungskonfigurationsdatei** , und klicken Sie auf **OK**.

5.  Fügen Sie der im vorherigen Schritt erstellten Datei App.Config den folgenden Code hinzu.

    ```xml
    <system.serviceModel>
      <diagnostics>
        <endToEndTracing propagateActivity="true" messageFlowTracing="true"/>
      </diagnostics>
    </system.serviceModel>
    ```

6.  Führen Sie die Serveranwendung ohne Debuggen aus, indem Sie STRG+F5 drücken. Führen Sie das Clientprojekt, indem Sie mit der rechten Maustaste die **Client** Projekt- und Auswählen von **Debuggen**, **neue Instanz starten**.

7.  Um die Ereignisse vom Client zum Server zu verfolgen, fügen Sie der Anwendungskonfigurationsdatei im Projekt Client Folgendes hinzu.

    ```xml
    <diagnostics>
      <endToEndTracing propagateActivity="true" messageFlowTracing="true"/>
    </diagnostics>
    ```

8.  Fügen Sie in Program.cs auf dem Client die folgende Using-Anweisung hinzu.

    ```
    using System.Diagnostics;
    ```

9. Legen Sie in der Main-Methode in der Datei program.cs im Clientprojekt die Ablaufverfolgungs-GUID fest, die im Ereignisprotokoll weitergegeben werden soll.

    ```
    Guid guid = Guid.NewGuid();
    Trace.CorrelationManager.ActivityId = guid;
    ```

10. Aktualisieren und Überprüfen der **analytisch** Protokoll.  Suchen Sie nach einem Ereignis mit der Ereignis-ID 220.  Wählen Sie das Ereignis aus, und klicken Sie auf die **Details** Registerkarte im Vorschaufenster angezeigt. Dieses Ereignis enthält die Korrelations-ID für die aufrufende Aktivität.

    ```xml
    <Correlation ActivityID="{A066CCF1-8AB3-459B-B62F-F79F957A5036}" />
    ```

    > [!NOTE]
    >  Alle Ereignisse mit derselben GUID in der ActivityID beziehen sich auf eine Anforderung. Damit können Nachrichten von einem bestimmten Client mit einem bestimmten Dienst korreliert werden. Wenn der Client einen anderen Dienst aufgerufen hat, kann der Client anhand der ActivityID identifiziert werden.

11. Gelegentlich kann die ActivityID von der ursprünglichen GUID in eine neue ActivityID geändert werden. In diesem Fall wird ein Übertragungsereignis ausgegeben. Diese Ereignis-ID lautet 499, und das Ereignis enthält die folgenden Daten im Header.

    ```xml
    <Event xmlns="http://schemas.microsoft.com/win/2004/08/events/event">
        <System>
            <Provider Name="Microsoft-Windows-Application Server-Applications" Guid="{c651f5f6-1c0d-492e-8ae1-b4efd7c9d503}" />
            <EventID>499</EventID>
            ...
            <Correlation ActivityID="{A066CCF1-8AB3-459B-B62F-F79F957A5036}" RelatedActivityID="{85FC0930-9C49-42DA-804B-A7368104BD1B}" />
            ...
       </System>
    </Event>
    ```

    > [!NOTE]
    >  Im Übertragungsereignis wird die Änderung der aktiven ActivityID von der als ActivityID angegebenen GUID in die GUID aufgezeichnet, die als RelatedActivityID angegeben ist. Nach Ausgabe des Übertragungsereignisses enthalten sämtliche Ereignisse die neue GUID als ActivityID.
