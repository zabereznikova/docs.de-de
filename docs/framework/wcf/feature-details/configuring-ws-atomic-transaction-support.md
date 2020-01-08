---
title: Konfigurieren der WS-AtomicTransaction-Unterstützung
ms.date: 03/30/2017
helpviewer_keywords:
- WS-AT protocol [WCF], configuring WS-Atomic Transaction
ms.assetid: cb9f1c9c-1439-4172-b9bc-b01c3e09ac48
ms.openlocfilehash: 804e22c79c328a2ae96d8f1cb817d0aea2b0c25d
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/29/2019
ms.locfileid: "75544730"
---
# <a name="configure-ws-atomic-transaction-support"></a>Konfigurieren der WS-Atomic Transaction-Unterstützung

In diesem Thema wird beschrieben, wie Sie die WS-AtomicTransaction (WS-AT)-Unterstützung mit dem WS-AT-Konfigurationshilfsprogramm konfigurieren können.

## <a name="use-the-ws-at-configuration-utility"></a>Verwenden des WS-AT-Konfigurations Hilfsprogramms

Das WS-AT-Konfigurationshilfsprogramm (wsatConfig.exe) wird zum Konfigurieren von WS-AT-Einstellungen verwendet. Zum Aktivieren des WS-AT-Protokolldienstes müssen Sie mithilfe des Konfigurationshilfsprogramms den HTTPS-Anschluss für WS-AT konfigurieren, ein X.509-Zertifikat an den HTTPS-Anschluss binden und autorisierte Partnerzertifikate durch Angabe von Zertifikatantragstellernamen oder Fingerabdrücken konfigurieren. Mithilfe des Konfigurationshilfsprogramms können Sie außerdem den Modus für die Ablaufverfolgung auswählen und standardmäßige ausgehende and maximale eingehende Transaktionstimeouts festlegen.

Der Zugriff auf die Funktionen dieses Tools ist über ein Snap-In auf der Eigenschaftenseite der Microsoft Management Console (MMC) in der Komponentendienste-Managementkonsole oder aus einem Befehlszeilenfenster möglich. Konfigurieren Sie die WS-AT-Unterstützung auf dem lokalen Computer über das Befehlszeilenfenster, und konfigurieren Sie Einstellungen auf lokalen und Remotecomputern über das MMC-Snap-In.

Auf das Befehlszeilenfenster kann in dem Windows SDK-Installationspfad "%WINDIR%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation" zugegriffen werden.

Weitere Informationen zum Befehlszeilen Tool finden Sie unter [WS-AtomicTransaction-Konfigurations Hilfsprogramm (wsatConfig. exe)](../../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md).

Wenn Sie [!INCLUDE[wxp](../../../../includes/wxp-md.md)] oder Windows Server 2003 ausführen, können Sie auf das MMC-Snap-in zugreifen, indem Sie zu **Systemsteuerung/Verwaltung/Komponenten Dienste**navigieren, mit der rechten Maustaste auf **Arbeitsplatz**klicken und **Eigenschaften**auswählen. Dies ist die gleiche Position, an der Sie den Microsoft Distributed Transaction Coordinator (MSDTC) konfigurieren können. Optionen, die für die Konfiguration verfügbar sind, werden auf der Registerkarte **WS-AT** gruppiert. Wenn Sie Windows Vista oder Windows Server 2008 ausführen, finden Sie das MMC-Snap-in. Klicken Sie hierzu auf die Schaltfläche **Start** , und geben Sie `dcomcnfg.exe` in das **Suchfeld** ein. Wenn die MMC geöffnet ist, navigieren Sie zum Knoten **My computer\verteilte transaktions\lokale DTC** , klicken Sie mit der rechten Maustaste, und wählen Sie **Eigenschaften**aus. Optionen, die für die Konfiguration verfügbar sind, werden auf der Registerkarte **WS-AT** gruppiert.

