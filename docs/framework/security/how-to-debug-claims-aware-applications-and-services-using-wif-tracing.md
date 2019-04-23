---
title: 'Vorgehensweise: Debuggen von Ansprüche unterstützenden Anwendungen und Diensten mittels WIF-Ablaufverfolgung'
ms.date: 03/30/2017
ms.assetid: 3d51ba59-3adb-4ca4-bd33-5027531af687
author: BrucePerlerMS
ms.openlocfilehash: 43fa859aa84189817dffe74ecd72253ab9b82585
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59321548"
---
# <a name="how-to-debug-claims-aware-applications-and-services-using-wif-tracing"></a>Vorgehensweise: Debuggen von Ansprüche unterstützenden Anwendungen und Diensten mittels WIF-Ablaufverfolgung
## <a name="applies-to"></a>Gilt für  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   Service Trace Viewer-Tool (SvcTraceViewer.exe)  
  
-   Problembehandlung und Debuggen von WIF-Anwendungen  
  
## <a name="summary"></a>Zusammenfassung  
 Diese Anleitungen beschreiben die erforderlichen Schritte zum Konfigurieren der WIF-Ablaufverfolgung, zum Sammeln von Protokollen und zum Analysieren der Ablaufverfolgungsprotokolle mit dem Trace Viewer-Tool. Dieses Tool stellt eine allgemeine Zuordnung zwischen Protokolleinträgen und Aktionen bereit, die für die Behebung von WIF-bezogenen Problemen erforderlich sind.  
  
## <a name="contents"></a>Inhalt  
  
-   Ziele  
  
-   Zusammenfassung von Schritten  
  
-   Schritt 1- Konfigurieren der WIF-Ablaufverfolgung mithilfe der Konfigurationsdatei "Web.config"  
  
-   Schritt 2: Analysieren von WIF-Ablaufverfolgungsdateien mithilfe des Trace Viewer-Tools  
  
-   Schritt 3 – Identifizieren von Lösungen zum Beheben von WIF-bezogenen Problemen  
  
-   Verwandte Elemente  
  
## <a name="objectives"></a>Ziele  
  
-   Konfigurieren der WIF-Ablaufverfolgung.  
  
-   Anzeigen von Ablaufverfolgungsprotokollen im Trace Viewer-Tool.  
  
-   Identifizieren von WIF-bezogenen Problemen in den Ablaufverfolgungsprotokollen.  
  
-   Anwenden von Korrekturmaßnahmen auf WIF-bezogene Probleme, die in den Ablaufverfolgungsprotokollen gefunden wurden.  
  
## <a name="summary-of-steps"></a>Zusammenfassung von Schritten  
  
-   Schritt 1- Konfigurieren der WIF-Ablaufverfolgung mithilfe der Konfigurationsdatei "Web.config"  
  
-   Schritt 2: Analysieren von WIF-Ablaufverfolgungsdateien mithilfe des Trace Viewer-Tools  
  
-   Schritt 3 – Identifizieren von Lösungen zum Beheben von WIF-bezogenen Problemen  
  
## <a name="step-1--configure-wif-tracing-using-webconfig-configuration-file"></a>Schritt 1- Konfigurieren der WIF-Ablaufverfolgung mithilfe der Konfigurationsdatei "Web.config"  
 In diesem Schritt fügen Sie Konfigurationsabschnitten in der Datei *Web.config* Änderungen hinzu, damit WIF die zugehörigen Ereignisse verfolgen und in einem Ablaufverfolgungsprotokoll speichern kann.  
  
#### <a name="to-configure-wif-tracing-using-webconfig-configuration-file"></a>So konfigurieren Sie die WIF-Ablaufverfolgung mithilfe der Konfigurationsdatei "Web.config"  
  
1. Öffnen Sie die Stammkonfigurationsdatei **Web.config** oder **App.config** im Visual Studio-Editor, indem Sie im **Projektmappen-Explorer** darauf klicken. Wenn Ihre Projektmappe die Konfigurationsdatei **Web.config** bzw. **App.config** nicht enthält, müssen Sie diese hinzufügen. Klicken Sie dazu mit der rechten Maustaste im **Projektmappen-Explorer** auf die Projektmappe, klicken Sie auf **Hinzufügen**, und klicken Sie dann auf **Neues Element…**. Wählen Sie im Dialogfeld **Neues Element** die **Anwendungskonfigurationsdatei** (für **App.config**) oder die **Webkonfigurationsdatei** (für **Web.config**) aus der Liste aus, und klicken Sie auf **OK**.  
  
2. Fügen Sie in der Konfigurationsdatei dem **\<configuration>**-Knoten am Ende der Datei Konfigurationseinträge hinzu, die in etwa wie folgt lauten:  
  
    ```xml  
    <system.diagnostics>  
        <sources>  
            <source name="System.IdentityModel" switchValue="Verbose">  
                <listeners>  
                    <add name="xml" type="System.Diagnostics.XmlWriterTraceListener" initializeData="WIFTrace.e2e"/>  
                </listeners>  
            </source>  
        </sources>  
        <trace autoflush="true"/>  
    </system.diagnostics>  
    ```  
  
