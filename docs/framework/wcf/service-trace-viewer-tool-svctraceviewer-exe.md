---
title: Service Trace Viewer-Tool (SvcTraceViewer.exe)
description: Verwenden Sie Service Trace Viewer, um Ablauf Verfolgungs Meldungen im Protokoll zusammenzuführen, anzuzeigen und zu filtern, sodass Sie Probleme bei WCF-Diensten diagnostizieren, reparieren und überprüfen können.
ms.date: 03/30/2017
ms.assetid: 9027efd3-df8d-47ed-8bcd-f53d55ed803c
ms.openlocfilehash: 0ad6094965291a965346522688a8334abbd4e6b3
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244568"
---
# <a name="service-trace-viewer-tool-svctraceviewerexe"></a>Service Trace Viewer-Tool (SvcTraceViewer.exe)

Windows Communication Foundation (WCF) Service Trace Viewer-Tool unterstützt Sie bei der Analyse von Diagnose Ablauf Verfolgungen, die von WCF generiert werden. Service Trace Viewer ermöglicht das einfache Zusammenführen, anzeigen und Filtern von Ablauf Verfolgungs Meldungen im Protokoll, sodass Sie Probleme bei WCF-Diensten diagnostizieren, reparieren und überprüfen können.

## <a name="configuring-tracing"></a>Konfigurieren der Ablaufverfolgung

Diagnoseablaufverfolgungen stellen Informationen bereit, die Aufschluss darüber geben, was beim Ausführen der Vorgänge in der Anwendung geschieht. Wie der Name bereits andeutet, können Sie Vorgänge von der Quelle zum Ziel und durch Zwischenpunkte hindurch verfolgen.

Sie können die Ablauf Verfolgung mithilfe der Konfigurationsdatei der Anwendung konfigurieren – Web.config entweder für im Internet gehostete Anwendungen oder *appname*. config für selbst gehostete Anwendungen. Hier ein Beispiel:

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

In diesem Beispiel werden Name und Typ des Ablaufverfolgungslisteners angegeben. Der Name des Listeners ist `sdt`, und der standardmäßige .NET Framework-Ablaufverfolgungslistener (System.Diagnostics.XmlWriterTraceListener) wird als Typ hinzugefügt. Das- `initializeData` Attribut wird verwendet, um den Namen der Protokolldatei für diesen Listener festzulegen `SdrConfigExample.e2e` . Für die Protokolldatei können Sie einen einfachen Dateinamen durch einen vollqualifizierten Pfad ersetzen.

Mit dem Beispiel wird eine Datei namens "SdrConfigExample.e2e" im Stammverzeichnis erstellt. Wenn Sie die Datei mit dem Trace Viewer öffnen, wie im Abschnitt "öffnen und Anzeigen von WCF-Ablauf Verfolgungs Dateien" beschrieben, können Sie alle gesendeten Nachrichten sehen.

Die Ablaufverfolgungsebene wird von der `switchValue`-Einstellung gesteuert. Die verfügbaren Ablaufverfolgungsebenen werden in der folgenden Tabelle beschrieben.

|Ablaufverfolgungsebene|BESCHREIBUNG|
|-----------------|-----------------|
|Kritisch|-Protokolliert Fehler-und Ereignisprotokoll Einträge sowie Korrelations Informationen für die Ablauf Verfolgung. Im Folgenden finden Sie einige Beispiele für die Verwendung der Critical-Ebene:<br />-Ihre AppDomain ist aufgrund einer nicht behandelten Ausnahme ausgefallen.<br />-Die Anwendung kann nicht gestartet werden.<br />-Die Meldung, die den Fehler verursacht hat, stammt aus dem Prozess MyApp.exe.|
|Fehler|-Protokolliert alle Ausnahmen. Sie können die Error-Ebene in den folgenden Situationen verwenden:<br />-Der Code ist aufgrund einer ungültigen Umwandlungs Ausnahme abgestürzt.<br />-Die Ausnahme "Fehler beim Erstellen eines Endpunkts" bewirkt, dass Ihre Anwendung beim Start fehlschlägt.|
|Warnung|-Es ist eine Bedingung vorhanden, die möglicherweise zu einem Fehler oder einem kritischen Fehler führt. Sie können diese Ebene in folgenden Situationen verwenden:<br />-Die Anwendung empfängt mehr Anforderungen, als die einschränkeneinstellungen zulassen.<br />-Die empfangende Warteschlange ist 98 Prozent der konfigurierten Kapazität.|
|Information|-Nachrichten, die für die Überwachung und Diagnose des Systemstatus, der Leistungsmessung oder der Profilerstellung hilfreich sind. Sie können solche Informationen zur Kapazitätsplanung und Leistungsverwaltung nutzen. Sie können diese Ebene in folgenden Situationen verwenden:<br />-Ein Fehler ist aufgetreten, nachdem die Nachricht die AppDomain erreicht und deserialisiert wurde.<br />-Fehler beim Erstellen der HTTP-Bindung.|
|Ausführlich|: Ablauf Verfolgung auf Debugebene für Benutzercode und Wartung. Legen Sie diese Ebene in folgenden Fällen fest:<br />-Sie sind nicht sicher, welche Methode in Ihrem Code aufgerufen wurde, als der Fehler aufgetreten ist.<br />-Sie haben einen falschen Endpunkt konfiguriert, und der Dienst konnte nicht gestartet werden, da der Eintrag im Reservierungs Speicher gesperrt ist.|
|ActivityTracing|Ablaufereignisse zwischen Verarbeitungsaktivitäten und Komponenten.<br /><br /> Diese Ebene ermöglicht es Administratoren und Entwicklern, Anwendungen in einer Anwendungsdomäne zu korrelieren.<br /><br /> -Ablauf Verfolgungen für Aktivitäts Grenzen: Start/Ende.<br />-Ablauf Verfolgungen für Übertragungen.|

 Mit `add` können Sie den Namen und den Typ des Ablaufverfolgungslisteners angeben, den Sie verwenden möchten. In der Beispielkonfiguration wird der Listener `sdt` genannt und der standardmäßige .NET Framework-Ablaufverfolgungslistener (`System.Diagnostics.XmlWriterTraceListener`) wird als Typ hinzugefügt. Verwenden Sie `initializeData`, um den Namen der Protokolldatei für diesen Listener festzulegen. Außerdem können Sie einen einfachen Dateinamen durch einen vollqualifizierten Pfad ersetzen.

