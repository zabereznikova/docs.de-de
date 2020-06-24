---
title: Configuration Editor-Tool (SvcConfigEditor.exe)
description: Erfahren Sie, wie Sie Einstellungen für WCF-Bindungen, Verhalten, Dienste und Diagnosen mit dem WCF-Dienstkonfigurations-Editor verwalten.
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files, creating
- configuration files
- Configuration file
- configuration file schema
ms.assetid: 2db21a57-5f64-426f-89df-fb0dc2d2def5
ms.openlocfilehash: 258437ff616b969d40feabbfff364ad2cc6b25bc
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247648"
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
> Der Editor kann kein Konfigurationselement aus der Konfigurationsdatei löschen, sobald das Element geändert wurde. Wenn Sie beispielsweise den Editor verwendet haben, um den Endpunktnamen auf eine nicht leere Zeichenfolge festzulegen, und diesen speichern, weist die Konfigurationsdatei folgenden Inhalt auf, wie im folgenden Beispiel gezeigt:
>
> `<endpoint binding="basicHttpBinding" name="somename" />`
>
> Wenn Sie versuchen, den Namen zu entfernen, indem Sie eine leere Zeichenfolge festlegen, und die Datei speichern, enthält die Konfigurationsdatei weiterhin das `name`-Attribut, wie im folgenden Beispiel gezeigt:
>
> `<endpoint binding="basicHttpBinding" name="" />`
>
> Um das Attribut zu löschen, müssen Sie das Element manuell mit einem anderen Text-Editor bearbeiten.
>
> Sie sollten besonders vorsichtig vorgehen, wenn Sie das `issueToken`-Element des `clientCredential`-Endpunktverhaltens verwenden. Vor allem das `address`-Attribut des `localIssuer`-Unterelements darf keine leere Zeichenfolge sein. Wenn Sie das `address`-Attribut mit dem Configuration Editor geändert haben und es vollständig entfernen möchten, sollten Sie dies mit einem anderen Tool als dem Editor durchführen. Andernfalls enthält das Attribut eine leere Zeichenfolge, und die Anwendung löst eine Ausnahme aus.

## <a name="using-the-configuration-editor"></a>Verwenden von Configuration Editor

Der Service Configuration Editor befindet sich in folgendem Windows SDK-Installationspfad:

C:\Programme\Microsoft SDKs\Windows\v6.0\Bin\SvcConfigEditor.exe

Nachdem Sie den Dienstkonfigurations-Editor gestartet haben, können Sie im Menü **Datei/öffnen** nach dem Dienst oder der Assembly suchen, die Sie verwalten möchten. Sie können Konfigurationsdateien direkt öffnen, nach WCF-/COM+-Diensten suchen und Konfigurationsdateien für über das Web gehostete Dienste öffnen.

Die Service Configuration Editor-Benutzeroberfläche ist in die folgenden Bereiche aufgeteilt:

- Strukturansichtsbereich, in dem die Konfigurationselemente links in einer Struktur angezeigt werden. Sie können in der Struktur Vorgänge durchführen, indem Sie mit der rechten Maustaste auf die Knoten klicken.

- Aufgabenbereich, der häufige Aufgaben für aktuelle Elemente links unten im Fenster anzeigt.

- Detailbereich, in dem ausführliche Einstellungen des rechts in der Strukturansicht ausgewählten Konfigurationsknotens angezeigt werden.

### <a name="opening-a-configuration-file"></a>Öffnen einer Konfigurationsdatei

1. Starten Sie den Dienstkonfigurations-Editor mithilfe eines Befehls Fensters, um zum WCF-Installationsverzeichnis zu navigieren, und geben Sie dann ein `SvcConfigEditor.exe` .

2. Wählen Sie im Menü **Datei** die Option **Öffnen** aus, und klicken Sie auf den Dateityp, den Sie verwalten möchten.

3. Navigieren Sie im Dialogfeld **Öffnen** zu der Datei, die Sie verwalten möchten, und doppelklicken Sie darauf.

