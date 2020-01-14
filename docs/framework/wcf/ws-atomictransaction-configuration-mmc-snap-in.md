---
title: WS-AtomicTransaction-Konfiguration-MMC-Snap-In
ms.date: 03/30/2017
ms.assetid: 23592973-1d51-44cc-b887-bf8b0d801e9e
ms.openlocfilehash: 9b6c7ecf112309b6c10414bfe506559e153911c2
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900728"
---
# <a name="ws-atomictransaction-configuration-mmc-snap-in"></a>WS-AtomicTransaction-Konfiguration-MMC-Snap-in

Das MMC-Snap-in für die WS-AtomicTransaction-Konfiguration wird verwendet, um einen Teil der WS-AtomicTransaction-Einstellungen auf lokalen Computern und Remote Computern zu konfigurieren.

## <a name="remarks"></a>Hinweise

Wenn Sie [!INCLUDE[wxp](../../../includes/wxp-md.md)] oder Windows Server 2003 ausführen, finden Sie das MMC-Snap-in. Navigieren Sie zu **Systemsteuerung**> Verwaltung > Komponenten Dienste >, klicken Sie mit der rechten Maustaste auf **Arbeitsplatz**, und wählen Sie **Eigenschaften**aus. Dort können Sie auch den MSDTC konfigurieren. Optionen, die für die Konfiguration verfügbar sind, werden auf der Registerkarte **WS-AT** gruppiert.

 Wenn Sie Windows Vista oder Windows Server 2008 ausführen, finden Sie das MMC-Snap-in, indem Sie auf die Schaltfläche **Start** klicken und in das **Suchfeld** `dcomcnfg.exe` eingeben. Wenn die MMC geöffnet ist, navigieren Sie zum Knoten **My computer\verteilte transaktions\lokale DTC** , klicken Sie mit der rechten Maustaste, und wählen Sie **Eigenschaften**aus. Optionen, die für die Konfiguration verfügbar sind, werden auf der Registerkarte **WS-AT** gruppiert.

 Die vorherigen Schritte werden verwendet, um das Snap-In zur Konfiguration eines lokalen Computers zu starten. Wenn Sie einen Remote Computer konfigurieren möchten, sollten Sie den Namen des Remote Computers in der Systemsteuerung > Verwaltung > **Komponenten Dienste**> ausführen und ähnliche Schritte ausführen, wenn Sie [!INCLUDE[wxp](../../../includes/wxp-md.md)] oder Windows Server 2003 ausführen. Wenn Sie Windows Vista oder Windows Server 2008 ausführen, führen Sie die vorherigen Schritte für Vista und Windows Server 2008 aus, aber verwenden Sie den Knoten **verteilte transaktionskoordinator\lokale DTC** unter dem Knoten des Remote Computers.

 Zum Verwenden der Benutzeroberfläche des Tools müssen Sie zuerst die Datei WsatUI.dll im folgenden Pfad registrieren:

 **%PROGRAMFILES%\Microsoft SDKs\Windows\v6.0\Bin\WsatUI.dll**

 Die Registrierung kann mit folgendem Befehl vorgenommen werden:

```console
regasm.exe /codebase WsatUI.dll
```

 Sie können dieses Tool verwenden, um die grundlegenden WS-AtomicTransaction-Einstellungen zu ändern. Sie können beispielsweise die WS-AtomicTransaction-Protokollunterstützung aktivieren und deaktivieren, die HTTP-Anschlüsse für WS-AT konfigurieren, ein SSL-Zertifikat an den HTTP-Anschluss binden, Zertifikate durch Angabe von Zertifikatsbetreffnamen konfigurieren, den Ablaufverfolgungsmodus aktivieren und Standard- und Maximaltimeouts festlegen.

 Wenn Sie die WS-AtomicTransaction-Unterstützung nur auf dem lokalen Computer konfigurieren müssen, können Sie die Befehlszeilenversion des Tools verwenden. Weitere Informationen zum Befehlszeilen Tool finden Sie im Thema [WS-AtomicTransaction-Konfigurations Hilfsprogramm (wsatConfig. exe)](ws-atomictransaction-configuration-utility-wsatconfig-exe.md) .

 Beachten Sie, dass das MMC-Snap-In und das Befehlszeilentool nicht die Konfiguration aller WS-AT-Einstellungen unterstützen. Diese Einstellungen können nur durch die Änderung der Registrierung bearbeitet werden. Weitere Informationen zu diesen Registrierungs Einstellungen finden Sie [unter Konfigurieren der WS-Atomic Transaction-Unterstützung](./feature-details/configuring-ws-atomic-transaction-support.md).

### <a name="user-interface-description"></a>Benutzeroberflächenbeschreibung

**Unterstützung für WS-Atomic Transaction-Netzwerk aktivieren**:

 Mit diesem Kontrollkästchen können die GUI-Komponenten dieses Snap-Ins aktiviert oder deaktiviert werden.

 Vor der Aktivierung dieses Kontrollkästchens sollten Sie sicherstellen, dass der DTC-Netzwerkzugriff mit eingehender oder/und ausgehender Kommunikation aktiviert ist. Dieser Wert kann auf der Registerkarte **Sicherheit** des MSDTC-Snap-Ins überprüft werden.

#### <a name="network-group-box"></a>Netzwerkgruppenfeld