Beginnend mit .NET Framework 4,8 werden ComboBox-Steuerelemente in einigen Designs mit hohem Kontrast in der richtigen Farbe angezeigt. Sie können diese Änderung deaktivieren, indem Sie die folgende Einstellung aus der *svcTraceViewer.exe.config* Datei entfernen:

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
```

## <a name="using-the-service-trace-viewer-tool"></a>Verwenden des Service Trace Viewer-Tools

### <a name="opening-and-viewing-wcf-trace-files"></a>Öffnen und Anzeigen von WCF-Ablaufverfolgungsdateien

Service Trace Viewer unterstützt drei Dateitypen:

- WCF-Ablauf Verfolgungs Datei (. SVCLOG)

- Ereignisablaufverfolgungs-Datei (.etl)

- Crimson-Ablaufverfolgungsdatei

 Mit Service Trace Viewer können Sie jede unterstützte Ablaufverfolgungsdatei öffnen, weitere Ablaufverfolgungsdateien hinzufügen und integrieren oder eine Gruppe von Ablaufverfolgungsdateien gleichzeitig öffnen und zusammenführen.

##### <a name="to-open-a-trace-file"></a>So öffnen Sie eine Ablaufverfolgungsdatei

1. Starten Sie Service Trace Viewer, indem Sie ein Befehlsfenster verwenden, um zu Ihrem WCF-Installationsverzeichnis (c:\Programme\Microsoft SDKs\Windows\v6.0\Bin) zu navigieren, und geben Sie dann ein `SvcTraceViewer.exe` .

> [!NOTE]
> Das Service Trace Viewer-Tool kann zwei Dateitypen zuweisen: .svclog und .stvproj. Sie können zwei Parameter in der Befehlszeile verwenden, um die Dateierweiterungen zu registrieren und deren Registrierung aufzuheben.
>
> /register: Registriert die Zuweisung der Dateierweiterungen ".svclog" und ".stvproj" in SvcTraceViewer.exe.
>
> /unregister: Hebt die Registrierung der zugewiesenen Dateierweiterungen ".svclog" und ".stvproj" in SvcTraceViewer.exe auf.

1. Wenn Service Trace Viewer gestartet wird, klicken Sie auf **Datei** , und zeigen Sie dann auf **Öffnen**. Navigieren Sie zu dem Speicherort, an dem die Ablaufverfolgungsdateien gespeichert sind.

2. Doppelklicken Sie auf die Ablaufverfolgungsdatei, die Sie öffnen möchten.

    > [!NOTE]
    > Halten Sie die UMSCHALTTASTE gedrückt, während Sie auf mehrere Ablaufverfolgungsdateien klicken, um sie gleichzeitig auszuwählen und zu öffnen. Service Trace Viewer führt den Inhalt aller Dateien zusammen und zeigt ihn in einer Ansicht an. Sie können zum Beispiel gleichzeitig Ablaufverfolgungsdateien von Client und Dienst öffnen. Dies ist nützlich, wenn Sie die Nachrichtenprotokollierung und Aktivitätspropagierung in der Konfiguration aktiviert haben. Auf diese Weise können Sie den Nachrichtenaustausch zwischen Client und Dienst untersuchen. Sie können auch mehrere Dateien in den Viewer ziehen oder die Registerkarte **Projekt** verwenden. Weitere Informationen finden Sie im Abschnitt Verwalten von Projekten.

3. Wenn Sie der geöffneten Sammlung weitere Ablauf Verfolgungs Dateien hinzufügen möchten, klicken Sie auf **Datei** , und zeigen Sie dann auf **Hinzufügen**. Navigieren Sie in dem geöffneten Fenster zum Speicherort der Ablaufverfolgungsdateien, und doppelklicken Sie auf die Datei, die Sie hinzufügen möchten.

> [!CAUTION]
> Es ist nicht empfehlenswert, eine Ablaufverfolgungsprotokolldatei zu laden, die größer als 200 MB ist. Wenn Sie eine Datei laden, die diesen Wert überschreitet, nimmt der Ladeprozess je nach Computerressourcen unter Umständen viel Zeit in Anspruch. Das Service Trace Viewer-Tool reagiert unter Umständen über einen längeren Zeitraum nicht oder belegt den gesamten Speicher des Computers. Es wird empfohlen, dass Sie das teilweise Laden konfigurieren, um dies zu vermeiden. Weitere Informationen dazu finden Sie im Abschnitt "Laden von großen Ablaufverfolgungsdateien".

#### <a name="event-tracing-and-crimson-tracing"></a>Ereignisablaufverfolgung und Crimson-Ablaufverfolgung

Das Native Format des Viewers ist das Aktivitätsablaufverfolgungs-Format, das WCF ausgibt. In einem anderen Format ausgegebene Ablaufverfolgungen müssen konvertiert werden, bevor der Viewer sie anzeigen kann. Zurzeit unterstützt der Viewer zusätzlich zum Aktivitätsablaufverfolgungs-Format die Ereignisablaufverfolgung und Crimson-Ablaufverfolgung.

Wenn Sie eine Datei öffnen, die keine Aktivitätsablaufverfolgungen enthält, versucht der Viewer, die Datei zu konvertieren. Sie müssen den Namen und den Speicherort der Datei angeben, die die zu konvertierenden Ablaufverfolgungsdaten enthält. Nachdem die Daten konvertiert wurden, zeigt der Viewer den Inhalt der neuen Datei an.

> [!NOTE]
> Konvertierung erfordert Speicherplatz zum Speichern der konvertierten Ablaufverfolgungsdaten. Stellen Sie sicher, dass ausreichender Speicherplatz zum Speichern der Daten vorhanden ist, bevor Sie eine Konvertierung starten. Andernfalls schlägt die Konvertierung fehl.

### <a name="managing-projects"></a>Verwalten von Projekten

Der Viewer unterstützt Projekte, um die Anzeige mehrerer Ablaufverfolgungsdateien zu vereinfachen. Wenn Sie zum Beispiel über eine Client- und eine Dienst-Ablaufverfolgungsdatei verfügen, können Sie diese einem Projekt hinzufügen. Auf diese Weise werden jedes Mal, wenn Sie das Projekt öffnen, alle Ablaufverfolgungsdateien im Projekt gleichzeitig geladen.

Es gibt zwei Möglichkeiten zum Verwalten von Projekten:

- Im Menü **Datei** können Sie Projekte öffnen, speichern und schließen.

- Auf der Registerkarte **Projekt** können Sie einem Projektdateien hinzufügen.

### <a name="viewing-wcf-traces"></a>Anzeigen von WCF-Ablaufverfolgungen

WCF gibt Ablauf Verfolgungen im Aktivitätsablaufverfolgungs-Format aus. Im Aktivitätsablaufverfolgungs-Modell werden einzelne Ablaufverfolgungen nach ihrem jeweiligen Zweck in Aktivitäten gruppiert. Zwischen den Aktivitäten wird eine logische Ablaufsteuerung übertragen. Zum Beispiel werden während der Lebensdaueraktivität einer Anwendung zahlreiche Nachrichtensendeaktivitäten angezeigt und wieder entfernt. Weitere Informationen zum Anzeigen von Ablauf Verfolgungen und Aktivitäten und zur Benutzeroberfläche des Service Trace Viewers finden [Sie unter Verwenden von Service Trace Viewer zum Anzeigen korrelierter Ablauf Verfolgungen und Problem](./diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)Behandlung.

#### <a name="switching-to-different-views"></a>Umschalten zu anderen Ansichten

Der Service Trace Viewer umfasst die folgenden Ansichten. Sie werden im linken Bereich des Viewers als Registerkarten angezeigt, und auf Sie kann auch über das Menü **Ansicht** zugegriffen werden.

- Aktivitätsansicht

- Projektansicht

- Nachrichtenansicht

- Diagrammansicht

##### <a name="activity-view"></a>Aktivitätsansicht

Nachdem die Ablauf Verfolgungs Dateien geöffnet wurden, sehen Sie die in Aktivitäten gruppierten Ablauf Verfolgungen, die in der **Aktivitäts** Ansicht im linken Bereich angezeigt werden.

In der **Aktivitäts** Ansicht werden Aktivitäts Namen, die Anzahl der Ablauf Verfolgungen in der Aktivität, die Dauer, die Startzeit und die Endzeit angezeigt.

Indem Sie auf eine der aufgeführten Aktivitäten klicken, werden die Ablaufverfolgungen in dieser Aktivität rechts im Ablaufverfolgungsfenster angezeigt. Sie können dann eine Ablaufverfolgung auswählen, um die Details anzuzeigen.

Sie können mehrere Aktivitäten auswählen, indem Sie die **STRG** -Taste oder die **UMSCHALT** Taste drücken und auf die gewünschten Aktivitäten klicken. Im Ablaufverfolgungsbereich werden alle Ablaufverfolgungen der ausgewählten Aktivitäten angezeigt.

Sie können auf eine Aktivität doppelklicken, um Sie in der **Diagramm** Ansicht anzuzeigen. Alternativ können Sie eine Aktivität auswählen und zur **Diagramm** Ansicht wechseln.

> [!NOTE]
> Die Aktivität "000000000000" ist eine spezielle Aktivität, die nicht in der Diagramm Ansicht angezeigt werden kann. Da alle anderen Aktivitäten damit verknüpft sind, hat das Anzeigen dieser Aktivität schwerwiegende Auswirkungen auf die Leistung.

Sie können auf den Spaltentitel klicken, um die Aktivitätsliste zu sortieren. Aktivitäten mit Warnungsablaufverfolgungen weisen einen gelben Hintergrund auf und Aktivitäten mit Fehlerablaufverfolgungen einen roten Hintergrund.

Es gibt verschiedene Typen von Aktivitäten, und jeder Typ verfügt über ein entsprechendes Symbol links neben der jeweiligen Aktivität. Informationen zur Bedeutung der Symbole finden Sie im Abschnitt zu Ablaufverfolgungssymbolen.

##### <a name="project-view"></a>Projektansicht

Diese Ansicht ermöglicht Ihnen, Ablaufverfolgungsdateien im aktuellen Projekt zu verwalten. Weitere Informationen finden Sie im Abschnitt über das Verwalten des Projekts.

##### <a name="message-view"></a>Nachrichtenansicht

In dieser Ansicht können Sie alle Nachrichtenprotokoll-Ablauf Verfolgungen anzeigen, einschließlich Aktion, Datum/Uhrzeit, Prozess, einlässigkeit und von/an und navigieren zu den Details der zugehörigen Nachrichtenprotokoll-Ablauf Verfolgung. Sie können die Nachrichtenprotokoll Ablauf Verfolgungen nach Aktivitäts Begrenzung, Prozess/Thread oder sende & Empfangs Vorgänge gruppieren, um die Navigation des Nachrichten Flusses zu vereinfachen.

##### <a name="graph-view"></a>Diagrammansicht

In dieser Ansicht werden die Ablauf Verfolgungs Daten für eine bestimmte Aktivität in Diagrammform angezeigt. Im Diagramm können Sie die schrittweise Ausführung von Ereignissen und die Wechselbeziehungen zwischen mehreren Aktivitäten nachvollziehen, während die Daten diese durchlaufen.

Um zur **Diagramm** Ansicht zu wechseln, wählen Sie eine Aktivität in der **Aktivitäts** Ansicht aus, und klicken Sie dann auf die Registerkarte **Aktivität** oder auf eine Nachrichtenprotokoll-Ablauf Verfolgung in der **Nachrichten** Ansicht. Wenn mehrere Ablaufverfolgungsdateien geladen sind und die Aktivität Ablaufverfolgungen aus mehr als einer Datei umfasst, werden alle relevanten Ablaufverfolgungen in der Diagrammansicht angezeigt. Wenn Sie auf die Aktivitäts-und Nachrichtenprotokoll-Ablauf Verfolgungen doppelklicken, gelangen Sie auch zur **Diagramm** Ansicht.

In der **Diagramm** Ansicht stellt jede vertikale Spalte eine Aktivität dar, und jeder Block in der Spalte stellt eine Ablauf Verfolgung dar. Die Aktivitäten werden nach Prozess (oder Thread) gruppiert. Die kleinen Pfeile zwischen Aktivitäten stellen Übertragungen dar. Die großen Pfeile zwischen Prozessen stellen Nachrichtenaustausch dar. Die ausgewählte Aktivität wird stets gelb angezeigt.

###### <a name="selecting-traces-in-the-graph"></a>Auswählen von Ablaufverfolgungen im Diagramm

1. Klicken Sie auf einen Block im Diagramm.

2. Wählen Sie mit den Nach-oben- und Nach-unten-Pfeilen die benachbarten Ablaufverfolgungen aus.

3. Achten Sie auf die Ablaufverfolgungsinformationen im Ablaufverfolgungsbereich und Detailbereich.

###### <a name="expanding-or-collapsing-activity-transfers"></a>Erweitern oder Reduzieren von Aktivitätsübertragungen

Sie können Aktivitätsübertragungen erweitern, wenn die ausgewählte Aktivität an eine andere Aktivität übertragen wird. Sie können auf diese Weise den Übertragungen folgen.

So erweitern oder reduzieren Sie Aktivitätsübertragungen

1. Suchen Sie auf der linken Seite des Übertragungs Symbols nach der Übertragungs Ablauf Verfolgung mit dem Zeichen "+".

2. Klicken Sie auf "+", oder drücken Sie **STRG** und "+" mithilfe der Tastatur.

3. Die nächste Aktivität wird im Diagramm angezeigt.

4. Ein "-" wird auf der linken Seite des Übertragungs Symbols angezeigt. Klicken Sie auf das Zeichen "-", oder drücken Sie STRG und "-", die Aktivitäts Übertragung wird reduziert.

> [!NOTE]
> Wenn eine Aktivität über mehrere Übertragungen verfügt und Sie eine der Übertragungen erweitern, werden Aktivitäten angezeigt, die von der Stammaktivität zu der neuen Aktivität führen. Diese neuen Aktivitäten werden reduziert angezeigt. Wenn Sie die Details dieser Aktivitäten anzeigen möchten, erweitern Sie sie vertikal, indem Sie auf das Erweiterungssymbol in der Kopfzeile des Diagramms klicken.

###### <a name="expanding-or-collapsing-activities-vertically"></a>Vertikales Erweitern oder Reduzieren von Aktivitäten

Der Viewer blendet unnötige Details im Aktivitätsdiagramm aus, indem er Aktivitäten reduziert. In einer reduzierten Aktivität werden einzelne Ablaufverfolgungen nicht angezeigt. Nur Ablaufverfolgungsübertragungen werden angezeigt. Wenn alle Ablaufverfolgungen in einer Aktivität angezeigt werden sollen, erweitern Sie die Aktivität vertikal, indem Sie auf das Erweiterungssymbol der Aktivität in der Kopfzeile des Diagramms klicken.

So erweitern oder reduzieren Sie Aktivitäten vertikal

1. Klicken Sie in der Aktivitäts Kopfzeile auf das Symbol "+", um die Aktivität vertikal zu erweitern.

2. Beachten Sie, dass alle Ablaufverfolgungen im Diagramm angezeigt werden.

3. Klicken Sie im Aktivitäts Header auf das Symbol "-", um die Aktivität vertikal zu reduzieren.

4. Beachten Sie, dass nur wichtige Übertragungen, Nachrichtenprotokolle, Warnungs- und Ausnahmeablaufverfolgungen in der Aktivität angezeigt werden.

###### <a name="options"></a>Optionen

Sie können zwei Optionen im Menü " **Option** " in der Diagramm Ansicht auswählen.

- Ablaufverfolgungen für Aktivitätsgrenzen anzeigen: Wenn diese Option nicht aktiviert ist, werden die Ablaufverfolgungen für Aktivitätsgrenzen im Diagramm ignoriert.

- Ausführliche Ablaufverfolgungen ohne Nachrichten anzeigen: Wenn diese Option deaktiviert ist, werden ausführliche Ebenenablaufverfolgungen, außer Nachrichtenablaufverfolgungen, ignoriert. In den meisten Fällen sind ausführliche Ebenenablaufverfolgungen für die Analyse weniger wichtig. Diese Option ist nützlich, wenn Sie ausführliche Ebenenablaufverfolgungen nicht analysieren möchten, sondern sich auf wichtigere Ablaufverfolgungen konzentrieren möchten.

###### <a name="layout-mode"></a>Layoutmodus

Der Viewer hat zwei Layoutmodi: **Prozess** und **Thread**. Diese Einstellung definiert die größte Organisationseinheit. Der standardlayoutmodus ist **Process**. Dies bedeutet, dass Aktivitäten nach Prozessen im Diagramm gruppiert werden.

###### <a name="execution-list"></a>Ausführungsliste

Sie können in dieser Dropdownliste auswählen, welcher Prozess oder Thread im Diagramm angezeigt werden soll. Wenn zum Beispiel Ablaufverfolgungsdateien von zwei Clients (A und B) sowie ein Dienst geöffnet sind und Sie nur den Dienst und Client A im Diagramm anzeigen möchten, können Sie die Auswahl von Client B aufheben.

#### <a name="viewing-trace-details"></a>Anzeigen von Ablaufverfolgungsdetails

Um Ablaufverfolgungsdetails anzuzeigen, wählen Sie eine Ablaufverfolgung im Ablaufverfolgungsbereich aus. Die Details werden im Detailbereich angezeigt.

##### <a name="trace-pane"></a>Ablaufverfolgungsbereich

Der rechte obere Bereich im Service Trace Viewer ist der Ablaufverfolgungsbereich. In diesem Bereich werden alle Ablaufverfolgungen in der ausgewählten Aktivität mit zusätzlichen Informationen aufgeführt, beispielsweise Ablaufverfolgungsebene, Thread-ID und Prozessname.

Sie können das unformatierte XML der Ablauf Verfolgung in die Zwischenablage kopieren, indem Sie mit der rechten Maustaste auf eine Ablauf Verfolgung klicken und Ablauf **Verfolgung in Zwischenablage kopieren**

##### <a name="detail-pane"></a>Detailbereich

Der unterste linke Bereich im Service Trace Viewer ist der Detailbereich. Er stellt drei Registerkarten zum Anzeigen von Ablaufverfolgungsdetails bereit.

In der **formatierten** Ansicht werden die Informationen in einer organisier teren Weise angezeigt. Es werden alle bekannten XML-Elemente in Tabellen und Strukturen aufgelistet, sodass die Informationen einfacher zu lesen und zu interpretieren sind.

In der **XML** -Ansicht wird XML angezeigt, das der ausgewählten Ablauf Verfolgung entspricht. Hervorhebung und Syntaxfarbe werden unterstützt. Wenn Sie " **Suchen" verwenden,** um Zeichen folgen zu suchen, werden die Suchergebnisse hervorgehoben.

In der Meldungs **Ansicht wird der Nachrichten** Teil des XML-Codes in Nachrichtenprotokoll-Ablauf Verfolgungen angezeigt. Er ist nicht sichtbar, wenn Sie eine Ablaufverfolgung ohne Nachrichten auswählen.

### <a name="filtering-wcf-traces"></a>Filtern von WCF-Ablaufverfolgungen

Um die Analyse von Ablaufverfolgungsdateien zu vereinfachen, können Sie sie auf folgende Weisen filtern:

- Die Filtersymbolleiste ermöglicht den Zugriff auf vordefinierte und benutzerdefinierte Filter. Sie kann über das Menü **Ansicht** aktiviert werden.

- Der vordefinierte Filter des Viewers kann verwendet werden, um Teile der WCF-Ablauf Verfolgungen selektiv zu filtern. Standardmäßig ist der Filter so eingestellt, dass alle Infrastrukturablaufverfolgungen zugelassen werden. Die Einstellungen dieses Filters werden im Menü **Ansicht** unter **Filteroptionen** definiert.

- Benutzerdefinierte XPath-Filter ermöglichen Benutzern den Vollzugriff auf die Filterung. Sie können im Menü **Ansicht** im **benutzerdefinierten Filter** definiert werden.

Es werden nur die Ablaufverfolgungen angezeigt, die alle Filter durchlaufen haben.

#### <a name="using-the-filter-toolbar"></a>Verwenden der Filtersymbolleiste

Die Filtersymbolleiste wird im oberen Teil des Tools angezeigt. Wenn Sie nicht vorhanden ist, können Sie Sie im Menü **Ansicht** aktivieren. Die Leiste verfügt über drei Komponenten:

- Suchen nach: **Suchen nach** definiert den Betreff, nach dem im Filter Vorgang gesucht werden soll. Wenn Sie z. b. alle Ablauf Verfolgungen suchen möchten, die im Kontext von Process X ausgegeben wurden, legen Sie dieses Feld auf X und das Feld **Suchen in** auf ' Prozess Name ' fest. Dieses Feld ändert sich in ein DateTime-Auswahlsteuerelement, wenn ein zeitbasierter Filter ausgewählt wird.

- Suche in: Dieses Feld definiert den Typ des anzuwendenden Filters.

- Ebene: Die Ebeneneinstellung definiert die minimale vom Filter zugelassene Ablaufverfolgungsebene. So werden bei Auswahl der Error-Ebene oder höher nur die Ablaufverfolgungen auf Fehlerebene oder einer höheren Ebene angezeigt. Dieser Filter wird mit den unter Suchen nach und Suchen in angegebenen Kriterien kombiniert.

Mit der Schaltfläche **jetzt filtern** wird der Filter Vorgang gestartet. Die Ausführung einiger Filter kann sehr lange dauern, insbesondere dann, wenn sie auf einen umfangreichen Datensatz angewendet werden. Sie können den Filter Vorgang abbrechen, indem Sie die Schaltfläche **Beenden** drücken, die in der Statusleiste unter dem Menü **Vorgänge** angezeigt wird.

Die Schaltfläche **Löschen** setzt vordefinierte und benutzerdefinierte Filter zurück, damit alle Ablauf Verfolgungen durchlaufen werden können.

#### <a name="filter-options"></a>Filteroptionen

Der Viewer kann WCF-Ablaufverfolgungen automatisch aus der Ansicht entfernen. Ablaufverfolgungen, die von bestimmten Bereichen von WCF ausgegeben wurden, können selektiv aus der Ansicht entfernt werden, zum Beispiel transaktionsbezogene Ablaufverfolgungen.

Die Einstellungen dieses Filters werden im Menü **Ansicht** unter **Filteroptionen** definiert.

#### <a name="custom-filters"></a>Benutzerdefinierte Filter

Wenn Sie mit der XML Path-Programmiersprache (XPath) vertraut sind, können Sie eigene benutzerdefinierte Filter zum Suchen nach Ablaufverfolgungsdaten für ein bestimmtes XML-Element erstellen. Sie können über die Filtersymbolleiste auf die Filter zugreifen.

Benutzerdefinierte Filter können Parameter einschließen. Sie können auch bereits vorhandene benutzerdefinierte Filter importieren.

##### <a name="creating-a-custom-filter"></a>Erstellen eines benutzerdefinierten Filters

Es gibt zwei Möglichkeiten zum Erstellen von Filtern:

###### <a name="creating-a-custom-filter-using-the-template-wizard"></a>Erstellen eines benutzerdefinierten Filters mit dem Vorlagen-Assistenten

Sie können auf eine vorhandene Ablaufverfolgung klicken und auf Grundlage der Struktur der Ablaufverfolgung einen Filter erstellen. In diesem Beispiel wird ein benutzerdefinierter Filter auf Grundlage der Thread-ID erstellt.

1. Wählen Sie im Ablaufverfolgungsbereich oben rechts im Viewer eine Ablaufverfolgung aus, die ein Element enthält, nach dem Sie filtern möchten.

2. Klicken Sie oben im Ablauf verfolgungsbereich auf die Schaltfläche **benutzerdefinierten Filter erstellen** .

3. Geben Sie im angezeigten Dialogfeld einen Namen für den Filter ein. Geben Sie in diesem Beispiel ein `Thread ID` . Sie können auch eine Beschreibung des Filters eingeben.

4. In der Strukturansicht links wird die Struktur des Ablaufverfolgungsdatensatzes angezeigt, den Sie in Schritt 1 ausgewählt haben. Wechseln Sie zu dem Element, für das Sie eine Bedingung erstellen möchten. Navigieren Sie in diesem Beispiel zu der ThreadID, die sich im XPath:- /E2ETraceEvent/System/Execution/@ThreadID Knoten befindet. Doppelklicken Sie auf das ThreadID-Attribut in der Strukturansicht. Hierdurch wird rechts im Dialogfeld ein Ausdruck für das Attribut erstellt.

5. Ändern Sie das Feld Parameter für die ThreadID-Bedingung von None in " {0} ". Dieser Schritt aktiviert den ThreadID-Wert, der beim Anwenden des Filters konfiguriert werden soll. (Siehe den Abschnitt zum Anwenden eines Filters.) Sie können bis zu vier Parameter definieren. Bedingungen werden mit dem OR-Operator kombiniert.

6. Klicken Sie auf **OK** , um den Filter zu erstellen.

> [!NOTE]
> Sobald ein Filter mit dem Vorlagen-Assistenten erstellt wurde, kann er nur manuell bearbeitet werden. Es ist nicht möglich, den Assistenten für einen Filter zu aktivieren, der bereits erstellt wurde. Darüber hinaus werden die Bedingungen eines XPath-Filters, der mit dem Vorlagen-Assistenten erstellt wurde, mit dem OR-Operator kombiniert. Wenn ein AND-Vorgang benötigt wird, können Sie den Filterausdruck bearbeiten, nachdem er erstellt wurde.

###### <a name="creating-a-custom-filter-manually"></a>Manuelles Erstellen eines benutzerdefinierten Filters

Das Menü Benutzerdefinierte Filter ermöglicht Ihnen, XPath-Filter manuell einzugeben.

1. Klicken Sie im Menü Ansicht auf das Menü Element **benutzerdefinierte Filter** .

2. Klicken Sie im angezeigten Dialogfeld auf **neu.**

3. Geben Sie mindestens einen Filternamen und einen XPath-Ausdruck an.

4. Klicken Sie auf **OK**.

###### <a name="applying-a-custom-filter"></a>Anwenden eines benutzerdefinierten Filters

Sobald ein benutzerdefinierter Filter erstellt wurde, kann er über die Filtersymbolleiste aufgerufen werden. Wählen Sie im Feld **Suchen in** der Filter Symbolleiste den Filter aus, der angewendet werden soll. Wählen Sie für das vorherige Beispiel 'Thread-ID' aus.

1. Geben Sie im Feld Suchen nach den Wert an, **nach dem Sie** suchen. Geben Sie in diesem Beispiel die ID des Threads ein, nach dem Sie suchen möchten.

2. Klicken Sie auf **jetzt filtern**, und beobachten Sie das Ergebnis des Vorgangs.

Wenn der Filter mehrere Parameter verwendet, geben Sie diese mithilfe von ";" als Trennzeichen in das Feld **Suchen** nach ein. Die folgende Zeichenfolge gibt zum Beispiel drei Parameter an: '1;findValue;text'. Der Viewer wendet ' 1 ' auf den {0} Parameter des Filters an. "findValue" und "Text" werden auf {1} {2} bzw. angewendet.

###### <a name="sharing-custom-filters"></a>Freigeben von benutzerdefinierten Filtern

Benutzerdefinierte Filter können für andere Sitzungen und andere Benutzer freigegeben werden. Sie können die Filter in eine Definitionsdatei exportieren, die Sie an einem anderen Speicherort importieren können.

 So importieren Sie einen benutzerdefinierten Filter

1. Klicken Sie im Menü **Ansicht** auf **benutzerdefinierte Filter**.

2. Klicken Sie im Dialogfeld, das geöffnet wird, auf die Schaltfläche **importieren** .

3. Navigieren Sie zur benutzerdefinierten Filterdatei (. stvcf), klicken Sie auf die Datei, und klicken Sie auf die Schaltfläche **Öffnen** .

So exportieren Sie einen benutzerdefinierten Filter

1. Klicken Sie im Menü Ansicht auf **benutzerdefinierte Filter**.

2. Wählen Sie im aufgerufenen Dialogfeld den Filter, den Sie exportieren möchten.

3. Klicken Sie auf die Schaltfläche **Exportieren**.

4. Geben Sie den Namen und den Speicherort der benutzerdefinierten Filter Definitionsdatei (. stvcf) an, und klicken Sie auf die Schaltfläche **Speichern** .

> [!NOTE]
> Diese benutzerdefinierten Filter können nur von Service Trace Viewer importiert und exportiert werden. Sie können nicht von anderen Tools gelesen werden.

### <a name="finding-data"></a>Suchen von Daten

Der Viewer bietet folgende Möglichkeiten zum Suchen von Daten:

- Die Symbolleiste Suchen stellt bietet schnellen Zugriff auf die allgemeinen Suchoptionen.

- Das Dialogfeld Suchen stellt weitere Suchoptionen zur Verfügung. Der Zugriff ist über das Menü **Bearbeiten** oder über die Kurztaste STRG + F möglich.

Die Symbolleiste Suchen wird am oberen Rand des Viewers angezeigt. Wenn Sie nicht vorhanden ist, können Sie Sie im Menü **Ansicht** aktivieren. Die Leiste verfügt über zwei Komponenten:

- Suchen nach: Ermöglicht Ihnen, ein Stichwort für die Suche einzugeben.

- Suchen in: Ermöglicht Ihnen, den Suchbereich einzugeben. Sie können auswählen, ob in allen Aktivitäten oder nur in der aktuellen Aktivität gesucht werden soll.

Das Suchdialogfeld stellt zwei zusätzliche Optionen bereit:

- Ziel suchen:

  - Mit der Option "RAW Log Data" wird das-Schlüsselwort in allen Rohdaten durchsucht.

  - Die Optionen "XML-Text" und "XML-Attribut" suchen nur in XML-Elementen.

  - Die Option "protokollierte Nachricht" durchsucht das-Schlüsselwort nur in Nachrichten.

- Stamm Aktivität ignorieren: bei der Suche werden die Ablauf Verfolgungen in der Aktivität "000000000000" ignoriert. Hierdurch wird die Leistung bei umfangreichen Ablaufverfolgungsdateien verbessert, wenn die Stammaktivität über Tausende von Ablaufverfolgungen verfügt, bei denen es sich zum Großteil um Übertragungen handelt.

### <a name="navigating-traces"></a>Navigieren in Ablaufverfolgungen

Da Ablaufverfolgungen bei Laufzeit der Anwendung Schritt für Schritt aufgezeichnet werden, kann Sie das Navigieren in Ablaufverfolgungen beim Debuggen Ihrer Anwendung unterstützen. Service Trace Viewer bietet mehrere Möglichkeiten zum Navigieren in Ablaufverfolgungen.

#### <a name="step-forward-or-backward"></a>Schritt vorwärts oder zurück

Wenn Sie jede Ablauf Verfolgung als Codezeile im Programm beachten, ist die schrittweise Weiterleitung in der integrierten Entwicklungsumgebung (Integrated Development Environment, IDE) von Visual Studio sehr ähnlich. Der Unterschied ist, dass Sie in der Ablaufverfolgung auch einen Schritt zurück gehen können. Einen Schritt vorwärts zu gehen bedeutet, zur nächsten Ablaufverfolgung in der Aktivität zu gehen.

- Step Forward: Verwenden Sie das Menü **Aktivität** , oder drücken Sie F10. Im Ablauf verfolgungsbereich können Sie auch die Pfeiltaste "nach unten" verwenden.

- Rückwärts Schritt: Verwenden Sie das Menü **Aktivität** , oder drücken Sie "F9". Sie können auch die Pfeiltaste "nach oben" im Ablauf verfolgungsbereich verwenden.

> [!NOTE]
> Dies kann zu einer Aktivität führen, die in einem anderen Prozess oder sogar auf einem anderen Computer auftritt, da WCF-Nachrichten Aktivitäts-IDs enthalten können, die sich über mehrere Computer erstrecken.

#### <a name="follow-transfer"></a>Verfolgen von Übertragungen

Übertragungsablaufverfolgungen sind spezielle Ablaufverfolgungen in der Ablaufverfolgungsdatei. Eine Aktivität wird möglicherweise über eine Übertragungsablaufverfolgung an eine andere Aktivität übertragen. Beispielsweise kann "Aktivität A" zu "Aktivität B" übertragen. In diesem Fall gibt es eine Übertragungs Ablauf Verfolgung in der "Aktivität a" mit dem Namen "an: Aktivität" und dem Übertragungs Symbol. Diese Übertragungsablaufverfolgung ist ein Link zwischen den beiden Ablaufverfolgungen. In "Aktivität B" kann auch eine Übertragungs Ablauf Verfolgung am Ende der Aktivität vorhanden sein, die zurück auf "Aktivität a" übertragen werden soll. Dies ähnelt Funktionsaufrufen in Programmen: A ruft B, dann gibt B Werte an A zurück.

"Übertragung übertragen" ähnelt "Einzelschritt" in einem Debugger. Dabei wird die Übertragung von Aktivität A zu Aktivität B verfolgt. Andere Ablaufverfolgungen sind davon nicht betroffen.

Es gibt zwei Möglichkeiten, einer Übertragung zu folgen: mit der Maus oder der Tastatur:

- Mit der Maus: Doppelklicken Sie im Ablaufverfolgungsbereich auf die Übertragungsablaufverfolgung.

- Per Tastatur: Wählen Sie eine Übertragungs Ablauf Verfolgung aus, und verwenden Sie "Übertragung übertragen" im Menü **Aktivität** , oder drücken Sie die Taste F11.

> [!NOTE]
> Wenn Aktivität A an Aktivität B übertragen wird, wartet Aktivität A in vielen Fällen, bis Aktivität B an Aktivität A zurückübertragen wurde. Dies bedeutet, dass für Aktivität A während des Zeitraums, in dem eine aktive Ablaufverfolgung für Aktivität B erfolgt, keine Ablaufverfolgung protokolliert wird. Es ist jedoch auch möglich, dass Aktivität A nicht wartet und mit dem Protokollieren von Ablaufverfolgungen fortfährt. Es ist auch möglich, dass Aktivität B nicht an Aktivität A zurückübertragen wird. In diesem Sinne unterscheiden sich Aktivitätsübertragungen weiterhin von Funktionsaufrufen. Aktivitätsübertragungen werden in der Diagrammansicht noch besser verdeutlicht.

#### <a name="jump-to-next-or-previous-transfer"></a>Zur nächsten oder zur vorherigen Übertragung wechseln

Wenn Sie die aktuelle Aktivität oder mehrere ausgewählte Aktivitäten analysieren, möchten Sie die Aktivitäten, an die die Übertragung stattfindet, möglicherweise schnell finden. "Zur nächsten Übertragung springen" ermöglicht es Ihnen, die nächste Übertragungs Ablauf Verfolgung in der Aktivität zu finden. Sobald Sie die Übertragungs Ablauf Verfolgung gefunden haben, können Sie "Übertragung übertragen" verwenden, um die nächste Aktivität schrittweise durchzugehen.

- Zur nächsten Übertragung springen: Verwenden Sie das Menü **Aktivität** , oder drücken Sie STRG + F10.

- Zur vorherigen Übertragung springen: Verwenden Sie das Menü **Aktivität** , oder drücken Sie STRG + F9.

#### <a name="navigate-in-graph-view"></a>Navigieren in der Diagrammansicht

Obwohl das Navigieren im Aktivitätsbereich und Ablauf verfolgungsbereich dem Debugging ähnelt, bietet die **Diagramm** Ansicht eine viel bessere Navigation. Weitere Informationen finden Sie im Abschnitt "Diagramm Ansicht".

### <a name="loading-large-trace-files"></a>Laden von großen Ablaufverfolgungsdateien

Ablaufverfolgungsdateien können sehr groß sein. Wenn Sie z. b. die Ablauf Verfolgung auf der Ebene "ausführlich" aktivieren, kann die resultierende Ablauf Verfolgungs Datei für die Ausführung von einigen Minuten problemlos Hunderte von Megabyte oder sogar größer sein, je nach Netzwerkgeschwindigkeit und Kommunikationsmuster.

Wenn Sie eine sehr große Ablaufverfolgungsdatei in Service Trace Viewer öffnen, kann sich dies negativ auf die Systemleistung auswirken. Die Ladegeschwindigkeit und die Antwortzeit nach dem Laden können langsam sein. Die tatsächliche Geschwindigkeit unterscheidet sich bisweilen, abhängig von der Hardwarekonfiguration. Bei den meisten PCs wirkt sich das Laden einer Ablaufverfolgungsdatei, die größer als 200&#160;MB ist, deutlich auf die Leistung aus. Für Ablaufverfolgungsdateien, die größer als 1 GB sind, verwendet das Tool möglicherweise den gesamten verfügbaren Arbeitsspeicher oder reagiert für einen sehr langen Zeitraum nicht mehr.

Um das langsame laden und die Reaktionszeit beim Analysieren von großen Ablauf Verfolgungs Dateien zu vermeiden, stellt Service Trace Viewer eine Funktion mit dem Namen "partielles laden" bereit, die jeweils nur einen kleinen Teil der Ablauf Verfolgung lädt. Sie verfügen zum Beispiel über eine Ablaufverfolgungsdatei mit mehr als 1&#160;GB, die mehrere Tage lang auf dem Server läuft. Wenn einige Fehler aufgetreten sind und Sie die Ablaufverfolgung analysieren möchten, müssen Sie nicht die gesamte Ablaufverfolgungsdatei öffnen. Stattdessen können Sie die Ablaufverfolgungen eines bestimmten Zeitraums, in dem der Fehler möglicherweise aufgetreten ist, laden. Da der Umfang geringer ist, kann das Service Trace Viewer-Tool die Datei schneller laden, und Sie können die Fehler anhand eines kleineren Datensatzes ermitteln.

#### <a name="enabling-partial-loading"></a>Aktivieren des teilweisen Ladens

Sie müssen das teilweise Laden nicht manuell aktivieren. Wenn die Gesamtgröße der Ablaufverfolgungsdatei(en), die Sie laden möchten, 40&#160;MB überschreitet, zeigt Service Trace Viewer das Dialogfeld Teilweises Laden automatisch an, sodass Sie den Teil auswählen können, den Sie laden möchten.

> [!NOTE]
> Da Ablaufverfolgungen möglicherweise nicht gleich im Zeitraum verteilt sind, ist die Länge des im Dialogfeld Teilweises Laden angegebenen Zeitraums möglicherweise nicht proportional zur angezeigten Ladegröße. Die tatsächliche Ladegröße kann kleiner als die im Dialogfeld Teilweises Laden geschätzte Größe sein.

#### <a name="adjusting-partial-loading"></a>Anpassen des teilweisen Ladens

Nachdem die Ablaufverfolgungsdatei teilweise geladen wurde, können Sie den geladenen Datensatz ändern. Passen Sie dazu die Symbolleiste für teilweises Laden oben im Viewer an.

1. Verschieben Sie die Symbolleiste mit der Maus, oder geben Sie die Anfangs- und Endzeit ein.

2. Klicken Sie auf die Schaltfläche **Anpassen** .

## <a name="understanding-trace-icons"></a>Verstehen von Ablaufverfolgungssymbolen

Im folgenden finden Sie eine Liste von Symbolen, die das Service Trace Viewer-Tool in der **Aktivitäts** Ansicht, in der **Diagramm** Ansicht und im Ablauf **Verfolgungs** Bereich verwendet, um unterschiedliche Elemente darzustellen.

> [!NOTE]
> Einige nicht kategorisierte Ablauf Verfolgungen (z. b. "eine Nachricht wird geschlossen") haben kein Symbol.

### <a name="activity-tracing-traces"></a>Aktivitätsablaufverfolgungs-Symbole

|Symbol|Beschreibung|
|----------|-----------------|
|![Warnungsablaufverfolgung](./media/7457c4ed-8383-4ac7-bada-bcb27409da58.gif "7457c4ed-8383-4ac7-Bada-bcb27409da58")|Warnungsablaufverfolgung: Eine Ablaufverfolgung, die auf der Warnebene ausgegeben wird.|
|![Fehlerablaufverfolgung](./media/7d908807-4967-4f6d-9226-d52125db69ca.gif "7d908807-4967-4f 6D-9226-d52125db69ca")|Fehlerablaufverfolgung: Eine Ablaufverfolgung, die auf der Fehlerebene ausgegeben wird.|
|![Ablaufverfolgung "Aktivitätsstart":](./media/8a728f91-5f80-4a95-afe8-0b6acd6e0317.gif "8a728b91-5 A95-afe8-0b6acd6e0317")|Aktivitätsstart-Ablaufverfolgung: Eine Ablaufverfolgung, die den Beginn einer Aktivität markiert. Enthält den Namen der Aktivität. Als Anwendungsentwickler sollten Sie eine Aktivitätsstart-Ablaufverfolgung pro Aktivitäts-ID und Prozess oder Thread definieren.<br /><br /> Wenn die Aktivitäts-ID über die Ablaufverfolgungsquellen der Ablaufverfolgungskorrelation hinweg propagiert wird, können Sie mehrere Starts für dieselbe Aktivitäts-ID sehen (einen pro Ablaufverfolgungsquelle). Die Start-Ablaufverfolgung wird ausgegeben, wenn die Aktivitätsablaufverfolgung für die Ablaufverfolgungsquelle aktiviert ist.|
|![Ablaufverfolgung "Aktivitätsstopp"](./media/a0493e95-653e-4af8-84a4-4d09a400bc31.gif "a0493e95-653e-4af8-84a4-4d09a400bc31")|Aktivitätsstopp-Ablaufverfolgung: Eine Ablaufverfolgung, die das Ende einer Aktivität markiert. . Enthält den Namen der Aktivität. Als Anwendungsentwickler sollten Sie eine Aktivitätsstopp-Ablaufverfolgung pro Aktivitäts-ID und Ablaufverfolgungsquelle definieren. Es werden keine Ablaufverfolgungen von einer bestimmten Ablaufverfolgungsquelle angezeigt, nachdem die Ablaufverfolgungsquelle einen Aktivitätsstopp ausgegeben hat, es sei denn, die Ablaufverfolgungszeit weist eine grobe Granularität auf. Ist das der Fall, überlappen sich zwei Ablaufverfolgungen mit der gleichen Zeit, einschließlich eines Stopps, möglicherweise bei der Anzeige. Wenn die Aktivitäts-ID über die Ablaufverfolgungsquellen der Ablaufverfolgungskorrelation hinweg propagiert wird, können Sie mehrere Stopps für dieselbe Aktivitäts-ID sehen (einen pro Ablaufverfolgungsquelle). Die Stoppablaufverfolgung wird ausgegeben, wenn die Aktivitätsablaufverfolgung für die Ablaufverfolgungsquelle aktiviert ist.|
|![Ablaufverfolgung "Aktivität anhalten"](./media/6f7f4191-df2b-4592-8998-8379769e2d32.gif "6f 7F 4191-DF2B-4592-8998-8379769e2d32")|Aktivität anhalten-Ablaufverfolgung: Eine Ablaufverfolgung, die markiert, wann eine Aktivität angehalten wurde. Es werden erst Ablaufverfolgungen in einer angehaltenen Aktivität ausgegeben, wenn die Aktivität fortgesetzt wird. Eine angehaltene Aktivität gibt an, dass keine Verarbeitungen in dieser Aktivität im Bereich der Ablaufverfolgungsquelle stattfinden. Anhalten/Fortsetzen-Ablaufverfolgungen sind hilfreich für die Profilerstellung. Die Anhalten-Ablaufverfolgung wird ausgegeben, wenn die Aktivitätsablaufverfolgung für die Ablaufverfolgungsquelle aktiviert ist.|
|![Ablaufverfolgung "Aktivität fortsetzen"](./media/1060d9d2-c9c8-4e0a-9988-cdc2f7030f17.gif "1060d9d2-c9c8-4E0A-9988-cdc2f7030f17")|Aktivität fortsetzen-Ablaufverfolgung: Eine Ablaufverfolgung, die die Zeit markiert, zu der eine Aktivität nach dem Anhalten wieder fortgesetzt wird. Ablaufverfolgungen können in dieser Aktivität möglicherweise erneut ausgegeben werden. Anhalten/Fortsetzen-Ablaufverfolgungen sind hilfreich für die Profilerstellung. Die Fortsetzen-Ablaufverfolgung wird ausgegeben, wenn die Aktivitätsablaufverfolgung für die Ablaufverfolgungsquelle aktiviert ist.|
|![Übertragen](./media/b2d9850e-f362-4ae5-bb8d-9f6f3ca036a5.gif "b2d9850e-f362-4ae5-bb8d-9f6f3ca036a5")|Übertragung: Eine Ablaufverfolgung, die ausgegeben wird, wenn eine logische Ablaufsteuerung von einer Aktivität auf eine andere übertragen wird. Die Aktivität, aus der die Übertragung stammt, kann unter Umständen parallel zur der Aktivität ausgeführt werden, an die die Übertragung stattfindet. Die Übertragen-Ablaufverfolgung wird ausgegeben, wenn die Aktivitätsablaufverfolgung für die Ablaufverfolgungsquelle aktiviert ist.|
|![Übertragung von](./media/1df215cb-b344-4f36-a20d-195999bda741.gif "1df215 CB-B344-4t36-a20d-195999bda741")|Übertragung von: Eine Ablaufverfolgung, die eine Übertragung von einer anderen Aktivität zur aktuellen Aktivität definiert.|
|![Übertragung an](./media/74255b6e-7c47-46ef-8e53-870c76b04c3f.gif "74255b6e-7c47-46ef-8e53-870c76b04c3f")|Übertragung an: Eine Ablaufverfolgung, die eine Übertragung der logischen Ablaufsteuerung von der aktuellen Aktivität auf eine andere definiert.|

### <a name="wcf-traces"></a>WCF-Ablaufverfolgungen

|Symbol|Beschreibung|
|----------|-----------------|
|![Nachrichtenprotokoll-Ablauf Verfolgung](./media/7c66e994-2476-4260-a0db-98948b9af197.gif "7c66e994-2476-4260-a0db-98948b9af197")|Nachrichtenprotokoll-Ablauf Verfolgung: eine Ablauf Verfolgung, die ausgegeben wird, wenn eine WCF-Nachricht von der Nachrichten Protokollierungsfunktion protokolliert wird, wenn die Ablauf `System.ServiceModel.MessageLogging` Verfolgungs Quelle aktiviert ist. Durch Klicken auf diese Ablaufverfolgung wird die Nachricht angezeigt. Es gibt vier konfigurierbare Protokollierungspunkte für eine Nachricht: ServiceLevelSendRequest, TransportSend, TransportReceive und ServiceLevelReceiveRequest, die auch durch das `messageSource`-Attribut in der Nachrichtenablaufverfolgung angegeben werden können.|
|![Nachricht empfangene Ablauf Verfolgung](./media/de4f586c-c5dd-41ec-b1c3-ac56b4dfa35c.gif "de4f586c-c5dd-41ec-b1c3-ac56b4dfa35c")|Nachricht empfangene Ablauf Verfolgung: eine Ablauf Verfolgung, die ausgegeben wird, wenn eine WCF-Nachricht empfangen wird, wenn die Ablauf `System.ServiceModel` Verfolgungs Quelle auf der Ebene "Information" oder "ausführlich" aktiviert ist. Diese Ablauf Verfolgung ist für die Anzeige des Nachrichten Korrelations Pfeils in der Aktivitäts **Diagramm** Ansicht von entscheidender Bedeutung.|
|![Ablauf Verfolgung für Nachricht gesendet](./media/558943c4-17cf-4c12-9405-677e995ac387.gif "558943c4-17cf-4c12-9405-677e995ac387")|Nachricht gesendet: Ablauf Verfolgung: eine Ablauf Verfolgung, die ausgegeben wird, wenn eine WCF-Nachricht gesendet wird, wenn die Ablauf `System.ServiceModel` Verfolgungs Quelle auf der Ebene "Information" oder "ausführlich" aktiviert ist Diese Ablauf Verfolgung ist für die Anzeige des Nachrichten Korrelations Pfeils in der Aktivitäts **Diagramm** Ansicht von entscheidender Bedeutung.|

### <a name="activities"></a>activities

|Symbol|Beschreibung|
|----------|-----------------|
|![Aktivität](./media/wcfc-defaultactivityc.gif "wcfc_defaultActivityc")|Aktivität: Gibt an, dass die aktuelle Aktivität eine generische Aktivität ist.|
|![Stammaktivität](./media/5dc8e0eb-1c32-4076-8c66-594935beaee9.gif "5dc8e0eb-1c32-4076-8c66-594935beaee9")|Stammaktivität: Gibt die Stammaktivität eines Prozesses an.|

### <a name="wcf-activities"></a>WCF-Aktivitäten

|Symbol|Beschreibung|
|----------|-----------------|
|![Umgebungsaktivität](./media/29fa00ac-cf78-46e5-822d-56222fff61d1.gif "29fa00ac-cf78-46e5-822d-56222fff61d1")|Umgebungs Aktivität: eine Aktivität, mit der ein WCF-Host oder-Client erstellt, geöffnet oder geschlossen wird. Fehler, die während dieser Phasen aufgetreten sind, werden in dieser Aktivität angezeigt.|
|![Lauschaktivität](./media/d7b135f6-ec7d-45d7-9913-037ab30e4c26.gif "d7b135f6-ec7d-45d7-9913-037ab30e4c26")|Abhöraktivität: Eine Aktivität, die mit einem Listener zusammenhängende Ablaufverfolgungen protokolliert. In dieser Aktivität werden Listenerinformationen und Verbindungsanforderungen angezeigt.|
|![Aktivität "Bytes empfangen"](./media/2f628580-b80f-45a7-925b-616c96426c0e.gif "2F 628580-b80o-45a7-925b-616c96426c0e")|Bytes empfangen-Aktivität: Eine Aktivität, die alle Ablaufverfolgungen gruppiert, die sich auf empfangene Bytes in einer Verbindung zwischen zwei Endpunkten beziehen. Diese Aktivität ist wesentlich beim Korrelieren von Transportaktivitäten, die ihre Aktivitäts-ID propagieren, wie z.&#160;B. http.sys. Verbindungsfehler, wie z.&#160;B. Abbrüche, treten in dieser Aktivität auf.|
|![Aktivität "Nachricht verarbeiten"](./media/wcfc-executionactivityiconc.GIF "wcfc_ExecutionActivityIconc")|Process Message-Aktivität: eine Aktivität, die Ablauf Verfolgungen für das Erstellen einer WCF-Nachricht gruppiert. Fehler aufgrund eines ungültigen Umschlags oder einer falsch formatierten Nachricht werden in dieser Aktivität angezeigt. In dieser Aktivität können Nachrichtenheader geprüft werden, um zu ermitteln, ob eine Aktivitäts-ID vom Aufrufer propagiert wurde. Wenn dies zutrifft, kann beim Übertragen an die Aktion verarbeiten-Aktivität (das nächste Symbol) dieser Aktivität auch die propagierte Aktivitäts-ID für die Korrelation zwischen dem Aufrufer und den Ablaufverfolgungen des Aufrufenden zugewiesen werden.|
|![Nachrichtenprotokoll-Ablauf Verfolgung](./media/7c66e994-2476-4260-a0db-98948b9af197.gif "7c66e994-2476-4260-a0db-98948b9af197")|Process Action-Aktivität: eine Aktivität, die alle Ablauf Verfolgungen gruppiert, die sich auf eine WCF-Anforderung über zwei Endpunkte beziehen. Wenn `propagateActivity` auf beiden Endpunkten in der Konfiguration auf `true` festgelegt ist, werden alle Ablaufverfolgungen für die direkte Korrelation in eine Aktivität zusammengeführt. Einige Aktivitäten enthalten Fehler, die bei der Transport- oder Sicherheitsverarbeitung auftreten und sich bis hin zu Benutzercodegrenzen und zurück erstrecken (sofern eine Antwort vorhanden ist).|
|![Aktivität "Nachricht verarbeiten"](./media/wcfc-executionactivityiconc.GIF "wcfc_ExecutionActivityIconc")|Benutzercodeaktivität ausführen-Aktivität: Eine Aktivität, die Benutzercode-Ablaufverfolgungen zur Verarbeitung einer Anforderung gruppiert.|

## <a name="troubleshooting"></a>Problembehandlung

Wenn Sie nicht über die Berechtigung zum Schreiben in die Registrierung verfügen, erhalten Sie die folgende Fehlermeldung: "der Microsoft Service Trace Viewer wurde nicht beim System registriert", wenn Sie das `svctraceviewer /register` Tool mit dem Befehl "" registrieren. Ist dies der Fall, sollten Sie sich über ein Konto anmelden, das Schreibzugriff auf die Registrierung bietet.

Außerdem schreibt das Service Trace Viewer-Tool einige Einstellungen (z.&#160;B. benutzerdefinierte Filter und Filteroptionen) in die SvcTraceViewer.exe.settings-Datei im Assemblyordner. Wenn Sie keine Leseberechtigungen für die Datei haben, können Sie das Tool starten, aber die Einstellungen nicht laden.

Wenn Sie die Fehlermeldung "Unbekannter Fehler bei der Verarbeitung von mindestens einer Ablaufverfolgung" beim Öffnen der ETL-Datei erhalten, bedeutet dies, dass das Format der ETL-Datei ungültig ist.

Wenn Sie ein in einem arabischen Betriebssystem erstelltes Ablaufverfolgungsprotokoll öffnen, stellen Sie unter Umständen fest, dass der Zeitfilter nicht funktioniert. Zum Beispiel entspricht das Jahr 2005 dem Jahr 1427 im arabischen Kalender. Der Filter des Service Trace Viewer-Tools unterstützt jedoch keine Jahresangabe vor 1752. Dies kann dazu führen, dass Sie kein korrektes Datum im Filter auswählen können. Um dieses Problem zu beheben, können Sie einen benutzerdefinierten Filter (**Ansicht/benutzerdefinierte Filter**) erstellen, indem Sie einen XPath-Ausdruck verwenden, um einen bestimmten Zeitbereich einzubeziehen.

## <a name="see-also"></a>Weitere Informationen

- [Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung](./diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [Konfigurieren der Ablaufverfolgung](./diagnostics/tracing/configuring-tracing.md)
- [End-to-End-Ablaufverfolgung](./diagnostics/tracing/end-to-end-tracing.md)
