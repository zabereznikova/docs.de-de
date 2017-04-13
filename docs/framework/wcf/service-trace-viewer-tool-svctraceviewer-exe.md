---
title: "Service Trace Viewer-Tool (SvcTraceViewer.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 9027efd3-df8d-47ed-8bcd-f53d55ed803c
caps.latest.revision: 55
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 55
---
# Service Trace Viewer-Tool (SvcTraceViewer.exe)
Das [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Service Trace Viewer\-Tool hilft Ihnen beim Analysieren von Diagnoseablaufverfolgungen, die von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] generiert werden.Service Trace Viewer ermöglicht das einfache Zusammenführen, Anzeigen und Filtern von Ablaufverfolgungsnachrichten im Protokoll, sodass Sie [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienstprobleme diagnostizieren, beheben und überprüfen können.  
  
## Konfigurieren der Ablaufverfolgung  
 Diagnoseablaufverfolgungen stellen Informationen bereit, die Aufschluss darüber geben, was beim Ausführen der Vorgänge in der Anwendung geschieht.Wie der Name bereits andeutet, können Sie Vorgänge von der Quelle zum Ziel und durch Zwischenpunkte hindurch verfolgen.  
  
 Sie können die Ablaufverfolgung mithilfe der Konfigurationsdatei der Anwendung konfigurieren: entweder mit "Web.config" für im webgehostete Anwendungen oder mit "*Appname*.config" für selbst gehostete Anwendungen.Im Folgenden finden Sie ein Beispiel:  
  
```  
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
  
 In diesem Beispiel werden Name und Typ des Ablaufverfolgungslisteners angegeben.Der Name des Listeners ist `sdt`, und der standardmäßige .NET Framework\-Ablaufverfolgungslistener \(System.Diagnostics.XmlWriterTraceListener\) wird als Typ hinzugefügt.Das `initializeData`\-Attribut wird verwendet, um den Namen der Protokolldatei für diesen Listener auf `SdrConfigExample.e2e` festzulegen.Für die Protokolldatei können Sie einen einfachen Dateinamen durch einen vollqualifizierten Pfad ersetzen.  
  
 Mit dem Beispiel wird eine Datei namens "SdrConfigExample.e2e" im Stammverzeichnis erstellt.Wenn Sie den Ablaufverfolgungs\-Viewer verwenden, um die Datei wie im Abschnitt "Öffnen und Anzeigen von WCF\-Ablaufverfolgungsdateien" beschrieben zu öffnen, können Sie alle gesendeten Nachrichten sehen.  
  
 Die Ablaufverfolgungsebene wird von der `switchValue`\-Einstellung gesteuert.Die verfügbaren Ablaufverfolgungsebenen werden in der folgenden Tabelle beschrieben.  
  
|Ablaufverfolgungsebene|Beschreibung|  
|----------------------------|------------------|  
|Critical|-   Protokolliert Failfast\- und Ereignisprotokolleinträge und Korrelationsinformationen für die Ablaufverfolgung.Im Folgenden finden Sie einige Beispiele für die Verwendung der Critical\-Ebene:<br />-   Die AppDomain ist wegen einer nicht behandelten Ausnahme abgestürzt.<br />-   Die Anwendung kann nicht gestartet werden.<br />-   Die Nachricht, die den Fehler verursacht hat, stammt vom MyApp.exe\-Prozess.|  
|Error|-   Protokolliert alle Ausnahmen.Sie können die Error\-Ebene in den folgenden Situationen verwenden:<br />-   Der Code ist wegen einer ungültigen Umwandlung abgestürzt.<br />-   Eine Ausnahme wegen eines Fehlers bei der Endpunkterstellung bewirkt, dass die Anwendung beim Starten abstürzt.|  
|Warning|-   Eine Bedingung ist vorhanden, die möglicherweise zu einem Fehler oder einem kritischen Fehler führt.Sie können diese Ebene in folgenden Situationen verwenden:<br />-   Die Anwendung empfängt mehr Anforderungen, als die Einschränkungseinstellungen zulassen.<br />-   Die empfangende Warteschlange hat 98 Prozent der konfigurierten Kapazität erreicht.|  
|Information|-   Meldungen, die bei der Überwachung und Diagnose des Systemstatus, der Leistungsmessung oder Profilerstellung nützlich sind.Sie können solche Informationen zur Kapazitätsplanung und Leistungsverwaltung nutzen.Sie können diese Ebene in folgenden Situationen verwenden:<br />-   Ein Fehler ist aufgetreten, nachdem die Nachricht die AppDomain erreicht hat und deserialisiert wurde.<br />-   Ein Fehler ist aufgetreten, während die HTTP\-Bindung erstellt wurde.|  
|Verbose|-   Ablaufverfolgung auf Debugebene für sowohl Benutzercode als auch Dienste.Legen Sie diese Ebene in folgenden Fällen fest:<br />-   Sie sind nicht sicher, welche Methode im Code aufgerufen wurde, als der Fehler auftrat.<br />-   Sie haben einen falschen Endpunkt konfiguriert, und der Dienst konnte nicht gestartet werden, da der Eintrag im Reservierungsspeicher gesperrt ist.|  
|ActivityTracing|Ablaufereignisse zwischen Verarbeitungsaktivitäten und Komponenten.<br /><br /> Diese Ebene ermöglicht es Administratoren und Entwicklern, Anwendungen in einer Anwendungsdomäne zu korrelieren.<br /><br /> -   Ablaufverfolgungen für Aktivitätsgrenzen: Start\/Stop.<br />-   Ablaufverfolgungen für Übertragungen.|  
  
 Mit `add` können Sie den Namen und den Typ des Ablaufverfolgungslisteners angeben, den Sie verwenden möchten.In der Beispielkonfiguration wird der Listener `sdt` genannt und der standardmäßige .NET Framework\-Ablaufverfolgungslistener \(`System.Diagnostics.XmlWriterTraceListener`\) wird als Typ hinzugefügt.Verwenden Sie `initializeData`, um den Namen der Protokolldatei für diesen Listener festzulegen.Außerdem können Sie einen einfachen Dateinamen durch einen vollqualifizierten Pfad ersetzen.  
  
## Verwenden des Service Trace Viewer\-Tools  
  
### Öffnen und Anzeigen von WCF\-Ablaufverfolgungsdateien  
 Service Trace Viewer unterstützt drei Dateitypen:  
  
-   [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Ablaufverfolgungsdatei \(.svcLog\)  
  
-   Ereignisablaufverfolgungs\-Datei \(.etl\)  
  
-   Crimson\-Ablaufverfolgungsdatei  
  
 Mit Service Trace Viewer können Sie jede unterstützte Ablaufverfolgungsdatei öffnen, weitere Ablaufverfolgungsdateien hinzufügen und integrieren oder eine Gruppe von Ablaufverfolgungsdateien gleichzeitig öffnen und zusammenführen.  
  
##### So öffnen Sie eine Ablaufverfolgungsdatei  
  
1.  Starten Sie Service Trace Viewer, indem Sie im Befehlsfenster zum [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Installationsspeicherort \(C:\\Programme\\Microsoft SDKs\\Windows\\v6.0\\Bin\) wechseln und `SvcTraceViewer.exe` eingeben.  
  
> [!NOTE]
>  Das Service Trace Viewer\-Tool kann zwei Dateitypen zuweisen: .svclog und .stvproj.Sie können zwei Parameter in der Befehlszeile verwenden, um die Dateierweiterungen zu registrieren und deren Registrierung aufzuheben.  
>   
>  \/register: Registriert die Zuweisung der Dateierweiterungen ".svclog" und ".stvproj" in SvcTraceViewer.exe.  
>   
>  \/unregister: Hebt die Registrierung der zugewiesenen Dateierweiterungen ".svclog" und ".stvproj" in SvcTraceViewer.exe auf.  
  
1.  Klicken Sie beim Starten von Service Trace Viewer auf **Datei**, und zeigen Sie auf **Öffnen**.Navigieren Sie zu dem Speicherort, an dem die Ablaufverfolgungsdateien gespeichert sind.  
  
2.  Doppelklicken Sie auf die Ablaufverfolgungsdatei, die Sie öffnen möchten.  
  
    > [!NOTE]
    >  Halten Sie die UMSCHALTTASTE gedrückt, während Sie auf mehrere Ablaufverfolgungsdateien klicken, um sie gleichzeitig auszuwählen und zu öffnen.Service Trace Viewer führt den Inhalt aller Dateien zusammen und zeigt ihn in einer Ansicht an.Sie können zum Beispiel gleichzeitig Ablaufverfolgungsdateien von Client und Dienst öffnen.Dies ist nützlich, wenn Sie die Nachrichtenprotokollierung und Aktivitätspropagierung in der Konfiguration aktiviert haben.Auf diese Weise können Sie den Nachrichtenaustausch zwischen Client und Dienst untersuchen.Sie können auch mehrere Dateien in den Viewer ziehen oder die Registerkarte **Projekt** verwenden.Weitere Informationen finden Sie im Abschnitt über das Verwalten des Projekts.  
  
3.  Klicken Sie zum Hinzufügen weiterer Ablaufverfolgungsdateien zur geöffneten Auflistung auf **Datei**, und zeigen Sie auf **Hinzufügen**.Navigieren Sie in dem geöffneten Fenster zum Speicherort der Ablaufverfolgungsdateien, und doppelklicken Sie auf die Datei, die Sie hinzufügen möchten.  
  
> [!CAUTION]
>  Es ist nicht empfehlenswert, eine Ablaufverfolgungsprotokolldatei zu laden, die größer als 200 MB ist.Wenn Sie eine Datei laden, die diesen Wert überschreitet, nimmt der Ladeprozess je nach Computerressourcen unter Umständen viel Zeit in Anspruch.Das Service Trace Viewer\-Tool reagiert unter Umständen über einen längeren Zeitraum nicht oder belegt den gesamten Speicher des Computers.Es wird empfohlen, dass Sie das teilweise Laden konfigurieren, um dies zu vermeiden.Weitere Informationen dazu finden Sie im Abschnitt "Laden von großen Ablaufverfolgungsdateien".  
  
#### Ereignisablaufverfolgung und Crimson\-Ablaufverfolgung  
 Das systemeigene Format des Viewers ist das Aktivitätsablaufverfolgungs\-Format, das von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] ausgegeben wird.In einem anderen Format ausgegebene Ablaufverfolgungen müssen konvertiert werden, bevor der Viewer sie anzeigen kann.Zurzeit unterstützt der Viewer zusätzlich zum Aktivitätsablaufverfolgungs\-Format die Ereignisablaufverfolgung und Crimson\-Ablaufverfolgung.  
  
 Wenn Sie eine Datei öffnen, die keine Aktivitätsablaufverfolgungen enthält, versucht der Viewer, die Datei zu konvertieren.Sie müssen den Namen und den Speicherort der Datei angeben, die die zu konvertierenden Ablaufverfolgungsdaten enthält.Nachdem die Daten konvertiert wurden, zeigt der Viewer den Inhalt der neuen Datei an.  
  
> [!NOTE]
>  Konvertierung erfordert Speicherplatz zum Speichern der konvertierten Ablaufverfolgungsdaten.Stellen Sie sicher, dass ausreichender Speicherplatz zum Speichern der Daten vorhanden ist, bevor Sie eine Konvertierung starten.Andernfalls schlägt die Konvertierung fehl.  
  
### Verwalten von Projekten  
 Der Viewer unterstützt Projekte, um die Anzeige mehrerer Ablaufverfolgungsdateien zu vereinfachen.Wenn Sie zum Beispiel über eine Client\- und eine Dienst\-Ablaufverfolgungsdatei verfügen, können Sie diese einem Projekt hinzufügen.Auf diese Weise werden jedes Mal, wenn Sie das Projekt öffnen, alle Ablaufverfolgungsdateien im Projekt gleichzeitig geladen.  
  
 Es gibt zwei Möglichkeiten zum Verwalten von Projekten:  
  
-   Im Menü **Datei** können Sie Projekte öffnen, speichern und schließen.  
  
-   Auf der Registerkarte **Projekt** können Sie einem Projekt Dateien hinzufügen.  
  
### Anzeigen von WCF\-Ablaufverfolgungen  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] gibt Ablaufverfolgungen im Aktivitätsablaufverfolgungs\-Format aus.Im Aktivitätsablaufverfolgungs\-Modell werden einzelne Ablaufverfolgungen nach ihrem jeweiligen Zweck in Aktivitäten gruppiert.Zwischen den Aktivitäten wird eine logische Ablaufsteuerung übertragen.Zum Beispiel werden während der Lebensdaueraktivität einer Anwendung zahlreiche Nachrichtensendeaktivitäten angezeigt und wieder entfernt.Weitere Informationen zum Anzeigen von Ablaufverfolgungen und Aktivitäten und zur Benutzeroberfläche von Service Trace Viewer finden Sie unter [Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung](../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
#### Umschalten zu anderen Ansichten  
 Der Service Trace Viewer umfasst die folgenden Ansichten.Sie werden als Registerkarten im linken Bereich des Viewers angezeigt und können auch über das Menü **Ansicht** aufgerufen werden.  
  
-   Aktivitätsansicht  
  
-   Projektansicht  
  
-   Nachrichtenansicht  
  
-   Diagrammansicht  
  
##### Aktivitätsansicht  
 Nachdem die Ablaufverfolgungsdateien geöffnet wurden, werden die Ablaufverfolgungen in Aktivitäten gruppiert im linken Fensterbereich in der **Aktivitätsansicht** angezeigt.  
  
 In der **Aktivitätsansicht** werden Aktivitätsnamen, die Anzahl der Ablaufverfolgungen in der Aktivität, die Dauer und die Anfangs\- sowie Endzeit angezeigt.  
  
 Indem Sie auf eine der aufgeführten Aktivitäten klicken, werden die Ablaufverfolgungen in dieser Aktivität rechts im Ablaufverfolgungsfenster angezeigt.Sie können dann eine Ablaufverfolgung auswählen, um die Details anzuzeigen.  
  
 Sie können mehrere Aktivitäten auswählen, indem Sie die **STRG**\-Taste oder **UMSCHALTTASTE** gedrückt halten und dann auf die gewünschten Aktivitäten klicken.Im Ablaufverfolgungsbereich werden alle Ablaufverfolgungen der ausgewählten Aktivitäten angezeigt.  
  
 Sie können auf eine Aktivität doppelklicken, um sie in der **Diagrammansicht** anzuzeigen.Sie können auch eine Aktivität auswählen und zur **Diagrammansicht** wechseln.  
  
> [!NOTE]
>  Die Aktivität "000000000000" ist eine spezielle Aktivität, die nicht in der Diagrammansicht angezeigt werden kann.Da alle anderen Aktivitäten damit verknüpft sind, hat das Anzeigen dieser Aktivität schwerwiegende Auswirkungen auf die Leistung.  
  
 Sie können auf den Spaltentitel klicken, um die Aktivitätsliste zu sortieren.Aktivitäten mit Warnungsablaufverfolgungen weisen einen gelben Hintergrund auf und Aktivitäten mit Fehlerablaufverfolgungen einen roten Hintergrund.  
  
 Es gibt verschiedene Typen von Aktivitäten, und jeder Typ verfügt über ein entsprechendes Symbol links neben der jeweiligen Aktivität.Informationen zur Bedeutung der Symbole finden Sie im Abschnitt zu Ablaufverfolgungssymbolen.  
  
##### Projektansicht  
 Diese Ansicht ermöglicht Ihnen, Ablaufverfolgungsdateien im aktuellen Projekt zu verwalten.Weitere Informationen finden Sie im Abschnitt über das Verwalten des Projekts.  
  
##### Diagrammansicht  
 Eines der leistungsstärksten Features von Service Trace Viewer ist die **Diagrammansicht**, in der die Ablaufverfolgungsdaten einer bestimmten Aktivität als Diagramm angezeigt werden.Im Diagramm können Sie die schrittweise Ausführung von Ereignissen und die Wechselbeziehungen zwischen mehreren Aktivitäten nachvollziehen, während die Daten diese durchlaufen.  
  
 Um zur **Diagrammansicht** zu wechseln, wählen Sie in der **Aktivitätsansicht** eine Aktivität aus und klicken auf die Registerkarte **Aktivität**, oder Sie klicken auf eine Nachrichtenprotokoll\-Ablaufverfolgung in der **Nachrichtenansicht**.Wenn mehrere Ablaufverfolgungsdateien geladen sind und die Aktivität Ablaufverfolgungen aus mehr als einer Datei umfasst, werden alle relevanten Ablaufverfolgungen in der Diagrammansicht angezeigt.Die **Diagrammansicht** wird auch angezeigt, wenn Sie auf die Aktivitäten und Nachrichtenprotokoll\-Ablaufverfolgungen doppelklicken.  
  
 In der **Diagrammansicht** stellt jede vertikale Spalte eine Aktivität und jeder Block in der Spalte eine Ablaufverfolgung dar.Die Aktivitäten werden nach Prozess \(oder Thread\) gruppiert.Die kleinen Pfeile zwischen Aktivitäten stellen Übertragungen dar.Die großen Pfeile zwischen Prozessen stellen Nachrichtenaustausch dar.Die ausgewählte Aktivität wird stets gelb angezeigt.  
  
###### Auswählen von Ablaufverfolgungen im Diagramm  
  
1.  Klicken Sie auf einen Block im Diagramm.  
  
2.  Wählen Sie mit den Nach\-oben\- und Nach\-unten\-Pfeilen die benachbarten Ablaufverfolgungen aus.  
  
3.  Achten Sie auf die Ablaufverfolgungsinformationen im Ablaufverfolgungsbereich und Detailbereich.  
  
###### Erweitern oder Reduzieren von Aktivitätsübertragungen  
 Sie können Aktivitätsübertragungen erweitern, wenn die ausgewählte Aktivität an eine andere Aktivität übertragen wird.Sie können auf diese Weise die Übertragungen verfolgen.  
  
 So erweitern oder reduzieren Sie Aktivitätsübertragungen  
  
1.  Suchen Sie die Übertragungsablaufverfolgung mit dem Pluszeichen \("\+"\) links neben dem Übertragungssymbol.  
  
2.  Klicken Sie auf das "\+", oder drücken Sie **STRG** und "\+" auf der Tastatur.  
  
3.  Die nächste Aktivität wird im Diagramm angezeigt.  
  
4.  Ein Minuszeichen \("\-"\) erscheint links neben dem Übertragungssymbol.Klicken Sie auf das "\-", oder drücken Sie STRG und "\-". Die Aktivitätsübertragung wird reduziert.  
  
> [!NOTE]
>  Wenn eine Aktivität über mehrere Übertragungen verfügt und Sie eine der Übertragungen erweitern, werden Aktivitäten angezeigt, die von der Stammaktivität zu der neuen Aktivität führen.Diese neuen Aktivitäten werden reduziert angezeigt.Wenn Sie die Details dieser Aktivitäten anzeigen möchten, erweitern Sie sie vertikal, indem Sie auf das Erweiterungssymbol in der Kopfzeile des Diagramms klicken.  
  
###### Vertikales Erweitern oder Reduzieren von Aktivitäten  
 Der Viewer blendet unnötige Details im Aktivitätsdiagramm aus, indem er Aktivitäten reduziert.In einer reduzierten Aktivität werden einzelne Ablaufverfolgungen nicht angezeigt.Nur Ablaufverfolgungsübertragungen werden angezeigt.Wenn alle Ablaufverfolgungen in einer Aktivität angezeigt werden sollen, erweitern Sie die Aktivität vertikal, indem Sie auf das Erweiterungssymbol der Aktivität in der Kopfzeile des Diagramms klicken.  
  
 So erweitern oder reduzieren Sie Aktivitäten vertikal  
  
1.  Klicken Sie auf das Pluszeichen \("\+"\) in der Kopfzeile der Aktivität, um die Aktivität vertikal zu erweitern.  
  
2.  Beachten Sie, dass alle Ablaufverfolgungen im Diagramm angezeigt werden.  
  
3.  Klicken Sie auf das Minuszeichen \("\-"\) in der Kopfzeile der Aktivität, um die Aktivität vertikal zu reduzieren.  
  
4.  Beachten Sie, dass nur wichtige Übertragungen, Nachrichtenprotokolle, Warnungs\- und Ausnahmeablaufverfolgungen in der Aktivität angezeigt werden.  
  
###### Optionen  
 Sie können zwei Optionen im Menü **Option** in der Diagrammansicht auswählen.  
  
-   Ablaufverfolgungen für Aktivitätsgrenzen anzeigen: Wenn diese Option nicht aktiviert ist, werden die Ablaufverfolgungen für Aktivitätsgrenzen im Diagramm ignoriert.  
  
-   Ausführliche Ablaufverfolgungen ohne Nachrichten anzeigen: Wenn diese Option deaktiviert ist, werden ausführliche Ebenenablaufverfolgungen, außer Nachrichtenablaufverfolgungen, ignoriert.In den meisten Fällen sind ausführliche Ebenenablaufverfolgungen für die Analyse weniger wichtig.Diese Option ist nützlich, wenn Sie ausführliche Ebenenablaufverfolgungen nicht analysieren möchten, sondern sich auf wichtigere Ablaufverfolgungen konzentrieren möchten.  
  
###### Layoutmodus  
 Der Viewer hat zwei Layoutmodi: **Prozess** und **Thread**.Diese Einstellung definiert die größte Organisationseinheit.Der Standardlayoutmodus ist **Prozess**. Dabei werden Aktivitäten im Diagramm nach Prozessen gruppiert.  
  
###### Ausführungsliste  
 Sie können in dieser Dropdownliste auswählen, welcher Prozess oder Thread im Diagramm angezeigt werden soll.Wenn zum Beispiel Ablaufverfolgungsdateien von zwei Clients \(A und B\) sowie ein Dienst geöffnet sind und Sie nur den Dienst und Client A im Diagramm anzeigen möchten, können Sie die Auswahl von Client B aufheben.  
  
#### Anzeigen von Ablaufverfolgungsdetails  
 Um Ablaufverfolgungsdetails anzuzeigen, wählen Sie eine Ablaufverfolgung im Ablaufverfolgungsbereich aus.Die Details werden im Detailbereich angezeigt.  
  
##### Ablaufverfolgungsbereich  
 Der rechte obere Bereich im Service Trace Viewer ist der Ablaufverfolgungsbereich.In diesem Bereich werden alle Ablaufverfolgungen in der ausgewählten Aktivität mit zusätzlichen Informationen aufgeführt, beispielsweise Ablaufverfolgungsebene, Thread\-ID und Prozessname.  
  
 Sie können die unformatierten XML\-Daten der Ablaufverfolgung in die Zwischenablage kopieren, indem Sie mit der rechten Maustaste auf eine Ablaufverfolgung klicken und **Ablaufverfolgung in Zwischenablage kopieren** wählen.  
  
##### Detailbereich  
 Der unterste linke Bereich im Service Trace Viewer ist der Detailbereich.Er stellt drei Registerkarten zum Anzeigen von Ablaufverfolgungsdetails bereit.  
  
 Die Ansicht **Formatiert** zeigt die Informationen organisiert an.Es werden alle bekannten XML\-Elemente in Tabellen und Strukturen aufgelistet, sodass die Informationen einfacher zu lesen und zu interpretieren sind.  
  
 Die Ansicht **XML** zeigt XML\-Code an, der der ausgewählten Ablaufverfolgung entspricht.Hervorhebung und Syntaxfarbe werden unterstützt.Wenn Sie mit **Suchen** nach Zeichenfolgen suchen, werden die Suchergebnisse markiert.  
  
 Die **Nachrichtenansicht** zeigt den Nachrichtenteil des XML\-Codes in Nachrichtenprotokoll\-Ablaufverfolgungen an.Er ist nicht sichtbar, wenn Sie eine Ablaufverfolgung ohne Nachrichten auswählen.  
  
### Filtern von WCF\-Ablaufverfolgungen  
 Um die Analyse von Ablaufverfolgungsdateien zu vereinfachen, können Sie sie auf folgende Weisen filtern:  
  
-   Die Filtersymbolleiste ermöglicht den Zugriff auf vordefinierte und benutzerdefinierte Filter.Sie kann durch das Menü **Ansicht** aktiviert werden.  
  
-   Der vordefinierte Filter des Viewers kann verwendet werden, um Teile von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Ablaufverfolgungen selektiv zu filtern.Standardmäßig ist der Filter so eingestellt, dass alle Infrastrukturablaufverfolgungen zugelassen werden.Die Einstellungen dieses Filters werden im Menü **Ansicht** unter **Filteroptionen** definiert.  
  
-   Benutzerdefinierte XPath\-Filter ermöglichen Benutzern den Vollzugriff auf die Filterung.Sie können unter **Benutzerdefinierter Filter** im Menü **Ansicht** definiert werden.  
  
 Es werden nur die Ablaufverfolgungen angezeigt, die alle Filter durchlaufen haben.  
  
#### Verwenden der Filtersymbolleiste  
 Die Filtersymbolleiste wird im oberen Bereich des Tools angezeigt.Wenn sie nicht angezeigt wird, können Sie sie über das Menü **Ansicht** aktivieren.Die Leiste verfügt über drei Komponenten:  
  
-   Suchen nach: **Suchen nach** definiert das Objekt, nach dem bei dem Filtervorgang gesucht werden soll.Wenn Sie zum Beispiel alle Ablaufverfolgungen suchen möchten, die im Zusammenhang mit Prozess X ausgegeben wurden, legen Sie für dieses Feld X fest und geben im Feld **Suchen in** 'Prozessname' ein.Dieses Feld ändert sich in ein DateTime\-Auswahlsteuerelement, wenn ein zeitbasierter Filter ausgewählt wird.  
  
-   Suchen in: Dieses Feld definiert den Typ des anzuwendenden Filters.  
  
-   Ebene: Die Ebeneneinstellung definiert die minimale vom Filter zugelassene Ablaufverfolgungsebene.So werden bei Auswahl der Error\-Ebene oder höher nur die Ablaufverfolgungen auf Fehlerebene oder einer höheren Ebene angezeigt.Dieser Filter wird mit den unter Suchen nach und Suchen in angegebenen Kriterien kombiniert.  
  
 Mit der Schaltfläche **Jetzt filtern** wird der Filtervorgang gestartet.Die Ausführung einiger Filter kann sehr lange dauern, insbesondere dann, wenn sie auf einen umfangreichen Datensatz angewendet werden.Sie können den Filtervorgang beenden, indem Sie auf die Schaltfläche **Beenden** klicken, die in der Statusleiste unter dem Menü **Vorgänge** angezeigt wird.  
  
 Die Schaltfläche **Löschen** setzt alle vordefinierten und benutzerdefinierten Filter zurück, damit alle Ablaufverfolgungen aktiviert werden.  
  
#### Filteroptionen  
 Der Viewer kann [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Ablaufverfolgungen automatisch aus der Ansicht entfernen.Ablaufverfolgungen, die von bestimmten Bereichen von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] ausgegeben wurden, können selektiv aus der Ansicht entfernt werden, zum Beispiel transaktionsbezogene Ablaufverfolgungen.  
  
 Die Einstellungen dieses Filters werden im Menü **Ansicht** unter **Filteroptionen** definiert.  
  
#### Benutzerdefinierte Filter  
 Wenn Sie mit der XML Path\-Programmiersprache \(XPath\) vertraut sind, können Sie eigene benutzerdefinierte Filter zum Suchen nach Ablaufverfolgungsdaten für ein bestimmtes XML\-Element erstellen.Sie können über die Filtersymbolleiste auf die Filter zugreifen.  
  
 Benutzerdefinierte Filter können Parameter einschließen.Sie können auch bereits vorhandene benutzerdefinierte Filter importieren.  
  
##### Erstellen eines benutzerdefinierten Filters  
 Es gibt zwei Möglichkeiten zum Erstellen von Filtern:  
  
###### Erstellen eines benutzerdefinierten Filters mit dem Vorlagen\-Assistenten  
 Sie können auf eine vorhandene Ablaufverfolgung klicken und auf Grundlage der Struktur der Ablaufverfolgung einen Filter erstellen.In diesem Beispiel wird ein benutzerdefinierter Filter auf Grundlage der Thread\-ID erstellt.  
  
1.  Wählen Sie im Ablaufverfolgungsbereich oben rechts im Viewer eine Ablaufverfolgung aus, die ein Element enthält, nach dem Sie filtern möchten.  
  
2.  Klicken Sie oben im Ablaufverfolgungsbereich auf die Schaltfläche **Benutzerdefinierten Filter erstellen**.  
  
3.  Geben Sie im angezeigten Dialogfeld einen Namen für den Filter ein.Geben Sie in diesem Beispiel `Thread-ID` ein.Sie können auch eine Beschreibung des Filters eingeben.  
  
4.  In der Strukturansicht links wird die Struktur des Ablaufverfolgungsdatensatzes angezeigt, den Sie in Schritt 1 ausgewählt haben.Wechseln Sie zu dem Element, für das Sie eine Bedingung erstellen möchten.Wechseln Sie in diesem Beispiel zu der ThreadID, die sich im Knoten XPath: \/E2ETraceEvent\/System\/Execution\/@ThreadID befindet.Doppelklicken Sie auf das ThreadID\-Attribut in der Strukturansicht.Hierdurch wird rechts im Dialogfeld ein Ausdruck für das Attribut erstellt.  
  
5.  Ändern Sie das Parameterfeld für die ThreadID\-Bedingung von Keine in '{0}'.Dieser Schritt aktiviert den ThreadID\-Wert, der beim Anwenden des Filters konfiguriert werden soll.\(Siehe den Abschnitt zum Anwenden eines Filters.\) Sie können bis zu vier Parameter definieren.Bedingungen werden mit dem OR\-Operator kombiniert.  
  
6.  Klicken Sie auf **OK**, um den Filter zu erstellen.  
  
> [!NOTE]
>  Sobald ein Filter mit dem Vorlagen\-Assistenten erstellt wurde, kann er nur manuell bearbeitet werden.Es ist nicht möglich, den Assistenten für einen Filter zu aktivieren, der bereits erstellt wurde.Darüber hinaus werden die Bedingungen eines XPath\-Filters, der mit dem Vorlagen\-Assistenten erstellt wurde, mit dem OR\-Operator kombiniert.Wenn ein AND\-Vorgang benötigt wird, können Sie den Filterausdruck bearbeiten, nachdem er erstellt wurde.  
  
###### Manuelles Erstellen eines benutzerdefinierten Filters  
 Das Menü Benutzerdefinierte Filter ermöglicht Ihnen, XPath\-Filter manuell einzugeben.  
  
1.  Klicken Sie im Menü Ansicht auf **Benutzerdefinierte Filter**.  
  
2.  Klicken Sie im angezeigten Dialogfeld auf **Neu**.  
  
3.  Geben Sie mindestens einen Filternamen und einen XPath\-Ausdruck an.  
  
4.  Klicken Sie auf **OK**.  
  
###### Anwenden eines benutzerdefinierten Filters  
 Sobald ein benutzerdefinierter Filter erstellt wurde, kann er über die Filtersymbolleiste aufgerufen werden.Wählen Sie auf der Filtersymbolleiste im Feld **Suchen in** den Filter aus, den Sie anwenden möchten.Wählen Sie für das vorherige Beispiel 'Thread\-ID' aus.  
  
1.  Geben Sie den zu suchenden Wert im Feld **Suchen nach** ein.Geben Sie in diesem Beispiel die ID des Threads ein, nach dem Sie suchen möchten.  
  
2.  Klicken Sie auf **Jetzt filtern**, und beachten Sie das Ergebnis des Vorgangs.  
  
 Wenn der Filter mehrere Parameter verwendet, geben Sie diese mit einem Komma als Trennzeichen in das Feld **Suchen nach** ein.Die folgende Zeichenfolge gibt zum Beispiel drei Parameter an: '1;findValue;text'.Der Viewer wendet '1' auf den {0}\-Parameter des Filters an.'findValue' und 'text' werden auf {1} bzw. {2} angewendet.  
  
###### Freigeben von benutzerdefinierten Filtern  
 Benutzerdefinierte Filter können für andere Sitzungen und andere Benutzer freigegeben werden.Sie können die Filter in eine Definitionsdatei exportieren, die Sie an einem anderen Speicherort importieren können.  
  
 So importieren Sie einen benutzerdefinierten Filter  
  
1.  Klicken Sie im Menü **Ansicht** auf **Benutzerdefinierte Filter**.  
  
2.  Klicken Sie im angezeigten Dialogfeld auf die Schaltfläche **Importieren**.  
  
3.  Navigieren Sie zur benutzerdefinierten Filterdatei \(.stvcf\), klicken Sie auf die Datei, und klicken Sie auf **Öffnen**.  
  
 So exportieren Sie einen benutzerdefinierten Filter  
  
1.  Klicken Sie im Ansichtsmenü auf **Benutzerdefinierte Filter**.  
  
2.  Wählen Sie im aufgerufenen Dialogfeld den Filter, den Sie exportieren möchten.  
  
3.  Klicken Sie auf die Schaltfläche **Exportieren**.  
  
4.  Geben Sie den Namen und den Speicherort der benutzerdefinierten Filterdefinitionsdatei \(.stvcf\) an, und klicken Sie auf **Speichern**.  
  
> [!NOTE]
>  Diese benutzerdefinierten Filter können nur von Service Trace Viewer importiert und exportiert werden.Sie können nicht von anderen Tools gelesen werden.  
  
### Suchen von Daten  
 Der Viewer bietet folgende Möglichkeiten zum Suchen von Daten:  
  
-   Die Symbolleiste Suchen bietet schnellen Zugriff auf die allgemeinen Suchoptionen.  
  
-   Das Dialogfeld Suchen stellt weitere Suchoptionen zur Verfügung.Sie können über das Menü **Bearbeiten** oder mit der Tastenkombination STRG\+F darauf zugreifen.  
  
 Die Symbolleiste Suchen wird am oberen Rand des Viewers angezeigt.Wenn sie nicht angezeigt wird, können Sie sie über das Menü **Ansicht** aktivieren.Die Leiste verfügt über zwei Komponenten:  
  
-   Suchen nach: Ermöglicht Ihnen, ein Stichwort für die Suche einzugeben.  
  
-   Suchen in: Ermöglicht Ihnen, den Suchbereich einzugeben.Sie können auswählen, ob in allen Aktivitäten oder nur in der aktuellen Aktivität gesucht werden soll.  
  
 Das Suchdialogfeld stellt zwei zusätzliche Optionen bereit:  
  
-   Ziel suchen:  
  
    -   Mit der Option "Nicht aufbereitete Protokolldaten" wird in allen unformatierten Daten nach dem Stichwort gesucht.  
  
    -   Mit den Optionen "In XML\-Text" und "In XML\-Attribut" wird nur in XML\-Elementen gesucht.  
  
    -   Mit der Option "Protokollierte Nachricht" wird nur in Nachrichten nach dem Stichwort gesucht.  
  
-   Stammaktivität ignorieren: Bei der Suche werden die Ablaufverfolgungen in der Aktivität "000000000000" ignoriert.Hierdurch wird die Leistung bei umfangreichen Ablaufverfolgungsdateien verbessert, wenn die Stammaktivität über Tausende von Ablaufverfolgungen verfügt, bei denen es sich zum Großteil um Übertragungen handelt.  
  
### Navigieren in Ablaufverfolgungen  
 Da Ablaufverfolgungen bei Laufzeit der Anwendung Schritt für Schritt aufgezeichnet werden, kann Sie das Navigieren in Ablaufverfolgungen beim Debuggen Ihrer Anwendung unterstützen.Service Trace Viewer bietet mehrere Möglichkeiten zum Navigieren in Ablaufverfolgungen.  
  
#### Schritt vorwärts oder zurück  
 Wenn Sie jede Ablaufverfolgung als Zeile im Programmcode betrachten, ist das Tätigen eines Schritts vorwärts vergleichbar mit einem Prozedurschritt in der integrierten Entwicklungsumgebung \(Integrated Development Environment, IDE\) von Visual Studio.Der Unterschied ist, dass Sie in der Ablaufverfolgung auch einen Schritt zurück gehen können.Einen Schritt vorwärts zu gehen bedeutet, zur nächsten Ablaufverfolgung in der Aktivität zu gehen.  
  
-   Schritt vorwärts: Verwenden Sie das Menü **Aktivität**, oder drücken Sie "F10".Sie können auch die Nach\-unten\-Pfeiltaste im Ablaufverfolgungsbereich verwenden.  
  
-   Schritt zurück: Verwenden Sie das Menü **Aktivität**, oder drücken Sie "F9".Sie können auch die Nach\-oben\-Pfeiltaste im Ablaufverfolgungsbereich verwenden.  
  
> [!NOTE]
>  Dies kann Sie zu einer Aktivität führen, die in einem anderen Prozess oder sogar auf einem anderen Computer abläuft, da [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Nachrichten computerübergreifende Aktivitäts\-IDs enthalten.  
  
#### Verfolgen von Übertragungen  
 Übertragungsablaufverfolgungen sind spezielle Ablaufverfolgungen in der Ablaufverfolgungsdatei.Eine Aktivität wird möglicherweise über eine Übertragungsablaufverfolgung an eine andere Aktivität übertragen.So kann zum Beispiel "Aktivität A" an "Aktivität B" übertragen werden.In diesem Fall liegt eine Übertragungsablaufverfolgung in der "Aktivität A" mit dem Namen "An: Aktivität" und dem Übertragungssymbol vor.Diese Übertragungsablaufverfolgung ist ein Link zwischen den beiden Ablaufverfolgungen.In "Aktivität B" kann außerdem eine Übertragungsablaufverfolgung am Ende der Aktivität für eine Übertragung zurück zur "Aktivität A" vorliegen.Dies ähnelt Funktionsaufrufen in Programmen: A ruft B, dann gibt B Werte an A zurück.  
  
 "Übertragung verfolgen" ist vergleichbar mit "Einzelschritt" in einem Debugger.Dabei wird die Übertragung von Aktivität A zu Aktivität B verfolgt.Andere Ablaufverfolgungen sind davon nicht betroffen.  
  
 Es gibt zwei Möglichkeiten, einer Übertragung zu folgen: mit der Maus oder der Tastatur:  
  
-   Mit der Maus: Doppelklicken Sie im Ablaufverfolgungsbereich auf die Übertragungsablaufverfolgung.  
  
-   Mit der Tastatur: Wählen Sie eine Übertragungsablaufverfolgung aus, und verwenden Sie "Übertragung verfolgen" im Menü **Aktivität**, oder drücken Sie "F11".  
  
> [!NOTE]
>  Wenn Aktivität A an Aktivität B übertragen wird, wartet Aktivität A in vielen Fällen, bis Aktivität B an Aktivität A zurückübertragen wurde.Dies bedeutet, dass für Aktivität A während des Zeitraums, in dem eine aktive Ablaufverfolgung für Aktivität B erfolgt, keine Ablaufverfolgung protokolliert wird.Es ist jedoch auch möglich, dass Aktivität A nicht wartet und mit dem Protokollieren von Ablaufverfolgungen fortfährt.Es ist auch möglich, dass Aktivität B nicht an Aktivität A zurückübertragen wird.In diesem Sinne unterscheiden sich Aktivitätsübertragungen weiterhin von Funktionsaufrufen.Aktivitätsübertragungen werden in der Diagrammansicht noch besser verdeutlicht.  
  
#### Zur nächsten oder zur vorherigen Übertragung wechseln  
 Wenn Sie die aktuelle Aktivität oder mehrere ausgewählte Aktivitäten analysieren, möchten Sie die Aktivitäten, an die die Übertragung stattfindet, möglicherweise schnell finden."Zur nächsten Übertragung springen" ermöglicht Ihnen, die nächste Übertragungsablaufverfolgung in der Aktivität zu suchen.Sobald Sie die Übertragungsablaufverfolgung gefunden haben, können Sie mit "Übertragung verfolgen" zur nächsten Aktivität übergehen.  
  
-   Zur nächsten Übertragung springen: Verwenden Sie das Menü **Aktivität**, oder drücken Sie die Tastenkombination "STRG\+F10".  
  
-   Zur vorherigen Übertragung wechseln: Verwenden Sie das Menü **Aktivität**, oder drücken Sie die Tastenkombination "STRG\+F9".  
  
#### Navigieren in der Diagrammansicht  
 Obwohl das Navigieren im Aktivitätsbereich und Ablaufverfolgungsbereich dem Debugging ähnlich ist, bietet die **Diagrammansicht** bessere Navigationsmöglichkeiten.Weitere Informationen über den Ansichtszustand finden Sie im Abschnitt "Diagrammansicht".  
  
### Laden von großen Ablaufverfolgungsdateien  
 Ablaufverfolgungsdateien können sehr groß sein.Wenn Sie zum Beispiel die Ablaufverfolgung auf ausführlicher Ebene aktivieren, kann die für eine Ausführung von wenigen Minuten erstellte Ablaufverfolgungsdatei leicht mehrere hundert Megabyte oder mehr umfassen, je nach Netzwerkgeschwindigkeit und Kommunikationsmuster.  
  
 Wenn Sie eine sehr große Ablaufverfolgungsdatei in Service Trace Viewer öffnen, kann sich dies negativ auf die Systemleistung auswirken.Die Ladegeschwindigkeit und die Antwortzeit nach dem Laden können langsam sein.Die tatsächliche Geschwindigkeit unterscheidet sich bisweilen, abhängig von der Hardwarekonfiguration.Bei den meisten PCs wirkt sich das Laden einer Ablaufverfolgungsdatei, die größer als 200 MB ist, deutlich auf die Leistung aus.Für Ablaufverfolgungsdateien, die größer als 1 GB sind, verwendet das Tool möglicherweise den gesamten verfügbaren Arbeitsspeicher oder reagiert für einen sehr langen Zeitraum nicht mehr.  
  
 Um das verlangsamte Laden und eine verzögerte Antwortzeit bei der Analyse von großen Ablaufverfolgungsdateien zu vermeiden, stellt Service Trace Viewer ein Feature mit der Bezeichnung "Teilweises Laden" zur Verfügung, mit dem jeweils nur kleine Teile der Ablaufverfolgung geladen werden.Sie verfügen zum Beispiel über eine Ablaufverfolgungsdatei mit mehr als 1 GB, die mehrere Tage lang auf dem Server läuft.Wenn einige Fehler aufgetreten sind und Sie die Ablaufverfolgung analysieren möchten, müssen Sie nicht die gesamte Ablaufverfolgungsdatei öffnen.Stattdessen können Sie die Ablaufverfolgungen eines bestimmten Zeitraums, in dem der Fehler möglicherweise aufgetreten ist, laden.Da der Umfang geringer ist, kann das Service Trace Viewer\-Tool die Datei schneller laden, und Sie können die Fehler anhand eines kleineren Datensatzes ermitteln.  
  
#### Aktivieren des teilweisen Ladens  
 Sie müssen das teilweise Laden nicht manuell aktivieren.Wenn die Gesamtgröße der Ablaufverfolgungsdatei\(en\), die Sie laden möchten, 40 MB überschreitet, zeigt Service Trace Viewer das Dialogfeld Teilweises Laden automatisch an, sodass Sie den Teil auswählen können, den Sie laden möchten.  
  
> [!NOTE]
>  Da Ablaufverfolgungen möglicherweise nicht gleich im Zeitraum verteilt sind, ist die Länge des im Dialogfeld Teilweises Laden angegebenen Zeitraums möglicherweise nicht proportional zur angezeigten Ladegröße.Die tatsächliche Ladegröße kann kleiner als die im Dialogfeld Teilweises Laden geschätzte Größe sein.  
  
#### Anpassen des teilweisen Ladens  
 Nachdem die Ablaufverfolgungsdatei teilweise geladen wurde, können Sie den geladenen Datensatz ändern.Passen Sie dazu die Symbolleiste für teilweises Laden oben im Viewer an.  
  
1.  Verschieben Sie die Symbolleiste mit der Maus, oder geben Sie die Anfangs\- und Endzeit ein.  
  
2.  Klicken Sie auf die Schaltfläche **Anpassen**.  
  
## Verstehen von Ablaufverfolgungssymbolen  
 Im Folgenden finden Sie eine Liste mit Symbolen, die in der **Aktivitätsansicht**, **Diagrammansicht** und im **Ablaufverfolgungsbereich** verschiedene Elemente darstellen.  
  
> [!NOTE]
>  Einige nicht kategorisierte Ablaufverfolgungen \(z. B. "eine Nachricht wird geschlossen"\) haben kein Symbol.  
  
### Aktivitätsablaufverfolgungs\-Symbole  
  
|Symbol|Beschreibung|  
|------------|------------------|  
|![Warnungsablaufverfolgung](../../../docs/framework/wcf/media/7457c4ed-8383-4ac7-bada-bcb27409da58.gif "7457c4ed\-8383\-4ac7\-bada\-bcb27409da58")|Warnungsablaufverfolgung: Eine Ablaufverfolgung, die auf der Warnebene ausgegeben wird.|  
|![Fehlerablaufverfolgung](../../../docs/framework/wcf/media/7d908807-4967-4f6d-9226-d52125db69ca.gif "7d908807\-4967\-4f6d\-9226\-d52125db69ca")|Fehlerablaufverfolgung: Eine Ablaufverfolgung, die auf der Fehlerebene ausgegeben wird.|  
|![Aktivitätsstart&#45;Ablaufverfolgung:](../../../docs/framework/wcf/media/8a728f91-5f80-4a95-afe8-0b6acd6e0317.gif "8a728f91\-5f80\-4a95\-afe8\-0b6acd6e0317")|Aktivitätsstart\-Ablaufverfolgung: Eine Ablaufverfolgung, die den Beginn einer Aktivität markiert.Sie enthält den Namen der Aktivität.Als Anwendungsentwickler sollten Sie eine Aktivitätsstart\-Ablaufverfolgung pro Aktivitäts\-ID und Prozess oder Thread definieren.<br /><br /> Wenn die Aktivitäts\-ID über die Ablaufverfolgungsquellen der Ablaufverfolgungskorrelation hinweg propagiert wird, können Sie mehrere Starts für dieselbe Aktivitäts\-ID sehen \(einen pro Ablaufverfolgungsquelle\).Die Start\-Ablaufverfolgung wird ausgegeben, wenn die Aktivitätsablaufverfolgung für die Ablaufverfolgungsquelle aktiviert ist.|  
|![Aktivitätsstopp&#45;Ablaufverfolgung](../../../docs/framework/wcf/media/a0493e95-653e-4af8-84a4-4d09a400bc31.gif "a0493e95\-653e\-4af8\-84a4\-4d09a400bc31")|Aktivitätsstopp\-Ablaufverfolgung: Eine Ablaufverfolgung, die das Ende einer Aktivität markiert..Sie enthält den Namen der Aktivität.Als Anwendungsentwickler sollten Sie eine Aktivitätsstopp\-Ablaufverfolgung pro Aktivitäts\-ID und Ablaufverfolgungsquelle definieren.Es werden keine Ablaufverfolgungen von einer bestimmten Ablaufverfolgungsquelle angezeigt, nachdem die Ablaufverfolgungsquelle einen Aktivitätsstopp ausgegeben hat, es sei denn, die Ablaufverfolgungszeit weist eine grobe Granularität auf.Ist das der Fall, überlappen sich zwei Ablaufverfolgungen mit der gleichen Zeit, einschließlich eines Stopps, möglicherweise bei der Anzeige.Wenn die Aktivitäts\-ID über die Ablaufverfolgungsquellen der Ablaufverfolgungskorrelation hinweg propagiert wird, können Sie mehrere Stopps für dieselbe Aktivitäts\-ID sehen \(einen pro Ablaufverfolgungsquelle\).Die Stoppablaufverfolgung wird ausgegeben, wenn die Aktivitätsablaufverfolgung für die Ablaufverfolgungsquelle aktiviert ist.|  
|![Aktivität anhalten&#45;Ablaufverfolgung](../../../docs/framework/wcf/media/6f7f4191-df2b-4592-8998-8379769e2d32.gif "6f7f4191\-df2b\-4592\-8998\-8379769e2d32")|Aktivität anhalten\-Ablaufverfolgung: Eine Ablaufverfolgung, die markiert, wann eine Aktivität angehalten wurde.Es werden erst Ablaufverfolgungen in einer angehaltenen Aktivität ausgegeben, wenn die Aktivität fortgesetzt wird.Eine angehaltene Aktivität gibt an, dass keine Verarbeitungen in dieser Aktivität im Bereich der Ablaufverfolgungsquelle stattfinden.Anhalten\/Fortsetzen\-Ablaufverfolgungen sind hilfreich für die Profilerstellung.Die Anhalten\-Ablaufverfolgung wird ausgegeben, wenn die Aktivitätsablaufverfolgung für die Ablaufverfolgungsquelle aktiviert ist.|  
|![Aktivität fortsetzen&#45;Ablaufverfolgung](../../../docs/framework/wcf/media/1060d9d2-c9c8-4e0a-9988-cdc2f7030f17.gif "1060d9d2\-c9c8\-4e0a\-9988\-cdc2f7030f17")|Aktivität fortsetzen\-Ablaufverfolgung: Eine Ablaufverfolgung, die die Zeit markiert, zu der eine Aktivität nach dem Anhalten wieder fortgesetzt wird.Ablaufverfolgungen können in dieser Aktivität möglicherweise erneut ausgegeben werden.Anhalten\/Fortsetzen\-Ablaufverfolgungen sind hilfreich für die Profilerstellung.Die Fortsetzen\-Ablaufverfolgung wird ausgegeben, wenn die Aktivitätsablaufverfolgung für die Ablaufverfolgungsquelle aktiviert ist.|  
|![Übertragung](../../../docs/framework/wcf/media/b2d9850e-f362-4ae5-bb8d-9f6f3ca036a5.gif "b2d9850e\-f362\-4ae5\-bb8d\-9f6f3ca036a5")|Übertragung: Eine Ablaufverfolgung, die ausgegeben wird, wenn eine logische Ablaufsteuerung von einer Aktivität auf eine andere übertragen wird.Die Aktivität, aus der die Übertragung stammt, kann unter Umständen parallel zur der Aktivität ausgeführt werden, an die die Übertragung stattfindet.Die Übertragen\-Ablaufverfolgung wird ausgegeben, wenn die Aktivitätsablaufverfolgung für die Ablaufverfolgungsquelle aktiviert ist.|  
|![Übertragung von](../../../docs/framework/wcf/media/1df215cb-b344-4f36-a20d-195999bda741.gif "1df215cb\-b344\-4f36\-a20d\-195999bda741")|Übertragung von: Eine Ablaufverfolgung, die eine Übertragung von einer anderen Aktivität zur aktuellen Aktivität definiert.|  
|![Übertragung an](../../../docs/framework/wcf/media/74255b6e-7c47-46ef-8e53-870c76b04c3f.gif "74255b6e\-7c47\-46ef\-8e53\-870c76b04c3f")|Übertragung an: Eine Ablaufverfolgung, die eine Übertragung der logischen Ablaufsteuerung von der aktuellen Aktivität auf eine andere definiert.|  
  
### WCF\-Ablaufverfolgungen  
  
|Symbol|Beschreibung|  
|------------|------------------|  
|![Nachrichtenprotokollierung&#45;Ablaufverfolgung](../../../docs/framework/wcf/media/7c66e994-2476-4260-a0db-98948b9af197.gif "7c66e994\-2476\-4260\-a0db\-98948b9af197")|Nachrichtenprotokollierung\-Ablaufverfolgung: Es wird eine Ablaufverfolgung ausgegeben, wenn eine [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Nachricht vom Nachrichtenprotokollierungsfeature protokolliert wird, sofern die `System.ServiceModel.MessageLogging`\-Ablaufverfolgungsquelle aktiviert ist.Durch Klicken auf diese Ablaufverfolgung wird die Nachricht angezeigt.Es gibt vier konfigurierbare Protokollierungspunkte für eine Nachricht: ServiceLevelSendRequest, TransportSend, TransportReceive und ServiceLevelReceiveRequest, die auch durch das `messageSource`\-Attribut in der Nachrichtenablaufverfolgung angegeben werden können.|  
|![Ablaufverfolgung für empfangene Meldung](../../../docs/framework/wcf/media/de4f586c-c5dd-41ec-b1c3-ac56b4dfa35c.gif "de4f586c\-c5dd\-41ec\-b1c3\-ac56b4dfa35c")|Nachricht empfangen\-Ablaufverfolgung: Es wird eine Ablaufverfolgung ausgegeben, wenn eine [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Nachricht empfangen wird, sofern die `System.ServiceModel`\-Ablaufverfolgungsquelle auf Information\- oder Verbose\-Ebene aktiviert ist.Diese Ablaufverfolgung ist wesentlich zum Anzeigen des Nachrichtenkorrelationspfeils in der **Diagrammansicht** der Aktivitäten.|  
|![Nachricht gesendet&#45;Ablaufverfolgung](../../../docs/framework/wcf/media/558943c4-17cf-4c12-9405-677e995ac387.gif "558943c4\-17cf\-4c12\-9405\-677e995ac387")|Nachricht gesendet\-Ablaufverfolgung: Es wird eine Ablaufverfolgung ausgegeben, wenn eine [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Nachricht gesendet wird, sofern die `System.ServiceModel`\-Ablaufverfolgungsquelle auf Information\- oder Verbose\-Ebene aktiviert ist.Diese Ablaufverfolgung ist wesentlich zum Anzeigen des Nachrichtenkorrelationspfeils in der **Diagrammansicht** der Aktivitäten.|  
  
### Aktivitäten  
  
|Symbol|Beschreibung|  
|------------|------------------|  
|![Aktivität](../../../docs/framework/wcf/media/wcfc-defaultactivityc.gif "wcfc\_defaultActivityc")|Aktivität: Gibt an, dass die aktuelle Aktivität eine generische Aktivität ist.|  
|![Stammaktivität](../../../docs/framework/wcf/media/5dc8e0eb-1c32-4076-8c66-594935beaee9.gif "5dc8e0eb\-1c32\-4076\-8c66\-594935beaee9")|Stammaktivität: Gibt die Stammaktivität eines Prozesses an.|  
  
### WCF\-Aktivitäten  
  
|Symbol|Beschreibung|  
|------------|------------------|  
|![Umgebungsaktivität](../../../docs/framework/wcf/media/29fa00ac-cf78-46e5-822d-56222fff61d1.gif "29fa00ac\-cf78\-46e5\-822d\-56222fff61d1")|Umgebungsaktivität: Eine Aktivität, die einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Host oder \-Client erstellt, öffnet oder schließt.Fehler, die während dieser Phasen aufgetreten sind, werden in dieser Aktivität angezeigt.|  
|![Listen&#45;Aktivität](../../../docs/framework/wcf/media/d7b135f6-ec7d-45d7-9913-037ab30e4c26.gif "d7b135f6\-ec7d\-45d7\-9913\-037ab30e4c26")|Abhöraktivität: Eine Aktivität, die mit einem Listener zusammenhängende Ablaufverfolgungen protokolliert.In dieser Aktivität werden Listenerinformationen und Verbindungsanforderungen angezeigt.|  
|![Bytes empfangen&#45;Aktivität](../../../docs/framework/wcf/media/2f628580-b80f-45a7-925b-616c96426c0e.gif "2f628580\-b80f\-45a7\-925b\-616c96426c0e")|Bytes empfangen\-Aktivität: Eine Aktivität, die alle Ablaufverfolgungen gruppiert, die sich auf empfangene Bytes in einer Verbindung zwischen zwei Endpunkten beziehen.Diese Aktivität ist wesentlich beim Korrelieren von Transportaktivitäten, die ihre Aktivitäts\-ID propagieren, wie z. B. http.sys.Verbindungsfehler, wie z. B. Abbrüche, treten in dieser Aktivität auf.|  
|![Meldungsverarbeitungsaktivität](../../../docs/framework/wcf/media/wcfc-executionactivityiconc.GIF "wcfc\_ExecutionActivityIconc")|Nachricht verarbeiten\-Aktivität: Eine Aktivität, die Ablaufverfolgungen gruppiert, die sich auf das Erstellen einer [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Nachricht beziehen.Fehler aufgrund eines ungültigen Umschlags oder einer falsch formatierten Nachricht werden in dieser Aktivität angezeigt.In dieser Aktivität können Nachrichtenheader geprüft werden, um zu ermitteln, ob eine Aktivitäts\-ID vom Aufrufer propagiert wurde.Wenn dies zutrifft, kann beim Übertragen an die Aktion verarbeiten\-Aktivität \(das nächste Symbol\) dieser Aktivität auch die propagierte Aktivitäts\-ID für die Korrelation zwischen dem Aufrufer und den Ablaufverfolgungen des Aufrufenden zugewiesen werden.|  
|![Nachrichtenprotokollierung&#45;Ablaufverfolgung](../../../docs/framework/wcf/media/7c66e994-2476-4260-a0db-98948b9af197.gif "7c66e994\-2476\-4260\-a0db\-98948b9af197")|Aktion verarbeiten\-Aktivität: Eine Aktivität, die alle Ablaufverfolgungen gruppiert, die mit einer [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Anforderung über zwei Endpunkte hinweg zusammenhängen.Wenn `propagateActivity` auf beiden Endpunkten in der Konfiguration auf `true` festgelegt ist, werden alle Ablaufverfolgungen für die direkte Korrelation in eine Aktivität zusammengeführt.Einige Aktivitäten enthalten Fehler, die bei der Transport\- oder Sicherheitsverarbeitung auftreten und sich bis hin zu Benutzercodegrenzen und zurück erstrecken \(sofern eine Antwort vorhanden ist\).|  
|![Meldungsverarbeitungsaktivität](../../../docs/framework/wcf/media/wcfc-executionactivityiconc.GIF "wcfc\_ExecutionActivityIconc")|Benutzercodeaktivität ausführen\-Aktivität: Eine Aktivität, die Benutzercode\-Ablaufverfolgungen zur Verarbeitung einer Anforderung gruppiert.|  
  
## Problembehandlung  
 Wenn Sie nicht über Berechtigungen zum Schreiben in die Registrierung verfügen, erhalten Sie die Fehlermeldung "Microsoft Service Trace Viewer wurde nicht im System registriert" bei Verwendung des "`svctraceviewer /register`"\-Befehls zum Registrieren des Tools.Ist dies der Fall, sollten Sie sich über ein Konto anmelden, das Schreibzugriff auf die Registrierung bietet.  
  
 Außerdem schreibt das Service Trace Viewer\-Tool einige Einstellungen \(z. B. benutzerdefinierte Filter und Filteroptionen\) in die SvcTraceViewer.exe.settings\-Datei im Assemblyordner.Wenn Sie keine Leseberechtigungen für die Datei haben, können Sie das Tool starten, aber die Einstellungen nicht laden.  
  
 Wenn Sie die Fehlermeldung "Unbekannter Fehler bei der Verarbeitung von mindestens einer Ablaufverfolgung" beim Öffnen der ETL\-Datei erhalten, bedeutet dies, dass das Format der ETL\-Datei ungültig ist.  
  
 Wenn Sie ein in einem arabischen Betriebssystem erstelltes Ablaufverfolgungsprotokoll öffnen, stellen Sie unter Umständen fest, dass der Zeitfilter nicht funktioniert.Zum Beispiel entspricht das Jahr 2005 dem Jahr 1427 im arabischen Kalender.Der Filter des Service Trace Viewer\-Tools unterstützt jedoch keine Jahresangabe vor 1752.Dies kann dazu führen, dass Sie kein korrektes Datum im Filter auswählen können.Um dieses Problem zu beheben, können Sie einen benutzerdefinierten Filter \(**Ansicht\/Benutzerdefinierte Filter**\) mithilfe eines XPath\-Ausdrucks erstellen, um einen bestimmten Zeitbereich abzudecken.  
  
## Siehe auch  
 [Verwenden von Service Trace Viewer zum Anzeigen korrelierender Ablaufverfolgungen und der Problembehandlung](../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)   
 [Konfigurieren der Ablaufverfolgung](../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)   
 [Activity Tracing and Propagation for End\-To\-End Trace Correlation](http://msdn.microsoft.com/de-de/2c11a905-64f8-47b5-bae5-a74fc666137e)