3. Die obige Konfiguration weist WIF an, ausführliche Ablaufverfolgungsereignisse zu erstellen und in der Datei *WIFTrace.e2e* zu protokollieren. Eine vollständige Liste der Werte für die **SwitchValue** wechseln, finden Sie in der Ablaufverfolgungsebene-Tabelle finden Sie im folgenden Thema: [Konfigurieren der Ablaufverfolgung](../wcf/diagnostics/tracing/configuring-tracing.md).  
  
## <a name="step-2--analyze-wif-trace-files-using-trace-viewer-tool"></a>Schritt 2: Analysieren von WIF-Ablaufverfolgungsdateien mithilfe des Trace Viewer-Tools  
 In diesem Schritt verwenden Sie das Trace Viewer-Tool (SvcTraceViewer.exe), um WIF-Ablaufverfolgungsprotokolle zu analysieren.  
  
#### <a name="to-analyze-wif-trace-logs-using-trace-viewer-tool-svctraceviewerexe"></a>So analysieren Sie WIF-Ablaufverfolgungsprotokolle mit dem Trace Viewer-Tool (SvcTraceViewer.exe)  
  
1. Das Trace Viewer-Tool (SvcTraceViewer.exe) ist im Windows SDK enthalten. Wenn Sie das Windows SDK noch nicht installiert haben, können Sie es hier herunterladen: [Windows SDK](https://www.microsoft.com/download/en/details.aspx?id=8279).  
  
2. Führen Sie das Trace Viewer-Tool (SvcTraceViewer.exe) aus. Es befindet sich in der Regel im Installationspfad im Ordner **Bin**.  
  
3. Öffnen Sie die WIF-Ablaufverfolgungsprotokolldatei, zum Beispiel „WIFTrace.e2e“, indem Sie im Menü auf **Datei**, **Öffnen...** klicken. oder die Tastenkombination **Strg+O** verwenden. Die Ablaufverfolgungsprotokolldatei wird im Trace Viewer-Tool geöffnet.  
  
4. Überprüfen Sie die Einträge auf der Registerkarte **Aktivität**. Jeder Eintrag muss eine Aktivitätsnummer, die Anzahl der protokollierten Ablaufverfolgungen, die Dauer der Aktivität sowie Zeitstempel für Anfang und Ende der Aktivität enthalten.  
  
5. Klicken Sie auf die Registerkarte **Aktivität**. Im Hauptbereich des Tools sollten ausführliche Ablaufverfolgungseinträge angezeigt werden. Verwenden der **Ebene** Dropdown-Liste auf das Menü, um bestimmte Ablaufverfolgungsebenen, z. B. filtern: **Alle**, **Warnung**, **Fehler**, **Informationen**usw.  
  
6. Klicken Sie auf bestimmte Ablaufverfolgungseinträge, um die Einzelheiten im unteren Bereich des Tools zu überprüfen. Die Einzelheiten können in den Ansichten **Formatiert** und **XML** angezeigt werden. Wählen Sie die jeweils entsprechende Registerkarte aus.  
  
## <a name="step-3--identify-solutions-to-fix-wif-related-issues"></a>Schritt 3 – Identifizieren von Lösungen zum Beheben von WIF-bezogenen Problemen  
 In diesem Schritt ermitteln Sie mithilfe des WIF-Ablaufverfolgungsprotokolls und des Trace Viewer-Tools Lösungen für identifizierte WIF-bezogene Probleme. Dieses Tool zeigt allgemeine Zuordnungen zwischen WIF-bezogenen Ausnahmen und möglichen Lösungen oder Aktionen auf, die zum Beheben des Problems erforderlich sind.  
  
#### <a name="to-identify-solutions-to-fix-wif-related-issues"></a>So identifizieren Sie Lösungen zum Beheben WIF-bezogener Probleme  
  
1. Überprüfen Sie in der folgenden Tabelle die WIF-Ausnahmen und die Aktionen, die zum Beheben der Probleme erforderlich sind.  
  
|**Fehler-ID**|**Fehlermeldung**|**Aktion zum Beheben des Fehlers**|  
|-|-|-|  
|ID4175|Der Aussteller des Sicherheitstokens wurde von der IssuerNameRegistry nicht erkannt.  Konfigurieren Sie die IssuerNameRegistry, um einen gültigen Name für diesen Aussteller zurückzugeben und die Sicherheitstoken dieses Ausstellers zu akzeptieren.|Dieser Fehler kann entstehen, wenn Sie einen Fingerabdruck aus dem MMC-Snap-In kopieren und in die Datei *Web.config* einfügen. Insbesondere beim Kopieren des Fingerabdrucks aus dem Fenster mit den Zertifikateigenschaften kann es passieren, dass ein zusätzliches, nicht druckbares Zeichen in die Zeichenfolge eingefügt wird. Dieses zusätzliche Zeichen bewirkt, dass der Fingerabdruck Übereinstimmung ein Fehler auftritt. Das Verfahren für den Fingerabdruck richtig kopieren finden Sie unter [Claims-basierte Single Sign-in für das Web und die Microsoft Azure](https://docs.microsoft.com/previous-versions/msp-n-p/ff359102%28v=pandp.10%29).|  
  
## <a name="related-items"></a>Verwandte Elemente  
  
-   [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting (Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung)](../wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
