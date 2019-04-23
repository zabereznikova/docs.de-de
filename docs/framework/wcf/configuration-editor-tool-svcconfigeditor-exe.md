---
title: Configuration Editor-Tool (SvcConfigEditor.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files, creating
- configuration files
- Configuration file
- configuration file schema
ms.assetid: 2db21a57-5f64-426f-89df-fb0dc2d2def5
ms.openlocfilehash: e4b54026c71e18e4011661c5cad2ca95dfcb733e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979939"
---
# <a name="configuration-editor-tool-svcconfigeditorexe"></a>Configuration Editor-Tool (SvcConfigEditor.exe)
Der Service Configuration Editor (SvcConfigEditor.exe) der Windows Communication Foundation (WCF) ermöglicht Administratoren und Entwicklern, Konfigurationseinstellungen für WCF-Dienste anhand einer grafischen Benutzeroberfläche zu erstellen und zu bearbeiten. Mit diesem Tool können Sie die Einstellungen für Bindungen, Verhalten, Dienste und Diagnosen von WCF verwalten, ohne XML-Dateien direkt bearbeiten zu müssen.  
  
 Der Service Configuration Editor befindet sich im Ordner "C:\Programme\Microsoft SDKs\Windows\v6.0\Bin".  
  
## <a name="the-wcf-configuration-editor"></a>Der WCF-Configuration Editor  
 Der Service Configuration Editor umfasst einen Assistenten, der Sie durch den Prozess der Konfiguration eines WCF-Diensts oder -Clients führt. Es wird dringend geraten, den Assistenten und nicht den Editor zu verwenden.  
  
 Wenn Sie bereits über Konfigurationsdateien verfügen, die mit dem standardmäßigen System.Configuration-Schema konform sind, können Sie spezielle Einstellungen für Bindungen, Verhaltensweisen, Dienste und Diagnosen anhand der Benutzeroberfläche verwalten. Mit dem Service Configuration Editor können Sie die Einstellungen von vorhandenen WCF-Konfigurationsdateien sowie von ausführbaren Dateien, COM+-Diensten und im Internet gehosteten Diensten verwalten. Beim Öffnen eines im Internet gehosteten Diensts mit dem Service Configuration Editor werden sowohl die eigene Konfiguration des Diensts sowie die von Knoten der oberen Ebene übernommenen Konfigurationsabschnitte angezeigt.  
  
 Da sich die WCF-Konfigurationseinstellungen im `<system.serviceModel>`-Abschnitt der Konfigurationsdatei befinden, arbeitet der Editor nur mit dem Inhalt dieses Elements und greift auf keine anderen Elemente in dieser Datei zu. Sie können direkt zu vorhandenen Konfigurationsdateien wechseln, oder Sie können eine Assembly auswählen, die einen Dienst, ein virtuelles Verzeichnis oder einen COM+-Dienst enthält. Der Editor lädt die Konfigurationsdatei für diesen Dienst und ermöglicht dem Benutzer, neue Elemente hinzuzufügen oder vorhandene Elemente des `<system.serviceModel>`-Abschnitts der Konfigurationsdatei zu bearbeiten.  
  
 Der Editor unterstützt IntelliSense und erzwingt Schemakompatibilität. Die Ausgabe entspricht garantiert dem Schema der Konfigurationsdatei und weist syntaktisch korrekte Datenwerte auf. Der Editor garantiert jedoch nicht, dass die Konfigurationsdatei semantisch gültig ist. Mit anderen Worten: Der Editor garantiert nicht, dass die Konfigurationsdatei mit dem Dienst zusammenarbeiten kann, den sie konfiguriert.  
  
> [!CAUTION]
>  Der Editor kann kein Konfigurationselement aus der Konfigurationsdatei löschen, sobald das Element geändert wurde. Wenn Sie beispielsweise den Editor verwendet haben, um den Endpunktnamen auf eine nicht leere Zeichenfolge festzulegen, und diesen speichern, weist die Konfigurationsdatei folgenden Inhalt auf, wie im folgenden Beispiel gezeigt:  
>   
>  `<endpoint binding="basicHttpBinding" name="somename" />`  
>   
>  Wenn Sie versuchen, den Namen zu entfernen, indem Sie eine leere Zeichenfolge festlegen, und die Datei speichern, enthält die Konfigurationsdatei weiterhin das `name`-Attribut, wie im folgenden Beispiel gezeigt:  
>   
>  `<endpoint binding="basicHttpBinding" name="" />`  
>   
>  Um das Attribut zu löschen, müssen Sie das Element manuell mit einem anderen Text-Editor bearbeiten.  
>   
>  Sie sollten besonders vorsichtig vorgehen, wenn Sie das `issueToken`-Element des `clientCredential`-Endpunktverhaltens verwenden. Vor allem das `address`-Attribut des `localIssuer`-Unterelements darf keine leere Zeichenfolge sein. Wenn Sie das `address`-Attribut mit dem Configuration Editor geändert haben und es vollständig entfernen möchten, sollten Sie dies mit einem anderen Tool als dem Editor durchführen. Andernfalls enthält das Attribut eine leere Zeichenfolge, und die Anwendung löst eine Ausnahme aus.  
  
## <a name="using-the-configuration-editor"></a>Verwenden von Configuration Editor  
 Der Service Configuration Editor befindet sich in folgendem Windows SDK-Installationspfad:  
  
 C:\Programme\Microsoft SDKs\Windows\v6.0\Bin\SvcConfigEditor.exe  
  
 Nachdem Sie dem Service Configuration Editor starten, können Sie mithilfe der **Datei/öffnen** Menü zum Durchsuchen für den Dienst oder die Assembly, die Sie verwalten möchten. Sie können Konfigurationsdateien direkt öffnen, nach WCF-/COM+-Diensten suchen und Konfigurationsdateien für über das Web gehostete Dienste öffnen.  
  
 Die Service Configuration Editor-Benutzeroberfläche ist in die folgenden Bereiche aufgeteilt:  
  
-   Strukturansichtsbereich, in dem die Konfigurationselemente links in einer Struktur angezeigt werden. Sie können in der Struktur Vorgänge durchführen, indem Sie mit der rechten Maustaste auf die Knoten klicken.  
  
-   Aufgabenbereich, der häufige Aufgaben für aktuelle Elemente links unten im Fenster anzeigt.  
  
-   Detailbereich, in dem ausführliche Einstellungen des rechts in der Strukturansicht ausgewählten Konfigurationsknotens angezeigt werden.  
  
### <a name="opening-a-configuration-file"></a>Öffnen einer Konfigurationsdatei  
  
1. Der Service Configuration Editor starten, navigieren zu WCF-Installationsverzeichnis, und geben Sie ein Befehlsfenster mit `SvcConfigEditor.exe`.  
  
2. Von der **Datei** , wählen Sie im Menü **öffnen** , und klicken Sie auf den Typ der Datei, die Sie verwalten möchten.  
  
3. In der **öffnen** Dialogfeld navigieren Sie zu der Datei, zu verwalten, und doppelklicken darauf.  
  
 Der Viewer folgt dem Pfad für den Konfigurationsmerge automatisch und erstellt eine Ansicht der zusammengeführten Konfiguration. So ist zum Beispiel die tatsächliche Konfiguration eines nicht gehosteten Diensts eine Kombination von Machine.config und App.config. Änderungen werden für die aktive Datei in SvcConfigEditor übernommen. Wenn Sie eine bestimmte Datei im Pfad für den Konfigurationsmerge bearbeiten möchten, öffnen Sie diese Datei direkt.  
  
> [!NOTE]
>  Configuration Editor lädt die gerade geöffnete Konfigurationsdatei erneut, wenn sie außerhalb des Editors geändert wurde. Wenn dies geschieht, gehen alle Änderungen verloren, die nicht dauerhaft im Editor gespeichert wurden. Wenn das erneute Laden häufig auftritt, liegt dies meist an einem Dienst, der kontinuierlich auf die Konfigurationsdatei zugreift, z. B. eine im Hintergrund ausgeführte Antivirensoftware. Um dies zu beheben, müssen Sie sicherstellen, dass Configuration Editor der einzige Prozess ist, der auf die Datei zugreifen kann, wenn sie geöffnet ist.  
  
### <a name="services"></a>Dienste  
 Die **Services** -Knoten zeigt alle Dienste, die derzeit in der Konfigurationsdatei zugewiesen. Jeder Unterknoten in der Struktur entspricht einem Unterelement des der <`services`>-Element in der Konfigurationsdatei.  
  
 Beim Klicken auf die **Services** Knoten, die Sie anzeigen oder ausführen können Aufgaben auf den Dienst Zusammenfassung auf der Seite die **Detail** Bereich.  
  
#### <a name="creating-a-new-service-configuration"></a>Erstellen einer neuen Dienstkonfiguration  
 Sie können eine neue Dienstkonfiguration auf folgende Weise erstellen:  
  
-   Mithilfe eines Assistenten: Klicken Sie auf den Link **einen neuen Dienst erstellen...** auf im Aufgabenbereich oder auf Seite "Zusammenfassung" auf den Assistenten zu starten. Sie können auch dazu die **Datei** -> **neues Element hinzufügen**.  
  
-   Manuelles Erstellen: Sie können mit der rechten Maustaste die **Services** Knoten, und wählen Sie **neuen Dienst**.  
  
#### <a name="creating-a-new-service-endpoint-configuration"></a>Erstellen einer neuen Dienstendpunkt-Konfiguration  
 Sie können eine neue Dienstendpunkt-Konfiguration auf folgende Weise erstellen:  
  
-   Erstellen mit dem Assistenten: Klicken Sie auf den Link **einen neuen Dienstendpunkt erstellen...** auf im Aufgabenbereich oder auf Seite "Zusammenfassung" auf den Assistenten zu starten. Sie können auch dazu die **Datei** -> **neues Element hinzufügen**.  
  
-   Manuelles Erstellen: Nachdem Sie einen Dienst erstellt, Sie können mit der rechten Maustaste die **Endpunkte** Knoten, und wählen Sie "**neuer Dienstendpunkt**".  
  
#### <a name="editing-a-service-configuration"></a>Bearbeiten einer Dienstkonfiguration  
  
1. Klicken Sie auf eine **Service** Knoten.  
  
2. Bearbeiten Sie die Einstellungen in den Eigenschaftenrastern.  
  
#### <a name="editing-a-service-endpoint-configuration"></a>Bearbeiten einer Dienstendpunkt-Konfiguration  
  
1. Klicken Sie auf eine **Dienstendpunkt** Knoten.  
  
2. Bearbeiten Sie die Einstellungen in den Eigenschaftenrastern.  
  
#### <a name="adding-a-base-address"></a>Hinzufügen einer Basisadresse  
  
1. Klicken Sie auf die **Host** Knoten.  
  
2. Klicken Sie auf die **neu...** Schaltfläche der **Basisadressen** Abschnitt.  
  
3. Geben Sie den Basisadressen-URI im Dialogfeld ein.  
  
4. Klicken Sie auf **OK**.  
  
> [!NOTE]
>  Sie können nicht den Wert der Bearbeiten [ \<BaseAddressPrefixFilters >](../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md) in diesem Tool. Um dieses Element hinzuzufügen oder zu ändern, sollten Sie einen Text-Editor oder Visual Studio verwenden.  
  
### <a name="client"></a>Client  
 Die **Client** -Knoten zeigt alle Clientendpunkte in der Konfigurationsdatei. Jeder Unterknoten in der Struktur entspricht einem Unterelement des der <`client`>-Element in der Konfigurationsdatei.  
  
 Beim Klicken auf die **Client** Knoten können Sie anzeigen oder Ausführen von Aufgaben auf dem Client **Seite "Zusammenfassung"** in die **Detailbereich**.  
  
#### <a name="creating-a-new-client-endpoint-configuration"></a>Erstellen einer neuen Clientendpunkt-Konfiguration  
 Sie können eine neue Clientendpunkt-Konfiguration auf folgende Weise erstellen:  
  
-   Erstellen Sie vom Assistenten: Klicken Sie auf den Link **einen neuen Client erstellen...** auf der **Aufgabenbereich** auf der unteren linken Ecke des Fensters oder **Seite "Zusammenfassung"** um den Assistenten zu starten. Sie können auch dazu die **Datei** -> **neues Element hinzufügen**. Der Assistent fordert Sie auf, auf den Speicherort der Dienstkonfiguration zu zeigen, über den die Clientkonfiguration generiert wird. Sie können dann den Dienstendpunkt auswählen, mit dem eine Verbindung hergestellt werden soll.  
  
-   Manuelles Erstellen: Mit der rechten Maustaste die **Endpunkte** Knoten unter **Client**, und wählen Sie **neuer Clientendpunkt**.  
  
#### <a name="editing-a-client-endpoint-configuration"></a>Bearbeiten einer Clientendpunkt-Konfiguration  
  
1. Klicken Sie auf eine **Clientendpunkt** Knoten.  
  
2. Bearbeiten Sie die Einstellungen in den Eigenschaftenrastern.  
  
### <a name="standard-endpoint"></a>Standardendpunkt  
 Standardendpunkte sind spezialisierte Endpunkte, bei denen einer oder mehrere Aspekte der Adresse, des Vertrags und des Bindungssatzes auf die Standardwerte festgelegt sind.  
  
 Diese Konfigurationseinstellungen werden gespeichert, der **Standardendpunkt** Knoten. Die **Standardendpunkt** -Knoten zeigt alle standardendpunkteinstellungen in der Konfigurationsdatei. Jeder Unterknoten in der Struktur entspricht einem Unterelement in der `<standardEndpoints>` Element in der Konfigurationsdatei.  
  
 Beim Klicken auf die **Standardendpunkt** Knoten können Sie anzeigen oder Ausführen von Aufgaben auf den Standardendpunkt **Seite "Zusammenfassung"** in die **Detailbereich**.  
  
#### <a name="creating-a-new-standard-endpoint-configuration"></a>Erstellen einer neuen Standardendpunktkonfiguration  
 Sie können eine neue Standardendpunktkonfiguration auf folgende Weise erstellen:  
  
-   Mit der rechten Maustaste die **Standardendpunkt** Knoten, und wählen **neue Konfiguration des Standardendpunkts...** Wählen Sie den Bindungstyp im Dialogfeld, und klicken Sie auf **OK**.  
  
-   Wählen Sie die **Standardendpunkt** Knoten, und klicken Sie auf **neue Konfiguration des Standardendpunkts...** in der **Aufgabenbereich** auf der unteren linken Ecke des Fensters.  
  
 Die **erstellen einen neuen Standardendpunkt** Dialogfeld zeigt an, und alle registrierten standardendpunkttypen aufgeführt.  
  
#### <a name="viewing-and-editing-a-standard-endpoint-configuration"></a>Anzeigen und Bearbeiten einer Standardendpunktkonfiguration  
 Sie können eine Standardendpunktkonfiguration auf die folgende Weise zum Anzeigen und Bearbeiten öffnen:  
  
-   Klicken Sie zum Erweitern der **Standardendpunkt** Knoten, und klicken Sie auf den jeweiligen untergeordneten Endpunktknoten.  
  
-   Klicken Sie auf die **Standardendpunkt** Knoten, und klicken Sie auf den jeweiligen Endpunkt im Detailbereich.  
  
 Attribute für den Endpunkt werden zur Bearbeitung im rechten Bereich angezeigt.  
  
#### <a name="deleting-a-standard-endpoint-configuration"></a>Löschen einer Standardendpunktkonfiguration  
 Sie können eine Standardendpunktkonfiguration auf folgende Weise löschen:  
  
-   Klicken Sie zum Erweitern der **Standardendpunkt** Knoten und mit der rechten Maustaste den jeweiligen untergeordneten Endpunktknoten. Verwenden Sie den Kontextbefehl **Konfiguration des Standardendpunkts löschen** auf den Endpunkt löschen.  
  
-   Klicken Sie auf die **Standardendpunkt** Knoten. In der **Aufgabe** Bereich, klicken Sie auf **Konfiguration des Standardendpunkts löschen**.  
  
 Wenn der Standardendpunkt verwendet ist, wird eine Warnmeldung angezeigt, wenn Sie versuchen, ihn zu löschen: **Der Standardendpunkt wird verwendet. Wenn er jetzt gelöscht wird, müssen Sie sicherstellen, dass alle dazugehörigen Verweise an anderen Stellen der Konfiguration (z. B. im Dienstendpunkt oder Clientendpunkt) ebenfalls gelöscht werden. Andernfalls ist die Konfiguration ungültig und kann nächstes Mal nicht geöffnet werden. Sind Sie sicher, dass Sie den Standardendpunkt löschen möchten? "**  
  
### <a name="binding"></a>Bindung  
 Bindungskonfigurationen werden zum Konfigurieren von Bindungen auf Endpunkten verwendet. Diese Konfigurationseinstellungen werden gespeichert, der **Bindung** Knoten. Endpunkte verweisen anhand des Namens auf Bindungskonfigurationen, und mehrere Endpunkte können auf eine einzelne Bindungskonfiguration verweisen.  
  
 Die **Bindungen** -Knoten zeigt alle bindungseinstellungen in der Konfigurationsdatei. Jeder Unterknoten in der Struktur entspricht einem Unterelement in der <`bindings`>-Element in der Konfigurationsdatei.  
  
 Beim Klicken auf die **Bindungen** Knoten können Sie anzeigen oder Ausführen von Aufgaben für die Bindung **Seite "Zusammenfassung"** in die **Detailbereich**.  
  
#### <a name="creating-a-new-binding-configuration"></a>Erstellen einer neuen Bindungskonfiguration  
 Sie können eine neue Bindungskonfiguration auf folgende Weise erstellen:  
  
-   Mit der rechten Maustaste die **Bindungen** Knoten, und wählen **neue Bindungskonfiguration**... Wählen Sie den Bindungstyp im Dialogfeld, und klicken Sie auf **OK**.  
  
-   Wählen Sie die **Bindungen** Knoten, und klicken Sie auf **neue Bindungskonfiguration**... in der **Aufgabenbereich** auf der unteren linken Ecke des Fensters.  
  
-   Klicken Sie in der Dienst- oder Clientanwendung Seite Zusammenfassung auf **klicken Sie auf Erstellen** in die **Bindungskonfiguration** Feld, um eine Bindungskonfiguration für den entsprechenden Endpunkt zu erstellen.  
  
#### <a name="adding-binding-element-extensions-to-a-custom-binding"></a>Hinzufügen von Bindungselementerweiterungen zu einer benutzerdefinierten Bindung  
  
1. Wählen Sie die Bindung aus, der Sie ein Erweiterungselement hinzufügen möchten.  
  
2. Klicken Sie auf **Hinzufügen**.  
  
3. Wählen Sie aus der Liste der verfügbaren Erweiterungen die Bindungselementerweiterung aus, die Sie hinzufügen möchten. Sie können mehrere Elemente auswählen, indem Sie die STRG-TASTE gedrückt halten.  
  
4. Klicken Sie auf **Hinzufügen**.  
  
#### <a name="adjusting-the-extension-position-in-a-custom-binding"></a>Anpassen der Erweiterungsposition in einer benutzerdefinierten Bindung  
 Eine benutzerdefinierte Bindung ist eine Auflistung von Bindungselementen, die einen Stapel bilden. Jedes Bindungselement auf dem Stapel verfügt über eigene Konfigurationseinstellungen. Die Reihenfolge der Bindungselementerweiterungen in einer benutzerdefinierten Bindung gibt ihre Positionen im Stapel an. Elemente oben im Stapel werden zuerst übernommen. So ändern Sie die Reihenfolge  
  
1. Wählen Sie den benutzerdefinierten Bindungsknoten aus.  
  
2. Wählen Sie ein bindungserweiterungselement aus, in der **Bindungselementerweiterungs-Position** Abschnitt.  
  
3. Verwenden der **einrichten** oder **unten** Schaltfläche auf der linken Seite der Liste, um die Position des ausgewählten Elements zu ändern.  
  
#### <a name="editing-the-configuration-of-binding-element-extensions-in-a-custom-binding"></a>Bearbeiten der Bindungselementerweiterungs-Konfiguration in einer benutzerdefinierten Bindung  
  
1. Wählen Sie den Bindungsknoten in der Struktur aus.  
  
2. Wählen Sie die benutzerdefinierte Bindung, die das zu bearbeitende Element enthält.  
  
3. Wählen Sie die Bindungselementerweiterung aus, die Sie bearbeiten möchten. Die Einstellungen des Elements werden im rechten Bereich angezeigt, in dem sie bearbeitet werden können.  
  
### <a name="diagnostics"></a>Diagnose  
 Die **Diagnose** -Knoten zeigt alle diagnoseeinstellungen in der Konfigurationsdatei. Sie können Sie aktivieren oder deaktivieren Sie die Leistungsindikatoren, aktivieren oder Deaktivieren von Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI), konfigurieren WCF-Ablaufverfolgung und WCF-meldungsprotokollierung zu konfigurieren. Die Einstellungen in der **Diagnose** -Knoten entsprechen dem <`system.diagnostics`> Abschnitt und `<diagnostics>` im Abschnitt `<system.serviceModel>` in der Konfigurationsdatei.  
  
 Beim Klicken auf die **Diagnose** Knoten können Sie anzeigen oder Ausführen von Aufgaben auf die Diagnose **Seite "Zusammenfassung"** in die **Detailbereich**.  
  