Der Viewer folgt dem Pfad für den Konfigurationsmerge automatisch und erstellt eine Ansicht der zusammengeführten Konfiguration. Die tatsächliche Konfiguration eines nicht gehosteten Dienstanbieter ist beispielsweise eine Kombination aus Machine.config und App.config. Alle Änderungen werden auf die aktive Datei im SvcConfigEditor angewendet. Wenn Sie eine bestimmte Datei im Pfad für den Konfigurationsmerge bearbeiten möchten, öffnen Sie diese Datei direkt.

> [!NOTE]
> Configuration Editor lädt die gerade geöffnete Konfigurationsdatei erneut, wenn sie außerhalb des Editors geändert wurde. Wenn dies geschieht, gehen alle Änderungen verloren, die nicht dauerhaft im Editor gespeichert wurden. Wenn das erneute Laden häufig auftritt, liegt dies meist an einem Dienst, der kontinuierlich auf die Konfigurationsdatei zugreift, z. B. eine im Hintergrund ausgeführte Antivirensoftware. Um dies zu beheben, müssen Sie sicherstellen, dass Configuration Editor der einzige Prozess ist, der auf die Datei zugreifen kann, wenn sie geöffnet ist.

### <a name="services"></a>Dienste

Der Knoten **Dienste** zeigt alle Dienste an, die zurzeit in der Konfigurationsdatei zugewiesen sind. Jeder unter Knoten in der Struktur entspricht einem Unterelement des <`services`>-Elements in der Konfigurationsdatei.

Wenn Sie auf den Knoten **Dienste** klicken, können Sie auf der Seite Dienst Zusammenfassung im **Detail** Bereich Aufgaben anzeigen oder ausführen.

#### <a name="creating-a-new-service-configuration"></a>Erstellen einer neuen Dienstkonfiguration

Sie können eine neue Dienstkonfiguration auf folgende Weise erstellen:

- Mithilfe eines Assistenten: Klicken Sie auf den Link **neuen Dienst erstellen...** im Aufgabenbereich oder auf der Zusammenfassungs Seite, um den Assistenten zu starten. Sie können dies auch im Menü **Datei** > **Neues Element hinzufügen**.

- Manuell erstellen: Sie können mit der rechten Maustaste auf den Knoten **Dienste** klicken und **neuer Dienst**auswählen.

#### <a name="creating-a-new-service-endpoint-configuration"></a>Erstellen einer neuen Dienstendpunkt-Konfiguration

Sie können eine neue Dienstendpunkt-Konfiguration auf folgende Weise erstellen:

- Erstellen mithilfe eines Assistenten: Klicken Sie auf den Link **neuen Dienst Endpunkt erstellen...** im Aufgabenbereich oder auf der Zusammenfassungs Seite, um den Assistenten zu starten. Sie können dies auch im Menü **Datei** > **Neues Element hinzufügen**.

- Manuelles Erstellen: Nachdem Sie einen Dienst erstellt haben, können Sie mit der rechten Maustaste auf den Knoten **Endpunkte** klicken und dann "**neuer Dienst Endpunkt**" auswählen.

#### <a name="editing-a-service-configuration"></a>Bearbeiten einer Dienstkonfiguration

1. Klicken Sie auf einen **Dienst** Knoten.

2. Bearbeiten Sie die Einstellungen in den Eigenschaftenrastern.

#### <a name="editing-a-service-endpoint-configuration"></a>Bearbeiten einer Dienstendpunkt-Konfiguration

1. Klicken Sie auf einen **Dienst Endpunkt** -Knoten.

2. Bearbeiten Sie die Einstellungen in den Eigenschaftenrastern.

#### <a name="adding-a-base-address"></a>Hinzufügen einer Basisadresse

1. Klicken Sie auf den **Host** Knoten.

2. Klicken Sie im **Quellen-Editor für OData** im Abschnitt " **Basisadressen** ".

3. Geben Sie den Basisadressen-URI im Dialogfeld ein.

4. Klicken Sie auf **OK**.

> [!NOTE]
> Der Wert von kann [\<baseAddressPrefixFilters>](../configure-apps/file-schema/wcf/baseaddressprefixfilters.md) in diesem Tool nicht bearbeitet werden. Um dieses Element hinzuzufügen oder zu ändern, sollten Sie einen Text-Editor oder Visual Studio verwenden.

