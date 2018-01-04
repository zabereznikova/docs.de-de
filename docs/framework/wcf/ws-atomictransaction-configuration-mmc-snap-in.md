---
title: WS-AtomicTransaction-Konfiguration-MMC-Snap-In
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 23592973-1d51-44cc-b887-bf8b0d801e9e
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 73db4b201aba6e07891803aa86c56403f135f863
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ws-atomictransaction-configuration-mmc-snap-in"></a>WS-AtomicTransaction-Konfiguration-MMC-Snap-In
Das MMC-Snap-In für die WS-AtomicTransaction-Konfiguration wird zur Konfiguration eines Teils der WS-AtomicTransaction-Einstellungen auf lokalen und Remotecomputern eingesetzt.  
  
## <a name="remarks"></a>Hinweise  
 Ausgeführtes Betriebssystem [!INCLUDE[wxp](../../../includes/wxp-md.md)] oder [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], das MMC-Snap-in finden Sie navigieren zu **Steuerelement Systemsteuerung/Verwaltung/Komponentendienste /**, mit der rechten Maustaste **Arbeitsplatz**, und Auswählen von **Eigenschaften**. Dort können Sie auch den MSDTC konfigurieren. Für die Konfiguration verfügbare Optionen sind unter gruppiert die **WS-AT-** Registerkarte.  
  
 Wenn Sie Windows Vista ausgeführt werden oder [!INCLUDE[lserver](../../../includes/lserver-md.md)], MMC-Snap-in finden Sie auf der **starten** Schaltfläche aus, und geben Sie im `dcomcnfg.exe` in der **Suche** Feld. Wenn die MMC geöffnet ist, navigieren Sie zu der **arbeitsplatz\distributed Transaction coordinator\lokaler DTC** Knoten mit der rechten Maustaste, und wählen Sie **Eigenschaften**. Für die Konfiguration verfügbare Optionen sind unter gruppiert die **WS-AT-** Registerkarte.  
  
 Die vorherigen Schritte werden verwendet, um das Snap-In zur Konfiguration eines lokalen Computers zu starten. Wenn Sie einen Remotecomputer konfigurieren möchten, suchen Sie den Remotecomputer Verzeichnisnamens **Steuerelement Systemsteuerung/Verwaltung/Komponentendienste /**, und führen Sie ähnliche Schritte aus, wenn Sie [!INCLUDE[wxp](../../../includes/wxp-md.md)] oder [!INCLUDE[ws2003](../../../includes/ws2003-md.md)]. Wenn Sie Windows Vista ausgeführt werden oder [!INCLUDE[lserver](../../../includes/lserver-md.md)], führen Sie die vorherigen Schritte für Vista und [!INCLUDE[lserver](../../../includes/lserver-md.md)], verwenden jedoch den **Distributed Transaction coordinator\lokaler DTC** Knoten unter dem Knoten des Remotecomputers.  
  
 Zum Verwenden der Benutzeroberfläche des Tools müssen Sie zuerst die Datei WsatUI.dll im folgenden Pfad registrieren:  
  
 **%ProgramFiles%\Microsoft SDKs\Windows\v6.0\Bin\WsatUI.dll**  
  
 Die Registrierung kann mit folgendem Befehl vorgenommen werden:  
  
```Output  
regasm.exe /codebase WsatUI.dll  
```  
  
 Sie können dieses Tool verwenden, um die grundlegenden WS-AtomicTransaction-Einstellungen zu ändern. Sie können beispielsweise die WS-AtomicTransaction-Protokollunterstützung aktivieren und deaktivieren, die HTTP-Anschlüsse für WS-AT konfigurieren, ein SSL-Zertifikat an den HTTP-Anschluss binden, Zertifikate durch Angabe von Zertifikatsbetreffnamen konfigurieren, den Ablaufverfolgungsmodus aktivieren und Standard- und Maximaltimeouts festlegen.  
  
 Wenn Sie die WS-AtomicTransaction-Unterstützung nur auf dem lokalen Computer konfigurieren müssen, können Sie die Befehlszeilenversion des Tools verwenden. [!INCLUDE[crabout](../../../includes/crabout-md.md)]Das Tool über die Befehlszeile finden Sie unter der [WS-AtomicTransaction-Konfigurationsdienstprogramm (wsatConfig.exe)](../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md) Thema.  
  
 Beachten Sie, dass das MMC-Snap-In und das Befehlszeilentool nicht die Konfiguration aller WS-AT-Einstellungen unterstützen. Diese Einstellungen können nur durch die Änderung der Registrierung bearbeitet werden. [!INCLUDE[crabout](../../../includes/crabout-md.md)]Diese registrierungseinstellungen finden Sie unter [WS-AtomicTransaction-Unterstützung konfigurieren](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md).  
  
### <a name="user-interface-description"></a>Benutzeroberflächenbeschreibung  
 **WS-AtomicTransaction-Netzwerkunterstützung aktivieren**:  
  
 Mit diesem Kontrollkästchen können die GUI-Komponenten dieses Snap-Ins aktiviert oder deaktiviert werden.  
  
 Vor der Aktivierung dieses Kontrollkästchens sollten Sie sicherstellen, dass der DTC-Netzwerkzugriff mit eingehender oder/und ausgehender Kommunikation aktiviert ist. Dieser Wert kann überprüft werden, der **Sicherheit** Registerkarte des MSDTC-Snap-Ins.  
  
#### <a name="network-group-box"></a>Netzwerkgruppenfeld  
 Sie können den HTTPS-Anschluss und zusätzliche Sicherheitseinstellungen, wie z.&#160;B. SSL-Verschlüsselung, in der Netzwerkgruppe angeben. Diese Gruppe ist deaktiviert (abgeblendet), wenn DTC-Netzwerktransaktionen nicht aktiviert sind.  
  
 **HTTPS-Port**  
  
 Dies ist der Wert des für WS-AT verwendeten HTTPS-Anschlusses. Der Wert muss eine Zahl im Bereich von 1 bis 65535 sein (um einen gültigen Anschluss darzustellen). Durch das Ändern des HTTP-Anschlusses wird die HTTP-Dienstkonfiguration geändert, was bedeutet, dass die zuvor verwendete WS-AT-Dienstadresse freigegeben wird und eine neue WS-AT-Dienstadresse basierend auf dem neuen Anschluss registriert wird. Außerdem wird der neu ausgewählte Anschluss mit dem derzeit ausgewählten Zertifikat für die SSL-Verschlüsselung verschlüsselt.  
  
> [!NOTE]
>  Wenn Sie die Firewall schon vor dem Ausführen dieses Tools aktiviert haben, wird der Anschluss automatisch in der Ausnahmeliste registriert. Wenn die Firewall vor dem Ausführen dieses Tools deaktiviert wird, werden keine zusätzlichen Konfigurationen in Bezug auf die Firewall vorgenommen.  
  
 Wenn Sie die Firewall nach der Konfiguration von WS-AT aktivieren, müssen Sie dieses Tool erneut ausführen und die Anschlussnummer mit diesem Parameter angeben. Wenn Sie die Firewall nach der Konfiguration deaktivieren, wird WS-AT ohne zusätzliche Eingabe ausgeführt.  
  
 **Endpunktzertifikat**  
  
 Klicken auf die **wählen** Schaltfläche zeigt eine Liste mit den derzeit verfügbaren Zertifikaten auf dem lokalen Computer, sodass der Benutzer das Zertifikat aus, die für die SSL-Verschlüsselung verwendet werden kann. Die Zertifikate müssen einen privaten Schlüssel haben. Andernfalls wird eine Fehlermeldung ausgegeben.  
  
> [!NOTE]
>  Wenn Sie ein SSL-Zertifikat für einen bestimmten Port festlegen, wird dabei das ursprüngliche SSL-Zertifikat überschrieben, das diesem Port zugeordnet ist (sofern vorhanden).  
  
 **Autorisierte Konten**  
  
 Klicken auf die **wählen** Schaltfläche ruft die Windows-Zugriffssteuerungsliste-Editor, in dem Sie angeben können Benutzer oder Gruppe, die einbezogen werden kann WS-Atomic-Transaktionen durch Überprüfen der **zulassen** oder **Deny** Feld der **teilnehmen** Berechtigungsgruppe.  
  
 **Autorisierte Zertifikate**  
  
 Klicken auf die **wählen** Schaltfläche zeigt eine Liste der aktuell verfügbare Zertifikate auf dem lokalen Computer. Sie können dann auswählen, welchen Zertifikatsidentitäten ermöglicht wird, an WS-Atomic-Transaktionen teilzunehmen.  
  
#### <a name="timeout-group-box"></a>Gruppenfeld Timeout  
 Die **Timeout** Gruppenfeld ermöglicht Ihnen das Festlegen der Standard- und das maximaltimeout für eine WS-Atomic-Transaktion. Ein gültiger Wert für ein ausgehendes Timeout liegt zwischen 1 und 3600. Ein gültiger Wert für ein eingehendes Timeout liegt zwischen 0 und 3600.  
  
#### <a name="tracing-and-logging-group-box"></a>Gruppenfeld Ablaufverfolgung und Protokollierung  
 Die **Ablaufverfolgungs- und Protokollierungsoptionen** Gruppenfeld können Sie die gewünschte Ablaufverfolgungs- und Protokollierungsebene zu konfigurieren.  
  
 Klicken auf die **Optionen** Schaltfläche aufruft, eine Seite, in dem Sie zusätzliche Einstellungen angeben können.  
  
 Die **Ablaufverfolgungsebene** Kombinationsfeld können Sie einen gültigen Wert der Auswahl der <xref:System.Diagnostics.TraceLevel> Enumeration. Sie können mit den Kontrollkästchen auch angeben, ob Sie die Ablaufverfolgung oder die Aktivitätspropagierung durchführen oder persönlich identifizierbare Informationen sammeln möchten.  
  
 Sie können auch protokollierungssitzungen im Angeben der **Protokollierungssitzung** Gruppenfeld.  
  
> [!NOTE]
>  Wenn ein anderer Benutzer der Ablaufverfolgung den WS-AT-Ablaufverfolgungsanbieter verwendet, können Sie keine neue Protokollsitzung für Ablaufverfolgungsereignisse erstellen. Jeder Versuch, die Protokollierung zu diesem Zeitpunkt zu konfigurieren, führt zur Fehlermeldung "Fehler beim Aktivieren des Anbieters. Fehlercode: 1".  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]Ablaufverfolgung und Protokollierung, finden Sie unter [Verwaltung und Diagnose](../../../docs/framework/wcf/diagnostics/index.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Konfigurieren der Unterstützung von WS-Atomic-Transaction](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)  
 [WS-AtomicTransaction-Konfigurationshilfsprogramm (wsatConfig.exe)](../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md)  
 [Verwaltung und Diagnose](../../../docs/framework/wcf/diagnostics/index.md)