#### <a name="configuring-performance-counters-and-wmi"></a>Konfigurieren von Leistungsindikatoren und WMI  
  
1. Klicken Sie auf die **Diagnose** Knoten.  
  
2. Klicken Sie auf **Umschalten von Leistungsindikatoren**. Der Leistungsindikator verfügt über drei Zustände: Off (Standardeinstellung) ServiceOnly und alles. Wenn Sie auf den Link klicken, wird diese Einstellung auf einen der drei Zustände festgelegt.  
  
#### <a name="configuring-wmi-provider"></a>Konfigurieren eines WMI-Anbieters  
  
1. Klicken Sie auf die **Diagnose** Knoten.  
  
2. Um WMI-Anbieter zu aktivieren, klicken Sie auf die **WMI-Anbieter aktivieren** Link.  
  
#### <a name="enabling-wcf-tracing"></a>Aktivieren von WCF-Ablaufverfolgung  
 Sie können eine WCF-Ablaufverfolgungsdatei mit Standardeigenschaften erstellen oder eine benutzerdefinierte Ablaufverfolgungsdatei einrichten.  
  
1. Klicken Sie auf die **Diagnose** Knoten.  
  
2. Klicken Sie auf **Aktivieren der Ablaufverfolgung**.  
  
3. Klicken Sie auf die **Ablaufverfolgungsebene** Link, um die Ablaufverfolgungsebene einzustellen. Es gibt sechs Ablaufverfolgungsebenen: Deaktiviert, kritische, Fehler-, Warn-, Informationen und ausführlich. Die **Aktivitätsablaufverfolgung** und **Aktivität propagieren** aktivieren, die Sie verwenden die WCF aktivitätsablaufverfolgungs-Funktion.  
  