### <a name="client"></a>Client

Der **Client** Knoten zeigt alle Client Endpunkte in der Konfigurationsdatei an. Jeder unter Knoten in der Struktur entspricht einem Unterelement des <`client`>-Elements in der Konfigurationsdatei.

Wenn Sie auf den **Client** Knoten klicken, können Sie auf der **Seite Client Zusammenfassung** im **Detail**Bereich Aufgaben anzeigen oder ausführen.

#### <a name="creating-a-new-client-endpoint-configuration"></a>Erstellen einer neuen Clientendpunkt-Konfiguration

Sie können eine neue Clientendpunkt-Konfiguration auf folgende Weise erstellen:

- Create by Wizard: Klicken Sie auf den Link **neuen Client erstellen...** im **Aufgaben** Bereich links unten im Fenster oder auf der **Zusammenfassungs Seite** , um den Assistenten zu starten. Sie können dies auch im Menü **Datei** > **Neues Element hinzufügen**. Der Assistent fordert Sie auf, auf den Speicherort der Dienstkonfiguration zu zeigen, über den die Clientkonfiguration generiert wird. Sie können dann den Dienstendpunkt auswählen, mit dem eine Verbindung hergestellt werden soll.

- Manuell erstellen: Klicken Sie mit der rechten Maustaste auf den Knoten **Endpunkte** unter **Client**, und wählen Sie **neuer Client Endpunkt**aus.

#### <a name="editing-a-client-endpoint-configuration"></a>Bearbeiten einer Clientendpunkt-Konfiguration

1. Klicken Sie auf einen **Client Endpunkt** -Knoten.

2. Bearbeiten Sie die Einstellungen in den Eigenschaftenrastern.

### <a name="standard-endpoint"></a>Standardendpunkt

Standardendpunkte sind spezialisierte Endpunkte, bei denen einer oder mehrere Aspekte der Adresse, des Vertrags und des Bindungssatzes auf die Standardwerte festgelegt sind.

Diese Konfigurationseinstellungen werden im **Standard Endpunkt** -Knoten gespeichert. Der Knoten **Standard Endpunkt** zeigt alle Standard Endpunkt Einstellungen in der Konfigurationsdatei an. Jeder unter Knoten in der Struktur entspricht einem Unterelement im- `<standardEndpoints>` Element in der Konfigurationsdatei.

Wenn Sie auf den **Standard Endpunkt** -Knoten klicken, können Sie auf der Seite Standard-Endpunkt **Zusammenfassung** im **Detail**Bereich Aufgaben anzeigen oder ausführen.

#### <a name="creating-a-new-standard-endpoint-configuration"></a>Erstellen einer neuen Standardendpunktkonfiguration

Sie können eine neue Standardendpunktkonfiguration auf folgende Weise erstellen:

- Klicken Sie mit der rechten Maustaste auf den Knoten **Standard Endpunkt** , und wählen Sie **neue Konfiguration des Standard Endpunkts aus.** Wählen Sie den Bindungstyp im Dialogfeld aus, und klicken Sie auf **OK**.

- Wählen Sie den Knoten **Standard Endpunkt** aus, und klicken Sie auf **neue standardend Punkt Konfiguration...** im **Aufgaben** Bereich links unten im Fenster.

Im Dialogfeld **Erstellen eines neuen Standard Endpunkts** werden alle registrierten standardend Punkt Typen angezeigt.

#### <a name="viewing-and-editing-a-standard-endpoint-configuration"></a>Anzeigen und Bearbeiten einer Standardendpunktkonfiguration

Sie können eine Standardendpunktkonfiguration auf die folgende Weise zum Anzeigen und Bearbeiten öffnen:

- Klicken Sie, um den **Standard Endpunkt** Knoten zu erweitern, und klicken Sie auf den entsprechenden Endpunkt unter Knoten.

- Klicken Sie auf den Knoten **Standard Endpunkt** , und klicken Sie im Detail Bereich auf den entsprechenden Endpunkt.

Attribute für den Endpunkt werden zur Bearbeitung im rechten Bereich angezeigt.

#### <a name="deleting-a-standard-endpoint-configuration"></a>Löschen einer Standardendpunktkonfiguration

