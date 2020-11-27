---
title: Übersicht über den Nachrichtenfluss
ms.date: 03/30/2017
ms.assetid: fb0899e1-84cc-4d90-b45b-dc5a50063943
ms.openlocfilehash: cb2924b62fce62620b664efa34208deb12dd34b7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285537"
---
# <a name="message-flow-overview"></a>Übersicht über den Nachrichtenfluss

In einem verteilten System mit untereinander verbundenen Diensten müssen kausale Beziehungen zwischen den Diensten bestimmt werden. Es ist unerlässlich, die verschiedenen Komponenten eines Anforderungsflusses zu verstehen, wenn kritische Szenarien wie Systemüberwachung, Fehlerbehebung und Fehlerursachenanalyse unterstützt werden sollen. Um eine Korrelation der Ablaufverfolgungen verschiedener Dienste zu ermöglichen, wurde in .NET Framework 4 eine entsprechende Unterstützung über folgende Funktionen hinzugefügt:

- Analytische Ablaufverfolgung: Hierbei handelt es sich um eine Ablaufverfolgungsfunktion mit hoher Leistung und geringer Ausführlichkeit, die auf der Ereignisablaufverfolgung für Windows (Event Tracing for Windows, ETW) aufbaut.

- End-to-End-Aktivitätsmodell für WCF/WF-Dienste: Diese Funktion unterstützt die Korrelation von Ablaufverfolgungen, die vom <xref:System.ServiceModel>-Namespace und vom <xref:System.Workflow.ComponentModel>-Namespace generiert wurden.

- ETW-Nachverfolgung für WF: Diese Funktion verwendet Überwachungsdatensätze, die von WF-Diensten generiert wurden, um einen Überblick über den aktuellen Status und Fortschritt eines bestimmten Workflows zu geben.

 Anhand der in einem Überwachungs- oder Ablaufverfolgungsdatensatz protokollierten Fehler können Codefehler oder fehlerhaft formatierte Nachrichten aufgefunden werden. Mit der ActivityId-Eigenschaft des Knotens Korrelation im Nachrichtenheader des Ereignisses kann die Aktivität ermittelt werden, die den Fehler verursacht hat. Informationen zum Aktivieren der Ablauf Verfolgung für den Nachrichtenfluss nach der Aktivitäts-ID finden Sie unter [Konfigurieren der Ablauf Verfolgung](./etw/configuring-message-flow-tracing.md) In diesem Thema wird veranschaulicht, wie die Ablaufverfolgung des Nachrichtenflusses im Projekt aktiviert wird, das im Lernprogramm "Erste Schritte" erstellt wurde.

### <a name="to-enable-message-flow-tracing-in-the-getting-started-tutorial"></a>So aktivieren Sie die Ablaufverfolgung des Nachrichtenflusses im Lernprogramm "Erste Schritte"

1. Öffnen Sie Ereignisanzeige, indem Sie auf **Start** und **Ausführen** klicken und dann eingeben `eventvwr.exe` .

2. Wenn Sie die analytische Ablauf Verfolgung nicht aktiviert haben, erweitern Sie **Anwendungs-und Dienst Protokolle**, **Microsoft**, **Windows**, **Anwendungs Server-Anwendungen**. Wählen Sie **Ansicht**, **analytische und Debugprotokolle anzeigen** aus. Klicken Sie mit der rechten Maustaste auf **Analyse** , und wählen Sie **Protokoll aktivieren** Lassen Sie die Ereignisanzeige geöffnet, damit die Ablaufverfolgungen eingesehen werden können.

3. Öffnen Sie das Beispiel, das im [Tutorial "Getting Started](../getting-started-tutorial.md) " in Visual Studio 2012 erstellt wurde. Beachten Sie, dass Sie Visual Studio 2012 als Administrator ausführen müssen, damit der Dienst erstellt werden kann. Wenn Sie die WCF-Beispiele installiert [haben, können Sie die ersten](../samples/getting-started-sample.md)Schritte öffnen, die das abgeschlossene Projekt enthalten, das Sie im Tutorial erstellt haben.

4. Klicken Sie mit der rechten Maustaste auf das **Dienst** Projekt, und wählen Sie **Hinzufügen**, **Neues Element** Wählen Sie **Anwendungs Konfigurationsdatei** , und klicken Sie auf **OK**

5. Fügen Sie der im vorherigen Schritt erstellten Datei App.Config den folgenden Code hinzu.

    ```xml
    <system.serviceModel>
      <diagnostics>
        <endToEndTracing propagateActivity="true" messageFlowTracing="true"/>
      </diagnostics>
    </system.serviceModel>
    ```

6. Führen Sie die Serveranwendung ohne Debuggen aus, indem Sie STRG+F5 drücken. Führen Sie das Client Projekt aus, indem Sie mit der rechten Maustaste auf das **Client** Projekt klicken und **Debuggen**, **neue Instanz starten** auswählen

7. Um die Ereignisse vom Client zum Server zu verfolgen, fügen Sie der Anwendungskonfigurationsdatei im Projekt Client Folgendes hinzu.

    ```xml
    <diagnostics>
      <endToEndTracing propagateActivity="true" messageFlowTracing="true"/>
    </diagnostics>
    ```

8. Fügen Sie in Program.cs auf dem Client die folgende Using-Anweisung hinzu.

    ```csharp
    using System.Diagnostics;
    ```

9. Legen Sie in der Main-Methode in der Datei program.cs im Clientprojekt die Ablaufverfolgungs-GUID fest, die im Ereignisprotokoll weitergegeben werden soll.

    ```csharp
    Guid guid = Guid.NewGuid();
    Trace.CorrelationManager.ActivityId = guid;
    ```

10. Aktualisieren Sie das **analytische**  Protokoll, und untersuchen Sie es.  Suchen Sie nach einem Ereignis mit der Ereignis-ID 220.  Wählen Sie das Ereignis aus, und klicken Sie im Vorschaufenster auf die Registerkarte **Details** . Dieses Ereignis enthält die Korrelations-ID für die aufrufende Aktivität.

    ```xml
    <Correlation ActivityID="{A066CCF1-8AB3-459B-B62F-F79F957A5036}" />
    ```

    > [!NOTE]
    > Alle Ereignisse mit derselben GUID in der ActivityID beziehen sich auf eine Anforderung. Damit können Nachrichten von einem bestimmten Client mit einem bestimmten Dienst korreliert werden. Wenn der Client einen anderen Dienst aufgerufen hat, kann der Client anhand der ActivityID identifiziert werden.

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
    > Im Übertragungsereignis wird die Änderung der aktiven ActivityID von der als ActivityID angegebenen GUID in die GUID aufgezeichnet, die als RelatedActivityID angegeben ist. Nach Ausgabe des Übertragungsereignisses enthalten sämtliche Ereignisse die neue GUID als ActivityID.
