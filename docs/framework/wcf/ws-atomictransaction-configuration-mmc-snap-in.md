---
title: WS-AtomicTransaction-Konfiguration-MMC-Snap-In
ms.date: 03/30/2017
ms.assetid: 23592973-1d51-44cc-b887-bf8b0d801e9e
ms.openlocfilehash: b1d86fa57b31d1f9be12f76c28f9d042e7e28e24
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138205"
---
# <a name="ws-atomictransaction-configuration-mmc-snap-in"></a>WS-AtomicTransaction-Konfiguration-MMC-Snap-In
Das MMC-Snap-In für die WS-AtomicTransaction-Konfiguration wird zur Konfiguration eines Teils der WS-AtomicTransaction-Einstellungen auf lokalen und Remotecomputern eingesetzt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie ausführen [!INCLUDE[wxp](../../../includes/wxp-md.md)] oder [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], das MMC-Snap-in finden Sie durch Navigieren zu **Steuerelement Systemsteuerung/Verwaltung/Komponentendienste /** der rechten Maustaste auf **Arbeitsplatz**, und Auswählen von **Eigenschaften**. Dort können Sie auch den MSDTC konfigurieren. Optionen für die Konfiguration verfügbar werden gruppiert, unter dem **WS-AT** Registerkarte.  
  
 Wenn Sie Windows Vista ausführen oder [!INCLUDE[lserver](../../../includes/lserver-md.md)], MMC-Snap-in finden Sie durch Klicken auf die **starten** Schaltfläche aus, und geben Sie im `dcomcnfg.exe` in der **Suche** Feld. Wenn Sie die MMC geöffnet ist, navigieren Sie zu der **Meine arbeitsplatz\distributed Transaction coordinator\lokaler DTC** -Knoten mit der rechten Maustaste, und wählen Sie **Eigenschaften**. Optionen für die Konfiguration verfügbar werden gruppiert, unter dem **WS-AT** Registerkarte.  
  
 Die vorherigen Schritte werden verwendet, um das Snap-In zur Konfiguration eines lokalen Computers zu starten. Wenn Sie einen Remotecomputer konfigurieren möchten, suchen Sie remote den Namen des Computers in **Steuerelement Systemsteuerung/Verwaltung/Komponentendienste /**, und führen Sie ähnliche Schritte aus, wenn Sie [!INCLUDE[wxp](../../../includes/wxp-md.md)] oder [!INCLUDE[ws2003](../../../includes/ws2003-md.md)]. Wenn Sie Windows Vista ausführen oder [!INCLUDE[lserver](../../../includes/lserver-md.md)], führen Sie die vorherigen Schritte für Vista und [!INCLUDE[lserver](../../../includes/lserver-md.md)], aber der **Distributed Transaction coordinator\lokaler DTC** Knotens unter dem Knoten mit dem Remotecomputer.  
  
 Zum Verwenden der Benutzeroberfläche des Tools müssen Sie zuerst die Datei WsatUI.dll im folgenden Pfad registrieren:  
  
 **%PROGRAMFILES%\Microsoft SDKs\Windows\v6.0 \Bin\WsatUI.dll**  
  
 Die Registrierung kann mit folgendem Befehl vorgenommen werden:  
  
```Output  
regasm.exe /codebase WsatUI.dll  
```  
  
 Sie können dieses Tool verwenden, um die grundlegenden WS-AtomicTransaction-Einstellungen zu ändern. Sie können beispielsweise die WS-AtomicTransaction-Protokollunterstützung aktivieren und deaktivieren, die HTTP-Anschlüsse für WS-AT konfigurieren, ein SSL-Zertifikat an den HTTP-Anschluss binden, Zertifikate durch Angabe von Zertifikatsbetreffnamen konfigurieren, den Ablaufverfolgungsmodus aktivieren und Standard- und Maximaltimeouts festlegen.  
  
 Wenn Sie die WS-AtomicTransaction-Unterstützung nur auf dem lokalen Computer konfigurieren müssen, können Sie die Befehlszeilenversion des Tools verwenden. Weitere Informationen über das Befehlszeilentool finden Sie unter den [WS-AtomicTransaction-Konfigurationsdienstprogramm (wsatConfig.exe)](../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md) Thema.  
  
 Beachten Sie, dass das MMC-Snap-In und das Befehlszeilentool nicht die Konfiguration aller WS-AT-Einstellungen unterstützen. Diese Einstellungen können nur durch die Änderung der Registrierung bearbeitet werden. Weitere Informationen zu diesen registrierungseinstellungen finden Sie unter [WS-AtomicTransaction-Unterstützung konfigurieren](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md).  
  
### <a name="user-interface-description"></a>Benutzeroberflächenbeschreibung  
 **Aktivieren von WS-AtomicTransaction-Netzwerkunterstützung**:  
  
 Mit diesem Kontrollkästchen können die GUI-Komponenten dieses Snap-Ins aktiviert oder deaktiviert werden.  
  
 Vor der Aktivierung dieses Kontrollkästchens sollten Sie sicherstellen, dass der DTC-Netzwerkzugriff mit eingehender oder/und ausgehender Kommunikation aktiviert ist. Dieser Wert kann überprüft werden, der **Sicherheit** Registerkarte des MSDTC-Snap-Ins.  
  
#### <a name="network-group-box"></a>Netzwerkgruppenfeld  
 Sie können den HTTPS-Anschluss und zusätzliche Sicherheitseinstellungen, wie z.&amp;#160;B. SSL-Verschlüsselung, in der Netzwerkgruppe angeben. Diese Gruppe ist deaktiviert (abgeblendet), wenn DTC-Netzwerktransaktionen nicht aktiviert sind.  
  
 **HTTPS-Anschluss**  
  
 Dies ist der Wert des für WS-AT verwendeten HTTPS-Anschlusses. Der Wert muss eine Zahl im Bereich von 1 bis 65535 sein (um einen gültigen Anschluss darzustellen). Durch das Ändern des HTTP-Anschlusses wird die HTTP-Dienstkonfiguration geändert, was bedeutet, dass die zuvor verwendete WS-AT-Dienstadresse freigegeben wird und eine neue WS-AT-Dienstadresse basierend auf dem neuen Anschluss registriert wird. Außerdem wird der neu ausgewählte Anschluss mit dem derzeit ausgewählten Zertifikat für die SSL-Verschlüsselung verschlüsselt.  
  
> [!NOTE]
>  Wenn Sie die Firewall schon vor dem Ausführen dieses Tools aktiviert haben, wird der Anschluss automatisch in der Ausnahmeliste registriert. Wenn die Firewall vor dem Ausführen dieses Tools deaktiviert wird, werden keine zusätzlichen Konfigurationen in Bezug auf die Firewall vorgenommen.  
  
 Wenn Sie die Firewall nach der Konfiguration von WS-AT aktivieren, müssen Sie dieses Tool erneut ausführen und die Anschlussnummer mit diesem Parameter angeben. Wenn Sie die Firewall nach der Konfiguration deaktivieren, wird WS-AT ohne zusätzliche Eingabe ausgeführt.  
  
 **Endpunktzertifikat**  
  
 Klicken auf die **wählen** Schaltfläche zeigt eine Liste mit den derzeit verfügbaren Zertifikaten auf dem lokalen Computer, sodass der Benutzer das Zertifikat aus, die für die SSL-Verschlüsselung verwendet werden können. Die Zertifikate müssen einen privaten Schlüssel haben. Andernfalls wird eine Fehlermeldung ausgegeben.  
  
> [!NOTE]
>  Wenn Sie ein SSL-Zertifikat für einen bestimmten Port festlegen, wird dabei das ursprüngliche SSL-Zertifikat überschrieben, das diesem Port zugeordnet ist (sofern vorhanden).  
  
 **Autorisierte Konten**  
  
 Klicken auf die **wählen** Schaltfläche rufen Sie die Zugriffssteuerungsliste für Windows-Editor, in dem Sie angeben können Benutzer oder Gruppe, die einbezogen werden kann WS-Atomic-Transaktionen durch Überprüfen der **zulassen** oder **Verweigern** im Feld der **teilnehmen** Berechtigungsgruppe.  
  
 **Autorisierte Zertifikate**  
  
 Klicken auf die **wählen** Schaltfläche zeigt eine Liste der derzeit verfügbaren Zertifikate auf dem lokalen Computer. Sie können dann auswählen, welchen Zertifikatsidentitäten ermöglicht wird, an WS-Atomic-Transaktionen teilzunehmen.  
  
#### <a name="timeout-group-box"></a>Gruppenfeld Timeout  
 Die **Timeout** Gruppenfeld ermöglicht Ihnen die Angabe der Standard- und das maximaltimeout für eine WS-Atomic-Transaktion. Ein gültiger Wert für ein ausgehendes Timeout liegt zwischen 1 und 3600. Ein gültiger Wert für ein eingehendes Timeout liegt zwischen 0 und 3600.  
  
#### <a name="tracing-and-logging-group-box"></a>Gruppenfeld Ablaufverfolgung und Protokollierung  
 Die **Ablaufverfolgungs- und Protokollierungsoptionen** Gruppenfeld können Sie die gewünschte Ablaufverfolgungs- und Protokollierungsebene zu konfigurieren.  
  
 Klicken auf die **Optionen** Schaltfläche rufen Sie eine Seite, in dem Sie zusätzliche Einstellungen angeben können.  
  
 Die **Ablaufverfolgungsebene** Kombinationsfeld ermöglicht Ihnen, wählen Sie einen gültigen Wert für die <xref:System.Diagnostics.TraceLevel> Enumeration. Sie können mit den Kontrollkästchen auch angeben, ob Sie die Ablaufverfolgung oder die Aktivitätspropagierung durchführen oder persönlich identifizierbare Informationen sammeln möchten.  
  
 Sie können auch protokollierungssitzungen im Angeben der **Protokollierungssitzung** Gruppenfeld.  
  
> [!NOTE]
>  Wenn ein anderer Benutzer der Ablaufverfolgung den WS-AT-Ablaufverfolgungsanbieter verwendet, können Sie keine neue Protokollsitzung für Ablaufverfolgungsereignisse erstellen. Jeder Versuch, die Protokollierung zu diesem Zeitpunkt zu konfigurieren, führt zur Fehlermeldung "Fehler beim Aktivieren des Anbieters. Fehlercode: 1".  
  
 Weitere Informationen zu Protokollierung und Ablaufverfolgung, finden Sie unter [Verwaltung und Diagnose](../../../docs/framework/wcf/diagnostics/index.md).  
  
## <a name="see-also"></a>Siehe auch

- [Konfigurieren der WS-AtomicTransaction-Unterstützung](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)
- [WS-AtomicTransaction-Konfigurationsdienstprogramm (wsatConfig.exe)](../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md)
- [Verwaltung und Diagnose](../../../docs/framework/wcf/diagnostics/index.md)