Sie können eine Standardendpunktkonfiguration auf folgende Weise löschen:

- Klicken Sie, um den **Standard Endpunkt** Knoten zu erweitern, und klicken Sie mit der rechten Maustaste auf den entsprechenden Endpunkt unter Knoten. Verwenden Sie den Kontext Befehl **Standard Endpunkt Konfiguration löschen** , um den Endpunkt zu löschen.

- Klicken Sie auf den Knoten **Standard Endpunkt** . Klicken Sie im **Aufgaben** Bereich auf **Standard Endpunkt Konfiguration löschen**.

Wenn der Standard Endpunkt verwendet wird, wird eine Warnmeldung angezeigt, wenn Sie versuchen, Sie zu löschen: **der Standard Endpunkt wird verwendet. Wenn Sie Sie jetzt löschen, achten Sie darauf, alle Verweise in anderen Teilen der Konfiguration zu löschen (z. b. im Dienst Endpunkt oder Client Endpunkt). Andernfalls ist die Konfiguration ungültig und kann nicht das nächste Mal geöffnet werden. Möchten Sie den Standard Endpunkt wirklich löschen? "**

### <a name="binding"></a>Bindung

Bindungskonfigurationen werden zum Konfigurieren von Bindungen auf Endpunkten verwendet. Diese Konfigurationseinstellungen werden im **Bindungs** Knoten gespeichert. Endpunkte verweisen anhand des Namens auf Bindungskonfigurationen, und mehrere Endpunkte können auf eine einzelne Bindungskonfiguration verweisen.

Der Knoten **Bindungen** zeigt alle Bindungs Einstellungen in der Konfigurationsdatei an. Jeder unter Knoten in der Struktur entspricht einem Unterelement im <`bindings`>-Element in der Konfigurationsdatei.

Wenn Sie auf den Knoten **Bindungen** klicken, können Sie auf der **Seite Bindungs Zusammenfassung** im **Detail**Bereich Aufgaben anzeigen oder ausführen.

#### <a name="creating-a-new-binding-configuration"></a>Erstellen einer neuen Bindungskonfiguration

Sie können eine neue Bindungskonfiguration auf folgende Weise erstellen:

- Klicken Sie mit der rechten Maustaste auf den Knoten **Bindungen** , und wählen Sie **neue Bindungs Konfiguration**... Wählen Sie den Bindungstyp im Dialogfeld aus, und klicken Sie auf **OK**.

- Wählen Sie den Knoten **Bindungen** aus, und klicken Sie auf **neue Bindungs Konfiguration**... im **Aufgaben** Bereich links unten im Fenster.

- Klicken Sie auf der Seite Dienst-oder Client Zusammenfassung im Feld **Bindungs Konfiguration** auf **zum Erstellen klicken** , um eine Bindungs Konfiguration für den entsprechenden Endpunkt zu erstellen.

#### <a name="adding-binding-element-extensions-to-a-custom-binding"></a>Hinzufügen von Bindungselementerweiterungen zu einer benutzerdefinierten Bindung

1. Wählen Sie die Bindung aus, der Sie ein Erweiterungselement hinzufügen möchten.

2. Klicken Sie auf **Hinzufügen**.

3. Wählen Sie aus der Liste der verfügbaren Erweiterungen die Bindungselementerweiterung aus, die Sie hinzufügen möchten. Sie können mehrere Elemente auswählen, indem Sie die STRG-TASTE gedrückt halten.

4. Klicken Sie auf **Hinzufügen**.

#### <a name="adjusting-the-extension-position-in-a-custom-binding"></a>Anpassen der Erweiterungsposition in einer benutzerdefinierten Bindung

Eine benutzerdefinierte Bindung ist eine Auflistung von Bindungselementen, die einen Stapel bilden. Jedes Bindungselement auf dem Stapel verfügt über eigene Konfigurationseinstellungen. Die Reihenfolge der Bindungselementerweiterungen in einer benutzerdefinierten Bindung gibt ihre Positionen im Stapel an. Elemente oben im Stapel werden zuerst übernommen. So ändern Sie die Reihenfolge

