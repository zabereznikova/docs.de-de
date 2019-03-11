---
title: Service Trace Viewer-Tool (SvcTraceViewer.exe)
ms.date: 03/30/2017
ms.assetid: 9027efd3-df8d-47ed-8bcd-f53d55ed803c
ms.openlocfilehash: 723b1c6858f0c56d4834dc937b9f4883e22156e6
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57680385"
---
# <a name="service-trace-viewer-tool-svctraceviewerexe"></a>Service Trace Viewer-Tool (SvcTraceViewer.exe)
Windows Communication Foundation (WCF) Service Trace Viewer-Tool können Sie die Analyse der diagnoseablaufverfolgungen, die von WCF generiert werden. Service Trace Viewer bietet eine Möglichkeit, ganz einfach zusammenführen, anzeigen und Filtern von Ablaufverfolgungsnachrichten im Protokoll, damit können Sie diagnostizieren, reparieren und prüfen die WCF-Dienstprobleme.  
  
## <a name="configuring-tracing"></a>Konfigurieren der Ablaufverfolgung  
 Diagnoseablaufverfolgungen stellen Informationen bereit, die Aufschluss darüber geben, was beim Ausführen der Vorgänge in der Anwendung geschieht. Wie der Name bereits andeutet, können Sie Vorgänge von der Quelle zum Ziel und durch Zwischenpunkte hindurch verfolgen.  
  
 Sie können die Ablaufverfolgung, die mithilfe der Anwendungskonfigurationsdatei konfigurieren – entweder Web.config für im Web gehostete Anwendungen oder *Appname*.config für selbst gehostete Anwendungen. Im Folgenden finden Sie ein Beispiel dazu:  
  
```xml  
<system.diagnostics>  
    <trace autoflush="true" />  
    <sources>  
            <source name="System.ServiceModel"   
                    switchValue="Information, ActivityTracing"  
                    propagateActivity="true">  
            <listeners>  
               <add name="sdt"   
                   type="System.Diagnostics.XmlWriterTraceListener"   
                   initializeData= "SdrConfigExample.e2e" />  
            </listeners>  
         </source>  
    </sources>  
</system.diagnostics>  
```  
  
 In diesem Beispiel werden Name und Typ des Ablaufverfolgungslisteners angegeben. Der Name des Listeners ist `sdt`, und der standardmäßige .NET Framework-Ablaufverfolgungslistener (System.Diagnostics.XmlWriterTraceListener) wird als Typ hinzugefügt. Die `initializeData` Attribut wird verwendet, um den Namen der Protokolldatei für diesen Listener auf festzulegen `SdrConfigExample.e2e`. Für die Protokolldatei können Sie einen einfachen Dateinamen durch einen vollqualifizierten Pfad ersetzen.  
  
 Mit dem Beispiel wird eine Datei namens "SdrConfigExample.e2e" im Stammverzeichnis erstellt. Wenn Sie das Trace Viewer zum Öffnen der Datei wie im Abschnitt "Öffnen und Anzeigen von WCF-Ablaufverfolgungsdateien" beschrieben verwenden, sehen Sie alle Nachrichten, die gesendet wurden.  
  
 Die Ablaufverfolgungsebene wird von der `switchValue`-Einstellung gesteuert. Die verfügbaren Ablaufverfolgungsebenen werden in der folgenden Tabelle beschrieben.  
  
|Ablaufverfolgungsebene|Beschreibung|  
|-----------------|-----------------|  
|Kritisch|-Protokolliert FailFast- und Ereignisprotokolleinträge und Korrelationsinformationen für die Ablaufverfolgung. Im Folgenden finden Sie einige Beispiele für die Verwendung der Critical-Ebene:<br />-Die AppDomain ist wegen einer nicht behandelten Ausnahme.<br />– In Ihrer Anwendung nicht gestartet.<br />– Die Meldung, die den Fehler stammt vom MyApp.exe-Prozess verursacht hat.|  
|Fehler|-Protokolliert alle Ausnahmen. Sie können die Error-Ebene in den folgenden Situationen verwenden:<br />-Code ist aufgrund einer ungültigen Umwandlungsausnahme abgestürzt.<br />-Eine Ausnahme "Fehler beim Erstellen des Endpunkts" verursacht Ihrer Anwendung beim Start nicht.|  
|Warnung|– Eine Bedingung vorhanden ist, kann anschließend in einen Fehler oder einen kritischen Fehler führen. Sie können diese Ebene in folgenden Situationen verwenden:<br />– Die Anwendung empfängt mehr Anforderungen, als die einschränkungseinstellungen zulassen.<br />– Die empfangende Warteschlange hat 98 Prozent der konfigurierten Kapazität erreicht.|  
|Information|-Nachrichten für die Überwachung und Diagnose des Systemstatus, der leistungsmessung oder profilerstellung nützlich werden generiert. Sie können solche Informationen zur Kapazitätsplanung und Leistungsverwaltung nutzen. Sie können diese Ebene in folgenden Situationen verwenden:<br />– Ein Fehler auf, nachdem die Nachricht die AppDomain erreicht hat und deserialisiert wurde.<br />– Ein Fehler auf, während die HTTP-Bindung erstellt wurde.|  
|Ausführlich|Debugebene für sowohl Benutzercode Ablaufverfolgung und Wartung. Legen Sie diese Ebene in folgenden Fällen fest:<br />– Sie sind nicht Sie sicher, dass die Methode im Code aufgerufen wurde, wenn der Fehler aufgetreten ist.<br />– Sie haben einen falschen Endpunkt konfiguriert, und der Dienst konnte nicht gestartet werden, da der Eintrag im reservierungsspeicher gesperrt ist.|  
|ActivityTracing|Ablaufereignisse zwischen Verarbeitungsaktivitäten und Komponenten.<br /><br /> Diese Ebene ermöglicht es Administratoren und Entwicklern, Anwendungen in einer Anwendungsdomäne zu korrelieren.<br /><br /> -Ablaufverfolgungen für Aktivitätsgrenzen: Start/Stopp.<br />-Ablaufverfolgungen für Übertragungen.|  
  
 Mit `add` können Sie den Namen und den Typ des Ablaufverfolgungslisteners angeben, den Sie verwenden möchten. In der Beispielkonfiguration wird der Listener `sdt` genannt und der standardmäßige .NET Framework-Ablaufverfolgungslistener (`System.Diagnostics.XmlWriterTraceListener`) wird als Typ hinzugefügt. Verwenden Sie `initializeData`, um den Namen der Protokolldatei für diesen Listener festzulegen. Außerdem können Sie einen einfachen Dateinamen durch einen vollqualifizierten Pfad ersetzen.  