4. Klicken Sie auf den Namen des Ablaufverfolgungslisteners, um die Ablaufverfolgungsdatei und die Optionen festzulegen.  
  
#### <a name="enabling-wcf-logging"></a>Aktivieren der WCF-Protokollierung  
 Sie können eine WCF-Ablaufverfolgungsdatei mit Standardeigenschaften erstellen oder eine benutzerdefinierte Ablaufverfolgungsdatei einrichten.  
  
1. Klicken Sie auf die **Diagnose** Knoten.  
  
2. Klicken Sie auf **Nachrichtenprotokollierung aktivieren,**.  
  
3. Klicken Sie auf die **Protokollebene** Link, um die Protokollebene einzustellen. Es gibt drei Protokollebenen: Fehlerhaft, Dienst und Transport.  
  
4. Klicken Sie auf den Namen des Listeners, um die Protokolldatei und die Optionen festzulegen.  
  
> [!NOTE]
>  Wenn Sie möchten die Ablaufverfolgungs- und Nachrichtenprotokollen automatisch geleert werden, wenn die Anwendung geschlossen wird, aktivieren Sie die **automatische Leerung** Option.  
  
 Die **Diagnose** **Seite "Zusammenfassung"** ermöglicht es Ihnen, die häufigsten Aufgaben bei der Diagnosekonfiguration. Allerdings sollten Sie die Listener- und die Quelleneinstellungen-Einstellungen manuell zu bearbeiten, erweitern Sie die **Diagnose** Knoten, und Bearbeiten von Einstellungen in **Nachrichtenprotokollierung**, **Listener** und **Quellen** Knoten.  
  