1. Wählen Sie den benutzerdefinierten Bindungsknoten aus.

2. Wählen Sie im Abschnitt **Bindungs Element-Erweiterungs Position** ein Bindungs Erweiterungs Element aus.

3. Verwenden Sie die nach- **oben** -oder **nach-unten** -Taste auf der linken Seite der Liste, um die Position des ausgewählten Elements zu ändern.

#### <a name="editing-the-configuration-of-binding-element-extensions-in-a-custom-binding"></a>Bearbeiten der Bindungselementerweiterungs-Konfiguration in einer benutzerdefinierten Bindung

1. Wählen Sie den Bindungsknoten in der Struktur aus.

2. Wählen Sie die benutzerdefinierte Bindung, die das zu bearbeitende Element enthält.

3. Wählen Sie die Bindungselementerweiterung aus, die Sie bearbeiten möchten. Die Einstellungen des Elements werden im rechten Bereich angezeigt, in dem sie bearbeitet werden können.

### <a name="diagnostics"></a>Diagnose

Der **Diagnose** Knoten zeigt alle Diagnose Einstellungen in der Konfigurationsdatei an. Sie ermöglicht es Ihnen, Leistungsindikatoren ein-oder auszuschalten, Windows-Verwaltungsinstrumentation (WMI) zu aktivieren oder deaktivieren, die WCF-Ablauf Verfolgung zu konfigurieren und die WCF-Nachrichten Protokollierung zu konfigurieren. Die Einstellungen im **Diagnose** Knoten entsprechen dem `system.diagnostics` Abschnitt <> und im Abschnitt in `<diagnostics>` `<system.serviceModel>` der Konfigurationsdatei.

Wenn Sie auf den **Diagnose** Knoten klicken, können Sie im **Detail**Bereich auf der Seite "Diagnose **Zusammenfassung** " Aufgaben anzeigen oder ausführen.

#### <a name="configuring-performance-counters-and-wmi"></a>Konfigurieren von Leistungsindikatoren und WMI

1. Klicken Sie auf den Knoten **Diagnose** .

2. Klicken Sie auf **Leistungsindikatoren umschalten**. Der Leistungsindikator verfügt über drei Zustände: Aus (Standard), ServiceOnly und Alles. Wenn Sie auf den Link klicken, wird diese Einstellung auf einen der drei Zustände festgelegt.

#### <a name="configuring-wmi-provider"></a>Konfigurieren eines WMI-Anbieters

1. Klicken Sie auf den Knoten **Diagnose** .

2. Um den WMI-Anbieter zu aktivieren, klicken Sie auf den Link **WMI-Anbieter aktivieren** .

#### <a name="enabling-wcf-tracing"></a>Aktivieren von WCF-Ablaufverfolgung

Sie können eine WCF-Ablaufverfolgungsdatei mit Standardeigenschaften erstellen oder eine benutzerdefinierte Ablaufverfolgungsdatei einrichten.

1. Klicken Sie auf den Knoten **Diagnose** .

2. Klicken Sie auf Ablauf **Verfolgung aktivieren**.

3. Klicken Sie auf den Link Ablauf **Verfolgungs Ebene** , um die Ablauf Verfolgungs Ebene anzupassen. Es gibt sechs Ablaufverfolgungsebenen: Off, Critical, Error, Warning, Information und Verbose. Mithilfe der Option **Aktivitäts Ablauf Verfolgung** und **Aktivität propagieren** können Sie die Funktion für die WCF-Aktivitäts Ablauf Verfolgung verwenden.

4. Klicken Sie auf den Namen des Ablaufverfolgungslisteners, um die Ablaufverfolgungsdatei und die Optionen festzulegen.

#### <a name="enabling-wcf-logging"></a>Aktivieren der WCF-Protokollierung

Sie können eine WCF-Ablaufverfolgungsdatei mit Standardeigenschaften erstellen oder eine benutzerdefinierte Ablaufverfolgungsdatei einrichten.

1. Klicken Sie auf den Knoten **Diagnose** .

2. Klicken Sie auf **Nachrichten Protokollierung aktivieren**.