Ab .NET Framework 4.8, werden in die richtige Farbe Kombinationsfeld-Steuerelemente in einigen Designs mit hohem Kontrast angezeigt werden. Sie können diese Änderung deaktivieren, durch das Entfernen der folgenden Einstellung aus der *svcTraceViewer.exe.config* Datei:

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
```

## <a name="using-the-service-trace-viewer-tool"></a>Verwenden des Service Trace Viewer-Tools  
  
### <a name="opening-and-viewing-wcf-trace-files"></a>Öffnen und Anzeigen von WCF-Ablaufverfolgungsdateien  
 Service Trace Viewer unterstützt drei Dateitypen:  
  
-   WCF-Ablaufverfolgungsdatei (.svcLog)  
  
-   Ereignisablaufverfolgungs-Datei (.etl)  
  
-   Crimson-Ablaufverfolgungsdatei  
  
 Mit Service Trace Viewer können Sie jede unterstützte Ablaufverfolgungsdatei öffnen, weitere Ablaufverfolgungsdateien hinzufügen und integrieren oder eine Gruppe von Ablaufverfolgungsdateien gleichzeitig öffnen und zusammenführen.  
  
##### <a name="to-open-a-trace-file"></a>So öffnen Sie eine Ablaufverfolgungsdatei  
  
1.  Starten Sie Ihre WCF-Installationsverzeichnis (c:\Programme\Microsoft SDKs\Windows\v6.0\Bin) wechseln, und geben Sie ein Befehlsfenster mit Service Trace Viewer `SvcTraceViewer.exe`.  
  
> [!NOTE]
>  Das Service Trace Viewer-Tool kann zwei Dateitypen zuweisen: .svclog und .stvproj. Sie können zwei Parameter in der Befehlszeile verwenden, um die Dateierweiterungen zu registrieren und deren Registrierung aufzuheben.  
>   
>  /register: Registriert die Zuweisung der Dateierweiterungen ".svclog" und ".stvproj" in SvcTraceViewer.exe.  
>   
>  /unregister: Hebt die Registrierung der zugewiesenen Dateierweiterungen ".svclog" und ".stvproj" in SvcTraceViewer.exe auf.  
  
1.  Service Trace Viewer starten, klicken Sie auf **Datei** und zeigen Sie dann auf **öffnen**. Navigieren Sie zu dem Speicherort, an dem die Ablaufverfolgungsdateien gespeichert sind.  
  
2.  Doppelklicken Sie auf die Ablaufverfolgungsdatei, die Sie öffnen möchten.  
  
    > [!NOTE]
    >  Halten Sie die UMSCHALTTASTE gedrückt, während Sie auf mehrere Ablaufverfolgungsdateien klicken, um sie gleichzeitig auszuwählen und zu öffnen. Service Trace Viewer führt den Inhalt aller Dateien zusammen und zeigt ihn in einer Ansicht an. Sie können zum Beispiel gleichzeitig Ablaufverfolgungsdateien von Client und Dienst öffnen. Dies ist nützlich, wenn Sie die Nachrichtenprotokollierung und Aktivitätspropagierung in der Konfiguration aktiviert haben. Auf diese Weise können Sie den Nachrichtenaustausch zwischen Client und Dienst untersuchen. Sie können auch mehrere Dateien in den Viewer ziehen oder verwenden Sie die **Projekt** Registerkarte. Weitere Informationen finden Sie im Abschnitt über das Verwalten des Projekts.  
  
3.  Um der Auflistung, das geöffnet ist Weitere Ablaufverfolgungsdateien hinzuzufügen, klicken Sie auf **Datei** und zeigen Sie dann auf **hinzufügen**. Navigieren Sie in dem geöffneten Fenster zum Speicherort der Ablaufverfolgungsdateien, und doppelklicken Sie auf die Datei, die Sie hinzufügen möchten.  
  
> [!CAUTION]
>  Es ist nicht empfehlenswert, eine Ablaufverfolgungsprotokolldatei zu laden, die größer als 200 MB ist. Wenn Sie eine Datei laden, die diesen Wert überschreitet, nimmt der Ladeprozess je nach Computerressourcen unter Umständen viel Zeit in Anspruch. Das Service Trace Viewer-Tool reagiert unter Umständen über einen längeren Zeitraum nicht oder belegt den gesamten Speicher des Computers. Es wird empfohlen, dass Sie das teilweise Laden konfigurieren, um dies zu vermeiden. Weitere Informationen dazu finden Sie im Abschnitt "Laden von großen Ablaufverfolgungsdateien".  
  
#### <a name="event-tracing-and-crimson-tracing"></a>Ereignisablaufverfolgung und Crimson-Ablaufverfolgung  
 Systemeigene Format des Viewers ist das aktivitätsablaufverfolgungs-Format, das von WCF ausgegeben. In einem anderen Format ausgegebene Ablaufverfolgungen müssen konvertiert werden, bevor der Viewer sie anzeigen kann. Zurzeit unterstützt der Viewer zusätzlich zum Aktivitätsablaufverfolgungs-Format die Ereignisablaufverfolgung und Crimson-Ablaufverfolgung.  
  
 Wenn Sie eine Datei öffnen, die keine Aktivitätsablaufverfolgungen enthält, versucht der Viewer, die Datei zu konvertieren. Sie müssen den Namen und den Speicherort der Datei angeben, die die zu konvertierenden Ablaufverfolgungsdaten enthält. Nachdem die Daten konvertiert wurden, zeigt der Viewer den Inhalt der neuen Datei an.  
  
> [!NOTE]
>  Konvertierung erfordert Speicherplatz zum Speichern der konvertierten Ablaufverfolgungsdaten. Stellen Sie sicher, dass ausreichender Speicherplatz zum Speichern der Daten vorhanden ist, bevor Sie eine Konvertierung starten. Andernfalls schlägt die Konvertierung fehl.  
  
### <a name="managing-projects"></a>Verwalten von Projekten  
 Der Viewer unterstützt Projekte, um die Anzeige mehrerer Ablaufverfolgungsdateien zu vereinfachen. Wenn Sie zum Beispiel über eine Client- und eine Dienst-Ablaufverfolgungsdatei verfügen, können Sie diese einem Projekt hinzufügen. Auf diese Weise werden jedes Mal, wenn Sie das Projekt öffnen, alle Ablaufverfolgungsdateien im Projekt gleichzeitig geladen.  
  
 Es gibt zwei Möglichkeiten zum Verwalten von Projekten:  
  
-   In der **Datei** Menü öffnen, speichern und schließen Sie Projekte.  
  
-   In der **Projekt** Registerkarte können Sie ein Projekt Dateien hinzufügen.  
  
### <a name="viewing-wcf-traces"></a>Anzeigen von WCF-Ablaufverfolgungen  
 WCF gibt ablaufverfolgungen im aktivitätsablaufverfolgungs-Format. Im Aktivitätsablaufverfolgungs-Modell werden einzelne Ablaufverfolgungen nach ihrem jeweiligen Zweck in Aktivitäten gruppiert. Zwischen den Aktivitäten wird eine logische Ablaufsteuerung übertragen. Zum Beispiel werden während der Lebensdaueraktivität einer Anwendung zahlreiche Nachrichtensendeaktivitäten angezeigt und wieder entfernt. Weitere Informationen zum Anzeigen von ablaufverfolgungen und Aktivitäten und die Benutzeroberfläche des Service Trace Viewer zu finden Sie unter [mithilfe von Service Trace Viewer für korreliert Ablaufverfolgungen anzeigen und Problembehandlung](../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
#### <a name="switching-to-different-views"></a>Umschalten zu anderen Ansichten  
 Der Service Trace Viewer umfasst die folgenden Ansichten. Sie werden als Registerkarten im linken Bereich des Viewers angezeigt und kann auch aus zugegriffen werden die **Ansicht** Menü.  
  
-   Aktivitätsansicht  
  
-   Projektansicht  
  
-   Nachrichtenansicht  
  
-   Diagrammansicht  
  
##### <a name="activity-view"></a>Aktivitätsansicht  
 Nachdem die Ablaufverfolgungsdateien geöffnet sind, sehen Sie die ablaufverfolgungen in Aktivitäten gruppiert und angezeigt, der **Aktivität** im linken Bereich.  
  
 Die **Aktivität** Ansicht zeigt Aktivitätsnamen, die Anzahl der ablaufverfolgungen in der Aktivität, Dauer, Startzeit und Endzeit.  
  
 Indem Sie auf eine der aufgeführten Aktivitäten klicken, werden die Ablaufverfolgungen in dieser Aktivität rechts im Ablaufverfolgungsfenster angezeigt. Sie können dann eine Ablaufverfolgung auswählen, um die Details anzuzeigen.  
  
 Sie können mehrere Aktivitäten auswählen, durch Drücken der **STRG** oder **UMSCHALT** Schlüssel und die gewünschten Aktivitäten klicken. Im Ablaufverfolgungsbereich werden alle Ablaufverfolgungen der ausgewählten Aktivitäten angezeigt.  
  
 Sie können eine Aktivität, um in der sie angezeigt doppelklicken **Graph** anzeigen. Die alternative besteht darin, eine Aktivität auswählen, und wechseln Sie zur **Graph** anzeigen.  
  
> [!NOTE]
>  Die Aktivität "000000000000" ist eine spezielle Aktivität, die in der Diagrammansicht angezeigt werden kann. Da alle anderen Aktivitäten damit verknüpft sind, hat das Anzeigen dieser Aktivität schwerwiegende Auswirkungen auf die Leistung.  
  
 Sie können auf den Spaltentitel klicken, um die Aktivitätsliste zu sortieren. Aktivitäten mit Warnungsablaufverfolgungen weisen einen gelben Hintergrund auf und Aktivitäten mit Fehlerablaufverfolgungen einen roten Hintergrund.  
  
 Es gibt verschiedene Typen von Aktivitäten, und jeder Typ verfügt über ein entsprechendes Symbol links neben der jeweiligen Aktivität. Informationen zur Bedeutung der Symbole finden Sie im Abschnitt zu Ablaufverfolgungssymbolen.  
  
##### <a name="project-view"></a>Projektansicht  
 Diese Ansicht ermöglicht Ihnen, Ablaufverfolgungsdateien im aktuellen Projekt zu verwalten. Weitere Informationen finden Sie im Abschnitt über das Verwalten des Projekts.  
  
##### <a name="graph-view"></a>Diagrammansicht  
 Eines der leistungsstärksten Funktionen von Service Trace Viewer ist der **Graph** Ansicht, in der die Ablaufverfolgungsdaten für eine bestimmte Aktivität als Diagramm angezeigt. Im Diagramm können Sie die schrittweise Ausführung von Ereignissen und die Wechselbeziehungen zwischen mehreren Aktivitäten nachvollziehen, während die Daten diese durchlaufen.  
  
 So wechseln Sie zu **Graph** anzuzeigen, wählen Sie eine Aktivität in der **Aktivität** anzuzeigen, und klicken Sie auf die **Aktivität** Registerkarte oder auf eine Nachrichtenprotokoll-Ablaufverfolgung in der **Nachricht**Anzeigen. Wenn mehrere Ablaufverfolgungsdateien geladen sind und die Aktivität Ablaufverfolgungen aus mehr als einer Datei umfasst, werden alle relevanten Ablaufverfolgungen in der Diagrammansicht angezeigt. Doppelklicken auf die Aktivitäten und Nachrichtenprotokoll-ablaufverfolgungen auch gelangen Sie in der **Graph** anzeigen.  
  
 In **Graph** jede vertikale Spalte stellt eine Aktivität, und jeder Block in der Spalte eine Ablaufverfolgung dar. Die Aktivitäten werden nach Prozess (oder Thread) gruppiert. Die kleinen Pfeile zwischen Aktivitäten stellen Übertragungen dar. Die großen Pfeile zwischen Prozessen stellen Nachrichtenaustausch dar. Die ausgewählte Aktivität wird stets gelb angezeigt.  
  
###### <a name="selecting-traces-in-the-graph"></a>Auswählen von Ablaufverfolgungen im Diagramm  
  
1.  Klicken Sie auf einen Block im Diagramm.  
  
2.  Wählen Sie mit den Nach-oben- und Nach-unten-Pfeilen die benachbarten Ablaufverfolgungen aus.  
  
3.  Achten Sie auf die Ablaufverfolgungsinformationen im Ablaufverfolgungsbereich und Detailbereich.  
  
###### <a name="expanding-or-collapsing-activity-transfers"></a>Erweitern oder Reduzieren von Aktivitätsübertragungen  
 Sie können Aktivitätsübertragungen erweitern, wenn die ausgewählte Aktivität an eine andere Aktivität übertragen wird. Sie können auf diese Weise den Übertragungen folgen.  
  
 So erweitern oder reduzieren Sie Aktivitätsübertragungen  
  
1.  Suchen Sie die übertragungsablaufverfolgung mit einem Zeichen "+", auf der linken Seite neben dem übertragungssymbol.  
  
2.  Klicken Sie auf "+", oder drücken Sie **STRG** und "+" mithilfe der Tastatur.  
  
3.  Die nächste Aktivität wird im Diagramm angezeigt.  
  
4.  Ein "-" wird links neben dem übertragungssymbol. Klicken Sie auf der "-" oder drücken Sie STRG und "-", die aktivitätsübertragung wird reduziert.  
  
> [!NOTE]
>  Wenn eine Aktivität über mehrere Übertragungen verfügt und Sie eine der Übertragungen erweitern, werden Aktivitäten angezeigt, die von der Stammaktivität zu der neuen Aktivität führen. Diese neuen Aktivitäten werden reduziert angezeigt. Wenn Sie die Details dieser Aktivitäten anzeigen möchten, erweitern Sie sie vertikal, indem Sie auf das Erweiterungssymbol in der Kopfzeile des Diagramms klicken.  
  
###### <a name="expanding-or-collapsing-activities-vertically"></a>Vertikales Erweitern oder Reduzieren von Aktivitäten  
 Der Viewer blendet unnötige Details im Aktivitätsdiagramm aus, indem er Aktivitäten reduziert. In einer reduzierten Aktivität werden einzelne Ablaufverfolgungen nicht angezeigt. Nur Ablaufverfolgungsübertragungen werden angezeigt. Wenn alle Ablaufverfolgungen in einer Aktivität angezeigt werden sollen, erweitern Sie die Aktivität vertikal, indem Sie auf das Erweiterungssymbol der Aktivität in der Kopfzeile des Diagramms klicken.  
  
 So erweitern oder reduzieren Sie Aktivitäten vertikal  
  
1.  Klicken Sie auf das Symbol "+" in der Kopfzeile der Aktivität um die Aktivität vertikal zu erweitern.  
  
2.  Beachten Sie, dass alle Ablaufverfolgungen im Diagramm angezeigt werden.  
  
3.  Klicken Sie auf der "-"-Symbol in der Kopfzeile der Aktivität auf die Aktivität vertikal zu reduzieren.  
  
4.  Beachten Sie, dass nur wichtige Übertragungen, Nachrichtenprotokolle, Warnungs- und Ausnahmeablaufverfolgungen in der Aktivität angezeigt werden.  
  
###### <a name="options"></a>Optionen  
 Sie können zwei Optionen auswählen der **Option** Menü in der Diagrammansicht.  
  
-   Ablaufverfolgungen für Aktivitätsgrenzen anzeigen: Wenn diese Option nicht aktiviert ist, werden die Ablaufverfolgungen für Aktivitätsgrenzen im Diagramm ignoriert.  
  
-   Ausführliche Ablaufverfolgungen ohne Nachrichten anzeigen: Wenn diese Option deaktiviert ist, werden ausführliche Ebenenablaufverfolgungen, außer Nachrichtenablaufverfolgungen, ignoriert. In den meisten Fällen sind ausführliche Ebenenablaufverfolgungen für die Analyse weniger wichtig. Diese Option ist nützlich, wenn Sie ausführliche Ebenenablaufverfolgungen nicht analysieren möchten, sondern sich auf wichtigere Ablaufverfolgungen konzentrieren möchten.  
  
###### <a name="layout-mode"></a>Layoutmodus  
 Der Viewer hat zwei Layoutmodi: **Prozess** und **Thread**. Diese Einstellung definiert die größte Organisationseinheit. Der Standardwert ist **Prozess**, was bedeutet, dass die Aktivitäten im Diagramm nach Prozessen gruppiert werden.  
  
###### <a name="execution-list"></a>Ausführungsliste  
 Sie können in dieser Dropdownliste auswählen, welcher Prozess oder Thread im Diagramm angezeigt werden soll. Wenn zum Beispiel Ablaufverfolgungsdateien von zwei Clients (A und B) sowie ein Dienst geöffnet sind und Sie nur den Dienst und Client A im Diagramm anzeigen möchten, können Sie die Auswahl von Client B aufheben.  
  
#### <a name="viewing-trace-details"></a>Anzeigen von Ablaufverfolgungsdetails  
 Um Ablaufverfolgungsdetails anzuzeigen, wählen Sie eine Ablaufverfolgung im Ablaufverfolgungsbereich aus. Die Details werden im Detailbereich angezeigt.  
  
##### <a name="trace-pane"></a>Ablaufverfolgungsbereich  
 Der rechte obere Bereich im Service Trace Viewer ist der Ablaufverfolgungsbereich. In diesem Bereich werden alle Ablaufverfolgungen in der ausgewählten Aktivität mit zusätzlichen Informationen aufgeführt, beispielsweise Ablaufverfolgungsebene, Thread-ID und Prozessname.  
  
 Sie können die unformatierten XML-Codes der Ablaufverfolgung in die Zwischenablage kopieren, indem Sie mit der rechten Maustaste in einer Ablaufverfolgungs und auswählen **Ablaufverfolgung in Zwischenablage kopieren**.  
  
##### <a name="detail-pane"></a>Detailbereich  
 Der unterste linke Bereich im Service Trace Viewer ist der Detailbereich. Er stellt drei Registerkarten zum Anzeigen von Ablaufverfolgungsdetails bereit.  
  
 Die **formatierte** zeigt die Informationen organisiert. Es werden alle bekannten XML-Elemente in Tabellen und Strukturen aufgelistet, sodass die Informationen einfacher zu lesen und zu interpretieren sind.  
  
 Die **XML** Ansicht zeigt XML-Code, die der ausgewählten Ablaufverfolgung entspricht. Hervorhebung und Syntaxfarbe werden unterstützt. Bei Verwendung von **finden** nach Zeichenfolgen suchen, die Ergebnisse der Suche werden hervorgehoben.  
  
 Die **Nachricht** zeigt den Nachrichtenteil des XML-Nachrichtenprotokoll-ablaufverfolgungen. Er ist nicht sichtbar, wenn Sie eine Ablaufverfolgung ohne Nachrichten auswählen.  
  
### <a name="filtering-wcf-traces"></a>Filtern von WCF-Ablaufverfolgungen  
 Um die Analyse von Ablaufverfolgungsdateien zu vereinfachen, können Sie sie auf folgende Weisen filtern:  
  
-   Die Filtersymbolleiste ermöglicht den Zugriff auf vordefinierte und benutzerdefinierte Filter. Es kann aktiviert werden, über die **Ansicht** Menü.  
  
-   Der vordefinierte Filter des Viewers kann verwendet werden, um Teile der WCF-ablaufverfolgungen selektiv zu filtern. Standardmäßig ist der Filter so eingestellt, dass alle Infrastrukturablaufverfolgungen zugelassen werden. Die Einstellungen dieses Filters werden definiert, der **Filteroptionen** Untermenü unter **Ansicht** Menü.  
  
-   Benutzerdefinierte XPath-Filter ermöglichen Benutzern den Vollzugriff auf die Filterung. Sie können definiert werden, der **benutzerdefinierter Filter** unter **Ansicht** Menü.  
  
 Es werden nur die Ablaufverfolgungen angezeigt, die alle Filter durchlaufen haben.  
  
#### <a name="using-the-filter-toolbar"></a>Verwenden der Filtersymbolleiste  
 Die Filtersymbolleiste wird im oberen Teil des Tools angezeigt. Wenn es nicht vorhanden ist, können Sie sie in Aktivieren der **Ansicht** Menü. Die Leiste verfügt über drei Komponenten:  
  
-   Schaue nach: **Suchen Sie nach** definiert das Objekt, bei dem Filtervorgang gesucht. Z. B. Wenn Sie alle ablaufverfolgungen, die ausgegeben wird, wurden im Kontext des Prozesses X finden möchten, legen Sie dieses Feld x und **Suchen In** Feld 'Prozessname'. Dieses Feld ändert sich in ein DateTime-Auswahlsteuerelement, wenn ein zeitbasierter Filter ausgewählt wird.  
  
-   Suchen Sie: Dieses Feld definiert den Typ des anzuwendenden Filters.  
  
-   Ebene: Die ebeneneinstellung definiert die minimale vom Filter zugelassene Ablaufverfolgungsebene. So werden bei Auswahl der Error-Ebene oder höher nur die Ablaufverfolgungen auf Fehlerebene oder einer höheren Ebene angezeigt. Dieser Filter wird mit den unter Suchen nach und Suchen in angegebenen Kriterien kombiniert.  
  
 Die **jetzt filtern** Schaltfläche wird der Filtervorgang gestartet. Die Ausführung einiger Filter kann sehr lange dauern, insbesondere dann, wenn sie auf einen umfangreichen Datensatz angewendet werden. Sie können den Filtervorgang Abbrechen, indem Sie durch Drücken der **beenden** , in der Statusleiste unter erscheint, dem **Vorgänge** im Menü.  
  
 Die **löschen** Schaltfläche setzt vordefinierte und benutzerdefinierte Filter um alle ablaufverfolgungen zu ermöglichen.  
  
#### <a name="filter-options"></a>Filteroptionen  
 Der Viewer kann WCF-Ablaufverfolgungen automatisch aus der Ansicht entfernen. Ablaufverfolgungen, die von bestimmten Bereichen von WCF ausgegeben wurden, können selektiv aus der Ansicht entfernt werden, zum Beispiel transaktionsbezogene Ablaufverfolgungen.  
  
 Die Einstellungen dieses Filters werden definiert, der **Filteroptionen** Untermenü unter **Ansicht** Menü.  
  
#### <a name="custom-filters"></a>Benutzerdefinierte Filter  
 Wenn Sie mit der XML Path-Programmiersprache (XPath) vertraut sind, können Sie eigene benutzerdefinierte Filter zum Suchen nach Ablaufverfolgungsdaten für ein bestimmtes XML-Element erstellen. Sie können über die Filtersymbolleiste auf die Filter zugreifen.  
  
 Benutzerdefinierte Filter können Parameter einschließen. Sie können auch bereits vorhandene benutzerdefinierte Filter importieren.  
  
##### <a name="creating-a-custom-filter"></a>Erstellen eines benutzerdefinierten Filters  
 Es gibt zwei Möglichkeiten zum Erstellen von Filtern:  
  
###### <a name="creating-a-custom-filter-using-the-template-wizard"></a>Erstellen eines benutzerdefinierten Filters mit dem Vorlagen-Assistenten  
 Sie können auf eine vorhandene Ablaufverfolgung klicken und auf Grundlage der Struktur der Ablaufverfolgung einen Filter erstellen. In diesem Beispiel wird ein benutzerdefinierter Filter auf Grundlage der Thread-ID erstellt.  
  
1.  Wählen Sie im Ablaufverfolgungsbereich oben rechts im Viewer eine Ablaufverfolgung aus, die ein Element enthält, nach dem Sie filtern möchten.  
  
2.  Klicken Sie auf die **Erstellen benutzerdefinierter Filter** Schaltfläche am oberen Rand des Bereichs für die Ablaufverfolgung.  
  
3.  Geben Sie im angezeigten Dialogfeld einen Namen für den Filter ein. Geben Sie in diesem Beispiel `Thread ID`. Sie können auch eine Beschreibung des Filters eingeben.  
  
4.  In der Strukturansicht links wird die Struktur des Ablaufverfolgungsdatensatzes angezeigt, den Sie in Schritt 1 ausgewählt haben. Wechseln Sie zu dem Element, für das Sie eine Bedingung erstellen möchten. In diesem Beispiel durchsuchen, zu der ThreadID, die in der XPath-Ausdruck gefunden werden: /E2ETraceEvent/System/Execution/@ThreadID Knoten. Doppelklicken Sie auf das ThreadID-Attribut in der Strukturansicht. Hierdurch wird rechts im Dialogfeld ein Ausdruck für das Attribut erstellt.  
  
5.  Ändern Sie das Parameterfeld für die ThreadID-Bedingung von keine in '{0}". Dieser Schritt aktiviert den ThreadID-Wert, der beim Anwenden des Filters konfiguriert werden soll. (Siehe den Abschnitt zum Anwenden eines Filters.) Sie können bis zu vier Parameter definieren. Bedingungen werden mit dem OR-Operator kombiniert.  
  
6.  Klicken Sie auf **Ok** zum Erstellen des Filters.  
  
> [!NOTE]
>  Sobald ein Filter mit dem Vorlagen-Assistenten erstellt wurde, kann er nur manuell bearbeitet werden. Es ist nicht möglich, den Assistenten für einen Filter zu aktivieren, der bereits erstellt wurde. Darüber hinaus werden die Bedingungen eines XPath-Filters, der mit dem Vorlagen-Assistenten erstellt wurde, mit dem OR-Operator kombiniert. Wenn ein AND-Vorgang benötigt wird, können Sie den Filterausdruck bearbeiten, nachdem er erstellt wurde.  
  
###### <a name="creating-a-custom-filter-manually"></a>Manuelles Erstellen eines benutzerdefinierten Filters  
 Das Menü Benutzerdefinierte Filter ermöglicht Ihnen, XPath-Filter manuell einzugeben.  
  
1.  Klicken Sie im Menü Ansicht auf die **benutzerdefinierte Filter** Menüelement.  
  
2.  Klicken Sie im daraufhin angezeigten Dialogfeld auf **neu.**  
  
3.  Geben Sie mindestens einen Filternamen und einen XPath-Ausdruck an.  
  
4.  Klicken Sie auf **OK**.  
  
###### <a name="applying-a-custom-filter"></a>Anwenden eines benutzerdefinierten Filters  
 Sobald ein benutzerdefinierter Filter erstellt wurde, kann er über die Filtersymbolleiste aufgerufen werden. Wählen Sie den Filter, die Sie anwenden möchten die **Suchen In** die Filtersymbolleiste Feld. Wählen Sie für das vorherige Beispiel 'Thread-ID' aus.  
  
1.  Geben Sie den Wert, der Sie in Suchen der **Suchen nach** Feld. Geben Sie in diesem Beispiel die ID des Threads ein, nach dem Sie suchen möchten.  
  
2.  Klicken Sie auf **jetzt filtern**, und beobachten Sie das Ergebnis des Vorgangs.  
  
 Wenn der Filter mehrere Parameter verwendet werden, geben Sie sie mithilfe von ";" als Trennzeichen in den **Suchen nach** Feld. Die folgende Zeichenfolge definiert z. B. 3 Parameter: ‘1;findValue;text’. Der Viewer wendet '1', um die {0} -Parameter des Filters. 'FindValue' und 'Text' gelten für {1} und {2} bzw.  
  
###### <a name="sharing-custom-filters"></a>Freigeben von benutzerdefinierten Filtern  
 Benutzerdefinierte Filter können für andere Sitzungen und andere Benutzer freigegeben werden. Sie können die Filter in eine Definitionsdatei exportieren, die Sie an einem anderen Speicherort importieren können.  
  
 So importieren Sie einen benutzerdefinierten Filter  
  
1.  In der **Ansicht** Menü klicken Sie auf **benutzerdefinierte Filter**.  
  
2.  Klicken Sie im daraufhin angezeigten Dialogfeld klicken Sie auf die **Import** Schaltfläche.  
  
3.  Navigieren Sie zur benutzerdefinierten Filterdatei (.stvcf), klicken Sie auf die Datei, und klicken Sie auf die **öffnen** Schaltfläche.  
  
 So exportieren Sie einen benutzerdefinierten Filter  
  
1.  Klicken Sie im Menü Ansicht auf **benutzerdefinierte Filter**.  
  
2.  Wählen Sie im aufgerufenen Dialogfeld den Filter, den Sie exportieren möchten.  
  
3.  Klicken Sie auf die **exportieren** Schaltfläche.  
  
4.  Geben Sie den Namen und Speicherort der benutzerdefinierten filterdefinitionsdatei (.stvcf), und klicken Sie auf die **speichern** Schaltfläche.  
  
> [!NOTE]
>  Diese benutzerdefinierten Filter können nur von Service Trace Viewer importiert und exportiert werden. Sie können nicht von anderen Tools gelesen werden.  
  
### <a name="finding-data"></a>Suchen von Daten  
 Der Viewer bietet folgende Möglichkeiten zum Suchen von Daten:  
  
-   Die Symbolleiste Suchen stellt bietet schnellen Zugriff auf die allgemeinen Suchoptionen.  
  
-   Das Dialogfeld Suchen stellt weitere Suchoptionen zur Verfügung. Es ist über die **bearbeiten** Menü oder die Tastenkombination STRG + F.  
  
 Die Symbolleiste Suchen wird am oberen Rand des Viewers angezeigt. Wenn es nicht vorhanden ist, können Sie sie in Aktivieren der **Ansicht** Menü. Die Leiste verfügt über zwei Komponenten:  
  
-   Suchen Sie nach: Ermöglicht Ihnen, Suchschlüsselwort eingeben.  
  
-   Suchen Sie In: Können Sie den Suchbereich einzugeben. Sie können auswählen, ob in allen Aktivitäten oder nur in der aktuellen Aktivität gesucht werden soll.  
  
 Das Suchdialogfeld stellt zwei zusätzliche Optionen bereit:  
  
-   Ziel suchen:  
  
    -   Die Option "nicht aufbereitete Protokolldaten" nach dem Stichwort gesucht, in allen unformatierten Daten.  
  
    -   Die Optionen "XML-Text" und "XML-Attribute" werden nur in XML-Elementen suchen.  
  
    -   Die Option "Protokollierte Nachricht" nach dem Stichwort gesucht, nur in Nachrichten.  
  
-   Ignorieren Sie Stammaktivität: Die Suche werden die ablaufverfolgungen in der Aktivität "000000000000" ignoriert. Hierdurch wird die Leistung bei umfangreichen Ablaufverfolgungsdateien verbessert, wenn die Stammaktivität über Tausende von Ablaufverfolgungen verfügt, bei denen es sich zum Großteil um Übertragungen handelt.  
  
### <a name="navigating-traces"></a>Navigieren in Ablaufverfolgungen  
 Da Ablaufverfolgungen bei Laufzeit der Anwendung Schritt für Schritt aufgezeichnet werden, kann Sie das Navigieren in Ablaufverfolgungen beim Debuggen Ihrer Anwendung unterstützen. Service Trace Viewer bietet mehrere Möglichkeiten zum Navigieren in Ablaufverfolgungen.  
  
#### <a name="step-forward-or-backward"></a>Schritt vorwärts oder zurück  
 Wenn Sie jede Ablaufverfolgung als eine einzige Zeile Code in der Anwendung in Betracht ziehen, ist die einen Schritt vorwärts "Prozedurschritt" in der Visual Studio integrierte Entwicklungsumgebung (IDE) sehr ähnlich. Der Unterschied ist, dass Sie in der Ablaufverfolgung auch einen Schritt zurück gehen können. Einen Schritt vorwärts zu gehen bedeutet, zur nächsten Ablaufverfolgung in der Aktivität zu gehen.  
  
-   Schritt vorwärts: Verwenden der **Aktivität** Menü, oder drücken Sie "F10". Sie können auch oben-Taste "down" im ablaufverfolgungsbereich verwenden.  
  
-   Schritt zurück: Verwenden der **Aktivität** Menü, oder drücken Sie "F9". Sie können auch im ablaufverfolgungsbereich oben-Taste "up" verwenden.  
  
> [!NOTE]
>  Dies können Sie zu einer Aktivität auftreten in einem anderen Prozess oder sogar auf einem anderen Computer nutzen, da die WCF-Meldungen Aktivitäts-IDs enthalten können, die Computer umfassen.  
  
#### <a name="follow-transfer"></a>Verfolgen von Übertragungen  
 Übertragungsablaufverfolgungen sind spezielle Ablaufverfolgungen in der Ablaufverfolgungsdatei. Eine Aktivität wird möglicherweise über eine Übertragungsablaufverfolgung an eine andere Aktivität übertragen. Beispielsweise kann "Aktivität A" an "Aktivität B" übertragen. In diesem Fall liegt eine übertragungsablaufverfolgung in der "Aktivität A" mit dem Namen "auf: Aktivität"und dem übertragungssymbol. Diese Übertragungsablaufverfolgung ist ein Link zwischen den beiden Ablaufverfolgungen. In "Aktivität B" gibt es möglicherweise auch eine übertragungsablaufverfolgung am Ende der Aktivität an "Aktivität A" zu übertragen. Dies ähnelt Funktionsaufrufen in Programmen: Ein B aufruft, gibt dann B zurück.  
  
 "Übertragung verfolgen" ähnelt "Einzelschritt" in einem Debugger. Dabei wird die Übertragung von Aktivität A zu Aktivität B verfolgt. Andere Ablaufverfolgungen sind davon nicht betroffen.  
  
 Es gibt zwei Möglichkeiten, einer Übertragung zu folgen: mit der Maus oder der Tastatur:  
  
-   Mit der Maus: Doppelklicken Sie auf die übertragen-Ablaufverfolgung im ablaufverfolgungsbereich.  
  
-   Mit der Tastatur: Wählen Sie eine übertragungsablaufverfolgung aus, und verwenden Sie "Übertragung verfolgen" in der **Aktivität** Menü, oder drücken Sie "F11"  
  
> [!NOTE]
>  Wenn Aktivität A an Aktivität B übertragen wird, wartet Aktivität A in vielen Fällen, bis Aktivität B an Aktivität A zurückübertragen wurde. Dies bedeutet, dass für Aktivität A während des Zeitraums, in dem eine aktive Ablaufverfolgung für Aktivität B erfolgt, keine Ablaufverfolgung protokolliert wird. Es ist jedoch auch möglich, dass Aktivität A nicht wartet und mit dem Protokollieren von Ablaufverfolgungen fortfährt. Es ist auch möglich, dass Aktivität B nicht an Aktivität A zurückübertragen wird. In diesem Sinne unterscheiden sich Aktivitätsübertragungen weiterhin von Funktionsaufrufen. Aktivitätsübertragungen werden in der Diagrammansicht noch besser verdeutlicht.  
  
#### <a name="jump-to-next-or-previous-transfer"></a>Zur nächsten oder zur vorherigen Übertragung wechseln  
 Wenn Sie die aktuelle Aktivität oder mehrere ausgewählte Aktivitäten analysieren, möchten Sie die Aktivitäten, an die die Übertragung stattfindet, möglicherweise schnell finden. "Zur nächsten Übertragung springen" ermöglicht Ihnen die nächste übertragungsablaufverfolgung in der Aktivität zu suchen. Wenn Sie die übertragungsablaufverfolgung gefunden haben, können um einen Einzelschritt für die nächste Aktivität Sie "Übertragung verfolgen".  
  
-   Zu nächsten Übertragung springen: Verwenden der **Aktivität** Menü, oder drücken Sie "STRG + F10".  
  
-   Zur vorherigen Übertragung wechseln: Verwenden der **Aktivität** Menü, oder drücken Sie "STRG + F9".  
  
#### <a name="navigate-in-graph-view"></a>Navigieren in der Diagrammansicht  
 Obwohl das Navigieren im Aktivitätsbereich und ablaufverfolgungsbereich dem debugging ähnlich ist, **Graph** Ansicht bietet eine viel bessere Erfahrung im Navigationsbereich. Weitere Informationen finden Sie unter "Diagrammansicht" Abschnitt.  
  
### <a name="loading-large-trace-files"></a>Laden von großen Ablaufverfolgungsdateien  
 Ablaufverfolgungsdateien können sehr groß sein. Wenn Sie die Ablaufverfolgung auf der Ebene "Ausführlich", die Ergebnisdatei der Ablaufverfolgung, für die Ausführung von wenigen Minuten auf einfache Weise aktivieren werden Sie beispielsweise mehrere hundert Megabyte oder mehr umfassen, je nach netzwerkgeschwindigkeit und Kommunikationsmuster.  
  
 Wenn Sie eine sehr große Ablaufverfolgungsdatei in Service Trace Viewer öffnen, kann sich dies negativ auf die Systemleistung auswirken. Die Ladegeschwindigkeit und die Antwortzeit nach dem Laden können langsam sein. Die tatsächliche Geschwindigkeit unterscheidet sich bisweilen, abhängig von der Hardwarekonfiguration. Bei den meisten PCs wirkt sich das Laden einer Ablaufverfolgungsdatei, die größer als 200&amp;#160;MB ist, deutlich auf die Leistung aus. Für Ablaufverfolgungsdateien, die größer als 1 GB sind, verwendet das Tool möglicherweise den gesamten verfügbaren Arbeitsspeicher oder reagiert für einen sehr langen Zeitraum nicht mehr.  
  
 Um das verlangsamte laden und Antwortzeit bei der Analyse von großen Ablaufverfolgungsdateien zu vermeiden, stellt Service Trace Viewer eine Funktion, die Bezeichnung "Teilweises laden", die nur einen kleinen Teil der Ablaufverfolgung zu einem Zeitpunkt lädt. Sie verfügen zum Beispiel über eine Ablaufverfolgungsdatei mit mehr als 1&amp;#160;GB, die mehrere Tage lang auf dem Server läuft. Wenn einige Fehler aufgetreten sind und Sie die Ablaufverfolgung analysieren möchten, müssen Sie nicht die gesamte Ablaufverfolgungsdatei öffnen. Stattdessen können Sie die Ablaufverfolgungen eines bestimmten Zeitraums, in dem der Fehler möglicherweise aufgetreten ist, laden. Da der Umfang geringer ist, kann das Service Trace Viewer-Tool die Datei schneller laden, und Sie können die Fehler anhand eines kleineren Datensatzes ermitteln.  
  
#### <a name="enabling-partial-loading"></a>Aktivieren des teilweisen Ladens  
 Sie müssen das teilweise Laden nicht manuell aktivieren. Wenn die Gesamtgröße der Ablaufverfolgungsdatei(en), die Sie laden möchten, 40&amp;#160;MB überschreitet, zeigt Service Trace Viewer das Dialogfeld Teilweises Laden automatisch an, sodass Sie den Teil auswählen können, den Sie laden möchten.  
  
> [!NOTE]
>  Da Ablaufverfolgungen möglicherweise nicht gleich im Zeitraum verteilt sind, ist die Länge des im Dialogfeld Teilweises Laden angegebenen Zeitraums möglicherweise nicht proportional zur angezeigten Ladegröße. Die tatsächliche Ladegröße kann kleiner als die im Dialogfeld Teilweises Laden geschätzte Größe sein.  
  
#### <a name="adjusting-partial-loading"></a>Anpassen des teilweisen Ladens  
 Nachdem die Ablaufverfolgungsdatei teilweise geladen wurde, können Sie den geladenen Datensatz ändern. Passen Sie dazu die Symbolleiste für teilweises Laden oben im Viewer an.  
  
1.  Verschieben Sie die Symbolleiste mit der Maus, oder geben Sie die Anfangs- und Endzeit ein.  
  
2.  Klicken Sie auf die **anpassen** Schaltfläche.  
  
## <a name="understanding-trace-icons"></a>Verstehen von Ablaufverfolgungssymbolen  
 Im folgenden werden eine Liste von Symbolen, die das Service Trace Viewer-Tool verwendet die **Aktivität** Ansicht **Graph** anzeigen und **Ablaufverfolgung** Bereich, um verschiedene Elemente darstellen.  
  
> [!NOTE]
>  Einige, die nicht kategorisierte ablaufverfolgungen (z. B. "eine Nachricht wird geschlossen") haben kein Symbol.  
  
### <a name="activity-tracing-traces"></a>Aktivitätsablaufverfolgungs-Symbole  
  
|Symbol|Beschreibung|  
|----------|-----------------|  
|![Warnungsablaufverfolgung](../../../docs/framework/wcf/media/7457c4ed-8383-4ac7-bada-bcb27409da58.gif "7457c4ed-8383-4ac7-bada-bcb27409da58")|Warnungsablaufverfolgung: Eine Ablaufverfolgung, die auf der Warnebene ausgegeben wird|  
|![Fehlerablaufverfolgung](../../../docs/framework/wcf/media/7d908807-4967-4f6d-9226-d52125db69ca.gif "7d908807-4967-4f6d-9226-d52125db69ca")|Fehlerablaufverfolgung: Eine Ablaufverfolgung, die auf der Fehlerebene ausgegeben wird.|  
|![Ablaufverfolgung "Aktivitätsstart":](../../../docs/framework/wcf/media/8a728f91-5f80-4a95-afe8-0b6acd6e0317.gif "8a728f91-5f80-4a95-afe8-0b6acd6e0317")|Aktivitätsstart-Ablaufverfolgung: Eine Ablaufverfolgung, die den Anfang einer Aktivität markiert. Enthält den Namen der Aktivität. Als Anwendungsentwickler sollten Sie eine Aktivitätsstart-Ablaufverfolgung pro Aktivitäts-ID und Prozess oder Thread definieren.<br /><br /> Wenn die Aktivitäts-ID über die Ablaufverfolgungsquellen der Ablaufverfolgungskorrelation hinweg propagiert wird, können Sie mehrere Starts für dieselbe Aktivitäts-ID sehen (einen pro Ablaufverfolgungsquelle). Die Start-Ablaufverfolgung wird ausgegeben, wenn die Aktivitätsablaufverfolgung für die Ablaufverfolgungsquelle aktiviert ist.|  
|![Ablaufverfolgung "Aktivitätsstopp"](../../../docs/framework/wcf/media/a0493e95-653e-4af8-84a4-4d09a400bc31.gif "a0493e95-653e-4af8-84a4-4d09a400bc31")|Ablaufverfolgung "Aktivitätsstopp": Eine Ablaufverfolgung, die das Ende einer Aktivität markiert. sein. Enthält den Namen der Aktivität. Als Anwendungsentwickler sollten Sie eine Aktivitätsstopp-Ablaufverfolgung pro Aktivitäts-ID und Ablaufverfolgungsquelle definieren. Es werden keine Ablaufverfolgungen von einer bestimmten Ablaufverfolgungsquelle angezeigt, nachdem die Ablaufverfolgungsquelle einen Aktivitätsstopp ausgegeben hat, es sei denn, die Ablaufverfolgungszeit weist eine grobe Granularität auf. Ist das der Fall, überlappen sich zwei Ablaufverfolgungen mit der gleichen Zeit, einschließlich eines Stopps, möglicherweise bei der Anzeige. Wenn die Aktivitäts-ID über die Ablaufverfolgungsquellen der Ablaufverfolgungskorrelation hinweg propagiert wird, können Sie mehrere Stopps für dieselbe Aktivitäts-ID sehen (einen pro Ablaufverfolgungsquelle). Die Stoppablaufverfolgung wird ausgegeben, wenn die Aktivitätsablaufverfolgung für die Ablaufverfolgungsquelle aktiviert ist.|  
|![Aktivität anhalten-Ablaufverfolgung](../../../docs/framework/wcf/media/6f7f4191-df2b-4592-8998-8379769e2d32.gif "6f7f4191-df2b-4592-8998-8379769e2d32")|Aktivität anhalten-Ablaufverfolgung: Eine Ablaufverfolgung, die Zeit, eine Aktivität markiert, wurde angehalten. Es werden erst Ablaufverfolgungen in einer angehaltenen Aktivität ausgegeben, wenn die Aktivität fortgesetzt wird. Eine angehaltene Aktivität gibt an, dass keine Verarbeitungen in dieser Aktivität im Bereich der Ablaufverfolgungsquelle stattfinden. Anhalten/Fortsetzen-Ablaufverfolgungen sind hilfreich für die Profilerstellung. Die Anhalten-Ablaufverfolgung wird ausgegeben, wenn die Aktivitätsablaufverfolgung für die Ablaufverfolgungsquelle aktiviert ist.|  
|![Aktivität fortsetzen-Ablaufverfolgung](../../../docs/framework/wcf/media/1060d9d2-c9c8-4e0a-9988-cdc2f7030f17.gif "1060d9d2-c9c8-4e0a-9988-cdc2f7030f17")|Aktivität fortsetzen-Ablaufverfolgung: Eine Ablaufverfolgung, die Zeit markiert, die eine Aktivität nach dem Anhalten wieder fortgesetzt wird. Ablaufverfolgungen können in dieser Aktivität möglicherweise erneut ausgegeben werden. Anhalten/Fortsetzen-Ablaufverfolgungen sind hilfreich für die Profilerstellung. Die Fortsetzen-Ablaufverfolgung wird ausgegeben, wenn die Aktivitätsablaufverfolgung für die Ablaufverfolgungsquelle aktiviert ist.|  
|![Transfer](../../../docs/framework/wcf/media/b2d9850e-f362-4ae5-bb8d-9f6f3ca036a5.gif "b2d9850e-f362-4ae5-bb8d-9f6f3ca036a5")|Übertragung: Eine Ablaufverfolgung, die ausgegeben wird, wenn logische ablaufsteuerung von einer Aktivität in einen anderen übertragen wird. Die Aktivität, aus der die Übertragung stammt, kann unter Umständen parallel zur der Aktivität ausgeführt werden, an die die Übertragung stattfindet. Die Übertragen-Ablaufverfolgung wird ausgegeben, wenn die Aktivitätsablaufverfolgung für die Ablaufverfolgungsquelle aktiviert ist.|  
|![Transfer From](../../../docs/framework/wcf/media/1df215cb-b344-4f36-a20d-195999bda741.gif "1df215cb-b344-4f36-a20d-195999bda741")|Übertragen von: Eine Ablaufverfolgung, die eine Übertragung von einer anderen Aktivität mit der aktuellen Aktivität definiert.|  
|![Transfer To](../../../docs/framework/wcf/media/74255b6e-7c47-46ef-8e53-870c76b04c3f.gif "74255b6e-7c47-46ef-8e53-870c76b04c3f")|Übertragen Sie an: Eine Ablaufverfolgung, die eine Übertragung der logischen ablaufsteuerung von der aktuellen Aktivität an eine andere Aktivität definiert.|  
  
### <a name="wcf-traces"></a>WCF-Ablaufverfolgungen  
  
|Symbol|Beschreibung|  
|----------|-----------------|  
|![Nachrichtenprotokollierung-Ablaufverfolgung](../../../docs/framework/wcf/media/7c66e994-2476-4260-a0db-98948b9af197.gif "7c66e994-2476-4260-a0db-98948b9af197")|Nachrichtenprotokollierung-Ablaufverfolgung: Eine Ablaufverfolgung, die ausgegeben wird, wenn eine WCF-Nachricht von der nachrichtenprotokollierungsfunktion protokolliert wird bei der `System.ServiceModel.MessageLogging` -Ablaufverfolgungsquelle aktiviert ist. Durch Klicken auf diese Ablaufverfolgung wird die Nachricht angezeigt. Es gibt vier konfigurierbare protokollierungspunkte für eine Nachricht aus: ServiceLevelSendRequest, TransportSend, TransportReceive und ServiceLevelReceiveRequest, die auch durch angegeben werden, kann die `messageSource` -Attribut in der Nachrichtenprotokoll-Ablaufverfolgung.|  
|![Nachricht empfangen-Ablaufverfolgung](../../../docs/framework/wcf/media/de4f586c-c5dd-41ec-b1c3-ac56b4dfa35c.gif "de4f586c-c5dd-41ec-b1c3-ac56b4dfa35c")|Nachricht empfangen-Ablaufverfolgung: Eine Ablaufverfolgung, die ausgegeben wird, wenn eine WCF-Nachricht empfangen wird, wenn die `System.ServiceModel` -Ablaufverfolgungsquelle auf Information- oder Verbose-Ebene aktiviert ist. Diese Ablaufverfolgung ist wesentlich zum Anzeigen des nachrichtenkorrelationspfeils in der Aktivität **Graph** anzeigen.|  
|![Nachricht gesendet-Ablaufverfolgung](../../../docs/framework/wcf/media/558943c4-17cf-4c12-9405-677e995ac387.gif "558943c4-17cf-4c12-9405-677e995ac387")|Nachricht gesendet-Ablaufverfolgung: Eine Ablaufverfolgung, die ausgegeben wird, wenn eine WCF-Nachricht gesendet wird, wenn die `System.ServiceModel` -Ablaufverfolgungsquelle auf Information- oder Verbose-Ebene aktiviert ist. Diese Ablaufverfolgung ist wesentlich zum Anzeigen des nachrichtenkorrelationspfeils in der Aktivität **Graph** anzeigen.|  
  
### <a name="activities"></a>Aktivitäten  
  
|Symbol|Beschreibung|  
|----------|-----------------|  
|![Activity](../../../docs/framework/wcf/media/wcfc-defaultactivityc.gif "wcfc_defaultActivityc")|Aktivität: Gibt an, dass die aktuelle Aktivität eine generische Aktivität ist.|  
|![Stammaktivität](../../../docs/framework/wcf/media/5dc8e0eb-1c32-4076-8c66-594935beaee9.gif "5dc8e0eb-1c32-4076-8c66-594935beaee9")|Stammaktivität: Gibt die Stammaktivität eines Prozesses an.|  
  
### <a name="wcf-activities"></a>WCF-Aktivitäten  
  
|Symbol|Beschreibung|  
|----------|-----------------|  
|![Umgebungsaktivität](../../../docs/framework/wcf/media/29fa00ac-cf78-46e5-822d-56222fff61d1.gif "29fa00ac-cf78-46e5-822d-56222fff61d1")|Umgebungsaktivität: Eine Aktivität, die erstellt wird, öffnet oder schließt eines WCF-Host oder -Clients. Fehler, die während dieser Phasen aufgetreten sind, werden in dieser Aktivität angezeigt.|  
|![Listen activity](../../../docs/framework/wcf/media/d7b135f6-ec7d-45d7-9913-037ab30e4c26.gif "d7b135f6-ec7d-45d7-9913-037ab30e4c26")|Listen Sie-Aktivität: Eine Aktivität, die mit einem Listener zusammenhängende ablaufverfolgungen protokolliert. In dieser Aktivität werden Listenerinformationen und Verbindungsanforderungen angezeigt.|  
|![Bytes empfangen-Aktivität](../../../docs/framework/wcf/media/2f628580-b80f-45a7-925b-616c96426c0e.gif "2f628580-b80f-45a7-925b-616c96426c0e")|Empfangen Sie Bytes-Aktivität: Eine Aktivität, die alle ablaufverfolgungen, die im Zusammenhang mit der empfangene Bytes für eine Verbindung zwischen zwei Endpunkten gruppiert. Diese Aktivität ist wesentlich beim Korrelieren von Transportaktivitäten, die ihre Aktivitäts-ID propagieren, wie z.&amp;#160;B. http.sys. Verbindungsfehler, wie z.&amp;#160;B. Abbrüche, treten in dieser Aktivität auf.|  
|![Nachricht verarbeiten-Aktivität](../../../docs/framework/wcf/media/wcfc-executionactivityiconc.GIF "Wcfc_ExecutionActivityIconc")|Verarbeiten Sie Nachricht-Aktivität: Eine Aktivität, die im Zusammenhang mit der zum Erstellen einer WCF-Nachricht ablaufverfolgungen gruppiert. Fehler aufgrund eines ungültigen Umschlags oder einer falsch formatierten Nachricht werden in dieser Aktivität angezeigt. In dieser Aktivität können Nachrichtenheader geprüft werden, um zu ermitteln, ob eine Aktivitäts-ID vom Aufrufer propagiert wurde. Wenn dies zutrifft, kann beim Übertragen an die Aktion verarbeiten-Aktivität (das nächste Symbol) dieser Aktivität auch die propagierte Aktivitäts-ID für die Korrelation zwischen dem Aufrufer und den Ablaufverfolgungen des Aufrufenden zugewiesen werden.|  
|![Nachrichtenprotokollierung-Ablaufverfolgung](../../../docs/framework/wcf/media/7c66e994-2476-4260-a0db-98948b9af197.gif "7c66e994-2476-4260-a0db-98948b9af197")|Verarbeiten Sie Aktion-Aktivität: Eine Aktivität, die alle ablaufverfolgungen, die im Zusammenhang mit einem WCF-Anforderung über zwei Endpunkte hinweg gruppiert. Wenn `propagateActivity` auf beiden Endpunkten in der Konfiguration auf `true` festgelegt ist, werden alle Ablaufverfolgungen für die direkte Korrelation in eine Aktivität zusammengeführt. Einige Aktivitäten enthalten Fehler, die bei der Transport- oder Sicherheitsverarbeitung auftreten und sich bis hin zu Benutzercodegrenzen und zurück erstrecken (sofern eine Antwort vorhanden ist).|  
|![Nachricht verarbeiten-Aktivität](../../../docs/framework/wcf/media/wcfc-executionactivityiconc.GIF "Wcfc_ExecutionActivityIconc")|Führen Sie die Benutzer Codeaktivität: Eine Aktivität, die Benutzer Code ablaufverfolgungen zur Verarbeitung einer Anforderung gruppiert.|  
  
## <a name="troubleshooting"></a>Problembehandlung  
 Wenn Sie nicht über die Berechtigung zum Schreiben in die Registrierung verfügen, erhalten Sie die folgende Fehlermeldung angezeigt, die "Microsoft Service Trace Viewer wurde nicht mit dem System registriert" bei Verwendung der "`svctraceviewer /register`" Befehl aus, um das Tool zu registrieren. Ist dies der Fall, sollten Sie sich über ein Konto anmelden, das Schreibzugriff auf die Registrierung bietet.  
  
 Außerdem schreibt das Service Trace Viewer-Tool einige Einstellungen (z.&amp;#160;B. benutzerdefinierte Filter und Filteroptionen) in die SvcTraceViewer.exe.settings-Datei im Assemblyordner. Wenn Sie keine Leseberechtigungen für die Datei haben, können Sie das Tool starten, aber die Einstellungen nicht laden.  
  
 Wenn Sie die Fehlermeldung "Unbekannter Fehler bei der Verarbeitung von mindestens einer Ablaufverfolgung" beim Öffnen der ETL-Datei erhalten, bedeutet dies, dass das Format der ETL-Datei ungültig ist.  
  
 Wenn Sie ein in einem arabischen Betriebssystem erstelltes Ablaufverfolgungsprotokoll öffnen, stellen Sie unter Umständen fest, dass der Zeitfilter nicht funktioniert. Zum Beispiel entspricht das Jahr 2005 dem Jahr 1427 im arabischen Kalender. Der Filter des Service Trace Viewer-Tools unterstützt jedoch keine Jahresangabe vor 1752. Dies kann dazu führen, dass Sie kein korrektes Datum im Filter auswählen können. Um dieses Problem zu beheben, können Sie einen benutzerdefinierten Filter erstellen (**Ansicht/benutzerdefinierte Filter**) mithilfe eines XPath-Ausdrucks auf einen bestimmten Zeitbereich abzudecken.  
  
## <a name="see-also"></a>Siehe auch
- [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting (Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung)](../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [Konfigurieren der Ablaufverfolgung](../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)
- [End-to-End-Ablaufverfolgung](./diagnostics/tracing/end-to-end-tracing.md)