#### <a name="enabling-wcf-custom-tracing-or-message-logging"></a>Aktivieren von benutzerdefinierter WCF-Ablaufverfolgung oder Nachrichtenprotokollierung  
  
1. Klicken Sie auf die **Diagnose** Knoten, und erweitern Sie ihn.  
  
2. Mit der rechten Maustaste die **Listener** Knoten, und wählen **neuer Listener**.  
  
3. Geben Sie den Namen der Ablaufverfolgungsdatei in die **InitData** Feld. Klicken Sie auf die "..." Schaltfläche, um einen Pfad zu suchen.  
  
4. Klicken auf die **TypeName** Zeile zeigt die "..." Schaltfläche ". Klicken Sie auf diese Schaltfläche, um das Öffnen der **Ablaufverfolgungslistener-Typbrowser**, die Sie verwenden können, vorkonfigurierte Ablaufverfolgungslistener suchen, die bereits installiert sind.  
  
5. Beachten Sie die **Quelle** Abschnitt. Klicken Sie auf **hinzufügen** in diesem Abschnitt, um ein Dialogfeld mit einer Dropdown-Menü zu öffnen, die verfügbaren Ablaufverfolgungsquellen aufgeführt. Wählen Sie eine Ablaufverfolgungsquelle aus, und klicken Sie auf **OK**.  
  