Weitere Informationen zum Snap-in finden Sie im [MMC-Snap-in "WS-AtomicTransaction-Konfiguration](../../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md)".

Zum Aktivieren der Benutzeroberfläche des Tools müssen Sie zuerst die Datei WsatUI.dll im folgenden Pfad registrieren:

%PROGRAMFILES%\Microsoft SDKs\Windows\v6.0\Bin

Führen Sie zum Registrieren des Produkts den folgenden Befehl in einem Eingabeaufforderungsfenster aus:

`regasm.exe /codebase WsatUI.dll`

## <a name="enable-ws-at"></a>Aktivieren von WS-AT

Verwenden Sie zum Aktivieren des WS-AT-Protokolldienstes in MSDTC unter Nutzung von Anschluss 443 und eines X.509-Zertifikats mit einem privaten Schlüssel im Speicher des lokalen Computers das Tool wsatConfig.exe mit dem folgenden Befehl.

`WsatConfig.exe –network:enable –port:8443 –endpointCert:<machine|"Issuer\SubjectName"> -accountsCerts:<thumbprint|"Issuer\SubjectName"> -restart`

Ersetzen Sie die jeweiligen Parameter durch für Ihre Umgebung relevante Werte.

Verwenden Sie zum Deaktivieren des WS-AT-Protokolldienstes in MSDTC das Tool wsatConfig.exe mit dem folgenden Befehl.

`WsatConfig.exe –network:disable -restart`

## <a name="configure-trust-between-two-machines"></a>Konfigurieren der Vertrauensstellung zwischen zwei Computern

Der WS-AT-Protokolldienst erfordert, dass der Administrator einzelne Konten für die Teilnahme an verteilten Transaktionen explizit autorisiert. Als Administrator für zwei Computer können Sie beide Computer so konfigurieren, dass sie durch Austausch der richtigen Zertifikate zwischen den Computern, Installation in den richtigen Zertifikatspeichern und Verwenden des Tools wsatConfig.exe zum Hinzufügen des Zertifikats jedes Computers zur Liste autorisierter Teilnehmerzertifikate des anderen Computers eine gegenseitige Vertrauensstellung einrichten. Dieser Schritt ist erforderlich, um verteilte Transaktionen zwischen zwei Computern auszuführen, die WS-AT verwenden.

Im folgenden Beispiel werden die Schritte zum Einrichten einer Vertrauensstellung zwischen zwei Computern, A und B, beschrieben.

### <a name="create-and-export-certificates"></a>Erstellen und Exportieren von Zertifikaten

Für dieses Verfahren ist das MMC-Zertifikat-Snap-In erforderlich. Öffnen Sie zum Zugriff auf das Snap-In das Menü "Start/Ausführen", geben Sie "mmc" im Eingabefeld ein, und klicken Sie auf "OK". Navigieren Sie dann im Fenster **Konsole1** zum **Datei-/ausfüger-Snap** -in, klicken Sie auf Hinzufügen, und wählen Sie in der Liste **Verfügbare eigenständige** Snap-Ins die Option **Zertifikate** aus. Wählen Sie schließlich zu verwaltende **Computer Konto** aus, und klicken Sie auf **OK**. Der Knoten **Zertifikate** wird in der Snap-In-Konsole angezeigt.

Sie müssen bereits die erforderlichen Zertifikate besitzen, um Vertrauensstellungen einzurichten. Informationen zum Erstellen und Installieren neuer Zertifikate vor den folgenden Schritten finden Sie unter Gewusst [wie: Erstellen und installieren temporärer Client Zertifikate in WCF während der Entwicklung](https://go.microsoft.com/fwlink/?LinkId=158925).

1. Importieren Sie auf Computer A mit dem MMC-Zertifikat-Snap-In das vorhandene Zertifikat (certA) in den Speicher LocalMachine\MY (Persönlicher Knoten) und LocalMachine\ROOT (Knoten der vertrauenswürdigen Stammzertifizierungsstelle). Um ein Zertifikat in einen bestimmten Knoten zu importieren, klicken Sie mit der rechten Maustaste auf den Knoten, und wählen Sie **Alle Tasks/Importieren**aus.

2. Erstellen oder erhalten Sie auf Computer B mit dem MMC-Zertifikat-Snap-In ein Zertifikat (certB) mit einem privaten Schlüssel, und importieren Sie es in den Speicher LocalMachine\MY (Persönlicher Knoten) und LocalMachine\ROOT (Knoten der vertrauenswürdigen Stammzertifizierungsstelle).

3. Exportieren Sie den öffentlichen Schlüssel von certA zu einer Datei, wenn noch nicht geschehen.

4. Exportieren Sie den öffentlichen Schlüssel von certB zu einer Datei, wenn noch nicht geschehen.

### <a name="establish-mutual-trust-between-machines"></a>Einrichten von gegenseitiger Vertrauensstellung zwischen Computern

1. Importieren Sie auf Computer A die Dateidarstellung von certB in die Speicher LocalMachine\MY und LocalMachine\ROOT. Damit wird deklariert, dass Computer A certB für die Kommunikation vertraut.

2. Importieren Sie auf Computer B die Datei von certA in die Speicher LocalMachine\MY und LocalMachine\ROOT. Dies bedeutet, dass Computer B certA für die Kommunikation vertraut.

Mit diesen Schritten wurde eine Vertrauensstellung zwischen den beiden Computern eingerichtet, und sie können für die Kommunikation mit WS-AT konfiguriert werden.

### <a name="configure-msdtc-to-use-certificates"></a>Konfigurieren von MSDTC für die Verwendung von Zertifikaten

Da der WS-AT-Protokolldienst als Client und Server fungiert, muss er eingehende Verbindungen abhören und ausgehende Verbindungen initiieren. Sie müssen daher MSDTC so konfigurieren, dass bekannt ist, welche Zertifikate bei der Kommunikation mit externen Programmen verwendet werden müssen und welche Zertifikate beim Annehmen eingehender Kommunikation autorisiert werden müssen.

Sie können dies mit dem MMC-WS-AT-Snap-In konfigurieren. Weitere Informationen zu diesem Tool finden Sie im Thema [WS-AtomicTransaction Configuration MMC Snap-in](../../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md) . In den folgenden Schritten wird beschrieben, wie Sie eine Vertrauensstellung zwischen zwei Computern einrichten, auf denen MSDTC ausgeführt wird.

1. Konfigurieren Sie die Einstellungen von Computer A. Wählen Sie für "Endpunkt Zertifikat" certa aus. Wählen Sie für "autorisierte Zertifikate" certB aus.

2. Konfigurieren Sie die Einstellungen von Computer B. Wählen Sie für "Endpunkt Zertifikat" certB aus. Wählen Sie für "autorisierte Zertifikate" die certa aus.

> [!NOTE]
> Wenn ein Computer eine Nachricht an den anderen Computer sendet, versucht der Absender zu überprüfen, ob der Antragstellername des Zertifikats des Empfängers und der Name des Computers des Empfängers übereinstimmen. Wenn sie nicht übereinstimmen, schlägt die Zertifikatüberprüfung fehl, und die zwei Computer können nicht kommunizieren.
>
> Bei einem Computer, der Mitglied einer Domäne ist, ist der Name der vollqualifizierte Domänenname. Standardmäßig ist der Name eines Computers in einer Arbeitsgruppe der NetBIOS-Name des Computers. Allerdings kann der Name auch ein DNS-Suffix enthalten, falls dieses für die Verbindung zwischen den beiden Computern vorhanden ist.
>
> Falls sich der Name des Computers ändert, z. B. wenn ein Arbeitsgruppencomputer Mitglied einer Domäne wird, müssen Sie Zertifikate neu ausstellen oder DNS-Suffixe manuell konfigurieren.

## <a name="security"></a>Sicherheit

Da einige Einstellungen für MSDTC und WS-AT in der Registrierung unter HKLM\Software\Microsoft\MSDTC bzw. unter HKLM\Software\Microsoft\WSAT gespeichert werden, müssen Sie sicherstellen, dass diese Registrierungsschlüssel gesichert sind, sodass nur Administratoren darauf schreiben können. Klicken Sie im Registrierungs-Editor-Tool mit der rechten Maustaste auf den Schlüssel, den Sie sichern möchten, und wählen Sie die **Berechtigung** zum Festlegen der entsprechenden Zugriffs Steuerung aus. Für die Systemsicherheit und -integrität ist es entscheidend, dass wichtige Schlüssel für Benutzer mit weniger Rechten schreibgeschützt sind.

Beim Bereitstellen von MSDTC muss der Administrator sicherstellen, dass der gesamte MSDTC-Datenaustausch gesichert ist. Isolieren Sie bei einer Arbeitsgruppenbereitstellung die Transaktionsinfrastruktur von böswilligen Benutzern; sichern Sie bei einer Clusterbereitstellung die Clusterregistrierung.

## <a name="tracing"></a>Ablaufverfolgung

Der WS-AT-Protokolldienst unterstützt die integrierte, transaktionsspezifische Ablauf Verfolgung, die mithilfe des [WS-AtomicTransaction Configuration MMC-Snap-in-](../../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md) Tools aktiviert und verwaltet werden kann. Ablaufverfolgungen können Daten einschließen, die unter anderem den Zeitpunkt einer Eintragung für eine bestimmte Transaktion, den Zeitpunkt des Erreichens des Endstatus und das Ergebnis, das jede Transaktionseintragung empfangen hat, angeben. Alle Ablauf Verfolgungen können mit dem [Service Trace Viewer-Tool (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) angezeigt werden.

Der WS-AT-Protokolldienst unterstützt auch integrierte ServiceModel-Ablaufverfolgung über die ETW-Ablaufverfolgungssitzung. Dies bietet ausführlichere, kommunikationsspezifische Ablaufverfolgungen zusätzlich zu den vorhandenen Transaktionsablaufverfolgungen.  Führen Sie die folgenden Schritte aus, um diese zusätzlichen Ablaufverfolgungen zu aktivieren:

1. Öffnen Sie das Menü **Start/ausführen** , geben Sie "regedit" in das Eingabefeld ein, und wählen Sie **OK**aus.

2. Navigieren Sie im **Registrierungs-Editor**im linken Bereich zum folgenden Ordner, HKEY_LOCAL_MACHINE \software\microsoft\wsat\3.0\

3. Klicken Sie mit der rechten Maustaste auf den `ServiceModelDiagnosticTracing` Wert im rechten Bereich, und wählen Sie **ändern**aus.

4. Geben Sie im Eingabefeld **Wert** einen der folgenden gültigen Werte ein, um die Ablauf Verfolgungs Ebene anzugeben, die Sie aktivieren möchten.

- 0: Aus

- 1: Kritisch

- 3: Fehler. Dies ist der Standardwert.

- 7: Warnung

- 15: Informationen

- 31: Ausführlich

## <a name="see-also"></a>Siehe auch

- [WS-AtomicTransaction-Konfigurationshilfsprogramm (wsatConfig.exe)](../../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md)
- [WS-AtomicTransaction-Konfiguration-MMC-Snap-In](../../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md)
