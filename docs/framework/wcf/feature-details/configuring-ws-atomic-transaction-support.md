---
title: "Konfigurieren der WS-AtomicTransaction-Unterst&#252;tzung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WS-AT-Protokoll [WCF], Konfigurieren der WS-Atomic-Transaktion"
ms.assetid: cb9f1c9c-1439-4172-b9bc-b01c3e09ac48
caps.latest.revision: 31
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 31
---
# Konfigurieren der WS-AtomicTransaction-Unterst&#252;tzung
In diesem Thema wird beschrieben, wie Sie die WS\-AtomicTransaction \(WS\-AT\)\-Unterstützung mit dem WS\-AT\-Konfigurationshilfsprogramm konfigurieren können.  
  
## Verwenden des WS\-AT\-Konfigurationshilfsprogramms  
 Das WS\-AT\-Konfigurationshilfsprogramm \(wsatConfig.exe\) wird zum Konfigurieren von WS\-AT\-Einstellungen verwendet.  Zum Aktivieren des WS\-AT\-Protokolldienstes müssen Sie mithilfe des Konfigurationshilfsprogramms den HTTPS\-Anschluss für WS\-AT konfigurieren, ein X.509\-Zertifikat an den HTTPS\-Anschluss binden und autorisierte Partnerzertifikate durch Angabe von Zertifikatantragstellernamen oder Fingerabdrücken konfigurieren.  Mithilfe des Konfigurationshilfsprogramms können Sie außerdem den Modus für die Ablaufverfolgung auswählen und standardmäßige ausgehende and maximale eingehende Transaktionstimeouts festlegen.  
  
 Der Zugriff auf die Funktionen dieses Tools ist über ein Snap\-In auf der Eigenschaftenseite der Microsoft Management Console \(MMC\) in der Komponentendienste\-Managementkonsole oder aus einem Befehlszeilenfenster möglich.  Konfigurieren Sie die WS\-AT\-Unterstützung auf dem lokalen Computer über das Befehlszeilenfenster, und konfigurieren Sie Einstellungen auf lokalen und Remotecomputern über das MMC\-Snap\-In.  
  
 Auf das Befehlszeilenfenster kann in dem Windows SDK\-Installationspfad "%WINDIR%\\Microsoft.NET\\Framework\\v3.0\\Windows Communication Foundation" zugegriffen werden.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Befehlszeilentool finden Sie unter [WS\-AtomicTransaction\-Konfigurationsdienstprogramm \(wsatConfig.exe\)](../../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md).  
  
 Wenn Sie [!INCLUDE[wxp](../../../../includes/wxp-md.md)] oder [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] ausführen, können Sie auf das MMC\-Snap\-In zugreifen, indem Sie zu **Systemsteuerung\/Verwaltung\/Komponentendienste** navigieren, mit der rechten Maustaste auf **Arbeitsplatz** klicken und **Eigenschaften** auswählen.  Dies ist die gleiche Position, an der Sie den Microsoft Distributed Transaction Coordinator \(MSDTC\) konfigurieren können.  Für die Konfiguration verfügbare Optionen sind unter der Registerkarte **WS\-AT** gruppiert.  Wenn Sie Windows Vista oder [!INCLUDE[lserver](../../../../includes/lserver-md.md)] ausführen, finden Sie das MMC\-Snap\-In, indem Sie auf **Start** klicken und `dcomcnfg.exe` in das Feld **Suchen** eingeben.  Wenn die MMC geöffnet ist, navigieren Sie zum Knoten **Arbeitsplatz\\Distributed Transaction Coordinator\\Lokaler DTC**, klicken Sie mit der rechten Maustaste, und wählen Sie **Eigenschaften** aus.  Für die Konfiguration verfügbare Optionen sind unter der Registerkarte **WS\-AT** gruppiert.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Snap\-In finden Sie unter [WS\-AtomicTransaction\-Konfiguration\-MMC\-Snap\-In](../../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md).  
  
 Zum Aktivieren der Benutzeroberfläche des Tools müssen Sie zuerst die Datei WsatUI.dll im folgenden Pfad registrieren:  
  
 %PROGRAMFILES%\\Microsoft SDKs\\Windows\\v6.0\\Bin  
  
 Führen Sie zum Registrieren des Produkts den folgenden Befehl in einem Eingabeaufforderungsfenster aus:  
  
 `regasm.exe /codebase WsatUI.dll`  
  