6. Um Einstellungen für die Nachrichtenprotokollierung zu bearbeiten, klicken Sie auf die **Nachrichtenprotokollierung** Knoten. Sie können die Einstellungen im Eigenschaftenraster bearbeiten.  
  
### <a name="advanced"></a>Erweitert  
  
#### <a name="behaviors"></a>Verhalten  
 Die **Verhaltensweisen** Knoten zeigt an, die Verhaltensweisen, die derzeit in der Konfigurationsdatei definiert werden.  
  
 Verhaltenskonfigurationen werden verwendet, um Verhalten von Endpunkten und Diensten zu konfigurieren. Diese Konfigurationseinstellungen werden gespeichert, der **erweitert** Knoten unter **Dienstverhalten** und **Endpunktverhalten**. Dienstverhalten werden von Diensten verwendet, Endpunktverhalten dagegen von Endpunkten.  
  
 Verhalten sind eine Auflistung von Erweiterungselementen für einen Stapel. Das Element oben im Stapel wird zuerst übernommen. Jedes Erweiterungselement kann über eine eigene Konfiguration verfügen.  
  
##### <a name="creating-a-new-behavior-configuration"></a>Erstellen einer neuen Verhaltenskonfiguration  
 Sie können eine neue Verhaltenskonfiguration auf eine der folgenden Weisen erstellen:  
  