Sie können den HTTPS-Anschluss und zusätzliche Sicherheitseinstellungen, wie z.&#160;B. SSL-Verschlüsselung, in der Netzwerkgruppe angeben. Diese Gruppe ist deaktiviert (abgeblendet), wenn DTC-Netzwerktransaktionen nicht aktiviert sind.

 **HTTPS-Port**

 Dies ist der Wert des für WS-AT verwendeten HTTPS-Anschlusses. Der Wert muss eine Zahl im Bereich von 1 bis 65535 sein (um einen gültigen Anschluss darzustellen). Durch das Ändern des HTTP-Anschlusses wird die HTTP-Dienstkonfiguration geändert, was bedeutet, dass die zuvor verwendete WS-AT-Dienstadresse freigegeben wird und eine neue WS-AT-Dienstadresse basierend auf dem neuen Anschluss registriert wird. Außerdem wird der neu ausgewählte Anschluss mit dem derzeit ausgewählten Zertifikat für die SSL-Verschlüsselung verschlüsselt.

> [!NOTE]
> Wenn Sie die Firewall schon vor dem Ausführen dieses Tools aktiviert haben, wird der Anschluss automatisch in der Ausnahmeliste registriert. Wenn die Firewall vor dem Ausführen dieses Tools deaktiviert wird, werden keine zusätzlichen Konfigurationen in Bezug auf die Firewall vorgenommen.

 Wenn Sie die Firewall nach der Konfiguration von WS-AT aktivieren, müssen Sie dieses Tool erneut ausführen und die Anschlussnummer mit diesem Parameter angeben. Wenn Sie die Firewall nach der Konfiguration deaktivieren, wird WS-AT ohne zusätzliche Eingabe ausgeführt.

 **Endpunkt Zertifikat**

 Wenn Sie auf die Schaltfläche **auswählen** klicken, wird eine Liste mit den derzeit verfügbaren Zertifikaten auf dem lokalen Computer angezeigt, sodass der Benutzer das Zertifikat auswählen kann, das für die SSL-Verschlüsselung verwendet werden kann. Die Zertifikate müssen einen privaten Schlüssel haben. Andernfalls wird eine Fehlermeldung ausgegeben.

> [!NOTE]
> Wenn Sie ein SSL-Zertifikat für einen bestimmten Port festlegen, wird dabei das ursprüngliche SSL-Zertifikat überschrieben, das diesem Port zugeordnet ist (sofern vorhanden).

 **Autorisierte Konten**

 Durch Klicken auf die Schaltfläche **auswählen** wird der Editor für die Windows-Access Control Liste aufgerufen, in dem Sie den Benutzer oder die Gruppe angeben können, der Teil von WS-Atomic-Transaktionen sein kann, indem Sie das Kontrollkästchen **zulassen** oder **verweigern** in der Gruppe **Teilnahme**

 **Autorisierte Zertifikate**

 Wenn Sie auf die Schaltfläche **auswählen** klicken, wird eine Liste der derzeit verfügbaren Zertifikate auf dem LocalMachine angezeigt. Sie können dann auswählen, welchen Zertifikatsidentitäten ermöglicht wird, an WS-Atomic-Transaktionen teilzunehmen.

#### <a name="timeout-group-box"></a>Gruppenfeld Timeout

Das Gruppenfeld **Timeout** ermöglicht das Festlegen des Standard-und des maximalen Timeouts für eine WS-Atomic-Transaktion. Ein gültiger Wert für ein ausgehendes Timeout liegt zwischen 1 und 3600. Ein gültiger Wert für ein eingehendes Timeout liegt zwischen 0 und 3600.

#### <a name="tracing-and-logging-group-box"></a>Gruppenfeld Ablaufverfolgung und Protokollierung

Mit dem Gruppenfeld Ablauf **Verfolgung und Protokollierung** können Sie den gewünschten Ablauf Verfolgungs-und Protokollierungs Grad konfigurieren.

 Durch Klicken auf die Schaltfläche **Optionen** wird eine Seite aufgerufen, auf der Sie zusätzliche Einstellungen angeben können.

 Mit dem Kombinations Feld für die Ablauf **Verfolgungs Ebene** können Sie einen beliebigen gültigen Wert der <xref:System.Diagnostics.TraceLevel>-Enumeration auswählen. Sie können mit den Kontrollkästchen auch angeben, ob Sie die Ablaufverfolgung oder die Aktivitätspropagierung durchführen oder persönlich identifizierbare Informationen sammeln möchten.

 Sie können Protokollierungs Sitzungen auch im Gruppenfeld **Protokollierungs Sitzung** angeben.

> [!NOTE]
> Wenn ein anderer Benutzer der Ablaufverfolgung den WS-AT-Ablaufverfolgungsanbieter verwendet, können Sie keine neue Protokollsitzung für Ablaufverfolgungsereignisse erstellen. Jeder Versuch, die Protokollierung zu diesem Zeitpunkt zu konfigurieren, führt zur Fehlermeldung "Fehler beim Aktivieren des Anbieters. Fehlercode: 1".

 Weitere Informationen zur Ablauf Verfolgung und Protokollierung finden Sie unter [Verwaltung und Diagnose](./diagnostics/index.md).

## <a name="see-also"></a>Siehe auch

- [Konfigurieren der Unterstützung von WS-Atomic-Transaction](./feature-details/configuring-ws-atomic-transaction-support.md)
- [WS-AtomicTransaction-Konfigurationshilfsprogramm (wsatConfig.exe)](ws-atomictransaction-configuration-utility-wsatconfig-exe.md)
- [Verwaltung und Diagnose](./diagnostics/index.md)