## Aktivieren von WS\-AT  
 Verwenden Sie zum Aktivieren des WS\-AT\-Protokolldienstes in MSDTC unter Nutzung von Anschluss 443 und eines X.509\-Zertifikats mit einem privaten Schlüssel im Speicher des lokalen Computers das Tool wsatConfig.exe mit dem folgenden Befehl.  
  
 `WsatConfig.exe –network:enable –port:8443 –endpointCert:<machine|"Issuer\SubjectName"> -accountsCerts:<thumbprint|"Issuer\SubjectName"> -restart`  
  
 Ersetzen Sie die jeweiligen Parameter durch für Ihre Umgebung relevante Werte.  
  
 Verwenden Sie zum Deaktivieren des WS\-AT\-Protokolldienstes in MSDTC das Tool wsatConfig.exe mit dem folgenden Befehl.  
  
 `WsatConfig.exe –network:disable -restart`  
  
## Konfigurieren von Vertrauensstellungen zwischen zwei Computern  
 Der WS\-AT\-Protokolldienst erfordert, dass der Administrator einzelne Konten für die Teilnahme an verteilten Transaktionen explizit autorisiert.  Als Administrator für zwei Computer können Sie beide Computer so konfigurieren, dass sie durch Austausch der richtigen Zertifikate zwischen den Computern, Installation in den richtigen Zertifikatspeichern und Verwenden des Tools wsatConfig.exe zum Hinzufügen des Zertifikats jedes Computers zur Liste autorisierter Teilnehmerzertifikate des anderen Computers eine gegenseitige Vertrauensstellung einrichten.  Dieser Schritt ist erforderlich, um verteilte Transaktionen zwischen zwei Computern auszuführen, die WS\-AT verwenden.  
  
 Im folgenden Beispiel werden die Schritte zum Einrichten einer Vertrauensstellung zwischen zwei Computern, A und B, beschrieben.  
  
