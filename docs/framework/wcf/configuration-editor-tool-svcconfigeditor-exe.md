---
title: "Configuration Editor-Tool (SvcConfigEditor.exe) | Microsoft Docs"
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
helpviewer_keywords: 
  - "Konfigurationsdatei"
  - "Konfigurationsdateischema"
  - "Konfigurationsdateien"
  - "Konfigurationsdateien, Erstellen"
ms.assetid: 2db21a57-5f64-426f-89df-fb0dc2d2def5
caps.latest.revision: 45
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 45
---
# Configuration Editor-Tool (SvcConfigEditor.exe)
Der [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Service Configuration Editor \(SvcConfigEditor.exe\) ermöglicht Administratoren und Entwicklern, Konfigurationseinstellungen für [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienste mithilfe einer grafischen Benutzeroberfläche zu erstellen und zu bearbeiten.Mit diesem Tool können Sie die Einstellungen für Bindungen, Verhalten, Dienste und Diagnosen von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] verwalten, ohne XML\-Dateien direkt bearbeiten zu müssen.  
  
 Der Service Configuration Editor befindet sich im Ordner "C:\\Programme\\Microsoft SDKs\\Windows\\v6.0\\Bin".  
  
## Der WCF\-Configuration Editor  
 Der Service Configuration Editor umfasst einen Assistenten, der Sie durch den Prozess der Konfiguration eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensts oder \-Clients führt.Es wird dringend geraten, den Assistenten und nicht den Editor zu verwenden.  
  
 Wenn Sie bereits über Konfigurationsdateien verfügen, die mit dem standardmäßigen System.Configuration\-Schema konform sind, können Sie spezielle Einstellungen für Bindungen, Verhalten, Dienste und Diagnosen über die Benutzeroberfläche verwalten.Mit dem Service Configuration Editor \(SvcConfigEditor\) können Sie die Einstellungen von vorhandenen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Konfigurationsdateien sowie von ausführbaren Dateien, COM\+\-Diensten und im Web gehosteten Diensten verwalten.Beim Öffnen eines im Internet gehosteten Diensts mit dem Service Configuration Editor werden sowohl die eigene Konfiguration des Diensts sowie die von Knoten der oberen Ebene übernommenen Konfigurationsabschnitte angezeigt.  
  
 Da sich die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Konfigurationseinstellungen im `<system.serviceModel>`\-Abschnitt der Konfigurationsdatei befinden, arbeitet der Editor nur mit dem Inhalt dieses Elements und greift auf keine anderen Elemente in dieser Datei zu.Sie können direkt zu vorhandenen Konfigurationsdateien wechseln, oder Sie können eine Assembly auswählen, die einen Dienst, ein virtuelles Verzeichnis oder einen COM\+\-Dienst enthält.Der Editor lädt die Konfigurationsdatei für diesen Dienst und ermöglicht dem Benutzer, neue Elemente hinzuzufügen oder vorhandene Elemente des `<system.serviceModel>`\-Abschnitts der Konfigurationsdatei zu bearbeiten.  
  
 Der Editor unterstützt IntelliSense und erzwingt Schemakompatibilität.Die Ausgabe entspricht garantiert dem Schema der Konfigurationsdatei und weist syntaktisch korrekte Datenwerte auf.Der Editor garantiert jedoch nicht, dass die Konfigurationsdatei semantisch gültig ist.Mit anderen Worten: Der Editor garantiert nicht, dass die Konfigurationsdatei mit dem Dienst zusammenarbeiten kann, den sie konfiguriert.  
  
> [!CAUTION]
>  Der Editor kann kein Konfigurationselement aus der Konfigurationsdatei löschen, sobald das Element geändert wurde.Wenn Sie beispielsweise den Editor verwendet haben, um den Endpunktnamen auf eine nicht leere Zeichenfolge festzulegen, und diesen speichern, weist die Konfigurationsdatei folgenden Inhalt auf, wie im folgenden Beispiel gezeigt:  
>   
>  `<endpoint binding="basicHttpBinding" name="somename" />`  
>   
>  Wenn Sie versuchen, den Namen zu entfernen, indem Sie eine leere Zeichenfolge festlegen, und die Datei speichern, enthält die Konfigurationsdatei weiterhin das `name`\-Attribut, wie im folgenden Beispiel gezeigt:  
>   
>  `<endpoint binding="basicHttpBinding" name="" />`  
>   
>  Um das Attribut zu löschen, müssen Sie das Element manuell mit einem anderen Text\-Editor bearbeiten.  
>   
>  Sie sollten besonders vorsichtig vorgehen, wenn Sie das `issueToken`\-Element des `clientCredential`\-Endpunktverhaltens verwenden.Vor allem das `address`\-Attribut des `localIssuer`\-Unterelements darf keine leere Zeichenfolge sein.Wenn Sie das `address`\-Attribut mit dem Configuration Editor geändert haben und es vollständig entfernen möchten, sollten Sie dies mit einem anderen Tool als dem Editor durchführen.Andernfalls enthält das Attribut eine leere Zeichenfolge, und die Anwendung löst eine Ausnahme aus.  
  
## Verwenden von Service Configuration Editor  
 Der Service Configuration Editor befindet sich in folgendem Windows SDK\-Installationspfad:  
  
 C:\\Programme\\Microsoft SDKs\\Windows\\v6.0\\Bin\\SvcConfigEditor.exe  
  
 Nachdem Sie den Service Configuration Editor gestartet haben, können Sie über das Menü **Datei\/Öffnen** nach dem Dienst oder der Assembly suchen, die Sie verwalten möchten.Sie können Konfigurationsdateien direkt öffnen, nach [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-\/COM\+\-Diensten suchen und Konfigurationsdateien für über das Web gehostete Dienste öffnen.  
  
 Die Service Configuration Editor\-Benutzeroberfläche ist in die folgenden Bereiche aufgeteilt:  
  
-   Strukturansichtsbereich, in dem die Konfigurationselemente links in einer Struktur angezeigt werden.Sie können in der Struktur Vorgänge durchführen, indem Sie mit der rechten Maustaste auf die Knoten klicken.  
  
-   Aufgabenbereich, der häufige Aufgaben für aktuelle Elemente links unten im Fenster anzeigt.  
  
-   Detailbereich, in dem ausführliche Einstellungen des rechts in der Strukturansicht ausgewählten Konfigurationsknotens angezeigt werden.  
  
### Öffnen einer Konfigurationsdatei  
  
1.  Starten Sie den Service Configuration Editor, indem Sie im Befehlsfenster zum [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Installationsverzeichnis wechseln und dann `SvcConfigEditor.exe` eingeben.  
  
2.  Wählen Sie im Menü **Datei** die Option **Öffnen**, und klicken Sie auf den Dateityp, den Sie verwalten möchten.  
  
3.  Wechseln Sie im Dialogfeld **Öffnen** zu der Datei, die Sie verwalten möchten, und doppelklicken Sie darauf.  
  
 Der Viewer folgt dem Pfad für die Konfigurationszusammenführung automatisch und erstellt eine Ansicht der zusammengeführten Konfiguration.So ist zum Beispiel die tatsächliche Konfiguration eines nicht gehosteten Diensts eine Kombination von Machine.config und App.config.Änderungen werden für die aktive Datei in SvcConfigEditor übernommen.Wenn Sie eine bestimmte Datei im Pfad für die Konfigurationszusammenführung bearbeiten möchten, öffnen Sie diese Datei direkt.  
  
> [!NOTE]
>  Configuration Editor lädt die gerade geöffnete Konfigurationsdatei erneut, wenn sie außerhalb des Editors geändert wurde.Wenn dies geschieht, gehen alle Änderungen verloren, die nicht dauerhaft im Editor gespeichert wurden.Wenn das erneute Laden häufig auftritt, liegt dies meist an einem Dienst, der kontinuierlich auf die Konfigurationsdatei zugreift, z. B. eine im Hintergrund ausgeführte Antivirensoftware.Um dies zu beheben, müssen Sie sicherstellen, dass Configuration Editor der einzige Prozess ist, der auf die Datei zugreifen kann, wenn sie geöffnet ist.  
  
### Dienste  
 Der **Dienste**\-Knoten zeigt alle Dienste an, die zurzeit in der Konfigurationsdatei zugewiesen sind.Jeder Unterknoten in der Struktur entspricht einem Unterelement des \<`services`\>\-Elements in der Konfigurationsdatei.  
  
 Wenn Sie auf den Konten **Dienste** klicken, können Sie auf der Zusammenfassungsseite im **Detailbereich** Aufgaben anzeigen und durchführen.  
  
#### Erstellen einer neuen Dienstkonfiguration  
 Sie können eine neue Dienstkonfiguration auf folgende Weise erstellen:  
  
-   Mit dem Assistenten: Klicken Sie im Aufgabenbereich oder auf der Zusammenfassungsseite auf den Link **Neuen Dienst erstellen...**, um den Assistenten zu starten.Sie können auch im Menü **Datei** \> **Neues Element hinzufügen** wählen.  
  
-   Manuelles Erstellen: Sie können mit der rechten Maustaste auf den Knoten **Dienste** klicken und **Neuer Dienst** auswählen.  
  
#### Erstellen einer neuen Dienstendpunkt\-Konfiguration  
 Sie können eine neue Dienstendpunkt\-Konfiguration auf folgende Weise erstellen:  
  
-   Erstellen mit dem Assistenten: Klicken Sie im Aufgabenbereich oder auf der Zusammenfassungsseite auf den Link **Neuen Dienstendpunkt erstellen...**, um den Assistenten zu starten.Sie können auch im Menü **Datei** \> **Neues Element hinzufügen** wählen.  
  
-   Manuelles Erstellen: Nachdem Sie einen Dienst erstellt haben, können Sie mit der rechten Maustaste auf den **Endpunkte**\-Knoten klicken und **Neuer Dienstendpunkt** wählen.  
  
#### Bearbeiten einer Dienstkonfiguration  
  
1.  Klicken Sie auf einen **Dienst**\-Knoten.  
  
2.  Bearbeiten Sie die Einstellungen in den Eigenschaftenrastern.  
  
#### Bearbeiten einer Dienstendpunkt\-Konfiguration  
  
1.  Klicken Sie auf einen **Dienstendpunkt**\-Knoten.  
  
2.  Bearbeiten Sie die Einstellungen in den Eigenschaftenrastern.  
  
#### Hinzufügen einer Basisadresse  
  
1.  Klicken Sie auf den **Host**\-Knoten.  
  
2.  Klicken Sie im Abschnitt **Basisadressen** auf die Schaltfläche **Neu...**.  
  
3.  Geben Sie den Basisadressen\-URI im Dialogfeld ein.  
  
4.  Klicken Sie auf **OK**.  
  
> [!NOTE]
>  Der Wert von [\<baseAddressPrefixFilters\>](../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md) kann in diesem Tool nicht bearbeitet werden.Um dieses Element hinzuzufügen oder zu ändern, sollten Sie einen Text\-Editor oder [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] verwenden.  
  
### Client  
 Der **Client**\-Knoten zeigt alle Clientendpunkte in der Konfigurationsdatei an.Jeder Unterknoten in der Struktur entspricht einem Unterelement des \<`client`\>\-Elements in der Konfigurationsdatei.  
  
 Wenn Sie auf den **Client**\-Knoten klicken, können Sie auf der **Zusammenfassungsseite** im **Detailbereich** Aufgaben anzeigen und durchführen.  
  
#### Erstellen einer neuen Clientendpunkt\-Konfiguration  
 Sie können eine neue Clientendpunkt\-Konfiguration auf folgende Weise erstellen:  
  
-   Erstellen mit dem Assistenten: Klicken Sie im **Aufgabenbereich** unten links im Fenster oder auf der **Zusammenfassungsseite** auf den Link **Neuen Client erstellen...**, um den Assistenten zu starten.Sie können auch im Menü **Datei** \> **Neues Element hinzufügen** auswählen.Der Assistent fordert Sie auf, auf den Speicherort der Dienstkonfiguration zu zeigen, über den die Clientkonfiguration generiert wird.Sie können dann den Dienstendpunkt auswählen, mit dem eine Verbindung hergestellt werden soll.  
  
-   Manuelles Erstellen: Klicken Sie mit der rechten Maustaste auf den Knoten **Endpunkte** unter **Client**, und wählen Sie **Neuer Clientendpunkt** aus.  
  
#### Bearbeiten einer Clientendpunkt\-Konfiguration  
  
1.  Klicken Sie auf einen **Clientendpunkt**\-Knoten.  
  
2.  Bearbeiten Sie die Einstellungen in den Eigenschaftenrastern.  
  
### Standardendpunkt  
 Standardendpunkte sind spezialisierte Endpunkte, bei denen einer oder mehrere Aspekte der Adresse, des Vertrags und des Bindungssatzes auf die Standardwerte festgelegt sind.  
  
 Diese Konfigurationseinstellungen werden im **Standardendpunkt**\-Knoten gespeichert.Der **Standardendpunkt**\-Knoten zeigt alle Standardendpunkteinstellungen in der Konfigurationsdatei an.Jeder Unterknoten in der Struktur entspricht einem Unterelement des `<standardEndpoints>`\-Elements in der Konfigurationsdatei.  
  
 Wenn Sie auf den **Standardendpunkt**\-Knoten klicken, können Sie auf der **Zusammenfassungsseite** für den Standardendpunkt im **Detailbereich** Aufgaben anzeigen und durchführen.  
  
#### Erstellen einer neuen Standardendpunktkonfiguration  
 Sie können eine neue Standardendpunktkonfiguration auf folgende Weise erstellen:  
  
-   Klicken Sie mit der rechten Maustaste auf den **Standardendpunkt**\-Knoten, und wählen Sie **Neue Konfiguration des Standardendpunkts...** aus. Wählen Sie den Bindungstyp im Dialogfeld aus, und klicken Sie auf **OK**.  
  
-   Wählen Sie den **Standardendpunkt**\-Knoten aus, und klicken Sie im **Aufgabenbereich** links unten im Fenster auf **Neue Konfiguration des Standardendpunkts**.  
  
 Das Dialogfeld **Neuer Standardendpunkt wird erstellt** wird angezeigt, in dem alle registrierten Standardendpunkttypen aufgeführt sind.  
  
#### Anzeigen und Bearbeiten einer Standardendpunktkonfiguration  
 Sie können eine Standardendpunktkonfiguration auf die folgende Weise zum Anzeigen und Bearbeiten öffnen:  
  
-   Klicken Sie, um den **Standardendpunkt**\-Knoten zu erweitern, und klicken Sie dann auf den jeweiligen untergeordneten Endpunktknoten.  
  
-   Klicken Sie auf den **Standardendpunkt**\-Knoten, und klicken Sie auf den jeweiligen Endpunkt im Detailbereich.  
  
 Attribute für den Endpunkt werden zur Bearbeitung im rechten Bereich angezeigt.  
  
#### Löschen einer Standardendpunktkonfiguration  
 Sie können eine Standardendpunktkonfiguration auf folgende Weise löschen:  
  
-   Klicken Sie, um den **Standardendpunkt**\-Knoten zu erweitern, und klicken Sie dann mit der rechten Maustaste auf den jeweiligen untergeordneten Endpunktknoten.Verwenden Sie den Kontextbefehl **Konfiguration des Standardendpunks löschen**, um den Endpunkt zu löschen.  
  
-   Klicken Sie auf den **Standardendpunkt**\-Knoten.Klicken Sie im **Aufgabenbereich** auf **Konfiguration des Standardendpunkts löschen**.  
  
 Wenn der Standardendpunkt verwendet wird, wird beim Versuch, ihn zu löschen, eine Warnmeldung angezeigt: **Der Standardendpunkt wird verwendet. Wenn er jetzt gelöscht wird, müssen Sie sicherstellen, dass alle dazugehörigen Verweise an anderen Stellen der Konfiguration \(z. B. im Dienstendpunkt oder Clientendpunkt\) ebenfalls gelöscht werden. Andernfalls ist die Konfiguration ungültig und kann nächstes Mal nicht geöffnet werden. Sind Sie sicher, dass Sie den Standardendpunkt löschen möchten?"**  
  
### Bindung  
 Bindungskonfigurationen werden zum Konfigurieren von Bindungen auf Endpunkten verwendet.Diese Konfigurationseinstellungen werden im **Bindung**\-Knoten gespeichert.Endpunkte verweisen anhand des Namens auf Bindungskonfigurationen, und mehrere Endpunkte können auf eine einzelne Bindungskonfiguration verweisen.  
  
 Der Knoten **Bindungen** zeigt alle Bindungseinstellungen in der Konfigurationsdatei an.Jeder Unterknoten in der Struktur entspricht einem Unterelement des \<`bindings`\>\-Elements in der Konfigurationsdatei.  
  
 Wenn Sie auf den **Bindungen**\-Knoten klicken, können Sie auf der **Zusammenfassungsseite** im **Detailbereich** Aufgaben anzeigen und durchführen.  
  
#### Erstellen einer neuen Bindungskonfiguration  
 Sie können eine neue Bindungskonfiguration auf folgende Weise erstellen:  
  
-   Klicken Sie mit der rechten Maustaste auf den **Bindungen**\-Knoten, und wählen Sie **Neue Bindungskonfiguration** aus. Wählen Sie den Bindungstyp im Dialogfeld aus, und klicken Sie auf **OK**.  
  
-   Wählen Sie den **Bindungen**\-Knoten aus, und klicken Sie im **Aufgabenbereich** unten links im Fenster auf **Neue Bindungskonfiguration**.  
  
-   Klicken Sie auf der Zusammenfassungsseite für den Dienst oder Client im Feld **Bindungskonfiguration** auf **Hier zum Erstellen klicken**, um eine Bindungskonfiguration für den entsprechenden Endpunkt zu erstellen.  
  
#### Hinzufügen von Bindungselementerweiterungen zu einer benutzerdefinierten Bindung  
  
1.  Wählen Sie die Bindung aus, der Sie ein Erweiterungselement hinzufügen möchten.  
  
2.  Klicken Sie auf **Hinzufügen**.  
  
3.  Wählen Sie aus der Liste der verfügbaren Erweiterungen die Bindungselementerweiterung aus, die Sie hinzufügen möchten.Sie können mehrere Elemente auswählen, indem Sie die STRG\-TASTE gedrückt halten.  
  
4.  Klicken Sie auf **Hinzufügen**.  
  
#### Anpassen der Erweiterungsposition in einer benutzerdefinierten Bindung  
 Eine benutzerdefinierte Bindung ist eine Auflistung von Bindungselementen, die einen Stapel bilden.Jedes Bindungselement auf dem Stapel verfügt über eigene Konfigurationseinstellungen.Die Reihenfolge der Bindungselementerweiterungen in einer benutzerdefinierten Bindung gibt ihre Positionen im Stapel an.Elemente oben im Stapel werden zuerst übernommen.So ändern Sie die Reihenfolge  
  
1.  Wählen Sie den benutzerdefinierten Bindungsknoten aus.  
  
2.  Wählen Sie im Abschnitt **Bindungselementerweiterungs\-Position** ein Bindungserweiterungselement aus.  
  
3.  Klicken Sie auf die Schaltfläche **Nach oben** oder **Nach unten** links neben der Liste, um die Position des ausgewählten Elements zu ändern.  
  
#### Bearbeiten der Bindungselementerweiterungs\-Konfiguration in einer benutzerdefinierten Bindung  
  
1.  Wählen Sie den Bindungsknoten in der Struktur aus.  
  
2.  Wählen Sie die benutzerdefinierte Bindung, die das zu bearbeitende Element enthält.  
  
3.  Wählen Sie die Bindungselementerweiterung aus, die Sie bearbeiten möchten.Die Einstellungen des Elements werden im rechten Bereich angezeigt, in dem sie bearbeitet werden können.  
  
### Diagnose  
 Der **Diagnose**\-Knoten zeigt alle Diagnoseeinstellungen in der Konfigurationsdatei an.Hiermit können Sie Leistungsindikatoren ein\- oder ausschalten, die Windows\-Verwaltungsinstrumentation \(WMI\) aktivieren oder deaktivieren sowie die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Ablaufverfolgung und die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Meldungsprotokollierung konfigurieren.Die Einstellungen im **Diagnose**\-Knoten entsprechen dem \<`system.diagnostics`\>\-Abschnitt und dem `<diagnostics>`\-Abschnitt in der `<system.serviceModel>`\-Konfigurationsdatei.  
  
 Wenn Sie auf den **Diagnose**\-Knoten klicken, können Sie auf der **Zusammenfassungsseite** im **Detailbereich** Aufgaben anzeigen und durchführen.  
  
#### Konfigurieren von Leistungsindikatoren und WMI  
  
1.  Klicken Sie auf den **Diagnose**\-Knoten.  
  
2.  Klicken Sie auf **Leistungsindikatoren ein\-\/ausschalten**.Der Leistungsindikator verfügt über drei Zustände: Aus \(Standard\), ServiceOnly und Alles.Wenn Sie auf den Link klicken, wird diese Einstellung auf einen der drei Zustände festgelegt.  
  
#### Konfigurieren eines WMI\-Anbieters  
  
1.  Klicken Sie auf den **Diagnose**\-Knoten.  
  
2.  Um einen WMI\-Anbieter zu aktivieren, klicken Sie auf den Link **WMI\-Anbieter aktivieren**.  
  
#### Aktivieren von WCF\-Ablaufverfolgung  
 Sie können eine [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Ablaufverfolgungsdatei mit Standardeigenschaften erstellen oder eine benutzerdefinierte Ablaufverfolgungsdatei einrichten.  
  
1.  Klicken Sie auf den **Diagnose**\-Knoten.  
  
2.  Klicken Sie auf **Ablaufverfolgung aktivieren**.  
  
3.  Klicken Sie auf den Link **Ablaufverfolgungsebene**, um die Ablaufverfolgungsebene einzustellen.Es gibt sechs Ablaufverfolgungsebenen: Off, Critical, Error, Warning, Information und Verbose.Die Optionen **Aktivitätsablaufverfolgung** und **Aktivität propagieren** ermöglichen Ihnen, das Aktivitätsablaufverfolgungs\-Feature von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] zu verwenden.  
  
4.  Klicken Sie auf den Namen des Ablaufverfolgungslisteners, um die Ablaufverfolgungsdatei und die Optionen festzulegen.  
  
#### Aktivieren der WCF\-Protokollierung  
 Sie können eine [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Ablaufverfolgungsdatei mit Standardeigenschaften erstellen oder eine benutzerdefinierte Ablaufverfolgungsdatei einrichten.  
  
1.  Klicken Sie auf den **Diagnose**\-Knoten.  
  
2.  Klicken Sie auf **Nachrichtenprotokollierung aktivieren**.  
  
3.  Klicken Sie auf den Link **Protokollebene**, um die Protokollebene einzustellen.Es gibt drei Protokollebenen: Fehlerhaft, Dienst und Transport.  
  
4.  Klicken Sie auf den Namen des Listeners, um die Protokolldatei und die Optionen festzulegen.  
  
> [!NOTE]
>  Wenn die Ablaufverfolgungs\- und Meldungsprotokolle beim Schließen der Anwendung automatisch gelöscht werden sollen, aktivieren Sie die Option **Automatische Leerung**.  
  
 Die **Zusammenfassungsseite** der **Diagnose** ermöglicht Ihnen die Durchführung der häufigsten Aufgaben bei der Diagnosekonfiguration.Wenn Sie die Listener\- und die Quelleneinstellungen jedoch manuell bearbeiten möchten, müssen Sie den **Diagnose**\-Knoten erweitern und die Einstellungen in den Knoten **Nachrichtenprotokollierung**, **Listener** und **Quellen** bearbeiten.  
  
#### Aktivieren von benutzerdefinierter WCF\-Ablaufverfolgung oder Nachrichtenprotokollierung  
  
1.  Klicken Sie auf den **Diagnose**\-Knoten, und erweitern Sie ihn.  
  
2.  Klicken Sie mit der rechten Maustaste auf den **Listener**\-Knoten, und wählen Sie **Neuer Listener**.  
  
3.  Geben Sie den Namen der Ablaufverfolgungsdatei im **InitData**\-Feld ein.Sie können auf die Schaltfläche "…" klicken, um zu einem Pfad zu wechseln.  
  
4.  Wenn Sie auf die Zeile **TypeName** klicken, wird die Schaltfläche "…" angezeigt.Klicken Sie auf diese Schaltfläche, um den **Ablaufverfolgungslistener\-Typbrowser** zu öffnen, mit dem Sie bereits installierte, vorkonfigurierte Ablaufverfolgungslistener suchen können.  
  
5.  Beachten Sie den Abschnitt **Quelle**.Klicken Sie in diesem Abschnitt auf **Hinzufügen**, um ein Dialogfeld mit einem Dropdownmenü zu öffnen, in dem die verfügbaren Ablaufverfolgungsquellen aufgeführt sind.Wählen Sie eine Ablaufverfolgungsquelle aus, und klicken Sie auf **OK**.  
  
6.  Um Einstellungen für die Nachrichtenprotokollierung zu bearbeiten, klicken Sie auf den Knoten **Nachrichtenprotokollierung**.Sie können die Einstellungen im Eigenschaftenraster bearbeiten.  
  
### Erweiterte  
  
#### Verhalten  
 Im **Verhalten**\-Knoten werden die Verhalten angezeigt, die aktuell in der Konfigurationsdatei definiert sind.  
  
 Verhaltenskonfigurationen werden verwendet, um Verhalten von Endpunkten und Diensten zu konfigurieren.Diese Konfigurationseinstellungen werden im **Erweitert**\-Knoten unter **Dienstverhalten** und **Endpunktverhalten** gespeichert.Dienstverhalten werden von Diensten verwendet, Endpunktverhalten dagegen von Endpunkten.  
  
 Verhalten sind eine Auflistung von Erweiterungselementen für einen Stapel.Das Element oben im Stapel wird zuerst übernommen.Jedes Erweiterungselement kann über eine eigene Konfiguration verfügen.  
  
##### Erstellen einer neuen Verhaltenskonfiguration  
 Sie können eine neue Verhaltenskonfiguration auf eine der folgenden Weisen erstellen:  
  
-   Klicken Sie mit der rechten Maustaste auf einen der Verhaltensknoten, und wählen Sie **Neue Verhaltenskonfiguration**.  
  
-   Wählen Sie einen der Verhaltensknoten aus, und klicken Sie im **Aufgabenbereich** links unten im Fenster auf **Neue Verhaltenskonfiguration**.  
  
##### Hinzufügen von Verhaltenselementerweiterungen zu einem Verhalten  
  
1.  Wählen Sie einen der Verhaltensknoten aus.  
  
2.  Markieren Sie das zu bearbeitende Verhalten.  
  
3.  Klicken Sie auf **Hinzufügen**.  
  
4.  Wählen Sie aus der Liste der verfügbaren Erweiterungen die Verhaltenselementerweiterung aus, die Sie hinzufügen möchten.  
  
5.  Klicken Sie auf **Hinzufügen**.  
  
##### Anpassen der Erweiterungsposition in einem Verhalten  
 Verhalten sind Sammlungen von Elementen, die einen Stapel bilden.Jedes Element im Stapel verfügt über seine eigene Konfiguration.Die Reihenfolge der Verhaltenselementerweiterungen in einem Verhalten gibt ihre Positionen im Stapel an.Elemente oben im Stapel werden zuerst übernommen.So ändern Sie die Reihenfolge  
  
1.  Wählen Sie einen der Verhaltensknoten aus.  
  
2.  Markieren Sie das zu bearbeitende Verhalten.  
  
3.  Wählen Sie im Abschnitt **Verhaltenselementerweiterungs\-Position** ein Verhaltenserweiterungselement aus.  
  
4.  Klicken Sie auf die Schaltfläche **Nach oben** oder **Nach unten** links neben der Liste, um die Position des ausgewählten Elements zu ändern.  
  
##### Bearbeiten der Konfiguration von Verhaltenselementerweiterungen  
  
1.  Wählen Sie einen der Verhaltensknoten in der Struktur aus.  
  
2.  Wählen Sie das Verhalten aus, das das zu bearbeitende Element enthält.  
  
3.  Wählen Sie die Verhaltenselementerweiterung aus, die Sie bearbeiten möchten.Die Einstellungen des Elements werden im rechten Bereich angezeigt, wo sie bearbeitet werden können.  
  
#### ProtocolMapping  
 Mit diesem Abschnitt können Sie Standardbindungstypen für andere Protokolle, wie z. B. http, tcp, MSMQ oder net.pipe, über die definierte Zuordnung zwischen Protokolladressschemas und den möglichen Bindungen festlegen.Sie können darüber hinaus anderen Protokollen neue Zuordnungen hinzufügen.  
  
#### Erweiterungen  
 Neue Bindungserweiterungen, Bindungselementerweiterungen, Standardendpunkterweiterungen und Verhaltenserweiterungen können für die Verwendung in der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Konfiguration registriert werden.Erweiterungen sind Name\/Typ\-Paare.Der Name definiert den Namen der Erweiterung in der Konfiguration, wohingegen der Typ die Erweiterung implementiert.Es gibt vier Erweiterungstypen:  
  
-   Bindungserweiterungen definieren einen gesamten Bindungstyp.Beispiel: `basicHttpBinding`  
  
-   Bindungselementerweiterungen definieren ein Element einer Bindung.Beispiel: `textMessageEncoding`  
  
-   Standardendpunkterweiterungen definieren einen gesamten Standardendpunkt.Beispiel: `discoveryEndpoint`  
  
-   Verhaltenselementerweiterungen definieren ein Element eines Verhaltens.Beispiel: `clientVia`  
  
 Erweiterungen, die in einer Konfiguration registriert wurden, können wie jede andere [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Komponente des gleichen Typs verwendet werden.  
  
##### Hinzufügen einer neuen Erweiterung  
 Wählen Sie einen der Erweiterungsknoten in den erweiterten Knoten aus:  
  
1.  Klicken Sie auf **Neu**.  
  
2.  Geben Sie einen Namen und einen Typ ein.  
  
3.  Klicken Sie auf **OK**.  
  
4.  Die Erweiterung wird jetzt an der entsprechenden Stelle im Editor angezeigt.Wenn Sie z. B. eine Verhaltenselementerweiterung hinzufügen, wird sie in der Liste verfügbarer Erweiterungen angezeigt.  
  
#### Hostumgebung  
 Dieser Abschnitt ermöglicht Ihnen, Instanziierungseinstellungen für die Diensthostingumgebung zu definieren.  
  
### Erstellen einer Konfigurationsdatei mit dem Assistenten  
 Eine Möglichkeit zum Erstellen einer neuen Konfigurationsdatei ist die Verwendung des Assistenten für neue Dienstelemente.Der Assistent ermittelt die auf dem Computer installierten Diensttypen und andere Elemente, die mit [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] kompatibel sind, einschließlich COM\+\- und im Internet gehostete virtuelle Verzeichnisse, und lädt diese, um die Erstellung der Konfiguration zu straffen.  
  
#### Erstellen einer Konfigurationsdatei  
  
1.  Starten Sie den Service Configuration Editor, indem Sie im Befehlsfenster zum [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Installationsverzeichnis wechseln und dann `SvcConfigEditor.exe` eingeben.  
  
2.  Wählen Sie im Menü **Datei** die Option **Öffnen**, und klicken Sie auf **Ausführbare Datei**, **COM\+\-Dienst** oder **WebHosted\-Dienst**, je nachdem, welchen Konfigurationsdateityp Sie erstellen möchten.  
  
3.  Wechseln Sie im Dialogfeld **Öffnen** zu der Datei, für die Sie eine Konfigurationsdatei erstellen möchten, und doppelklicken Sie darauf.  
  
4.  Zeigen Sie im Menü **Datei** auf **Neues Element hinzufügen**, und klicken Sie auf **Dienst**.Der Assistent für neue Dienstelemente wird geöffnet.  
  
5.  Folgen Sie den Schritten im Assistenten, um den neuen Dienst zu erstellen.  
  
> [!NOTE]
>  Wenn Sie die NetPeerTcpBinding aus der vom Assistenten generierten Konfigurationsdatei verwendet möchten, müssen Sie manuell ein Bindungskonfigurationselement hinzufügen und das `mode`\-Attribut seines `security`\-Elements in "None" ändern.  
  
## Konfigurieren von COM\+  
 Mit dem Service Configuration Editor können Sie eine neue Konfigurationsdatei für eine vorhandene COM\+\-Anwendung erstellen oder eine vorhandene COM\+\-Konfiguration bearbeiten.Der **COM\-Vertrag**\-Knoten ist nur sichtbar, wenn der \<`comContract`\>\-Abschnitt in der Konfigurationsdatei vorhanden ist.  
  
### Erstellen einer neuen COM\+\-Konfigurationsdatei  
 Stellen Sie vor dem Erstellen einer neuen COM\+\-Konfiguration sicher, dass die COM\+\-Anwendung in den Komponentendiensten installiert und im globalen Assemblycache \(GAC\) registriert ist.  
  
1.  Wählen Sie **Datei** \-\> **Integrieren** \-\> **COM\+\-Anwendung**. Hierdurch wird die gerade geöffnete Datei geschlossen.Wenn die Datei noch nicht gespeicherte Daten enthält, wird ein Dialogfeld zum Speichern angezeigt.Der **COM\+\-Integrations\-Assistent** wird dann gestartet.  
  
2.  Wählen Sie auf der ersten Seite die COM\+\-Anwendung in der Struktur.Wenn die COM\+\-Anwendung nicht in der Struktur angezeigt wird, überprüfen Sie, ob sie in den Komponentendiensten installiert und im globalen Assemblycache \(GAC\) registriert ist.  
  
3.  Wählen Sie auf der nächsten Seite, welche Methode\(n\) Sie als [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienste verfügbar machen möchten.Alle unterstützten Methoden in der COM\+\-Anwendung werden angezeigt und sind standardmäßig ausgewählt.  
  
4.  Wählen Sie eine Hostingmethode aus.  
  
5.  Konfigurieren Sie andere Einstellungen entsprechend den Richtlinien des Assistenten.  
  
6.  Der Service Configuration Editor nutzt ComSvcConfig.exe im Hintergrund, um eine Konfigurationsdatei zu generieren.Nachdem dies abgeschlossen wurde, können Sie eine Zusammenfassung anzeigen und den Assistenten beenden.Die generierte Konfigurationsdatei wird geöffnet, damit Sie diese direkt bearbeiten können.  
  
### Bearbeiten einer vorhandenen COM\+\-Konfiguration  
  
1.  Wählen Sie **Datei** \-\> **Öffnen** \-\> **COM\+\-Dienst**.  
  
2.  Wählen Sie den zu bearbeitenden COM\+\-Dienst aus der Liste aus.  
  
3.  Bearbeiten Sie Konfigurationseinstellungen im **COM\-Verträge**\-Knoten.  
  
    > [!NOTE]
    >  Sie können eine Konfigurationsdatei mit COM\+\-Verträgen auch direkt öffnen und bearbeiten.  
  
## Sicherheit  
 Eine durch den Configuration Editor generierte Dienstkonfigurationsdatei ist nicht garantiert sicher.In der [Sicherheit](../../../docs/framework/wcf/feature-details/security.md)\-Dokumentation erfahren Sie, wie Sie [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienste sichern können.  
  
 Außerdem kann der Configuration Editor verwendet werden, um gültige [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Konfigurationselemente nur zu lesen und zu schreiben.Das Tool ignoriert schemakompatible, benutzerdefinierte Elemente.Es versucht außerdem nicht, diese Elemente aus der Konfigurationsdatei zu entfernen oder die Auswirkungen auf die bekannten [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Elemente zu ermitteln.Es ist die Aufgabe des Benutzers, zu ermitteln, ob diese Elemente eine Bedrohung für die Anwendung oder das System darstellen.