-   Mit der rechten Maustaste einen der verhaltensknoten, und wählen Sie "**neue Verhaltenskonfiguration**  
  
-   Wählen Sie einen der verhaltensknoten, und klicken Sie auf die **neue Verhaltenskonfiguration**... in der **Aufgabenbereich** auf der unteren linken Ecke des Fensters.  
  
##### <a name="adding-behavior-element-extensions-to-a-behavior"></a>Hinzufügen von Verhaltenselementerweiterungen zu einem Verhalten  
  
1. Wählen Sie einen der Verhaltensknoten aus.  
  
2. Markieren Sie das zu bearbeitende Verhalten.  
  
3. Klicken Sie auf **Hinzufügen**.  
  
4. Wählen Sie aus der Liste der verfügbaren Erweiterungen die Verhaltenselementerweiterung aus, die Sie hinzufügen möchten.  
  
5. Klicken Sie auf **Hinzufügen**.  
  
##### <a name="adjusting-the-extension-position-in-a-behavior"></a>Anpassen der Erweiterungsposition in einem Verhalten  
 Verhalten sind Auflistungen von Elementen, die einen Stapel bilden. Jedes Element im Stapel verfügt über seine eigene Konfiguration. Die Reihenfolge der Verhaltenselementerweiterungen in einem Verhalten gibt ihre Positionen im Stapel an. Elemente oben im Stapel werden zuerst übernommen. So ändern Sie die Reihenfolge  
  