### Erstellen und Exportieren von Zertifikaten  
 Für dieses Verfahren ist das MMC\-Zertifikat\-Snap\-In erforderlich.  Öffnen Sie zum Zugriff auf das Snap\-In das Menü "Start\/Ausführen", geben Sie "mmc" im Eingabefeld ein, und klicken Sie auf "OK".  Navigieren Sie anschließend im Fenster **Konsole1** zu **Datei\/Snap\-In hinzufügen\/entfernen**, klicken Sie auf "Hinzufügen", und wählen Sie **Zertifikate** in der Liste **Verfügbare eigenständige Snap\-Ins** aus.  Wählen Sie abschließend das zu verwaltende **Computerkonto** aus, und klicken Sie auf **OK**.  Der Knoten **Zertifikate** wird in der Snap\-In\-Konsole angezeigt.  
  
 Sie müssen bereits die erforderlichen Zertifikate besitzen, um Vertrauensstellungen einzurichten.  Weitere Informationen zum Erstellen und Installieren neuer Zertifikate, bevor Sie die nachfolgenden Schritte ausführen, finden Sie unter [Gewusst wie: Erstellen und Installieren temporärer Clientzertifikate in WCF während der Entwicklung](http://go.microsoft.com/fwlink/?LinkId=158925).  
  
1.  Importieren Sie auf Computer A mit dem MMC\-Zertifikat\-Snap\-In das vorhandene Zertifikat \(certA\) in den Speicher **LocalMachine\\MY** \(Persönlicher Knoten\) und **LocalMachine\\ROOT** \(Knoten der vertrauenswürdigen Stammzertifizierungsstelle\).  Um ein Zertifikat zu einem bestimmten Knoten zu importieren, klicken Sie mit der rechten Maustaste auf den Knoten, und wählen Sie **Alle Aufgaben\/Importieren** aus.  
  
2.  Erstellen oder erhalten Sie auf Computer B mit dem MMC\-Zertifikat\-Snap\-In ein Zertifikat \(certB\) mit einem privaten Schlüssel, und importieren Sie es in den Speicher **LocalMachine\\MY** \(Persönlicher Knoten\) und **LocalMachine\\ROOT** \(Knoten der vertrauenswürdigen Stammzertifizierungsstelle\).  
  
3.  Exportieren Sie den öffentlichen Schlüssel von certA zu einer Datei, wenn noch nicht geschehen.  
  
4.  Exportieren Sie den öffentlichen Schlüssel von certB zu einer Datei, wenn noch nicht geschehen.  
  
### Einrichten einer gegenseitigen Vertrauensstellung zwischen Computern  
  
1.  Importieren Sie auf Computer A die Dateidarstellung von certB in die Speicher LocalMachine\\MY und LocalMachine\\ROOT.  Damit wird deklariert, dass Computer A certB für die Kommunikation vertraut.  
  
2.  Importieren Sie auf Computer B die Datei von certA in die Speicher LocalMachine\\MY und LocalMachine\\ROOT.  Dies bedeutet, dass Computer B certA für die Kommunikation vertraut.  
  
 Mit diesen Schritten wurde eine Vertrauensstellung zwischen den beiden Computern eingerichtet, und sie können für die Kommunikation mit WS\-AT konfiguriert werden.  
  
### Konfigurieren von MSDTC für die Verwendung von Zertifikaten  
 Da der WS\-AT\-Protokolldienst als Client und Server fungiert, muss er eingehende Verbindungen abhören und ausgehende Verbindungen initiieren.  Sie müssen daher MSDTC so konfigurieren, dass bekannt ist, welche Zertifikate bei der Kommunikation mit externen Programmen verwendet werden müssen und welche Zertifikate beim Annehmen eingehender Kommunikation autorisiert werden müssen.  
  
 Sie können dies mit dem MMC\-WS\-AT\-Snap\-In konfigurieren.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu diesem Tool finden Sie unter [WS\-AtomicTransaction\-Konfiguration\-MMC\-Snap\-In](../../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md).  In den folgenden Schritten wird beschrieben, wie Sie eine Vertrauensstellung zwischen zwei Computern einrichten, auf denen MSDTC ausgeführt wird.  
  
1.  Konfigurieren Sie die Einstellungen von Computer A.  Wählen Sie für "Endpunktzertifikat" certA aus.  Wählen Sie für "Autorisierte Zertifikate" certB aus.  
  
2.  Konfigurieren Sie die Einstellungen von Computer B.  Wählen Sie für "Endpunktzertifikat" certB aus.  Wählen Sie für "Autorisierte Zertifikate" certA aus.  
  
> [!NOTE]
>  Wenn ein Computer eine Nachricht an den anderen Computer sendet, versucht der Absender zu überprüfen, ob der Antragstellername des Zertifikats des Empfängers und der Name des Computers des Empfängers übereinstimmen.  Wenn sie nicht übereinstimmen, schlägt die Zertifikatüberprüfung fehl, und die zwei Computer können nicht kommunizieren.  
>   
>  Bei einem Computer, der Mitglied einer Domäne ist, ist der Name der vollqualifizierte Domänenname.  Standardmäßig ist der Name eines Computers in einer Arbeitsgruppe der NetBIOS\-Name des Computers.  Allerdings kann der Name auch ein DNS\-Suffix enthalten, falls dieses für die Verbindung zwischen den beiden Computern vorhanden ist.  
>   
>  Falls sich der Name des Computers ändert, z. B. wenn ein Arbeitsgruppencomputer Mitglied einer Domäne wird, müssen Sie Zertifikate neu ausstellen oder DNS\-Suffixe manuell konfigurieren.  
  
## Sicherheit  
 Da einige Einstellungen für MSDTC und WS\-AT in der Registrierung unter HKLM\\Software\\Microsoft\\MSDTC bzw. unter HKLM\\Software\\Microsoft\\WSAT gespeichert werden, müssen Sie sicherstellen, dass diese Registrierungsschlüssel gesichert sind, sodass nur Administratoren darauf schreiben können.  Klicken Sie im Registrierungs\-Editor mit der rechten Maustaste auf den Schlüssel, der gesichert werden soll, und wählen Sie **Berechtigung** aus, um die entsprechende Zugriffssteuerung festzulegen.  Für die Systemsicherheit und \-integrität ist es entscheidend, dass wichtige Schlüssel für Benutzer mit weniger Rechten schreibgeschützt sind.  
  
 Beim Bereitstellen von MSDTC muss der Administrator sicherstellen, dass der gesamte MSDTC\-Datenaustausch gesichert ist.  Isolieren Sie bei einer Arbeitsgruppenbereitstellung die Transaktionsinfrastruktur von böswilligen Benutzern; sichern Sie bei einer Clusterbereitstellung die Clusterregistrierung.  
  
## Ablaufverfolgung  
 Der WS\-AT\-Protokolldienst unterstützt integrierte, transaktionsspezifische Ablaufverfolgung, die mithilfe des [WS\-AtomicTransaction\-Konfiguration\-MMC\-Snap\-In](../../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md)\-Tools aktiviert und verwaltet werden kann.  Ablaufverfolgungen können Daten einschließen, die unter anderem den Zeitpunkt einer Eintragung für eine bestimmte Transaktion, den Zeitpunkt des Erreichens des Endstatus und das Ergebnis, das jede Transaktionseintragung empfangen hat, angeben.  Alle Ablaufverfolgungen können mit dem [Service Trace Viewer\-Tool \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) angezeigt werden.  
  
 Der WS\-AT\-Protokolldienst unterstützt auch integrierte ServiceModel\-Ablaufverfolgung über die ETW\-Ablaufverfolgungssitzung.  Dies bietet ausführlichere, kommunikationsspezifische Ablaufverfolgungen zusätzlich zu den vorhandenen Transaktionsablaufverfolgungen.  Führen Sie die folgenden Schritte aus, um diese zusätzlichen Ablaufverfolgungen zu aktivieren:  
  
1.  Öffnen Sie das Menü **Start\/Ausführen**, geben Sie "regedit" im Eingabefeld ein, und klicken Sie auf **OK**.  
  
2.  Navigieren Sie im **Registrierungs\-Editor** zum folgenden Ordner im linken Bereich: Hkey\_Local\_Machine\\SOFTWARE\\Microsoft\\WSAT\\3.0\\  
  
3.  Klicken Sie mit der rechten Maustaste auf den `ServiceModelDiagnosticTracing`\-Wert im rechten Bereich, und wählen Sie **Ändern** aus.  
  
4.  Geben Sie im Eingabefeld **Wert** einen der folgenden gültigen Werte ein, um die zu aktivierende Ablaufverfolgungsebene anzugeben.  
  
-   0: Aus  
  
-   1: Kritisch  
  
-   3: Fehler.  Dies ist der Standardwert.  
  
-   7: Warnung  
  
-   15: Informationen  
  
-   31: Ausführlich  
  
## Siehe auch  
 [WS\-AtomicTransaction\-Konfigurationsdienstprogramm \(wsatConfig.exe\)](../../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md)   
 [WS\-AtomicTransaction\-Konfiguration\-MMC\-Snap\-In](../../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md)