3. Klicken Sie auf den Link **Protokollebene** , um die Protokollebene anzupassen. Es gibt drei Protokollebenen: Fehlerhaft, Dienst und Transport.

4. Klicken Sie auf den Namen des Listeners, um die Protokolldatei und die Optionen festzulegen.

> [!NOTE]
> Wenn Sie möchten, dass die Ablauf Verfolgungs-und Nachrichten Protokolle automatisch geleert werden, wenn die Anwendung geschlossen wird, aktivieren Sie die Option **Auto Flush** .

Auf der Seite " **Diagnose** **Zusammenfassung** " können Sie die gängigsten Aufgaben beim Konfigurieren der Diagnose ausführen. Wenn Sie jedoch die **Listener-und** Quellen Einstellungen manuell bearbeiten möchten, müssen Sie den **Diagnose** Knoten erweitern und die Einstellungen im Knoten **Nachrichten Protokollierung**, Listener und **Quellen** bearbeiten.

#### <a name="enabling-wcf-custom-tracing-or-message-logging"></a>Aktivieren von benutzerdefinierter WCF-Ablaufverfolgung oder Nachrichtenprotokollierung

1. Klicken Sie auf den **Diagnose** Knoten, und erweitern Sie ihn.

2. Klicken Sie **mit der rechten** Maustaste auf den Knoten Listener, und wählen Sie **neuer Listener**

3. Geben Sie den Namen der Ablauf Verfolgungs Datei im **initdata** -Feld ein. Sie können auf die "..." , um zu einem Pfad zu navigieren.

4. Wenn Sie auf die Zeile **tytzame** klicken, wird ein "..." angezeigt. gedrückt. Klicken Sie auf diese Schaltfläche, um den **Typ**des Ablaufverfolgungslistener zu öffnen, mit dem Sie vorkonfigurierte Ablaufverfolgungslistener suchen können

5. Beachten Sie den Abschnitt " **Quelle** ". Klicken Sie in diesem Abschnitt auf **Hinzufügen** , um ein Dialogfeld mit einem Dropdown Menü zu öffnen, in dem verfügbare Ablauf Verfolgungs Quellen aufgelistet sind. Wählen Sie eine Ablauf Verfolgungs Quelle aus und klicken Sie auf **OK**

6. Klicken Sie zum Bearbeiten der Einstellungen für die Nachrichten Protokollierung auf den Knoten **Nachrichten Protokollierung** . Sie können die Einstellungen im Eigenschaftenraster bearbeiten.

### <a name="advanced"></a>Fortgeschrittene

#### <a name="behaviors"></a>Verhalten

Der Knoten **Verhalten** zeigt die Verhalten an, die zurzeit in der Konfigurationsdatei definiert sind.

Verhaltenskonfigurationen werden verwendet, um Verhalten von Endpunkten und Diensten zu konfigurieren. Diese Konfigurationseinstellungen werden im **erweiterten** Knoten unter **Dienst Verhalten** und **Endpunkt Verhalten**gespeichert. Dienstverhalten werden von Diensten verwendet, Endpunktverhalten dagegen von Endpunkten.

Verhalten sind eine Auflistung von Erweiterungselementen für einen Stapel. Das Element oben im Stapel wird zuerst übernommen. Jedes Erweiterungselement kann über eine eigene Konfiguration verfügen.

##### <a name="creating-a-new-behavior-configuration"></a>Erstellen einer neuen Verhaltenskonfiguration

Sie können eine neue Verhaltenskonfiguration auf eine der folgenden Weisen erstellen:

- Klicken Sie mit der rechten Maustaste auf einen der Verhaltens Knoten, und wählen Sie**neue Verhaltens Konfiguration...**

- Wählen Sie einen der Verhaltens Knoten aus, und klicken Sie auf die **neue Verhaltens Konfiguration**... im **Aufgaben** Bereich links unten im Fenster.

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

3. Wählen Sie im Abschnitt **Verhaltens Element-Erweiterungs Position** ein Verhaltens Erweiterungs Element aus.

4. Verwenden Sie die nach- **oben** -oder **nach-unten** -Taste auf der linken Seite der Liste, um die Position des ausgewählten Elements zu ändern.