1. Wählen Sie einen der Verhaltensknoten aus.  
  
2. Markieren Sie das zu bearbeitende Verhalten.  
  
3. Wählen Sie ein verhaltenserweiterungselement aus, in der **Verhaltenselementerweiterungs-Position** Abschnitt.  
  
4. Verwenden der **einrichten** oder **unten** Schaltfläche auf der linken Seite der Liste, um die Position des ausgewählten Elements zu ändern.  
  
##### <a name="editing-the-configuration-of-behavior-element-extensions"></a>Bearbeiten der Konfiguration von Verhaltenselementerweiterungen  
  
1. Wählen Sie einen der Verhaltensknoten in der Struktur aus.  
  
2. Wählen Sie das Verhalten aus, das das zu bearbeitende Element enthält.  
  
3. Wählen Sie die Verhaltenselementerweiterung aus, die Sie bearbeiten möchten. Die Einstellungen des Elements werden im rechten Bereich angezeigt, wo sie bearbeitet werden können.  
  
#### <a name="protocolmapping"></a>ProtocolMapping  
 Mit diesem Abschnitt können Sie Standardbindungstypen für andere Protokolle, wie z. B. http, tcp, MSMQ oder net.pipe, über die definierte Zuordnung zwischen Protokolladressschemas und den möglichen Bindungen festlegen. Sie können darüber hinaus anderen Protokollen neue Zuordnungen hinzufügen.  
  
#### <a name="extensions"></a>Erweiterungen  
 Neue bindungserweiterungen, bindungselementerweiterungen, standardendpunkterweiterungen und verhaltenserweiterungen können für die Verwendung in WCF-Konfiguration registriert werden. Erweiterungen sind Name-/Typpaare. Der Name definiert den Namen der Erweiterung in der Konfiguration, wohingegen der Typ die Erweiterung implementiert. Es gibt vier Erweiterungstypen:  
  
-   Bindungserweiterungen definieren einen gesamten Bindungstyp. Beispiel: `basicHttpBinding`  
  
-   Bindungselementerweiterungen definieren ein Element einer Bindung. Beispiel: `textMessageEncoding`  
  
-   Standardendpunkterweiterungen definieren einen gesamten Standardendpunkt. Beispiel: `discoveryEndpoint`  
  
-   Verhaltenselementerweiterungen definieren ein Element eines Verhaltens. Beispiel: `clientVia`  
  
 Erweiterungen, die in einer Konfiguration registriert wurden, können wie jede andere WCF-Komponente des gleichen Typs verwendet werden.  
  
##### <a name="adding-a-new-extension"></a>Hinzufügen einer neuen Erweiterung  
 Wählen Sie einen der Erweiterungsknoten in den erweiterten Knoten aus:  
  
1. Klicken Sie auf **neue**.  
  
2. Geben Sie einen Namen und einen Typ ein.  
  
3. Klicken Sie auf **OK**.  
  
4. Die Erweiterung wird jetzt an der entsprechenden Stelle im Editor angezeigt. Wenn Sie z.&amp;#160;B. eine Verhaltenselementerweiterung hinzufügen, wird sie in der Liste verfügbarer Erweiterungen angezeigt.  
  
#### <a name="hosting-environment"></a>Hostumgebung  
 Dieser Abschnitt ermöglicht Ihnen, Instanziierungseinstellungen für die Diensthostingumgebung zu definieren.  
  
### <a name="creating-a-configuration-file-using-the-wizard"></a>Erstellen einer Konfigurationsdatei mit dem Assistenten  
 Eine Möglichkeit zum Erstellen einer neuen Konfigurationsdatei ist die Verwendung des Assistenten für neue Dienstelemente. Der Assistent sucht nach den installierten Diensttypen und andere Elemente mit WCF auf dem Computer, einschließlich COM+ und Web gehostete virtuelle Verzeichnisse, kompatibel und lädt diese, um die Erstellung der Konfigurations zu straffen.  
  
#### <a name="creating-a-configuration-file"></a>Erstellen einer Konfigurationsdatei  
  
1. Der Service Configuration Editor starten, navigieren zu WCF-Installationsverzeichnis, und geben Sie ein Befehlsfenster mit `SvcConfigEditor.exe`.  
  
2. Von der **Datei** , wählen Sie im Menü **öffnen** , und klicken Sie auf **ausführbare Datei**, **COM+ Service**, oder **WebHosted Service**, abhängig vom Typ der Konfigurationsdatei, die Sie erstellen möchten.  
  
3. In der **öffnen** Dialogfeld navigieren Sie zu der Datei, Sie verwenden möchten, erstellen eine Konfigurationsdatei für, und doppelklicken darauf.  
  
4. In der **Datei** Startmenü **neues Element hinzufügen** , und klicken Sie auf **Service**. Der Assistent für neue Dienstelemente wird geöffnet.  
  
5. Folgen Sie den Schritten im Assistenten, um den neuen Dienst zu erstellen.  
  
> [!NOTE]
>  Wenn Sie die NetPeerTcpBinding aus der vom Assistenten generierten Konfigurationsdatei verwendet möchten, müssen Sie manuell ein Bindungskonfigurationselement hinzufügen und das `mode`-Attribut seines `security`-Elements in „None“ ändern.  
  
## <a name="configuring-com"></a>Konfigurieren von COM+  
 Mit dem Service Configuration Editor können Sie eine neue Konfigurationsdatei für eine vorhandene COM+-Anwendung erstellen oder eine vorhandene COM+-Konfiguration bearbeiten. Die **COM-Vertrag** Knoten ist nur sichtbar, wenn die <`comContract`> Abschnitt in der Konfigurationsdatei vorhanden ist.  
  
### <a name="creating-a-new-com-configuration"></a>Erstellen einer neuen COM+-Konfigurationsdatei  
 Stellen Sie vor dem Erstellen einer neuen COM+-Konfiguration sicher, dass die COM+-Anwendung in den Komponentendiensten installiert und im globalen Assemblycache (GAC) registriert ist.  
  
1. Wählen Sie **Datei** -> **integrieren** -> **COM+-Anwendung.** Hierdurch wird die gerade geöffnete Datei geschlossen. Wenn die Datei noch nicht gespeicherte Daten enthält, wird ein Dialogfeld zum Speichern angezeigt. Die **COM+-Integration-Assistenten** wird gestartet.  
  
2. Wählen Sie auf der ersten Seite die COM+-Anwendung in der Struktur. Wenn die COM+-Anwendung nicht in der Struktur angezeigt wird, überprüfen Sie, ob sie in den Komponentendiensten installiert und im globalen Assemblycache (GAC) registriert ist.  
  
3. Wählen Sie auf der nächsten Seite, welche Methode(n) Sie als WCF-Dienste verfügbar machen möchten. Alle unterstützten Methoden in der COM+-Anwendung werden angezeigt und sind standardmäßig ausgewählt.  
  
4. Wählen Sie eine Hostingmethode aus.  
  
5. Konfigurieren Sie andere Einstellungen entsprechend den Richtlinien des Assistenten.  
  
6. Der Service Configuration Editor nutzt ComSvcConfig.exe im Hintergrund, um eine Konfigurationsdatei zu generieren. Nachdem dies abgeschlossen wurde, können Sie eine Zusammenfassung anzeigen und den Assistenten beenden. Die generierte Konfigurationsdatei wird geöffnet, damit Sie diese direkt bearbeiten können.  
  
### <a name="editing-an-existing-com-configuration"></a>Bearbeiten einer vorhandenen COM+-Konfiguration  
  
1. Wählen Sie **Datei** -> **öffnen** -> **COM+ Service**...  
  
2. Wählen Sie den zu bearbeitenden COM+-Dienst aus der Liste aus.  
  
3. Bearbeiten Sie Konfigurationseinstellungen in die **COM-Verträge** Knoten.  
  
    > [!NOTE]
    >  Sie können eine Konfigurationsdatei mit COM+-Verträgen auch direkt öffnen und bearbeiten.  
  
## <a name="security"></a>Sicherheit  
 Eine durch den Configuration Editor generierte Dienstkonfigurationsdatei ist nicht garantiert sicher. Finden Sie in der [Sicherheit](../../../docs/framework/wcf/feature-details/security.md) Dokumentation, um herauszufinden, wie Sie Ihre WCF-Dienste zu schützen.  
  
 Außerdem kann der Configuration Editor nur verwendet werden, um gültige WCF-Konfigurationselemente zu lesen und zu schreiben. Das Tool ignoriert schemakompatible, benutzerdefinierte Elemente. Es versucht außerdem nicht, diese Elemente aus der Konfigurationsdatei zu entfernen oder die Auswirkungen auf die bekannten WCF-Elemente zu ermitteln. Es ist die Aufgabe des Benutzers, zu ermitteln, ob diese Elemente eine Bedrohung für die Anwendung oder das System darstellen.