##### <a name="editing-the-configuration-of-behavior-element-extensions"></a>Bearbeiten der Konfiguration von Verhaltenselementerweiterungen

1. Wählen Sie einen der Verhaltensknoten in der Struktur aus.

2. Wählen Sie das Verhalten aus, das das zu bearbeitende Element enthält.

3. Wählen Sie die Verhaltenselementerweiterung aus, die Sie bearbeiten möchten. Die Einstellungen des Elements werden im rechten Bereich angezeigt, wo sie bearbeitet werden können.

#### <a name="protocolmapping"></a>ProtocolMapping

Mit diesem Abschnitt können Sie Standardbindungstypen für andere Protokolle, wie z. B. http, tcp, MSMQ oder net.pipe, über die definierte Zuordnung zwischen Protokolladressschemas und den möglichen Bindungen festlegen. Sie können darüber hinaus anderen Protokollen neue Zuordnungen hinzufügen.

#### <a name="extensions"></a>Erweiterungen

Neue Bindungs Erweiterungen, Bindungs Element Erweiterungen, standardend Punkt Erweiterungen und Verhaltens Erweiterungen können für die Verwendung in der WCF-Konfiguration registriert werden. Erweiterungen sind Name-/Typpaare. Der Name definiert den Namen der Erweiterung in der Konfiguration, wohingegen der Typ die Erweiterung implementiert. Es gibt vier Erweiterungstypen:

- Bindungserweiterungen definieren einen gesamten Bindungstyp. Beispiel: `basicHttpBinding`.

- Bindungselementerweiterungen definieren ein Element einer Bindung. Beispiel: `textMessageEncoding`.

- Standardendpunkterweiterungen definieren einen gesamten Standardendpunkt. Beispiel: `discoveryEndpoint`.

- Verhaltenselementerweiterungen definieren ein Element eines Verhaltens. Beispiel: `clientVia`.

 Erweiterungen, die in einer Konfiguration registriert wurden, können wie jede andere WCF-Komponente des gleichen Typs verwendet werden.

##### <a name="adding-a-new-extension"></a>Hinzufügen einer neuen Erweiterung

Wählen Sie einen der Erweiterungsknoten in den erweiterten Knoten aus:

1. Klicken Sie auf **Neu**.

2. Geben Sie einen Namen und einen Typ ein.

3. Klicken Sie auf **OK**.

4. Die Erweiterung wird jetzt an der entsprechenden Stelle im Editor angezeigt. Wenn Sie z.&#160;B. eine Verhaltenselementerweiterung hinzufügen, wird sie in der Liste verfügbarer Erweiterungen angezeigt.

#### <a name="hosting-environment"></a>Hostumgebung

Dieser Abschnitt ermöglicht Ihnen, Instanziierungseinstellungen für die Diensthostingumgebung zu definieren.

### <a name="creating-a-configuration-file-using-the-wizard"></a>Erstellen einer Konfigurationsdatei mit dem Assistenten

Eine Möglichkeit zum Erstellen einer neuen Konfigurationsdatei ist die Verwendung des Assistenten für neue Dienstelemente. Der Assistent ermittelt die installierten Dienst Typen und andere Elemente, die mit WCF auf dem Computer kompatibel sind, einschließlich com+-und im Internet gehosteter virtueller Verzeichnisse, und lädt diese, um die Erstellung der Konfiguration zu vereinfachen.

#### <a name="creating-a-configuration-file"></a>Erstellen einer Konfigurationsdatei

1. Starten Sie den Dienstkonfigurations-Editor mithilfe eines Befehls Fensters, um zum WCF-Installationsverzeichnis zu navigieren, und geben Sie dann ein `SvcConfigEditor.exe` .

2. Wählen Sie im Menü **Datei** die Option **Öffnen** aus, und klicken Sie abhängig vom Typ der Konfigurationsdatei, die Sie erstellen möchten, auf **ausführbare Datei**, **com+-Dienst**oder **webgehosteter Dienst**.

3. Navigieren Sie im Dialogfeld **Öffnen** zu der spezifischen Datei, für die Sie eine Konfigurationsdatei erstellen möchten, und doppelklicken Sie darauf.

4. Zeigen Sie im Menü **Datei** auf **Neues Element hinzufügen** , und klicken Sie auf **Dienst**. Der Assistent für neue Dienstelemente wird geöffnet.

5. Folgen Sie den Schritten im Assistenten, um den neuen Dienst zu erstellen.

> [!NOTE]
> Wenn Sie die NetPeerTcpBinding aus der vom Assistenten generierten Konfigurationsdatei verwendet möchten, müssen Sie manuell ein Bindungskonfigurationselement hinzufügen und das `mode`-Attribut seines `security`-Elements in „None“ ändern.

## <a name="configuring-com"></a>Konfigurieren von COM+

Mit dem Service Configuration Editor können Sie eine neue Konfigurationsdatei für eine vorhandene COM+-Anwendung erstellen oder eine vorhandene COM+-Konfiguration bearbeiten. Der **com-Vertrags** Knoten ist nur sichtbar, wenn der `comContract` Abschnitt <> in der Konfigurationsdatei vorhanden ist.

### <a name="creating-a-new-com-configuration"></a>Erstellen einer neuen COM+-Konfigurationsdatei

Stellen Sie vor dem Erstellen einer neuen COM+-Konfiguration sicher, dass die COM+-Anwendung in den Komponentendiensten installiert und im globalen Assemblycache (GAC) registriert ist.

1. Wählen Sie das Menü **Datei** aus, > **Integrate**  ->  **com+-Anwendung integrieren.** Hierdurch wird die gerade geöffnete Datei geschlossen. Wenn die Datei noch nicht gespeicherte Daten enthält, wird ein Dialogfeld zum Speichern angezeigt. Anschließend wird der **com+-Integrations-Assistent** gestartet.

2. Wählen Sie auf der ersten Seite die COM+-Anwendung in der Struktur. Wenn die COM+-Anwendung nicht in der Struktur angezeigt wird, überprüfen Sie, ob sie in den Komponentendiensten installiert und im globalen Assemblycache (GAC) registriert ist.

3. Wählen Sie auf der nächsten Seite, welche Methode(n) Sie als WCF-Dienste verfügbar machen möchten. Alle unterstützten Methoden in der COM+-Anwendung werden angezeigt und sind standardmäßig ausgewählt.

4. Wählen Sie eine Hostingmethode aus.

5. Konfigurieren Sie andere Einstellungen entsprechend den Richtlinien des Assistenten.

6. Der Service Configuration Editor nutzt ComSvcConfig.exe im Hintergrund, um eine Konfigurationsdatei zu generieren. Nachdem dies abgeschlossen wurde, können Sie eine Zusammenfassung anzeigen und den Assistenten beenden. Die generierte Konfigurationsdatei wird geöffnet, damit Sie diese direkt bearbeiten können.

### <a name="editing-an-existing-com-configuration"></a>Bearbeiten einer vorhandenen COM+-Konfiguration

1. Wählen Sie das Menü **Datei** aus, > Sie den **Open**  ->  **com+-Dienst**öffnen...

2. Wählen Sie den zu bearbeitenden COM+-Dienst aus der Liste aus.

3. Bearbeiten Sie die Konfigurationseinstellungen im Knoten **com-Verträge** .

    > [!NOTE]
    > Sie können eine Konfigurationsdatei mit COM+-Verträgen auch direkt öffnen und bearbeiten.

## <a name="security"></a>Sicherheit

Eine durch den Configuration Editor generierte Dienstkonfigurationsdatei ist nicht garantiert sicher. Informationen zum Sichern Ihrer WCF-Dienste finden Sie in der Dokumentation zur [Sicherheit](./feature-details/security.md) .

Außerdem kann der Configuration Editor nur verwendet werden, um gültige WCF-Konfigurationselemente zu lesen und zu schreiben. Das Tool ignoriert schemakompatible, benutzerdefinierte Elemente. Es versucht außerdem nicht, diese Elemente aus der Konfigurationsdatei zu entfernen oder die Auswirkungen auf die bekannten WCF-Elemente zu ermitteln. Es ist die Aufgabe des Benutzers, zu ermitteln, ob diese Elemente eine Bedrohung für die Anwendung oder das System darstellen.
